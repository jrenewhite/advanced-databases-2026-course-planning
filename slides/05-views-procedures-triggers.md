---
marp: true
theme: advanced-db-dark
paginate: true
---

<!-- _class: hero grid-lines -->

<div class="kicker">Clase 05</div>
<div class="meta">Lógica dentro de la base</div>

# Views, Stored Procedures and Triggers

## Encapsular con criterio, no esconder complejidad

---

<!-- _class: agenda grid-lines -->

<div class="kicker">Ruta</div>

# Agenda de sesión

<ul class="agenda-list">
  <li>Qué resuelve cada objeto</li>
  <li>Cuándo ayuda y cuándo estorba</li>
  <li>Checkpoint de media sesión</li>
  <li>Observación práctica, assignment y evidencia</li>
</ul>

---

<!-- _class: guide-question grid-dots -->

<div class="kicker">Pregunta guía</div>

# ¿Cuándo conviene poner lógica en la base y cuándo empieza la magia peligrosa?

> No toda reutilización es buena si vuelve opaco el comportamiento del sistema.

---

<!-- _class: real-world grid-lines -->

<div class="kicker">Problema real</div>

# La misma regla aparece en cinco lugares distintos

<div class="cards">
  <div class="card">
    <div class="meta">Síntoma</div>
    <p>Consultas repetidas, reglas duplicadas y efectos laterales difíciles de rastrear.</p>
  </div>
  <div class="card">
    <div class="meta">Impacto</div>
    <p>Cambios costosos, bugs sutiles y análisis que nadie sabe si siguen siendo correctos.</p>
  </div>
</div>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Objetivo</div>

# Qué debería quedar claro hoy

<ul class="checklist-list">
  <li>Qué resuelve una view</li>
  <li>Qué resuelve un stored procedure</li>
  <li>Qué riesgo introduce un trigger</li>
  <li>Cómo justificar su uso con contexto</li>
</ul>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Acrónimos y conceptos</div>

# Vocabulario mínimo de la sesión

<div class="cards">
  <div class="card"><div class="meta">View</div><p>Consulta encapsulada para acceso o reporting.</p></div>
  <div class="card"><div class="meta">SP</div><p>Stored Procedure: lógica reutilizable en BD.</p></div>
  <div class="card"><div class="meta">Trigger</div><p>Acción automática ante un evento.</p></div>
  <div class="card"><div class="meta">Side effect</div><p>Cambio implícito difícil de ver.</p></div>
</div>

---

<!-- _class: statement grid-lines -->

<div class="kicker">Idea central</div>

# El problema no es usar lógica en la base. El problema es usarla sin hacer visible su costo, alcance y efectos laterales.

---

<!-- _class: before-after grid-lines-small -->

<div class="kicker">Comparación</div>

# View vs procedure vs trigger

<div class="compare">
  <div class="panel">
    <div class="meta">Bueno para claridad</div>
    <p>Views y procedures bien nombrados pueden reducir duplicación y ordenar acceso.</p>
  </div>
  <div class="panel">
    <div class="meta">Riesgo de opacidad</div>
    <p>Triggers y lógica implícita pueden volver impredecible el comportamiento del sistema.</p>
  </div>
</div>

---

<!-- _class: tradeoff grid-lines -->

<div class="kicker">Tradeoff</div>

# Encapsulación útil vs comportamiento escondido

<div class="cards">
  <div class="card">
    <div class="meta">Gana</div>
    <p>Menos repetición, mejor centralización y acceso más uniforme.</p>
  </div>
  <div class="card">
    <div class="meta">Cuesta</div>
    <p>Mayor dificultad para debuggear si el flujo ya no es evidente desde el código o la consulta.</p>
  </div>
</div>

---

<!-- _class: grid-lines -->

<div class="kicker">Anti-pattern</div>

# Trigger como parche invisible

<div class="card">
  <div class="meta">Señal de riesgo</div>
  <p>Cuando el trigger existe para “corregir” problemas de modelo o de proceso que nadie quiso resolver de frente.</p>
</div>

---

<!-- _class: section grid-dots -->

<div class="kicker">Checkpoint</div>

# Media sesión

## Ya distinguimos los objetos. Ahora toca ver cuándo el comportamiento observable justifica o desaconseja cada uno.

---

<!-- _class: section grid-dots -->

<div class="kicker">Transición</div>

# Ahora vamos a observarlo en contexto técnico

## La meta no es crear todos los objetos, sino aprender a defender por qué uno sí y otro no.

---

<!-- _class: demo grid-lines-small -->

<div class="kicker">Demo setup</div>

# Qué vamos a observar

<div class="terminal">
$ TODO: crear una view simple
<br />
$ TODO: encapsular una operación o lectura
<br />
$ TODO: mostrar un trigger y discutir riesgo
</div>

---

<!-- _class: demo grid-lines -->

<div class="kicker">Demo</div>

# Qué queremos notar

<ul class="checklist-list">
  <li>Qué hace visible la view</li>
  <li>Qué abstrae el procedure</li>
  <li>Qué vuelve menos visible el trigger</li>
  <li>Qué tradeoff aparece en mantenimiento</li>
</ul>

---

<!-- _class: section grid-dots -->

<div class="kicker">Trabajo fuera de sesión</div>

# La implementación detallada seguirá en VS Code y en el assignment

## Aquí cerramos el marco de decisión; fuera de la slide se construye la evidencia real.

---

<!-- _class: exercise grid-lines -->

<div class="kicker">Ejercicio</div>

# Elegir el objeto correcto para un caso breve

<div class="cards">
  <div class="card">
    <div class="meta">Objetivo</div>
    <p>Decidir si conviene view, procedure, trigger o ninguna de las tres.</p>
  </div>
  <div class="card">
    <div class="meta">Entrega</div>
    <p>Justificación, objeto propuesto, evidencia y al menos un riesgo identificado.</p>
  </div>
</div>

---

<!-- _class: evidence grid-lines-small -->

<div class="kicker">Evidencia</div>

# Qué evidencia esperaremos

<ul class="checklist-list">
  <li>Objeto creado o propuesto</li>
  <li>Caso de uso concreto</li>
  <li>Ejemplo breve de uso</li>
  <li>Riesgo o limitación principal</li>
</ul>

---

<!-- _class: recap grid-dots -->

<div class="kicker">Recap</div>

# Qué nos llevamos hoy

<ul>
  <li>Encapsular no siempre simplifica</li>
  <li>La visibilidad del comportamiento importa</li>
  <li>Triggers piden mucho más cuidado</li>
  <li>La mejor opción depende del flujo real</li>
</ul>

---

<!-- _class: next grid-lines -->

<div class="kicker">Siguiente clase</div>

# Seguridad, roles y pooling

> Una base correcta también puede fallar por accesos mal diseñados o por operación deficiente.
