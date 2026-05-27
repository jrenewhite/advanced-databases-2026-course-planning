---
marp: true
theme: advanced-db-dark
paginate: true
---

<!-- _class: hero grid-lines -->

<div class="kicker">Clase 10</div>
<div class="meta">Cierre conceptual del curso</div>

# Object-Oriented Databases and Modern Models

## Qué intentó resolver BDOO y por qué hoy seguimos hablando de ORM, documentos y mismatch

---

<!-- _class: agenda grid-lines -->

<div class="kicker">Ruta</div>

# Agenda de sesión

<ul class="agenda-list">
  <li>Motivación histórica de BDOO</li>
  <li>Persistencia de objetos y modelos modernos</li>
  <li>Checkpoint de media sesión</li>
  <li>Cierre de proyecto, revisión y evidencia final</li>
</ul>

---

<!-- _class: guide-question grid-dots -->

<div class="kicker">Pregunta guía</div>

# ¿Por qué el mundo intentó guardar objetos directamente y por qué no todo terminó allí?

> Esta clase no busca nostalgia tecnológica: busca entender qué problema intentaban resolver esos modelos y qué sigue vivo hoy.

---

<!-- _class: real-world grid-lines -->

<div class="kicker">Problema real</div>

# El modelo del código no siempre encaja con el modelo de la base

<div class="cards">
  <div class="card">
    <div class="meta">Síntoma</div>
    <p>Objetos ricos en memoria, relaciones complejas y persistencia que obliga a traducir todo.</p>
  </div>
  <div class="card">
    <div class="meta">Impacto</div>
    <p>Mappers complejos, decisiones arquitectónicas forzadas y discusiones sobre qué modelo conviene realmente.</p>
  </div>
</div>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Objetivo</div>

# Qué debería quedar claro hoy

<ul class="checklist-list">
  <li>Qué buscaban las BDOO</li>
  <li>Qué significa persistir objetos con identidad y comportamiento</li>
  <li>Qué relación tiene esto con ORM y documentos</li>
  <li>Cómo cerrar el curso conectando modelos y tradeoffs</li>
</ul>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Acrónimos y conceptos</div>

# Vocabulario mínimo de la sesión

<div class="cards">
  <div class="card"><div class="meta">OODB</div><p>Object-Oriented DataBase.</p></div>
  <div class="card"><div class="meta">ORM</div><p>Object-Relational Mapping.</p></div>
  <div class="card"><div class="meta">ODMG</div><p>Estándar histórico de BDOO.</p></div>
  <div class="card"><div class="meta">Impedance mismatch</div><p>Tensión entre modelo objeto y relacional.</p></div>
</div>

---

<!-- _class: statement grid-lines -->

<div class="kicker">Idea central</div>

# BDOO importa menos como stack dominante y más como lente para entender por qué persistir objetos sigue siendo un problema de diseño.

---

<!-- _class: two-columns grid-lines -->

<div class="kicker">Concepto vs realidad</div>

# Objeto en memoria vs dato persistido

<div class="col">
  <div class="meta">Objeto</div>
  <p>Identidad, relaciones, encapsulamiento, herencia y comportamiento.</p>
</div>

<div class="col">
  <div class="meta">Persistencia</div>
  <p>Tablas, claves, joins, consistencia, concurrencia y recuperación.</p>
</div>

---

<!-- _class: tradeoff grid-lines -->

<div class="kicker">Tradeoff</div>

# Cercanía al modelo objeto vs claridad operacional

<div class="cards">
  <div class="card">
    <div class="meta">Gana</div>
    <p>Menos fricción conceptual para ciertos dominios complejos y estructuras ricas.</p>
  </div>
  <div class="card">
    <div class="meta">Cuesta</div>
    <p>Menor estandarización práctica, tooling desigual y preguntas operativas que siguen importando.</p>
  </div>
</div>

---

<!-- _class: before-after grid-lines-small -->

<div class="kicker">Comparación</div>

# BDOO, ORM y documentos

<div class="compare">
  <div class="panel">
    <div class="meta">Lo que intentaban resolver</div>
    <p>Persistir estructuras cercanas al modelo del software sin traducir demasiado.</p>
  </div>
  <div class="panel">
    <div class="meta">Lo que hoy observamos</div>
    <p>ORMS, documentos y modelos alternativos resuelven partes del problema con tradeoffs distintos.</p>
  </div>
</div>

---

<!-- _class: grid-lines -->

<div class="kicker">Conexión con el curso</div>

# Nada de esto elimina concurrencia, recuperación o performance

<div class="cards">
  <div class="card"><div class="meta">Persistencia</div><p>Sigue necesitando criterios de integridad.</p></div>
  <div class="card"><div class="meta">Concurrencia</div><p>Sigue necesitando orden y control.</p></div>
  <div class="card"><div class="meta">Operación</div><p>Sigue necesitando observabilidad y tradeoffs claros.</p></div>
</div>

---

<!-- _class: section grid-dots -->

<div class="kicker">Checkpoint</div>

# Media sesión

## Ya cerramos el marco histórico y conceptual. Ahora toca traducirlo a decisiones prácticas y al cierre del curso.

---

<!-- _class: workflow grid-lines-small -->

<div class="kicker">Proyecto final</div>

# Checkpoint de cierre de proyecto

<ul class="agenda-list">
  <li>Elegir el modelo correcto para el problema</li>
  <li>Justificar por qué no elegiste otro</li>
  <li>Cerrar evidencia, README y tradeoffs</li>
  <li>Preparar revisión o defensa breve</li>
</ul>

---

<!-- _class: section grid-dots -->

<div class="kicker">Transición</div>

# Ahora vamos a observarlo en contexto técnico

## No para implementar una OODB real, sí para comparar modelos y cerrar el curso con criterio.

---

<!-- _class: demo grid-lines-small -->

<div class="kicker">Demo conceptual</div>

# Qué vamos a observar

<div class="terminal">
$ TODO: comparar caso simple entre relacional y modelo alternativo
<br />
$ TODO: identificar mismatch o fricción
<br />
$ TODO: discutir tradeoff de persistencia
</div>

---

<!-- _class: workflow grid-lines -->

<div class="kicker">Observación</div>

# Qué queremos notar

<ul class="checklist-list">
  <li>Qué gana cada modelo</li>
  <li>Qué problema no desaparece</li>
  <li>Qué costo trae la elección</li>
  <li>Qué criterio usaríamos hoy</li>
</ul>

---

<!-- _class: section grid-dots -->

<div class="kicker">Trabajo fuera de sesión</div>

# La comparación detallada seguirá en VS Code y en la revisión final

## El cierre del curso continúa en el proyecto, la evidencia y la defensa breve cuando aplique.

---

<!-- _class: exercise grid-lines -->

<div class="kicker">Ejercicio</div>

# Defender el modelo elegido para un caso pequeño

<div class="cards">
  <div class="card">
    <div class="meta">Objetivo</div>
    <p>Comparar modelos y justificar cuál usarías hoy para un caso concreto.</p>
  </div>
  <div class="card">
    <div class="meta">Entrega</div>
    <p>Comparación, elección, evidencia y tradeoff principal.</p>
  </div>
</div>

---

<!-- _class: evidence grid-lines-small -->

<div class="kicker">Evidencia</div>

# Qué evidencia esperaremos

<ul class="checklist-list">
  <li>Caso de uso claro</li>
  <li>Comparación entre modelos</li>
  <li>Ventajas y límites</li>
  <li>Justificación final</li>
</ul>

---

<!-- _class: success grid-dots -->

<div class="kicker">Cierre</div>

# El curso termina cuando puedes justificar decisiones, no cuando puedes repetir nombres de tecnologías.

---

<!-- _class: recap grid-dots -->

<div class="kicker">Recap</div>

# Qué nos llevamos hoy

<ul>
  <li>BDOO importa como lente conceptual</li>
  <li>Persistir objetos sigue siendo un problema de diseño</li>
  <li>Modelos modernos heredan parte de esa discusión</li>
  <li>El criterio técnico conecta todo el curso</li>
</ul>

---

<!-- _class: next grid-lines -->

<div class="kicker">Cierre</div>

# Después de esta clase

> Lo importante ya no es “cubrir temas”, sino demostrar criterio con evidencia.
