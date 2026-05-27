---
marp: true
theme: advanced-db-dark
paginate: true
---

<!-- _class: hero grid-lines -->

<div class="kicker">Clase 04</div>
<div class="meta">Diagnóstico y rendimiento</div>

# Indexes and Query Performance

## Cómo pasar de “está lento” a una hipótesis con evidencia

---

<!-- _class: agenda grid-lines -->

<div class="kicker">Ruta</div>

# Agenda de sesión

<ul class="agenda-list">
  <li>Qué vuelve lenta una consulta</li>
  <li>Índices, planes y tradeoffs</li>
  <li>Checkpoint de media sesión</li>
  <li>Demo, avance de proyecto y evidencia</li>
</ul>

---

<!-- _class: guide-question grid-dots -->

<div class="kicker">Pregunta guía</div>

# ¿Por qué agregar un índice puede arreglar una query y empeorar otra parte del sistema?

> Performance no se mejora por intuición. Se mejora leyendo evidencia y aceptando tradeoffs.

---

<!-- _class: real-world grid-lines -->

<div class="kicker">Problema real</div>

# “Solo tarda a veces” no es una explicación

<div class="cards">
  <div class="card">
    <div class="meta">Síntoma</div>
    <p>La búsqueda por cliente se vuelve lenta cuando crece el histórico.</p>
  </div>
  <div class="card">
    <div class="meta">Impacto</div>
    <p>Timeouts, dashboards lentos y decisiones de tuning hechas a ciegas.</p>
  </div>
</div>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Objetivo</div>

# Qué debería quedar claro hoy

<ul class="checklist-list">
  <li>Cómo pensar selectividad y cardinalidad</li>
  <li>Qué nos dice un query plan</li>
  <li>Qué gana y qué cuesta un índice</li>
  <li>Cómo producir evidencia antes y después</li>
</ul>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Acrónimos y conceptos</div>

# Vocabulario mínimo de la sesión

<div class="cards">
  <div class="card"><div class="meta">B-tree</div><p>Estructura típica de índice.</p></div>
  <div class="card"><div class="meta">Scan</div><p>Forma de recorrer datos.</p></div>
  <div class="card"><div class="meta">EXPLAIN</div><p>Plan esperado.</p></div>
  <div class="card"><div class="meta">Selectividad</div><p>Qué tanto filtra una condición.</p></div>
</div>

---

<!-- _class: statement grid-lines -->

<div class="kicker">Idea central</div>

# Un índice no acelera “tablas”; acelera ciertos caminos de acceso para ciertas consultas.

---

<!-- _class: before-after grid-lines-small -->

<div class="kicker">Antes / después</div>

# Sequential scan vs index scan

<div class="compare">
  <div class="panel">
    <div class="meta">Sequential scan</div>
    <p>Lee mucho para encontrar poco. Puede ser correcto cuando filtras poco o la tabla es pequeña.</p>
  </div>
  <div class="panel">
    <div class="meta">Index scan</div>
    <p>Reduce recorrido cuando la condición es útil, pero agrega costo de mantenimiento.</p>
  </div>
</div>

---

<!-- _class: tradeoff grid-lines -->

<div class="kicker">Tradeoff</div>

# Índices: más lectura útil, más costo de escritura

<div class="cards">
  <div class="card">
    <div class="meta">Gana</div>
    <p>Menos trabajo en consultas selectivas y mejor tiempo de respuesta.</p>
  </div>
  <div class="card">
    <div class="meta">Cuesta</div>
    <p>Más almacenamiento, más mantenimiento y más trabajo por insert/update/delete.</p>
  </div>
</div>

---

<!-- _class: grid-lines -->

<div class="kicker">Mental model</div>

# Qué mirar antes de proponer un índice

<ul class="checklist-list">
  <li>Qué filtra la consulta</li>
  <li>Qué tanto reduce el conjunto</li>
  <li>Qué tan frecuente es la lectura</li>
  <li>Qué tan costosa es la escritura</li>
</ul>

---

<!-- _class: section grid-dots -->

<div class="kicker">Checkpoint</div>

# Media sesión

## Ya tenemos el modelo mental de rendimiento. Ahora toca observar evidencia real y conectar con el proyecto.

---

<!-- _class: workflow grid-lines-small -->

<div class="kicker">Proyecto final</div>

# Checkpoint de proyecto

<ul class="agenda-list">
  <li>Definir una consulta crítica</li>
  <li>Documentar por qué importa</li>
  <li>Guardar evidencia antes/después</li>
  <li>No proponer índices sin caso concreto</li>
</ul>

---

<!-- _class: section grid-dots -->

<div class="kicker">Transición</div>

# Ahora vamos a observarlo en contexto técnico

## El objetivo no es “poner índices”, sino aprender a justificar por qué uno sí y otro no.

---

<!-- _class: demo grid-lines-small -->

<div class="kicker">Demo setup</div>

# Qué vamos a observar

<div class="terminal">
$ TODO: cargar tabla con volumen suficiente
<br />
$ EXPLAIN ANALYZE ...
<br />
$ TODO: crear índice y comparar plan
</div>

---

<!-- _class: demo grid-lines -->

<div class="kicker">Demo</div>

# Guía de observación

<ul class="checklist-list">
  <li>Plan antes</li>
  <li>Cambio propuesto</li>
  <li>Plan después</li>
  <li>Tradeoff que aparece</li>
</ul>

---

<!-- _class: workflow grid-lines-small -->

<div class="kicker">Razonamiento</div>

# Cómo se explica una mejora de performance

<ul class="agenda-list">
  <li>Consulta y contexto</li>
  <li>Hallazgo en el plan</li>
  <li>Cambio aplicado</li>
  <li>Resultado y costo asociado</li>
</ul>

---

<!-- _class: section grid-dots -->

<div class="kicker">Trabajo fuera de sesión</div>

# El análisis detallado seguirá en VS Code y en el assignment

## La slide cierra el modelo mental; la evidencia técnica completa se construye fuera del deck.

---

<!-- _class: exercise grid-lines -->

<div class="kicker">Ejercicio</div>

# Diagnosticar una query lenta con evidencia

<div class="cards">
  <div class="card">
    <div class="meta">Objetivo</div>
    <p>Pasar de una queja de lentitud a una propuesta justificada.</p>
  </div>
  <div class="card">
    <div class="meta">Entrega</div>
    <p>Query, plan antes, índice o cambio, plan después y tradeoff.</p>
  </div>
</div>

---

<!-- _class: evidence grid-lines-small -->

<div class="kicker">Evidencia</div>

# Qué evidencia esperaremos

<ul class="checklist-list">
  <li>Query original</li>
  <li>Plan antes</li>
  <li>Cambio propuesto</li>
  <li>Plan después y lectura crítica</li>
</ul>

---

<!-- _class: recap grid-dots -->

<div class="kicker">Recap</div>

# Qué nos llevamos hoy

<ul>
  <li>Performance se diagnostica, no se adivina</li>
  <li>Índice útil depende de la consulta</li>
  <li>Antes/después sin plan no basta</li>
  <li>Todo tuning serio trae tradeoffs</li>
</ul>

---

<!-- _class: next grid-lines -->

<div class="kicker">Siguiente clase</div>

# Views, procedures y triggers

> Optimizar no solo es leer rápido; también es decidir dónde vive la lógica.
