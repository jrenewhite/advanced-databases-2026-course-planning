---
marp: true
theme: advanced-db-dark
paginate: true
---

<!-- _class: hero grid-lines -->

<div class="kicker">Clase 01</div>
<div class="meta">Sistemas Avanzados de Bases de Datos</div>

# Course Intro, OLTP vs OLAP

## Bases operativas, bases analíticas y dinámica real del curso

---

<!-- _class: agenda grid-lines -->

<div class="kicker">Ruta</div>

# Agenda de sesión

<ul class="agenda-list">
  <li>Qué vamos a construir en el curso</li>
  <li>Cómo se evaluará y cómo se trabajará</li>
  <li>OLTP vs OLAP como problema real</li>
  <li>Demo conceptual, evidencia y siguiente paso</li>
</ul>

---

<!-- _class: guide-question grid-dots -->

<div class="kicker">Pregunta guía</div>

# ¿Por qué una base que sirve para operar puede ser mala para decidir?

> La sesión abre la narrativa del curso: registrar eventos y analizar decisiones no son la misma carga, ni requieren el mismo diseño.

---

<!-- _class: real-world grid-lines -->

<div class="kicker">Problema real</div>

# Un sistema “sí funciona” y aun así no ayuda a decidir

<div class="cards">
  <div class="card">
    <div class="meta">Síntoma</div>
    <p>La app registra ventas, pagos y usuarios sin problema.</p>
  </div>
  <div class="card">
    <div class="meta">Impacto</div>
    <p>Nadie puede responder rápido qué producto crece, qué canal cae o dónde hay cuellos de botella.</p>
  </div>
</div>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Objetivo</div>

# Qué debería quedar claro hoy

<ul class="checklist-list">
  <li>Cómo está armado el curso y cómo se trabajará</li>
  <li>Qué diferencia a OLTP de OLAP</li>
  <li>Qué evidencia esperaremos durante el semestre</li>
  <li>Cómo usar IA sin delegar el criterio</li>
</ul>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Acrónimos y conceptos</div>

# Vocabulario mínimo de la sesión

<div class="cards">
  <div class="card"><div class="meta">OLTP</div><p>Procesamiento transaccional en línea.</p></div>
  <div class="card"><div class="meta">OLAP</div><p>Procesamiento analítico en línea.</p></div>
  <div class="card"><div class="meta">DW</div><p>Data Warehouse para decisión.</p></div>
  <div class="card"><div class="meta">DM</div><p>Data Mart para un área específica.</p></div>
</div>

---

<!-- _class: statement grid-lines -->

<div class="kicker">Idea central</div>

# La misma base rara vez optimiza al mismo tiempo operación, análisis y costo de cambio.

---

<!-- _class: before-after grid-lines -->

<div class="kicker">Antes / después</div>

# Base operativa vs base analítica

<div class="compare">
  <div class="panel">
    <div class="meta">Operación</div>
    <p>Consultas cortas, cambios frecuentes, consistencia, concurrencia, respuesta rápida por transacción.</p>
  </div>
  <div class="panel">
    <div class="meta">Análisis</div>
    <p>Consultas agregadas, periodos largos, joins amplios, comparaciones históricas e indicadores.</p>
  </div>
</div>

---

<!-- _class: tradeoff grid-lines -->

<div class="kicker">Tradeoff</div>

# Diseñar para una cosa suele costar en otra

<div class="cards">
  <div class="card">
    <div class="meta">Gana OLTP</div>
    <p>Respuesta corta, integridad, escrituras frecuentes y flujo operativo estable.</p>
  </div>
  <div class="card">
    <div class="meta">Cuesta OLTP</div>
    <p>Reporting pesado, análisis histórico y preguntas exploratorias complejas.</p>
  </div>
</div>

---

<!-- _class: grid-lines -->

<div class="kicker">Courseware</div>

# Cómo se separa el trabajo del curso

<div class="cards">
  <div class="card">
    <div class="meta">`class-*`</div>
    <p>Material de sesión: slides, demos, ejercicios guiados, notas y recursos.</p>
  </div>
  <div class="card">
    <div class="meta">`assignment-*`</div>
    <p>Trabajo evaluable fuera de clase con base común y rama por estudiante.</p>
  </div>
  <div class="card">
    <div class="meta">Proyecto final</div>
    <p>Repo separado con ownership del estudiante o del equipo.</p>
  </div>
</div>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Evaluación</div>

# Cómo se evaluará el curso

<div class="dashboard">
  <div class="metric-card">
    <div class="meta">Examen escrito</div>
    <div class="big-number">20%</div>
    <p class="muted">Conceptos y razonamiento.</p>
  </div>
  <div class="metric-card">
    <div class="meta">Prácticas</div>
    <div class="big-number">30%</div>
    <p class="muted">Assignments, evidencia y criterio.</p>
  </div>
  <div class="metric-card">
    <div class="meta">Proyecto final</div>
    <div class="big-number">30%</div>
    <p class="muted">Repo, evidencia y revisión final.</p>
  </div>
</div>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Evaluación</div>

# Lo demás también cuenta

<div class="cards">
  <div class="card">
    <div class="meta">Diagramas</div>
    <p>10% para modelado, arquitectura y comprensión estructural.</p>
  </div>
  <div class="card">
    <div class="meta">Reportes de lectura</div>
    <p>10% para notas breves, reflexión y research técnico.</p>
  </div>
</div>

---

<!-- _class: ai-judgment grid-lines -->

<div class="kicker">IA con criterio</div>

# IA permitida, criterio obligatorio

> La IA puede proponer alternativas, resumir opciones o acelerar borradores. Lo que se evalúa es la validación, la evidencia y la explicación técnica del estudiante.

---

<!-- _class: workflow grid-lines-small -->

<div class="kicker">Seguimiento</div>

# GitHub Projects como herramienta del curso

<ul class="agenda-list">
  <li>Seguimiento de assignments</li>
  <li>Checkpoints de proyecto final</li>
  <li>Bloqueos y revisiones</li>
  <li>No es el foco de `class-*`</li>
</ul>

---

<!-- _class: section grid-dots -->

<div class="kicker">Transición</div>

# Ahora vamos a observar el problema en modo práctico

## No para resolverlo todo, sí para ver qué cambia entre operación y análisis

---

<!-- _class: demo grid-lines-small -->

<div class="kicker">Demo setup</div>

# Qué vamos a observar

<div class="terminal">
$ psql postgresql://postgres:postgres@localhost:5432/demo
<br />
$ TODO: consulta transaccional corta
<br />
$ TODO: consulta agregada por periodo
</div>

---

<!-- _class: demo grid-lines -->

<div class="kicker">Demo</div>

# Dos preguntas, dos comportamientos

<ul class="checklist-list">
  <li>Buscar una orden puntual</li>
  <li>Agrupar ventas por mes</li>
  <li>Comparar volumen de lectura</li>
  <li>Discutir por qué la misma base sufre distinto</li>
</ul>

---

<!-- _class: evidence grid-lines-small -->

<div class="kicker">Evidencia</div>

# Qué evidencia esperaremos después de esta sesión

<ul class="checklist-list">
  <li>Explicación breve de OLTP vs OLAP</li>
  <li>Ejemplo de consulta operativa</li>
  <li>Ejemplo de pregunta analítica</li>
  <li>Relación entre arquitectura y tipo de carga</li>
</ul>

---

<!-- _class: section grid-dots -->

<div class="kicker">Trabajo fuera de sesión</div>

# La exploración guiada termina aquí

## El trabajo evaluable o explicado con más detalle seguirá en VS Code y en `assignment-*`

---

<!-- _class: exercise grid-lines -->

<div class="kicker">Ejercicio</div>

# Identificar operación vs análisis en un sistema conocido

<div class="cards">
  <div class="card">
    <div class="meta">Objetivo</div>
    <p>Distinguir qué datos viven para operar y cuáles para decidir.</p>
  </div>
  <div class="card">
    <div class="meta">Entrega</div>
    <p>Una tabla breve con preguntas operativas, analíticas y posibles evidencias.</p>
  </div>
</div>

---

<!-- _class: workflow grid-lines-small -->

<div class="kicker">Proyecto final</div>

# Qué deja sembrado esta clase

<ul class="agenda-list">
  <li>Elegir un problema realista</li>
  <li>Distinguir si será operativo, analítico o mixto</li>
  <li>No diseñar sin tener clara la pregunta central</li>
</ul>

---

<!-- _class: recap grid-dots -->

<div class="kicker">Recap</div>

# Qué nos llevamos hoy

<ul>
  <li>El curso se evalúa por evidencia y criterio</li>
  <li>OLTP y OLAP resuelven problemas distintos</li>
  <li>El repositorio correcto depende del tipo de trabajo</li>
  <li>La IA ayuda, pero no sustituye validación</li>
</ul>

---

<!-- _class: next grid-lines -->

<div class="kicker">Siguiente clase</div>

# Diseño lógico y reglas de dominio

> Si el modelo deja pasar datos absurdos, el resto del sistema hereda el problema.
