---
name: geogebra-ggb
description: Load when working with GeoGebra .ggb files (esp. GeoGebra 5) without or without the GeoGebra app - merging several .ggb into one, renaming objects, dynamic visibility, sliders, editing the XML directly, packaging/validating .ggb from the command line.
---

# Archivos GeoGebra (.ggb) por dentro

## Regla dura (instrucción del usuario en esta repo)

**Nunca crear ni modificar archivos** (.ggb, su XML, o cualquier archivo del
repo de mates) sin permiso explícito del usuario en la conversación, aunque la
tarea parezca trivial o ya se hubiera hecho antes. Proponer el cambio
concreto (función, etiqueta, XML resultante, comandos exactos) y esperar a que
el usuario dé el visto bueno o lo aplique él mismo. Las únicas excepciones son
los archivos de esta skill cuando el usuario pide actualizarla.

Un `.ggb` es un ZIP cuyas entradas son archivos XML; la única obligatoria es
`geogebra.xml` (macros, imágenes o JavaScript van en entradas extra). Todo el
trabajo se puede hacer con `unzip`/`zip` + edición de texto, sin abrir GeoGebra.

```bash
mkdir /tmp/ggb && unzip -o file.ggb -d /tmp/ggb   # inspeccionar
cd /tmp/ggb && zip -q -X out.ggb geogebra.xml      # reempaquetar
```

## Estructura de geogebra.xml (format 5.0)

    <geogebra format="5.0" ...>
      <gui/> <euclidianView/> <algebraView/> <kernel/> <scripting/>
      <construction title="" author="" date="">
        <expression label="X" exp="..."/>
        <element type="point|function|numeric|text|..." label="X"> ... </element>
      </construction>

- Cada objeto es un par `<expression>` (definición) + `<element>` (propiedades
  visuales). Los deslizadores numéricos independientes llevan solo `<element>`
  con `<value>` y `<slider>`; los puntos dependientes definidos "a mano" (p. ej.
  un punto blanco que marca un hueco) también pueden ir sin `<expression>`.
- **El orden importa**: un objeto solo puede referenciar a los definidos antes
  en `<construction>`.
- Escapado XML dentro de `exp`: textos `"...` van como `&quot;...&quot;` y los
  `<` de las expresiones como `&lt;`. Copiarlos tal cual al fusionar.
- El parser es SAX y tolerante: el orden de los subtags dentro de `<element>`
  no importa, pero los nombres de etiqueta sí.

## Etiquetas útiles dentro de <element> (verificado en la rama 5.0 de geogebra/geogebra)

- `<condition showObject="exprBooleana"/>` - visibilidad condicional dinámica.
  La expresión se evalúa como GeoBoolean (`algProc.evaluateToBoolean`).
  OJO: en formato 5.0 la etiqueta es `condition` con atributo `showObject`;
  **no** existe `conditionToShowObject` (el nombre correcto está en
  `GeoElement.getShowObjectConditionXML` / `ConsElementXMLHandler.handleCondition`
  del repo). Efecto: visible = `show object="true"` AND condición.
- `<startPoint x="-6.3" y="7.0" z="1"/>` - ancla textos, imágenes y deslizadores
  a coordenadas de construcción (z="1"). Válido para cualquier Locateable.
- `<slider min="" max="" absoluteStep="" absoluteStepWidth=""
  absoluteScreenLocation="true|false" width="200" fixed="" horizontal=""
  showAlgebra=""/>` - `absoluteScreenLocation="true"` fija el deslizador a la
  pantalla; `false` lo ancla a la construcción y entonces su posición es el
  `<startPoint>`. Sin `startPoint`, GeoGebra usa una posición por defecto.
- `<show object="" label="" ev=""/>`, `<objColor r g b alpha/>`, `<lineStyle
  thickness type typeHidden opacity/>`, `<coords x y z/>`, `<pointSize/>`,
  `<labelMode/>` (1 = nombre+valor), `<animation step speed type playing/>`.

## Fusionar varios .ggb en uno (receta para una sola vista)

1. Extraer los `geogebra.xml` de todos y elegir uno como base (gui/kernel/
   euclidianView son iguales entre archivos del mismo autor; quedarse con el
   `coordSystem` que muestre mejor los objetos).
2. Detectar colisiones de etiquetas: comparar los `label` de todos los
   `<element>`/`<expression>`. Renombrar (p. ej. `P`→`P1,P2,P3`,
   textos `t1`→`tA1,tB1,tC1`) actualizando TAMBIÉN las `exp` que los
   referencian.
3. Seleccionar escena con un deslizador compartido nuevo (`escena` = 1..3,
   paso 1) y añadir `<condition showObject="escena==n"/>` a cada objeto de la
   escena n (funciones, puntos, textos, puntos-agujero).
4. Declarar el deslizador selector ANTES de los objetos condicionados.
5. Compartir objetos idénticos entre archivos (p. ej. un mismo deslizador `t`).

## Validación rápida (GeoGebra 5 acepta o protesta; validarlo antes)

```bash
xmllint --noout geogebra.xml          # well-formed
python3 - <<'EOF'
import xml.etree.ElementTree as ET
t = ET.parse('geogebra.xml')
labels = [e.get('label') for e in t.iter('element')]
assert len(labels) == len(set(labels)), 'labels duplicados'
EOF
```

No hay forma práctica de validar semántica sin abrir GeoGebra; si el XML carga
con errores, GeoGebra 5 muestra los mensajes en un diálogo.

## Fuentes y herramientas

- Código fuente (autoridad sobre el formato): https://github.com/geogebra/geogebra
  - Rama/main actuales: parser `ConsElementXMLHandler` y escritor en
    `GeoElement`/`XMLBuilder` (usar el tag `5.0.x` más cercano para
    comportamientos de GeoGebra 5; layout antiguo `common/src/...`, nuevo
    `source/shared/common/src/...`).
- XSD documentado (incompleto, no cubre `condition`):
  https://geogebra.github.io/docs/reference/en/Common_XML_tags_and_types/
- App local si está instalada: `/Applications/GeoGebra5.app`
  (`open <fichero>.ggb` para ver el resultado).
