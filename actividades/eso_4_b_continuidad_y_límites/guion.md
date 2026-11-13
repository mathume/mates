# Guion docente · Continuidad y tendencia · 4.º ESO, Opción B
## Dos sesiones: (1) clase magistral con tareas pequeñas, (2) repetición + actividad TIC (escape room)

**Referencia:** Anaya 4.º B ESO, Unidad 4 (apartados 3 y 5).
**Criterio de nivel:** todo lo que se hace aquí es lectura e interpretación de gráficas, al nivel exacto del libro. La notación de límite se introduce SOLO como traducción formal de la idea de tendencia, nunca como objeto de cálculo algebraico.

**Material TIC (un solo archivo):** `continuidad_y_limites.ggb` — applet de GeoGebra con tres casos en un único archivo:
- deslizador **escena** (1 a 3): 1 continuidad · 2 salto · 3 punto que falta
- deslizador **t** (−5 a 5, paso 0,01): recorre el punto **P** por la curva
- Escena 1 (azul): f(x) = 0,5x² + 1 · Escena 2 (rojo): g(x) = Si(x < 2, f(x), 4) · Escena 3 (verde): h(x) = sen(x)/x

Y además: quiz en Kahoot/Quizizz, Google Forms "Puerta del laboratorio", hoja de investigador (para crear).

---

## Mapa de las dos sesiones

- **Sesión 1 (introducción):** gancho (5') + exploración del applet y definición verbal (10') + bautizo de la notación (5') + comprobaciones orales (5') + historia de la tortuga (~10') + tareas pequeñas del libro (15').
- **Sesión 2 (repetición + TIC):** escape room completo ("El laboratorio imposible", 50-55'): la Fase 2 (quiz) hace el papel de repetición sistemática.

---

# SESIÓN 1 · Clase magistral (20 min + tareas)

## Minutos 0-5 · Gancho: "¿a qué tiende?"

**Proyectada en la pizarra (dibujada a mano o a partir de `lactato_recuperacion.png`):** la gráfica del **lactato en sangre de un corredor justo después de terminar una carrera intensa**: en t = 0 está al máximo, y con el descanso va bajando con el tiempo, acercándose cada vez más a 1 (el nivel en reposo).

**Pregunta de apertura (no definiciones todavía):**
> "Acaba de terminar de correr y su lactato está por las nubes. Si descansa, ¿a qué valor se acercará el lactato de su sangre al pasar las horas?"

Respuestas esperables: "a cero", "a lo normal". No corregir aún.

**Réplica clave:**
> "¿Bajará hasta exactamente 0, o se queda *cerca* de algún valor? ¿Llegará alguna vez a ser exactamente 0?"

Construir entre todos la frase: **"el lactato TIENDE A 1 (su nivel en reposo) cuando el tiempo crece"**. El cuerpo siempre mantiene un lactato basal: la curva baja y se pega a 1, pero nunca llega a 0.

✍️ Escribir en la pizarra, subrayada:
**El punto al que se acerca una función (sin necesidad de llegar) se llama su TENDENCIA.**

## Minutos 5-10 · Continuidad y discontinuidades (todo gráfico)

**Proyectar el applet `continuidad_y_limites.ggb`.** Ir cambiando el deslizador **escena** (1, 2, 3). En cada escena, arrastrar **t** en directo y preguntar:

1. **Escena 1 (continua, azul):** P recorre la parábola f(x) = 0,5x² + 1 sin interrupciones → "se puede dibujar sin levantar el lápiz".
2. **Escena 2 (salto, roja):** g(x) = Si(x < 2, f(x), 4): al acercar P hacia 2 por la izquierda llega a la altura 3 (f(2)); desde la derecha está en el 4. **Hay un salto.**
3. **Escena 3 (punto que falta, verde):** h(x) = sen(x)/x: al acercar P hacia 0 por cualquier lado, la altura se acerca a 1… pero al pisar exactamente t = 0 **P desaparece** (h(0) no existe). El punto H_1 es el hueco. Le falta un punto.

**Preguntas encadenadas a la clase:**
- "¿Qué tienen de raro la 2 y la 3?" → hay un punto (abscisa 2 en la roja, abscisa 0 en la verde) donde la función "se rompe".
- "¿En la 2, a qué altura llega P viniendo desde la izquierda? ¿Y desde la derecha?" → 3 y 4, valores distintos. **Hay un salto.**
- "¿En la 3?" → P se acerca a la misma altura (1) por los dos lados, **pero en x = 0 no existe**. Le falta un punto.

✍️ Definición operativa (solo verbal, sin fórmulas):
**Una función es continua si puedo recorrer su gráfica sin levantar el lápiz. Si no, tiene una DISCONTINUIDAD en ese punto.**

**Contexto del libro para aterrizarlo (1 min):** la tarifa del aparcamiento que cobra "hora empezada, hora pagada" es una función discontinua: gráfica de escalones. ¿Preferiríais pagar según una función continua? (Anaya, pág. 49, actividades 1).

## Minutos 10-15 · El bautizo de la notación (el único momento "formal" de la clase)

**Guiño al futuro:** "Lo que acabáis de decir con palabras, los matemáticos lo escriben con un símbolo. Es el mismo que usaréis en Bachillerato."

✍️ Traducción en la pizarra, en paralelo:

| Lo que decimos (palabras) | Cómo se escribe |
|---|---|
| "El lactato tiende a 1 cuando el tiempo crece" | lim (t→+∞) de L(t) = 1 |
| "La función verde se acerca a 1 cuando x se acerca a 0" | lim (x→0) de h(x) = 1 (aunque h(0) no exista) |
| "La roja se acerca a 3 por la izquierda y a 4 por la derecha" | lim (x→2⁻) de g(x) = 3 y lim (x→2⁺) de g(x) = 4 → el límite no existe (salto) |

**Lectura coral en voz alta, una vez:** "el límite de efe de equis cuando equis tiende a dos, es tres".

**Las dos ideas-fuerza que deben salir de aquí (repetir dos veces cada una):**
1. **"El límite es a dónde se acerca la función; no importa cuánto vale (ni si existe) en ese punto."**
2. **"Si lo que se acerca por la izquierda y por la derecha no coincide, el límite no existe."**

⚠️ NO entrar aquí en: cálculo de límites por sustitución, indeterminaciones 0/0, factorizaciones, k/0, asíntotas con cálculo. No corresponde al nivel de este libro.

## Minutos 15-20 · Tres comprobaciones rápidas

**Con las escenas 2 y 3 proyectadas. Preguntas orales rápidas (manos levantadas):**

1. "¿Es continua esta función? ¿Dónde se rompe?" → escena 2: discontinuidad en el punto de abscisa 2; escena 3: en el 0.
2. "¿Cuánto vale el límite por la izquierda? ¿Y por la derecha?" → en el salto, 3 y 4 → no existe; en el agujero, ambos 1 → existe y vale 1 aunque h(0) no exista.
3. "Y si sigo la gráfica hacia la derecha, cada vez más lejos, ¿a qué valor se acerca?" → tendencia en +∞.

**Cierre de la sesión 1:** is not the escape room yet — desde aquí, tareas pequeñas del libro (gráfica del parking, noria, lectura de laterales en gráficas dadas) y, si sobra tiempo, el primer acto de la historia (la tortuga, abajo).

---

# SESIÓN 2 · "El laboratorio imposible" — Escape room (50-55 min)

**Narrativa para el alumnado:** el profesor del laboratorio matemático ha desaparecido dejando la puerta blindada. Solo se abre con un código de 4 cifras. Antes de marcharse dejó su ordenador encendido con un applet de tres escenas: solo quienes entiendan a dónde *tienden* las funciones sabrán leerlo. En parejas. El primer equipo que abra la puerta entra en el despacho del profesor; el resto sigue hasta lograrlo.

**Material:** aula de ordenadores · `continuidad_y_limites.ggb` (un archivo por equipo o en la plataforma del centro) · quiz de Kahoot/Quizizz · formulario de Google Forms con validación · cronómetro proyectado · hoja de investigador.

**Nivel:** lectura gráfica y tendencia (Anaya 4.º B, Unidad 4). Sin cálculo algebraico de límites.

## FASE 1 · El ordenador del profesor (15-18 min, en parejas)

Cada pareja abre el applet y rellena su **hoja de investigador** cambiando el deslizador `escena` y arrastrando `t`.

### Reto 1 · Escena azul (escena = 1, f(x) = 0,5x² + 1)
1. ¿Puedes recorrer toda la gráfica con el punto P sin que P desaparezca? ¿Se puede dibujar esta función sin levantar el lápiz?
2. ¿Cuánto vale f(3)? (mirad el punto P cuando t = 3)
3. **Clave 1:** la altura a la que llega P cuando t = −4. *(→ 9; ojo: la parábola es simétrica, en t = 4 sale lo mismo)*

### Reto 2 · Escena roja (escena = 2, g(x) = Si(x < 2, f(x), 4))
Acercad P poco a poco al punto de abscisa 2 desde la izquierda (t = 1; 1,5; 1,9; 1,99…):
1. ¿A qué altura llega P desde la izquierda? ¿Y desde la derecha?
2. ¿Existe lim (x→2) de g(x)? ¿Por qué? (escribid la respuesta con los dos límites laterales)
3. **Clave 2:** cuántas alturas distintas toma la función alrededor del salto. *(→ 2)*

### Reto 3 · Escena verde (escena = 3, h(x) = sen(x)/x)
Acercad P a x = 0 desde los dos lados con el deslizador (t = 1; 0,5; 0,1; 0,01…):
1. ¿Qué le pasa al punto P exactamente en t = 0? ¿Existe h(0)?
2. ¿A qué altura se acerca P al pasar por el agujero, vengáis de donde vengáis? ¿Existe lim (x→0) de h(x)?
3. **Clave 3:** la altura del agujero. *(→ 1)*

✍️ **Entregable:** foto o captura de la hoja de investigador (se valoran las respuestas de los apartados "¿existe?", no solo las claves).

## FASE 2 · El test del sistema de seguridad (12-15 min, todo el grupo)

Quiz en Kahoot/Quizizz (8-10 preguntas, 30 s cada una) proyectado en la pizarra, con el banco de preguntas de este guion (lectura de gráficas, límites laterales, tipos de discontinuidad, una de tendencia en +∞ y una de periodicidad como recordatorio). Esta fase es la **repetición sistemática** de la sesión matriz.

La cifra del podio se usa como cuarta parte del código: 1º → 9, 2º → 6, 3º → 3.
*(Recomendación docente: para simplificar el montaje, usar siempre la cifra del 1º y anunciar "el código del sistema es el del equipo ganador" — o directamente fijar el código.)*

## FASE 3 · La caja fuerte (8-10 min, en parejas)

Las claves 1-3 de la Fase 1 y la clave 4 de la Fase 2 forman el código de apertura en el orden **azul, rojo, verde, podio**. Comprobación en el Google Forms "Puerta del laboratorio": campo de texto con validación de respuesta exacta.

- **Código esperado:** 9 − 2 − 1 − (9/6/3). *Código fijo sugerido (1º del podio):* **9219**.
- Detrás de la puerta: el "secreto del profesor" — la anécdota histórica (el resto de los actos: Berkeley y los "fantasmas de cantidades desaparecidas") o un acertijo final de 30 segundos.

## Cierre (7-10 min, grupo clase)

- Puesta en común: ¿qué discontinuidad era "reparable"? (la del agujero: si pintáramos el punto H_1, sería continua; el salto no se repara pintando un punto).
- Ticket de salida en el mismo Forms: "Escribe con la notación de límite una cosa que hayas aprendido hoy".
- Conexión con la próxima clase: tendencias cuando x crece sin parar (+∞) — metabolismo del lactato, noria, glucemia.

---

# Historia de la matemática (para inyectar donde se elija)

**Opción A — Anécdota de 2 min en la sesión 1** (recomendada): en el minuto 10, justo antes del "bautizo" de la notación.
**Opción B — Narrativa del escape room:** el laboratorio cerrado puede ser el del "profesor desaparecido"; al abrir la caja fuerte, los alumnos descubren su historia.

### Los cuatro actos

**1. Los griegos y la tortuga (s. V a.C.).** Zenón de Elea plantea su paradoja: Aquiles nunca alcanza a la tortuga, porque siempre debe recorrer antes la mitad de la distancia que le separa. Es, sin saberlo, el primer límite de la historia: una suma infinita de intervalos cuyo resultado es finito. *(Pregunta para la clase: ¿de verdad no la alcanza? ¿Qué demuestra la experiencia? Conexión directa con el gancho: también la tortuga se acerca a su meta sin llegar del todo — igual que el lactato del corredor se acerca a 1 cada vez más, sin tocarse nunca.)*
   *(Variante: la **flecha** — "en cada instante la flecha ocupa un espacio igual a sí misma, luego está quieta; ¿de dónde sale el movimiento?" — conecta aún mejor con la idea de esta unidad: el valor en UN instante frente a lo que ocurre ALREDEDOR de ese instante.)*

**2. Newton y Leibniz (s. XVII).** Inventan el cálculo infinitesimal casi a la vez y se enzarzan en una disputa por la prioridad que enfrentó a Inglaterra y al continente durante un siglo. Hablan de "infinitésimos": cantidades "infinitamente pequeñas" que aparecen y desaparecen en los cálculos. Funciona de maravilla (¡con ello se calculan órbitas de planetas!), pero nadie sabe explicar bien qué es un infinitésimo.

**3. El obispo escéptico (1734).** George Berkeley lanza la crítica más famosa de la historia de las matemáticas: los infinitésimos son "fantasmas de cantidades desaparecidas". ¿Cómo puede algo ser distinto de cero durante el cálculo y luego tratarse como cero? El cálculo da resultados correctos, pero carece de fundamento. *(Exactamente el debate de la clase: el libro describe límites con intuición gráfica, "tiende a", sin definición formal — igual que Newton.)*

**4. Cauchy y Weierstrass (s. XIX).** Por fin se responde a Berkeley: el límite deja de ser "algo que se acerca" y se define con precisión. La notación lim y → que los alumnos acaban de aprender viene de esa época (el símbolo lim lo populariza Cauchy) — y en la misma centuria Cantor formaliza el conjunto de los números reales, justo lo que hace falta para que los límites tengan dónde vivir.

### Mensaje final para los alumnos (30 s)

> "Durante 150 años el cálculo funcionaba sin que nadie supiera explicar bien por qué, igual que hoy vosotros usáis la palabra 'tiende' con precisión intuitiva. La notación de límite que acabáis de aprender es la puerta a esa respuesta — y la abriréis del todo en Bachillerato."

---

# Banco de preguntas para el quiz (Fase 2) y las comprobaciones orales

1. Verdadero o falso: una función puede tener límite en un punto aunque no esté definida en él. (V — la escena verde: sen(x)/x en x = 0.)
2. Dada una gráfica con salto: ¿existe el límite en el punto de abscisa del salto? ¿Por qué?
3. El lactato en sangre tras una carrera es máximo en t = 0 y desciende con el descanso: ¿a qué valor tiende? → escribe lim (t→+∞) de L(t) = ...
4. ¿Es continua la tarifa de un parking que cobra por hora empezada? ¿Qué tipo de discontinuidad tiene?
5. Escena roja del applet: ¿cuánto vale lim (x→2⁻) y lim (x→2⁺) de g(x)?
6. Escena verde del applet: ¿a qué altura se acerca h(x) = sen(x)/x cuando x se acerca a 0? ¿Y qué vale... h(0)?
7. ¿Se puede dibujar una función continua sin levantar el lápiz?
8. ¿Cuál es el periodo de la función noria de 30 s? (recordatorio de periodicidad).
9. Dada una gráfica: ¿en qué intervalos crece, decrece, y a qué tiende cuando x crece?

---

# Para el docente: soluciones y montaje

| Reto | Respuesta esperada | Notas |
|---|---|---|
| 1.1 | Sí; sí, es continua | f(x) = 0,5x² + 1 |
| 1.2 | f(3) = 5,5 | leer P con t = 3 |
| 1.3 Clave 1 | **9** | f(−4) = 9 (y también f(4) = 9: parábola simétrica) |
| 2.1 | 3 por la izquierda; 4 por la derecha | g(x) = Si(x < 2, f(x), 4) |
| 2.2 | No existe: lim (x→2⁻) = 3 ≠ lim (x→2⁺) = 4 | el argumento es lo evaluable |
| 3.1 | P desaparece; h(0) no existe | 0/0 — sin nombrarlo aún |
| 3.2 | Se acerca a 1; el límite SÍ existe y vale 1 | aunque h(0) no exista: idea central |
| 3.3 Clave 3 | **1** | |
| Clave 4 | 9 / 6 / 3 | según podio; código fijo sugerido **9219** |

**Montaje previo (15 min):**
1. Copiar `continuidad_y_limites.ggb` al escritorio de cada equipo o subirlo a la plataforma del centro (Classroom, Moodle…). Probarlo una vez: deslizadores `escena` y `t`.
2. Crear el quiz con el banco de preguntas de arriba.
3. Crear el Forms "Puerta del laboratorio": pregunta de respuesta corta con validación "es igual a 9219" + ticket de salida al final.

**Rúbrica rápida (3 criterios):**
- Interpretación gráfica: identifica el tipo de discontinuidad y la justifica (Fase 1, apartados "¿existe?").
- Notación: usa lim (x→a) correctamente en el ticket de salida.
- Trabajo en pareja: hoja de investigador completa y capturas entregadas.

**Evidencias para la rúbrica del informe:**
- **Interpretación gráfica:** identifica discontinuidades y su tipo (salto / punto que falta).
- **Notación:** traduce frases de tendencia a lim (x→a) y viceversa.
- **Comunicación:** justifica oralmente por qué un límite no existe (laterales distintos).
