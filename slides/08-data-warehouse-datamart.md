---
marp: true
theme: advanced-db-dark
paginate: true
---

<!-- _class: hero grid-lines -->

<div class="kicker">Clase 08</div>
<div class="meta">Arquitectura para decisión</div>

# Data Warehouse and Data Mart

## Separar cargas, integrar fuentes y responder preguntas con mejor estructura

---

<!-- _class: agenda grid-lines -->

<div class="kicker">Ruta</div>

# Agenda de sesión

<ul class="agenda-list">
  <li>Por qué aparece el warehouse</li>
  <li>Warehouse vs Data Mart</li>
  <li>Checkpoint de media sesión</li>
  <li>Arquitectura, proyecto final y evidencia</li>
</ul>

---

<!-- _class: guide-question grid-dots -->

<div class="kicker">Pregunta guía</div>

# ¿Cuándo deja de tener sentido pedirle todo al OLTP?

> El warehouse aparece cuando registrar y analizar ya no pueden convivir cómodamente en el mismo diseño operativo.

---

<!-- _class: real-world grid-lines -->

<div class="kicker">Problema real</div>

# Reporting pesado sobre una base operativa

<div class="cards">
  <div class="card">
    <div class="meta">Síntoma</div>
    <p>Las consultas de análisis compiten con transacciones críticas y degradan la operación.</p>
  </div>
  <div class="card">
    <div class="meta">Impacto</div>
    <p>El sistema responde peor y además el análisis sigue siendo incómodo y poco consistente.</p>
  </div>
</div>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Objetivo</div>

# Qué debería quedar claro hoy

<ul class="checklist-list">
  <li>Por qué surge el warehouse</li>
  <li>Qué diferencia a un Data Mart</li>
  <li>Qué flujo conecta fuentes, transformación y modelo</li>
  <li>Qué evidencia vuelve defendible la arquitectura</li>
</ul>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Acrónimos y conceptos</div>

# Vocabulario mínimo de la sesión

<div class="cards">
  <div class="card"><div class="meta">ETL</div><p>Extraer, transformar y cargar.</p></div>
  <div class="card"><div class="meta">DW</div><p>Data Warehouse integrado.</p></div>
  <div class="card"><div class="meta">DM</div><p>Data Mart orientado a un área.</p></div>
  <div class="card"><div class="meta">Granularidad</div><p>Nivel al que se guarda el hecho.</p></div>
</div>

---

<!-- _class: statement grid-lines -->

<div class="kicker">Idea central</div>

# Un warehouse no es “una base más grande”: es una decisión de arquitectura para separar integración, análisis y operación.

---

<!-- _class: before-after grid-lines-small -->

<div class="kicker">Antes / después</div>

# OLTP presionado vs arquitectura de decisión

<div class="compare">
  <div class="panel">
    <div class="meta">Todo en OLTP</div>
    <p>La operación y el análisis compiten por recursos y estructura.</p>
  </div>
  <div class="panel">
    <div class="meta">Warehouse / Mart</div>
    <p>Se separan cargas, se integran fuentes y se modela para responder mejor.</p>
  </div>
</div>

---

<!-- _class: tradeoff grid-lines -->

<div class="kicker">Tradeoff</div>

# Separar análisis mejora lectura, pero agrega costo de integración

<div class="cards">
  <div class="card">
    <div class="meta">Gana</div>
    <p>Mejor rendimiento analítico, consistencia de indicadores y estructura para decisión.</p>
  </div>
  <div class="card">
    <div class="meta">Cuesta</div>
    <p>Procesos de carga, mayor complejidad arquitectónica y gobierno de datos.</p>
  </div>
</div>

---

<!-- _class: grid-lines -->

<div class="kicker">Arquitectura</div>

# Flujo conceptual del warehouse

<div class="diagram-placeholder">
  TODO: fuentes operativas, transformación, modelo dimensional y capa de consumo analítico.
</div>

---

<!-- _class: section grid-dots -->

<div class="kicker">Checkpoint</div>

# Media sesión

## Ya tenemos el mapa arquitectónico. Ahora toca ver qué decisiones mínimas vuelven revisable un caso real.

---

<!-- _class: workflow grid-lines-small -->

<div class="kicker">Proyecto final</div>

# Checkpoint de proyecto

<ul class="agenda-list">
  <li>Definir si tu caso necesita warehouse o solo mart</li>
  <li>Explicar fuentes de datos</li>
  <li>Definir granularidad del hecho principal</li>
  <li>Conservar evidencia de la decisión arquitectónica</li>
</ul>

---

<!-- _class: section grid-dots -->

<div class="kicker">Transición</div>

# Ahora vamos a observarlo en contexto técnico

## No para construir un ETL completo, sí para ver cómo una decisión arquitectónica cambia el análisis.

---

<!-- _class: demo grid-lines-small -->

<div class="kicker">Demo conceptual</div>

# Qué vamos a observar

<div class="terminal">
$ TODO: definir fuente operativa
<br />
$ TODO: proponer tabla de hechos y dimensiones
<br />
$ TODO: comparar consulta operativa vs consulta analítica
</div>

---

<!-- _class: demo grid-lines -->

<div class="kicker">Observación</div>

# Qué queremos notar

<ul class="checklist-list">
  <li>Qué separa operación de decisión</li>
  <li>Qué gana un Data Mart</li>
  <li>Qué dependencia agrega la integración</li>
  <li>Qué pregunta ya se puede contestar mejor</li>
</ul>

---

<!-- _class: section grid-dots -->

<div class="kicker">Trabajo fuera de sesión</div>

# La especificación detallada seguirá en VS Code y en el assignment

## La arquitectura se entiende aquí; la evidencia y el modelado fino se construyen fuera del deck.

---

<!-- _class: exercise grid-lines -->

<div class="kicker">Ejercicio</div>

# Diseñar un warehouse o mart mínimo para una decisión concreta

<div class="cards">
  <div class="card">
    <div class="meta">Objetivo</div>
    <p>Conectar una pregunta de negocio con una arquitectura de datos defendible.</p>
  </div>
  <div class="card">
    <div class="meta">Entrega</div>
    <p>Flujo fuente-transformación-modelo, hecho principal y consulta ejemplo.</p>
  </div>
</div>

---

<!-- _class: evidence grid-lines-small -->

<div class="kicker">Evidencia</div>

# Qué evidencia esperaremos

<ul class="checklist-list">
  <li>Fuente o sistema origen</li>
  <li>Hecho y dimensiones</li>
  <li>Granularidad</li>
  <li>Pregunta de decisión soportada</li>
</ul>

---

<!-- _class: recap grid-dots -->

<div class="kicker">Recap</div>

# Qué nos llevamos hoy

<ul>
  <li>Warehouse y Mart resuelven problemas distintos a OLTP</li>
  <li>Separar análisis mejora lectura y claridad</li>
  <li>La integración agrega costo y disciplina</li>
  <li>La arquitectura debe justificarse con una pregunta real</li>
</ul>

---

<!-- _class: next grid-lines -->

<div class="kicker">Siguiente clase</div>

# OLAP y Data Mining

> Ya que la arquitectura existe, toca extraer señales y discutir cómo interpretarlas.
