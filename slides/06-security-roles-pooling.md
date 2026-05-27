---
marp: true
theme: advanced-db-dark
paginate: true
---

<!-- _class: hero grid-lines -->

<div class="kicker">Clase 06</div>
<div class="meta">Seguridad y operación</div>

# Security, Roles, Pooling and Operational Concerns

## La base no solo debe funcionar: también debe resistir abuso, error y saturación

---

<!-- _class: agenda grid-lines -->

<div class="kicker">Ruta</div>

# Agenda de sesión

<ul class="agenda-list">
  <li>Acceso mínimo y roles</li>
  <li>Pooling y preocupaciones operativas</li>
  <li>Checkpoint de media sesión</li>
  <li>Demo, proyecto final y evidencia</li>
</ul>

---

<!-- _class: guide-question grid-dots -->

<div class="kicker">Pregunta guía</div>

# ¿Qué falla primero: el diseño lógico, los permisos o la operación?

> En producción, seguridad y operación no llegan al final: están mezcladas con el diseño desde el principio.

---

<!-- _class: real-world grid-lines -->

<div class="kicker">Problema real</div>

# Todo el mundo entra con demasiados permisos

<div class="cards">
  <div class="card">
    <div class="meta">Síntoma</div>
    <p>Usuarios con privilegios excesivos, credenciales compartidas y conexiones que crecen sin control.</p>
  </div>
  <div class="card">
    <div class="meta">Impacto</div>
    <p>Riesgo operativo, exposición de datos y degradación por saturación o configuración improvisada.</p>
  </div>
</div>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Objetivo</div>

# Qué debería quedar claro hoy

<ul class="checklist-list">
  <li>Cómo pensar mínimo privilegio</li>
  <li>Qué distingue rol, usuario y permiso</li>
  <li>Para qué sirve un connection pool</li>
  <li>Qué significa hablar de concerns operativos</li>
</ul>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Acrónimos y conceptos</div>

# Vocabulario mínimo de la sesión

<div class="cards">
  <div class="card"><div class="meta">RBAC</div><p>Role-Based Access Control.</p></div>
  <div class="card"><div class="meta">Pool</div><p>Reuso controlado de conexiones.</p></div>
  <div class="card"><div class="meta">Privilege</div><p>Permiso efectivo sobre un recurso.</p></div>
  <div class="card"><div class="meta">Buffer</div><p>Memoria útil para trabajo y acceso.</p></div>
</div>

---

<!-- _class: statement grid-lines -->

<div class="kicker">Idea central</div>

# Un sistema inseguro o mal operado puede invalidar el mejor modelo de datos.

---

<!-- _class: two-columns grid-lines -->

<div class="kicker">Concepto vs realidad</div>

# Seguridad “por política” vs seguridad real

<div class="col">
  <div class="meta">En teoría</div>
  <p>Hay roles definidos y permisos documentados.</p>
</div>

<div class="col">
  <div class="meta">En práctica</div>
  <p>Se usan accesos amplios porque “es más rápido”, y luego nadie sabe quién podía hacer qué.</p>
</div>

---

<!-- _class: tradeoff grid-lines -->

<div class="kicker">Tradeoff</div>

# Más control reduce riesgo, pero pide más disciplina operativa

<div class="cards">
  <div class="card">
    <div class="meta">Gana</div>
    <p>Mejor trazabilidad, menor superficie de daño y acceso más justificable.</p>
  </div>
  <div class="card">
    <div class="meta">Cuesta</div>
    <p>Más trabajo inicial para definir roles, rotar accesos y mantener una política clara.</p>
  </div>
</div>

---

<!-- _class: grid-lines -->

<div class="kicker">Operación</div>

# Pooling no es un lujo de arquitectura

<div class="cards">
  <div class="card"><div class="meta">Sirve para</div><p>Controlar apertura/cierre, latencia y uso de recursos.</p></div>
  <div class="card"><div class="meta">No resuelve</div><p>Consultas malas, permisos absurdos o infraestructura sin límites.</p></div>
</div>

---

<!-- _class: section grid-dots -->

<div class="kicker">Checkpoint</div>

# Media sesión

## Ya tenemos el marco de seguridad y operación. Ahora toca ver cómo se observa y cómo se convierte en evidencia útil.

---

<!-- _class: workflow grid-lines-small -->

<div class="kicker">Proyecto final</div>

# Checkpoint de proyecto

<ul class="agenda-list">
  <li>Definir roles mínimos por actor</li>
  <li>Explicar permisos críticos</li>
  <li>Justificar si habrá pooling o no</li>
  <li>Evitar cuentas “todopoderosas” por comodidad</li>
</ul>

---

<!-- _class: section grid-dots -->

<div class="kicker">Transición</div>

# Ahora vamos a observarlo en contexto técnico

## La práctica no es “dar permisos”, sino entender qué acceso conviene y cómo se comporta el sistema.

---

<!-- _class: demo grid-lines-small -->

<div class="kicker">Demo setup</div>

# Qué vamos a observar

<div class="terminal">
$ TODO: crear roles o usuarios simples
<br />
$ TODO: probar acceso permitido y denegado
<br />
$ TODO: diagramar pooling y límite operativo
</div>

---

<!-- _class: demo grid-lines -->

<div class="kicker">Demo</div>

# Qué queremos notar

<ul class="checklist-list">
  <li>Qué puede hacer cada rol</li>
  <li>Qué debería bloquearse</li>
  <li>Qué problema evita el pool</li>
  <li>Qué problema no arregla el pool</li>
</ul>

---

<!-- _class: section grid-dots -->

<div class="kicker">Trabajo fuera de sesión</div>

# La configuración detallada seguirá en VS Code y en el assignment

## Aquí cerramos el criterio; fuera del deck se construye la política concreta y la evidencia revisable.

---

<!-- _class: exercise grid-lines -->

<div class="kicker">Ejercicio</div>

# Diseñar una política mínima de acceso

<div class="cards">
  <div class="card">
    <div class="meta">Objetivo</div>
    <p>Separar lectura, escritura y administración con el menor privilegio posible.</p>
  </div>
  <div class="card">
    <div class="meta">Entrega</div>
    <p>Tabla de roles/permisos, justificación y nota operativa breve.</p>
  </div>
</div>

---

<!-- _class: evidence grid-lines-small -->

<div class="kicker">Evidencia</div>

# Qué evidencia esperaremos

<ul class="checklist-list">
  <li>Rol o usuario definido</li>
  <li>Acceso permitido/denegado</li>
  <li>Justificación de permisos</li>
  <li>Diagrama o nota de operación/pooling</li>
</ul>

---

<!-- _class: recap grid-dots -->

<div class="kicker">Recap</div>

# Qué nos llevamos hoy

<ul>
  <li>Seguridad también es diseño</li>
  <li>Mínimo privilegio evita deuda peligrosa</li>
  <li>Pooling mejora operación, no reemplaza criterio</li>
  <li>Permisos y operación deben poder explicarse</li>
</ul>

---

<!-- _class: next grid-lines -->

<div class="kicker">Siguiente clase</div>

# Modelado multidimensional

> Después de operar bien, toca pensar cómo estructurar datos para analizarlos mejor.
