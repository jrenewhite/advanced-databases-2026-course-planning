---
marp: true
theme: advanced-db-dark
paginate: true
---

<!-- _class: hero -->

<div class="kicker">Template reusable</div>
<div class="meta">dark editorial tech deck</div>

# TODO Titulo de sesion

## Subtitle placeholder

Esta presentacion demuestra el lenguaje visual reusable sin contenido especifico de clase.

---

<!-- _class: section grid-lines -->

<div class="kicker">Fondos</div>

# Variantes de grid

## Demo visual del sistema reusable

---

<!-- _class: grid-lines -->

<div class="kicker">Grid Lines</div>

# Grid default

<div class="card">
  <div class="meta">Uso sugerido</div>
  <p>TODO: usar como fondo por defecto para slides editoriales, conceptuales o de comparacion.</p>
</div>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Grid Lines Small</div>

# Grid lines small

<div class="card">
  <div class="meta">Uso sugerido</div>
  <p>TODO: usar cuando quieras un fondo mas tecnico y un poco mas denso sin competir con el contenido.</p>
</div>

---

<!-- _class: grid-dots -->

<div class="kicker">Grid Dots</div>

# Grid dots

<div class="card">
  <div class="meta">Uso sugerido</div>
  <p>TODO: usar para slides mas ligeras, recaps, preguntas guia o transiciones con mucho espacio negativo.</p>
</div>

---

<!-- _class: agenda -->

<div class="kicker">Ruta</div>

# Agenda / ruta de sesion

<ul class="agenda-list">
  <li>Contexto y pregunta guia</li>
  <li>Concepto clave y realidad</li>
  <li>Demo y evidencia</li>
  <li>Ejercicio y recap</li>
</ul>

---

<!-- _class: section -->

<div class="kicker">Separador</div>

# Bloque principal

## Cambio de contexto

---

<!-- _class: guide-question -->

<div class="kicker">Pregunta guia</div>

# Pregunta guia

> TODO: formular la pregunta que deberia sostener la sesion completa.

---

<!-- _class: real-world -->

<div class="kicker">Problema real</div>

# Problema real

> TODO: describir una situacion concreta y observable.

<div class="cards">
  <div class="card">
    <div class="meta">Sintoma</div>
    <p>TODO: que se ve mal.</p>
  </div>
  <div class="card">
    <div class="meta">Impacto</div>
    <p>TODO: por que importa.</p>
  </div>
</div>

---

<!-- _class: incident -->

<div class="kicker">Incidente</div>

# Incidente anonimizado

> TODO: resumir un incidente breve, tecnico y sin datos reales.

<div class="card">
  <div class="meta">Leccion</div>
  <p>TODO: que cambia en el criterio despues del incidente.</p>
</div>

---

<div class="kicker">Idea central</div>

# Concepto clave

<div class="statement">
  TODO: expresar una idea central en una frase grande y clara.
</div>

---

<!-- _class: two-columns -->

<div class="kicker">Concepto vs realidad</div>

# Concepto vs realidad

<div class="col">
  <div class="meta">En teoria</div>
  <p>TODO: regla simple o definicion compacta.</p>
</div>

<div class="col">
  <div class="meta">En practica</div>
  <p>TODO: restriccion, excepcion o tradeoff real.</p>
</div>

---

<div class="kicker">Dashboard</div>

# Dashboard visual

<div class="dashboard">
  <div class="metric-card">
    <div class="meta">Signal A</div>
    <div class="big-number">42</div>
    <p class="muted">TODO: lectura breve.</p>
  </div>
  <div class="metric-card">
    <div class="meta">Signal B</div>
    <div class="big-number">3x</div>
    <p class="muted">TODO: lectura breve.</p>
  </div>
  <div class="metric-card">
    <div class="meta">Signal C</div>
    <div class="big-number">OK</div>
    <p class="muted">TODO: lectura breve.</p>
  </div>
</div>

---

<!-- _class: before-after -->

<div class="kicker">Antes / despues</div>

# Antes vs despues

<div class="compare">
  <div class="panel">
    <div class="meta">Antes</div>
    <p>TODO: describir el estado inicial.</p>
  </div>
  <div class="panel">
    <div class="meta">Despues</div>
    <p>TODO: describir el estado mejorado.</p>
  </div>
</div>

---

<!-- _class: tradeoff -->

<div class="kicker">Tradeoff</div>

# Tradeoff con dos cards

<div class="cards">
  <div class="card">
    <div class="meta">Gana</div>
    <p>TODO: beneficio principal.</p>
  </div>
  <div class="card">
    <div class="meta">Cuesta</div>
    <p>TODO: costo o riesgo principal.</p>
  </div>
</div>

---

<div class="kicker">Diagrama</div>

# Diagrama conceptual

<div class="diagram-placeholder">
  TODO: insertar aqui diagrama conceptual, flujo o arquitectura simple.
</div>

---

<!-- _class: demo -->

<div class="kicker">Setup de demo</div>

# Setup de demo estilo terminal

<div class="terminal">
$ docker compose up -d
<br />
$ psql postgresql://postgres:postgres@localhost:5432/demo
<br />
$ TODO: preparar observacion principal
</div>

<div class="terminal right-controls">
$ psql -f demo/init.sql
<br />
$ psql -f demo/seed.sql
<br />
$ TODO: ejecutar variante con controles a la derecha
</div>

---

<!-- _class: demo small -->

<div class="kicker">Pasos de demo</div>

# Pasos de demo

<ul class="checklist-list">
  <li>Ejecutar query base</li>
  <li>Observar salida</li>
  <li>Aplicar cambio minimo</li>
  <li>Comparar resultado</li>
</ul>

---

<div class="kicker">SQL corto</div>

# SQL corto

```sql
EXPLAIN ANALYZE
SELECT *
FROM orders
WHERE customer_id = 42;
```

<span class="pill">short code only</span>

---

<!-- _class: workflow tiny -->

<div class="kicker">Plan de ejecucion</div>

# Recorrido del plan de ejecucion

<ul class="checklist-list">
  <li>Paso 1: TODO</li>
  <li>Paso 2: TODO</li>
  <li>Paso 3: TODO</li>
  <li>Hallazgo: TODO</li>
</ul>

---

<!-- _class: exercise -->

<div class="kicker">Ejercicio</div>

# Ejercicio

> TODO: describir actividad breve, evidencia esperada y tiempo sugerido.

<div class="cards">
  <div class="card">
    <div class="meta">Objetivo</div>
    <p>TODO</p>
  </div>
  <div class="card">
    <div class="meta">Evidencia</div>
    <p>TODO</p>
  </div>
</div>

---

<!-- _class: evidence -->

<div class="kicker">Evidencia</div>

# Evidencia esperada

<ul class="checklist-list">
  <li>Query antes</li>
  <li>Query despues</li>
  <li>Plan o resultado</li>
  <li>Tradeoff explicado</li>
</ul>

---

<!-- _class: ai-judgment -->

<div class="kicker">IA con criterio</div>

# IA permitida, criterio obligatorio

> TODO: indicar que la IA puede ayudar, pero la validacion sigue siendo humana.

---

<!-- _class: workflow -->

<div class="kicker">Workflow</div>

# GitHub / repo workflow

<ul class="agenda-list">
  <li>Repo base comun</li>
  <li>Rama de trabajo</li>
  <li>Evidencia y entrega</li>
  <li>Revision posterior</li>
</ul>

---

<!-- _class: anti-pattern -->

<div class="kicker">Anti-pattern</div>

# Warning / anti-pattern

> TODO: destacar una practica comun que parezca conveniente pero genere deuda o confusion.

---

<!-- _class: success -->

<div class="kicker">Resultado correcto</div>

# Resultado correcto / takeaway positivo

> TODO: resumir el resultado correcto o el aprendizaje central.

---

<!-- _class: recap -->

<div class="kicker">Recap</div>

# Recap visual

<ul>
  <li>Idea clave uno</li>
  <li>Idea clave dos</li>
  <li>Idea clave tres</li>
  <li>Paso siguiente</li>
</ul>

---

<!-- _class: next -->

<div class="kicker">Siguiente clase</div>

# Siguiente clase

> TODO: dejar una tension o pregunta para el proximo tema.
