---
marp: true
theme: advanced-db-dark
paginate: true
---

<!-- _class: hero grid-lines -->

<div class="kicker">Clase 03</div>
<div class="meta">Consistencia bajo acceso simultáneo</div>

# Transactions and Concurrency

## Cuando dos usuarios hacen lo correcto y aun así el sistema se rompe

---

<!-- _class: agenda grid-lines -->

<div class="kicker">Ruta</div>

# Agenda de sesión

<ul class="agenda-list">
  <li>Qué protege una transacción</li>
  <li>Cómo aparecen conflictos reales</li>
  <li>Checkpoint de media sesión</li>
  <li>Observación práctica, assignment y evidencia</li>
</ul>

---

<!-- _class: guide-question grid-dots -->

<div class="kicker">Pregunta guía</div>

# ¿Qué puede salir mal cuando todos hacen su trabajo “bien” al mismo tiempo?

> Concurrencia no es caos aleatorio: es interacción simultánea entre decisiones válidas.

---

<!-- _class: incident grid-lines -->

<div class="kicker">Incidente</div>

# Relato de incidente

> Dos operadores actualizan inventario y ventas al mismo tiempo. Ninguno comete un error obvio, pero el stock final queda imposible de explicar.

<div class="card">
  <div class="meta">Lección</div>
  <p>La consistencia no depende solo de validar datos; también depende del orden y aislamiento de las acciones.</p>
</div>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Objetivo</div>

# Qué debería quedar claro hoy

<ul class="checklist-list">
  <li>Qué protege una transacción</li>
  <li>Qué tipo de conflictos genera la concurrencia</li>
  <li>Cómo leer bloqueos, esperas y deadlocks</li>
  <li>Qué evidencia sirve para explicarlos</li>
</ul>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Acrónimos y conceptos</div>

# Vocabulario mínimo de la sesión

<div class="cards">
  <div class="card"><div class="meta">ACID</div><p>Propiedades esperadas de una transacción.</p></div>
  <div class="card"><div class="meta">MVCC</div><p>Control multiversión de concurrencia.</p></div>
  <div class="card"><div class="meta">Lock</div><p>Bloqueo para coordinar acceso.</p></div>
  <div class="card"><div class="meta">Deadlock</div><p>Espera circular sin avance.</p></div>
</div>

---

<!-- _class: statement grid-lines -->

<div class="kicker">Idea central</div>

# Una transacción no hace magia: solo define una unidad de trabajo que el sistema debe intentar aislar y cerrar de forma consistente.

---

<!-- _class: grid-lines -->

<div class="kicker">Conceptos clave</div>

# Qué observamos cuando hablamos de transacciones

<div class="cards">
  <div class="card"><div class="meta">Inicio</div><p>`BEGIN` y alcance del trabajo.</p></div>
  <div class="card"><div class="meta">Cierre</div><p>`COMMIT` o `ROLLBACK`.</p></div>
  <div class="card"><div class="meta">Aislamiento</div><p>Qué lecturas o cambios pueden verse.</p></div>
  <div class="card"><div class="meta">Contención</div><p>Quién espera a quién y por qué.</p></div>
</div>

---

<!-- _class: before-after grid-lines-small -->

<div class="kicker">Antes / después</div>

# Operación secuencial vs concurrencia real

<div class="compare">
  <div class="panel">
    <div class="meta">Secuencial</div>
    <p>Una operación termina, luego empieza la otra. El estado es fácil de narrar.</p>
  </div>
  <div class="panel">
    <div class="meta">Concurrente</div>
    <p>Las operaciones se intercalan. El problema ya no es solo la lógica, sino el orden de observación.</p>
  </div>
</div>

---

<!-- _class: tradeoff grid-lines -->

<div class="kicker">Tradeoff</div>

# Más aislamiento rara vez sale gratis

<div class="cards">
  <div class="card">
    <div class="meta">Gana</div>
    <p>Mayor consistencia y menos sorpresas para ciertos casos críticos.</p>
  </div>
  <div class="card">
    <div class="meta">Cuesta</div>
    <p>Más espera, más contención o mayor complejidad para ciertas cargas.</p>
  </div>
</div>

---

<!-- _class: section grid-dots -->

<div class="kicker">Checkpoint</div>

# Media sesión

## Ya tenemos el modelo mental de transacción y conflicto. Ahora toca verlo desde observación y debugging.

---

<!-- _class: section grid-dots -->

<div class="kicker">Transición</div>

# Ahora vamos a observarlo en contexto técnico

## La meta no es memorizar niveles de aislamiento, sino aprender a describir qué pasó y cómo mitigarlo.

---

<!-- _class: demo grid-lines-small -->

<div class="kicker">Demo setup</div>

# Qué vamos a observar

<div class="terminal">
$ psql session_a
<br />
$ psql session_b
<br />
$ TODO: reproducir bloqueo, espera o deadlock controlado
</div>

---

<!-- _class: demo grid-lines -->

<div class="kicker">Demo</div>

# Guía de observación

<ul class="checklist-list">
  <li>Quién tomó el lock primero</li>
  <li>Quién quedó esperando</li>
  <li>Qué ve cada sesión en cada momento</li>
  <li>Qué cambio elimina o reduce el conflicto</li>
</ul>

---

<!-- _class: workflow grid-lines-small -->

<div class="kicker">Razonamiento</div>

# Cómo explicar un conflicto sin caer en magia

<ul class="agenda-list">
  <li>Estado inicial</li>
  <li>Acción de la sesión A</li>
  <li>Acción de la sesión B</li>
  <li>Bloqueo, espera o inconsistencia observada</li>
</ul>

---

<!-- _class: section grid-dots -->

<div class="kicker">Trabajo fuera de sesión</div>

# El caso completo seguirá fuera de las slides

## La reproducción detallada y la entrega vivirán en VS Code y en el assignment correspondiente.

---

<!-- _class: exercise grid-lines -->

<div class="kicker">Ejercicio</div>

# Reproducir un conflicto simple y narrarlo bien

<div class="cards">
  <div class="card">
    <div class="meta">Objetivo</div>
    <p>Explicar qué ocurrió entre dos sesiones, no solo mostrar que falló.</p>
  </div>
  <div class="card">
    <div class="meta">Entrega</div>
    <p>Pasos, comportamiento observado, riesgo y posible mitigación.</p>
  </div>
</div>

---

<!-- _class: evidence grid-lines-small -->

<div class="kicker">Evidencia</div>

# Qué evidencia esperaremos

<ul class="checklist-list">
  <li>Secuencia de pasos</li>
  <li>Comportamiento observado</li>
  <li>Explicación del conflicto</li>
  <li>Mitigación o alternativa</li>
</ul>

---

<!-- _class: recap grid-dots -->

<div class="kicker">Recap</div>

# Qué nos llevamos hoy

<ul>
  <li>Una transacción protege una unidad de trabajo</li>
  <li>La concurrencia introduce riesgos de observación y orden</li>
  <li>Más aislamiento trae costos reales</li>
  <li>La mejor defensa es explicar el conflicto con evidencia</li>
</ul>

---

<!-- _class: next grid-lines -->

<div class="kicker">Siguiente clase</div>

# Índices y rendimiento

> Aun con consistencia correcta, una base puede fallar por costo y tiempo de respuesta.
