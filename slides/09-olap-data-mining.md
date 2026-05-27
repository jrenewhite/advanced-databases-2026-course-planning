---
marp: true
theme: advanced-db-dark
paginate: true
---

<!-- _class: hero grid-lines -->

<div class="kicker">Clase 09</div>
<div class="meta">Señales para decidir</div>

# OLAP and Data Mining

## Consultas analíticas, indicadores y patrones sin vender magia

---

<!-- _class: agenda grid-lines -->

<div class="kicker">Ruta</div>

# Agenda de sesión

<ul class="agenda-list">
  <li>Qué hace OLAP en la práctica</li>
  <li>Qué sí y qué no promete Data Mining</li>
  <li>Checkpoint de media sesión</li>
  <li>Observación, assignment y evidencia</li>
</ul>

---

<!-- _class: guide-question grid-dots -->

<div class="kicker">Pregunta guía</div>

# ¿Cómo pasamos de almacenar datos a encontrar señales útiles sin inventar conclusiones?

> Analizar no es solo agregar; también es saber qué lectura es válida y cuál es una sobreinterpretación.

---

<!-- _class: real-world grid-lines -->

<div class="kicker">Problema real</div>

# El dashboard muestra números, pero nadie sabe qué significan

<div class="cards">
  <div class="card">
    <div class="meta">Síntoma</div>
    <p>Hay indicadores, pero no está claro qué pregunta responden ni qué limitación tienen.</p>
  </div>
  <div class="card">
    <div class="meta">Impacto</div>
    <p>Se confunde agregación con insight y patrón con causalidad.</p>
  </div>
</div>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Objetivo</div>

# Qué debería quedar claro hoy

<ul class="checklist-list">
  <li>Qué hace una consulta OLAP</li>
  <li>Qué significa agregar por dimensión</li>
  <li>Qué tipo de patrón puede sugerir Data Mining</li>
  <li>Qué límites debe reconocer la interpretación</li>
</ul>

---

<!-- _class: grid-lines-small -->

<div class="kicker">Acrónimos y conceptos</div>

# Vocabulario mínimo de la sesión

<div class="cards">
  <div class="card"><div class="meta">OLAP</div><p>Análisis multidimensional y agregado.</p></div>
  <div class="card"><div class="meta">KPI</div><p>Indicador clave para observar desempeño.</p></div>
  <div class="card"><div class="meta">Slice</div><p>Recorte por dimensión o criterio.</p></div>
  <div class="card"><div class="meta">Pattern</div><p>Señal observada, no verdad absoluta.</p></div>
</div>

---

<!-- _class: statement grid-lines -->

<div class="kicker">Idea central</div>

# El análisis útil no sale de “tener muchos datos”, sino de formular buenas preguntas y reconocer límites de interpretación.

---

<!-- _class: two-columns grid-lines -->

<div class="kicker">Concepto vs realidad</div>

# OLAP vs Data Mining

<div class="col">
  <div class="meta">OLAP</div>
  <p>Explora, agrega, compara y navega dimensiones de un modelo ya estructurado.</p>
</div>

<div class="col">
  <div class="meta">Data Mining</div>
  <p>Busca patrones o segmentos, pero exige cautela para no vender hallazgos débiles como verdad.</p>
</div>

---

<!-- _class: tradeoff grid-lines -->

<div class="kicker">Tradeoff</div>

# Más agregación simplifica lectura, pero puede esconder contexto

<div class="cards">
  <div class="card">
    <div class="meta">Gana</div>
    <p>Resumen rápido, comparaciones útiles e indicadores accionables.</p>
  </div>
  <div class="card">
    <div class="meta">Cuesta</div>
    <p>Pérdida de detalle, riesgo de interpretación superficial y falsos patrones narrativos.</p>
  </div>
</div>

---

<!-- _class: grid-lines -->

<div class="kicker">Mental model</div>

# Qué debe responder una consulta analítica

<ul class="checklist-list">
  <li>Qué dimensión compara</li>
  <li>Qué medida resume</li>
  <li>Qué periodo o segmento observa</li>
  <li>Qué límite interpretativo mantiene</li>
</ul>

---

<!-- _class: section grid-dots -->

<div class="kicker">Checkpoint</div>

# Media sesión

## Ya tenemos el marco para leer análisis y patrones. Ahora toca observar qué evidencia vuelve útil esa lectura.

---

<!-- _class: section grid-dots -->

<div class="kicker">Transición</div>

# Ahora vamos a observarlo en contexto técnico

## La meta es formular una pregunta mejor, no fingir que una agregación ya explica el negocio.

---

<!-- _class: demo grid-lines-small -->

<div class="kicker">Demo conceptual</div>

# Qué vamos a observar

<div class="terminal">
$ TODO: consulta agregada por dimensión
<br />
$ TODO: recorte por periodo o segmento
<br />
$ TODO: interpretación breve y límite detectado
</div>

---

<!-- _class: demo grid-lines -->

<div class="kicker">Observación</div>

# Qué queremos notar

<ul class="checklist-list">
  <li>Qué pregunta responde la consulta</li>
  <li>Qué dimensión ordena la lectura</li>
  <li>Qué patrón parece emerger</li>
  <li>Qué conclusión todavía no podemos afirmar</li>
</ul>

---

<!-- _class: section grid-dots -->

<div class="kicker">Trabajo fuera de sesión</div>

# El análisis completo seguirá en VS Code y en el assignment

## Aquí cerramos la lógica de lectura; fuera del deck se construye la consulta y la evidencia interpretada.

---

<!-- _class: exercise grid-lines -->

<div class="kicker">Ejercicio</div>

# Resolver una pregunta de análisis y discutir su límite

<div class="cards">
  <div class="card">
    <div class="meta">Objetivo</div>
    <p>Formular una pregunta útil y responderla con consulta agregada o segmentación simple.</p>
  </div>
  <div class="card">
    <div class="meta">Entrega</div>
    <p>Pregunta, consulta, resultado, interpretación y una limitación explícita.</p>
  </div>
</div>

---

<!-- _class: evidence grid-lines-small -->

<div class="kicker">Evidencia</div>

# Qué evidencia esperaremos

<ul class="checklist-list">
  <li>Pregunta analítica clara</li>
  <li>Consulta o recorte usado</li>
  <li>Resultado observado</li>
  <li>Interpretación y riesgo</li>
</ul>

---

<!-- _class: recap grid-dots -->

<div class="kicker">Recap</div>

# Qué nos llevamos hoy

<ul>
  <li>OLAP organiza preguntas multidimensionales</li>
  <li>Data Mining sugiere patrones, no certezas automáticas</li>
  <li>Una buena lectura reconoce sus límites</li>
  <li>El insight serio necesita evidencia y contexto</li>
</ul>

---

<!-- _class: next grid-lines -->

<div class="kicker">Siguiente clase</div>

# BDOO y modelos modernos

> Cerramos el curso mirando cómo el mundo intentó persistir objetos y qué quedó vigente hoy.
