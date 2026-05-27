---
marp: true
theme: advanced-db-dark
paginate: true
---

<!-- _class: hero grid-lines -->

<div class="kicker">Clase 07</div>
<div class="meta">Pensar para analizar</div>

# Multidimensional Modeling

## Hechos, dimensiones y granularidad para preguntas de negocio

---

<!-- _class: agenda grid-lines -->

<div class="kicker">Ruta</div>

# Agenda de sesión

<ul class="agenda-list">
  <li>Por qué OLTP no basta para analizar</li>
  <li>Hechos, dimensiones y jerarquías</li>
  <li>Checkpoint de media sesión</li>
  <li>Observación conceptual, assignment y evidencia</li>
</ul>

---

<!-- _class: guide-question grid-dots -->

<div class="kicker">Pregunta guía</div>

# ¿Cómo modelamos datos para responder preguntas, no solo para registrar eventos?

> Modelar para análisis cambia la prioridad: ya no optimizamos la transacción, sino la lectura de decisiones.

---

<!-- _class: real-world grid-lines -->

<div class="kicker">Problema real</div>

# El sistema guarda todo, pero nadie encuentra patrones

<div class="cards">
  <div class="card">
    <div class="meta">Síntoma</div>
    <p>La información existe, pero cada pregunta requiere joins incómodos y reglas implícitas.</p>
  </div>
  <div class="card">
    <div class="meta">Impacto</div>
    <p>Reportes lentos, análisis poco comparables y decisiones apoyadas en intuición incompleta.</p>
  </div>
</div>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Objetivo</div>

# Qué debería quedar claro hoy

<ul class="checklist-list">
  <li>Qué es un hecho y qué es una dimensión</li>
  <li>Por qué la granularidad importa</li>
  <li>Cómo pensar jerarquías y agregación</li>
  <li>Qué evidencia muestra que un modelo sí responde preguntas</li>
</ul>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Acrónimos y conceptos</div>

# Vocabulario mínimo de la sesión

<div class="cards">
  <div class="card"><div class="meta">BDM</div><p>Base de datos multidimensional.</p></div>
  <div class="card"><div class="meta">Hecho</div><p>Evento medible o registrable.</p></div>
  <div class="card"><div class="meta">Dimensión</div><p>Eje para analizar un hecho.</p></div>
  <div class="card"><div class="meta">Granularidad</div><p>Nivel mínimo de detalle.</p></div>
</div>

---

<!-- _class: statement grid-lines -->

<div class="kicker">Idea central</div>

# Un modelo multidimensional no pregunta “qué guardo”, sino “qué quiero comparar, agrupar y entender”.

---

<!-- _class: two-columns grid-lines -->

<div class="kicker">Concepto vs realidad</div>

# Hecho vs dimensión

<div class="col">
  <div class="meta">Hecho</div>
  <p>Lo que ocurre y normalmente se mide: venta, pedido, sesión, transacción.</p>
</div>

<div class="col">
  <div class="meta">Dimensión</div>
  <p>Cómo se observa el hecho: tiempo, producto, cliente, sucursal, canal.</p>
</div>

---

<!-- _class: tradeoff grid-lines -->

<div class="kicker">Tradeoff</div>

# Más detalle vs más facilidad de análisis

<div class="cards">
  <div class="card">
    <div class="meta">Granularidad fina</div>
    <p>Más flexibilidad analítica, pero mayor volumen y más complejidad.</p>
  </div>
  <div class="card">
    <div class="meta">Granularidad gruesa</div>
    <p>Menos costo operativo, pero menos preguntas posibles después.</p>
  </div>
</div>

---

<!-- _class: grid-lines -->

<div class="kicker">Visualización</div>

# Cubo conceptual y jerarquías

<div class="diagram-placeholder">
  TODO: cubo conceptual con dimensiones de tiempo, producto y canal; incluir jerarquía simple de fecha.
</div>

---

<!-- _class: section grid-dots -->

<div class="kicker">Checkpoint</div>

# Media sesión

## Ya tenemos el lenguaje del modelo. Ahora toca usarlo para construir preguntas más observables y defendibles.

---

<!-- _class: section grid-dots -->

<div class="kicker">Transición</div>

# Ahora vamos a observarlo en contexto técnico

## No para construir un warehouse completo, sí para ver cómo una pregunta cambia el modelo.

---

<!-- _class: demo grid-lines-small -->

<div class="kicker">Demo conceptual</div>

# Qué vamos a observar

<div class="terminal">
$ TODO: definir hecho principal
<br />
$ TODO: proponer dimensiones y jerarquías
<br />
$ TODO: formular consulta agregada simple
</div>

---

<!-- _class: workflow grid-lines -->

<div class="kicker">Observación</div>

# Qué queremos notar

<ul class="checklist-list">
  <li>Qué pregunta guía el modelo</li>
  <li>Cuál es la granularidad elegida</li>
  <li>Qué dimensiones son realmente útiles</li>
  <li>Qué pregunta quedaría fuera</li>
</ul>

---

<!-- _class: section grid-dots -->

<div class="kicker">Trabajo fuera de sesión</div>

# El modelado detallado seguirá en VS Code y en el assignment

## La slide cierra el mapa mental; la formalización y evidencia siguen fuera del deck.

---

<!-- _class: exercise grid-lines -->

<div class="kicker">Ejercicio</div>

# Proponer un modelo multidimensional para una pregunta concreta

<div class="cards">
  <div class="card">
    <div class="meta">Objetivo</div>
    <p>Elegir un hecho, dimensiones útiles y una granularidad justificable.</p>
  </div>
  <div class="card">
    <div class="meta">Entrega</div>
    <p>Esquema conceptual, jerarquías y al menos una consulta analítica ejemplo.</p>
  </div>
</div>

---

<!-- _class: evidence grid-lines-small -->

# Qué evidencia esperaremos

<ul class="checklist-list">
  <li>Hecho principal</li>
  <li>Dimensiones y medidas</li>
  <li>Granularidad explícita</li>
  <li>Pregunta analítica que sí responde</li>
</ul>

---

<!-- _class: recap grid-dots -->

<div class="kicker">Recap</div>

# Qué nos llevamos hoy

<ul>
  <li>Modelar para análisis cambia la prioridad</li>
  <li>Hechos y dimensiones no son lo mismo</li>
  <li>Granularidad define el alcance del modelo</li>
  <li>El modelo correcto depende de la pregunta</li>
</ul>

---

<!-- _class: next grid-lines -->

<div class="kicker">Siguiente clase</div>

# Data Warehouse y Data Mart

> El modelo multidimensional gana poder cuando se integra a una arquitectura de decisión más grande.
