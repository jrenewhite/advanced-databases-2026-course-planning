---
marp: true
theme: advanced-db-dark
paginate: true
---

<!-- _class: hero grid-lines -->

<div class="kicker">Clase 02</div>
<div class="meta">Diseño lógico y calidad de datos</div>

# Logical Design and Domain Rules

## Qué errores debe impedir la base antes de que lleguen a producción

---

<!-- _class: agenda grid-lines -->

<div class="kicker">Ruta</div>

# Agenda de sesión

<ul class="agenda-list">
  <li>Problema real de modelado débil</li>
  <li>Reglas de dominio y constraints</li>
  <li>Checkpoint de media sesión</li>
  <li>Observación práctica, assignment y evidencia</li>
</ul>

---

<!-- _class: guide-question grid-dots -->

<div class="kicker">Pregunta guía</div>

# ¿Qué errores deberían morir en la base y no en la aplicación?

> Un modelo lógico no solo describe datos: también decide qué inconsistencias se aceptan y cuáles se rechazan.

---

<!-- _class: real-world grid-lines -->

<div class="kicker">Problema real</div>

# “La app lo valida” suele llegar tarde

<div class="cards">
  <div class="card">
    <div class="meta">Síntoma</div>
    <p>Clientes duplicados, montos negativos, estados imposibles y referencias huérfanas.</p>
  </div>
  <div class="card">
    <div class="meta">Impacto</div>
    <p>La lógica de negocio se fragmenta, las correcciones son costosas y el análisis se vuelve poco confiable.</p>
  </div>
</div>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Objetivo</div>

# Qué debería quedar claro hoy

<ul class="checklist-list">
  <li>Diseño lógico como contrato operativo</li>
  <li>Reglas de dominio como política explícita</li>
  <li>Constraints como primera barrera de calidad</li>
  <li>Evidencia mínima para justificar el modelo</li>
</ul>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Acrónimos y conceptos</div>

# Vocabulario mínimo de la sesión

<div class="cards">
  <div class="card"><div class="meta">PK</div><p>Primary Key: identidad única.</p></div>
  <div class="card"><div class="meta">FK</div><p>Foreign Key: relación válida.</p></div>
  <div class="card"><div class="meta">ERD</div><p>Diagrama entidad-relación.</p></div>
  <div class="card"><div class="meta">CHECK</div><p>Regla explícita sobre valores.</p></div>
</div>

---

<!-- _class: statement grid-lines -->

<div class="kicker">Idea central</div>

# Un buen modelo no evita todos los errores, pero sí evita los más caros y repetitivos.

---

<!-- _class: two-columns grid-lines -->

<div class="kicker">Concepto vs realidad</div>

# Modelo limpio vs sistema real

<div class="col">
  <div class="meta">En teoría</div>
  <p>Entidades, atributos y relaciones parecen obvios en el pizarrón.</p>
</div>

<div class="col">
  <div class="meta">En práctica</div>
  <p>Estados ambiguos, excepciones del negocio y datos heredados obligan a definir límites claros.</p>
</div>

---

<!-- _class: tradeoff grid-lines -->

<div class="kicker">Tradeoff</div>

# Flexibilidad sin control vs calidad con fricción

<div class="cards">
  <div class="card">
    <div class="meta">Más flexible</div>
    <p>Insertar casi cualquier cosa acelera el inicio, pero acumula basura.</p>
  </div>
  <div class="card">
    <div class="meta">Más estricto</div>
    <p>Las reglas frenan errores temprano, aunque obligan a diseñar mejor desde el principio.</p>
  </div>
</div>

---

<!-- _class: grid-lines -->

<div class="kicker">Conceptos clave</div>

# Qué reglas solemos fijar en la base

<div class="cards">
  <div class="card"><div class="meta">Identidad</div><p>PKs y unicidad.</p></div>
  <div class="card"><div class="meta">Obligatoriedad</div><p>`NOT NULL` y presencia mínima.</p></div>
  <div class="card"><div class="meta">Integridad</div><p>FKs y referencias válidas.</p></div>
  <div class="card"><div class="meta">Rango</div><p>`CHECK` y reglas de dominio.</p></div>
</div>

---

<!-- _class: before-after grid-lines-small -->

<div class="kicker">Antes / después</div>

# Reglas implícitas vs reglas visibles

<div class="compare">
  <div class="panel">
    <div class="meta">Implícitas</div>
    <p>“No debería pasar”, “la app ya lo cuida”, “eso nunca lo manda el usuario”.</p>
  </div>
  <div class="panel">
    <div class="meta">Explícitas</div>
    <p>El esquema rechaza estados inválidos y documenta mejor el comportamiento esperado.</p>
  </div>
</div>

---

<!-- _class: section grid-dots -->

<div class="kicker">Checkpoint</div>

# Media sesión

## Ya cerramos el modelo mental. Ahora veremos cómo se traduce a observación práctica y evidencia.

---

<!-- _class: section grid-dots -->

<div class="kicker">Transición</div>

# Ahora vamos a observarlo en contexto técnico

## No para construir un esquema completo, sí para ver cómo cambian las decisiones cuando el dato falla.

---

<!-- _class: demo grid-lines-small -->

<div class="kicker">Demo setup</div>

# Qué vamos a observar

<div class="terminal">
$ TODO: crear tabla base sin reglas
<br />
$ TODO: insertar casos ambiguos o inválidos
<br />
$ TODO: agregar constraints y repetir prueba
</div>

---

<!-- _class: demo grid-lines -->

<div class="kicker">Demo</div>

# Preguntas de observación

<ul class="checklist-list">
  <li>¿Qué datos pasan cuando no hay reglas?</li>
  <li>¿Qué cambia al agregar PK, FK o `CHECK`?</li>
  <li>¿Qué error conviene detectar temprano?</li>
  <li>¿Qué tradeoff trae un modelo más estricto?</li>
</ul>

---

<!-- _class: section grid-dots -->

<div class="kicker">Trabajo fuera de sesión</div>

# La explicación larga vive fuera de la slide

## El modelado, el diagrama y la evidencia se trabajarán con más detalle en VS Code y en el assignment.

---

<!-- _class: exercise grid-lines -->

<div class="kicker">Ejercicio</div>

# Diseñar un caso pequeño con reglas explícitas

<div class="cards">
  <div class="card">
    <div class="meta">Objetivo</div>
    <p>Modelar un dominio simple y decidir qué debe impedir la base de datos.</p>
  </div>
  <div class="card">
    <div class="meta">Entregable</div>
    <p>Diagrama lógico, lista de reglas y ejemplos válidos/ inválidos.</p>
  </div>
</div>

---

<!-- _class: evidence grid-lines-small -->

<div class="kicker">Evidencia</div>

# Qué evidencia esperaremos

<ul class="checklist-list">
  <li>Diagrama lógico claro</li>
  <li>Reglas de dominio explícitas</li>
  <li>SQL de constraints</li>
  <li>Supuestos y límites del modelo</li>
</ul>

---

<!-- _class: recap grid-dots -->

<div class="kicker">Recap</div>

# Qué nos llevamos hoy

<ul>
  <li>El modelo lógico también gobierna comportamiento</li>
  <li>Constraints reducen errores costosos</li>
  <li>Las reglas implícitas suelen fallar tarde</li>
  <li>La evidencia del diseño debe ser visible y defendible</li>
</ul>

---

<!-- _class: next grid-lines -->

<div class="kicker">Siguiente clase</div>

# Transacciones y concurrencia

> Un modelo correcto no basta si dos usuarios hacen cambios válidos al mismo tiempo.
