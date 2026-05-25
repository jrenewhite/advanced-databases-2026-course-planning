# 02_SLIDE_RULES.md — Reglas para presentaciones Marp

## Status

Draft inicial controlado por el instructor.

Este documento define las reglas para crear, revisar y mantener las presentaciones del curso **Sistemas Avanzados de Bases de Datos** de **UniVO**.

Debe leerse después de:

```txt
00-course-planning/docs/ai/00_COURSEWARE_OBJECTIVE.md
00-course-planning/docs/ai/01_AI_COLLABORATION.md
````

---

## Purpose

El propósito de este documento es asegurar que las presentaciones del curso sean claras, visuales, ligeras y útiles para explicar conceptos avanzados de bases de datos sin saturar a los alumnos.

Las slides deben apoyar la explicación del instructor, no reemplazarla.

Las presentaciones deben sentirse como parte de un workshop técnico o engineering walkthrough, no como un documento académico proyectado en pantalla.

---

## 1. Principio central

La regla principal es:

> Una slide debe ayudar a entender una idea, no contener toda la explicación.

Las slides no son apuntes completos, libro de texto ni guion literal de clase.

La explicación profunda ocurre mediante:

* voz del instructor
* diagramas
* demos
* discusión
* ejercicios
* ejemplos reales
* production tales anonimizados

---

## 2. Formato obligatorio

Las presentaciones deben escribirse en:

```txt
Markdown + Marp
```

Cada clase debe tener, como mínimo:

```txt
slides/session.md
```

Opcionalmente puede tener:

```txt
slides/session.pdf
slides/session.html
slides/assets/
```

Los archivos exportados (`.pdf`, `.html`) pueden generarse después, pero la fuente principal siempre debe ser Markdown.

---

## 3. Idioma

Las slides deben estar principalmente en español.

Se permiten términos técnicos en inglés cuando sean naturales para el tema, por ejemplo:

* query
* query plan
* index
* deadlock
* rollback
* commit
* connection pool
* warehouse
* data mart
* tradeoff
* production incident
* live demo

Evitar traducciones forzadas si hacen menos claro el concepto.

---

## 4. Estilo general

Preferir:

* poco texto
* frases cortas
* diagramas grandes
* una idea principal por slide
* ejemplos concretos
* contraste visual claro
* ritmo dinámico
* humor técnico moderado
* analogías simples
* transiciones claras entre teoría y práctica

Evitar:

* párrafos largos
* listas enormes
* diapositivas densas
* tablas excesivamente grandes
* capturas ilegibles
* demasiados conceptos en una sola slide
* definiciones académicas sin aplicación
* saturar con código
* explicar todo en la slide

---

## 5. Densidad máxima recomendada

Reglas prácticas:

* máximo 1 idea principal por slide
* máximo 5 bullets por slide
* máximo 7 palabras por bullet cuando sea posible
* máximo 1 bloque de código corto por slide
* máximo 1 diagrama principal por slide
* evitar más de 40–50 palabras por slide salvo excepciones justificadas

Si una slide necesita mucho texto, dividirla.

Si una tabla no se lee desde lejos, no debe ir en la slide.

---

## 6. Estructura sugerida por sesión

Una presentación de 2 horas debe ser ligera.

Rango recomendado:

```txt
15–30 slides
```

No crear decks de 60+ slides salvo que muchas sean visuales, transiciones o pasos muy breves de demo.

Estructura sugerida:

1. Título
2. Objetivo de la sesión
3. Problema real / motivación
4. Concepto central
5. Diagrama o visualización
6. Ejemplo simple
7. Production tale anonimizado
8. Demo setup
9. Demo walkthrough
10. Ejercicio
11. Evidencia esperada
12. Recap
13. Siguientes pasos

---

## 7. Tipos de slides permitidas

### Concept slide

Explica una idea de forma breve.

Debe responder:

* ¿qué es?
* ¿por qué importa?
* ¿cuándo aparece?

### Visual slide

Usa diagrama, flujo, timeline, tabla simple o comparación.

Debe reducir carga cognitiva.

### Demo slide

Prepara una actividad práctica.

Debe indicar:

* qué se va a observar
* qué archivo o comando se usará
* qué resultado esperamos analizar

### Exercise slide

Presenta una actividad para estudiantes.

Debe incluir:

* objetivo
* instrucciones breves
* evidencia esperada

### Recap slide

Resume aprendizajes clave.

Debe ser breve y accionable.

### Meme / humor slide

Permitida con moderación.

Debe reforzar el concepto, no sustituirlo.

---

## 8. Uso de código en slides

El código en slides debe ser mínimo.

Permitido:

```sql
EXPLAIN ANALYZE
SELECT * FROM orders WHERE customer_id = 42;
```

Evitar:

* archivos completos
* queries enormes
* bloques largos imposibles de leer
* código que requiera scroll mental
* snippets que deberían vivir en `demo/`

Regla:

> Si el código es para ejecutarse, debe vivir en el repo.
> Si el código es para entender una idea, puede aparecer en la slide.

---

## 9. Uso de diagramas

Preferir diagramas para explicar:

* OLTP vs OLAP
* flujo de transacciones
* locks
* MVCC
* deadlocks
* índices B-tree
* query planning
* connection pooling
* cubos OLAP
* star schema
* data warehouse pipeline
* ORM mapping
* modelos alternativos

Herramientas aceptadas:

* Mermaid
* Excalidraw
* SVG
* diagrams.net
* imágenes generadas por el instructor
* Motion Canvas exports
* HTML/CSS visual cuando aplique

Los diagramas deben ser originales o tener licencia compatible.

---

## 10. Uso de memes

Los memes están permitidos.

Objetivo:

* romper tensión
* mejorar recordación
* conectar con experiencia real
* reforzar un concepto técnico
* marcar transiciones

Reglas:

* usar con moderación
* no usar humor ofensivo
* no usar referencias demasiado oscuras
* no usar memes como relleno
* no usar memes que distraigan del aprendizaje
* no basar la clase en memes

Frecuencia sugerida:

```txt
1 meme cada 7–10 slides como máximo
```

O menos, si la sesión es muy técnica.

---

## 11. Referencias visuales

El material en:

```txt
00-course-planning/references
```

es únicamente inspiración interna.

Puede usarse para observar:

* ritmo visual
* nivel de concisión
* composición
* pacing
* uso de humor técnico
* estructura narrativa
* cómo explicar algo complejo rápido

No debe copiarse directamente.

La IA no debe copiar:

* imágenes
* screenshots
* transcripciones
* frases exactas
* layouts idénticos
* secuencias completas
* marcas visuales distintivas de terceros

Las presentaciones finales deben ser originales.

---

## 12. Uso de referencias tipo Fireship y CodeAesthetic

Las referencias tipo videos de Fireship y CodeAesthetic pueden inspirar:

* energía
* brevedad
* ritmo
* uso de analogías
* humor técnico
* visualizaciones rápidas

Pero no deben copiar:

* guion
* capturas
* audio
* imágenes
* frases exactas
* estructura completa del video
* diseño visual identificable

El objetivo no es hacer una copia de Fireship o CodeAesthetic.

El objetivo es lograr slides claras, modernas, visuales y memorables con identidad propia.

---

## 13. Animaciones

Las animaciones son opcionales para complementar los slides marp.

Solo deben usarse cuando aporten comprensión.

Buenos candidatos:

* MVCC
* locks
* deadlocks
* índices
* query planner
* connection pooling
* OLAP cubes
* warehouse pipelines

Reglas:

* la clase debe poder explicarse aunque falle la animación
* debe existir fallback estático
* no depender de una animación compleja para enseñar el concepto central
* no crear animaciones solo por estética
* no usar animaciones que consuman demasiado tiempo de preparación sin valor pedagógico claro
* usar remotion o hyperframes para las animaciones, pero antes de hacerlas,se debe crear el storyboard textual para diseñar la animación de tal forma que se pueda hacer uso de la integración de codex con esas herramientas (usar referencias de fireship y codeaesthtetic).

---

## 14. Estructura Marp sugerida

Cada `slides/session.md` debe iniciar con frontmatter Marp.

Ejemplo base:

```md
---
marp: true
theme: default
paginate: true
---

# Título de la sesión

Sistemas Avanzados de Bases de Datos  
UniVO

---

# Objetivo

Al final de esta sesión podrás...

---
```

Si se usa un theme custom, debe vivir en una ruta clara y documentada. 
Para el tema, se debe considerar las referencias de 00-course-planning/references/slides como base del tema y lenguaje visual base, pero con la intención de poner diagramas, imagenes y texto parecido a 00-course-planning/references/fireship

---

## 15. Naming de slides y assets

Estructura recomendada:

```txt
slides/
├── session.md
├── assets/
│   ├── diagram-oltp-vs-olap.svg
│   ├── mvcc-flow.png
│   └── meme-query-plan.png
└── exports/
    ├── session.pdf
    └── session.html
```

Si los assets se comparten con demo o README, pueden vivir en:

```txt
assets/
```

Pero debe evitarse duplicación innecesaria.

---

## 16. Relación slides-demo

Las slides deben conectar explícitamente con la demo.

Ejemplo:

```md
# Demo

Vamos a observar:

1. query lenta
2. plan de ejecución
3. índice propuesto
4. comparación antes/después
```

La lógica detallada debe vivir en:

```txt
demo/
```

No en la slide.

---

## 17. Relación slides-evaluación

Cuando una slide introduce un ejercicio, debe dejar claro:

* qué debe hacer el alumno
* qué evidencia debe producir
* cómo se revisará
* qué criterio profesional debe demostrar

Ejemplo:

```md
# Evidencia esperada

- Query original
- `EXPLAIN ANALYZE` antes
- Cambio realizado
- `EXPLAIN ANALYZE` después
- Tradeoff identificado
```

---

## 18. Evitar dependencia de IA

Las slides pueden mencionar IA cuando sea relevante, pero no deben convertirla en el centro.

Cuando se use IA como parte de una actividad, la slide debe reforzar:

> Puedes usar IA, pero debes validar y explicar.

Ejemplo de slide:

```md
# IA permitida, criterio obligatorio

Puedes pedir ayuda para proponer un índice.

Pero debes demostrar:

- por qué ese índice
- qué cambió en el query plan
- qué tradeoff introduce
```

---

## 19. Buenas slides

Una buena slide:

* tiene una idea clara
* se entiende en pocos segundos
* ayuda a explicar, no sustituye la explicación
* conecta con una demo o ejemplo
* usa visuales cuando aportan
* reduce carga cognitiva
* facilita preguntas

Ejemplo conceptual:

```md
# OLTP vs OLAP

OLTP pregunta:

> ¿Qué acaba de pasar?

OLAP pregunta:

> ¿Qué patrón estamos viendo?
```

---

## 20. Malas slides

Evitar slides que:

* tienen 12 bullets
* parecen documento Word
* contienen definiciones largas
* incluyen tablas ilegibles
* muestran queries enormes
* tienen demasiados colores
* usan memes sin conexión
* mezclan 4 conceptos
* no conectan con práctica
* no dejan claro qué importa

---

## 21. Checklist antes de aceptar una deck

Antes de aceptar una presentación, revisar:

* ¿Está en Marp?
* ¿Tiene objetivo claro?
* ¿Evita walls of text?
* ¿Tiene ritmo?
* ¿Incluye visuales útiles?
* ¿Conecta con demo o ejercicio?
* ¿Incluye recap?
* ¿Respeta el temario?
* ¿No copia referencias externas?
* ¿Es viable para 2 horas?
* ¿No sobreexplica?
* ¿No depende de animaciones frágiles?
* ¿Distingue entre material público e instructor?

---

## 22. Reglas para Codex/IA

Cuando Codex genere slides:

* debe leer primero `00_COURSEWARE_OBJECTIVE.md`
* debe leer primero `01_AI_COLLABORATION.md`
* debe seguir este documento
* debe producir primero un mini-plan si la deck es nueva
* no debe generar decks muy largos sin pedir aprobación
* no debe copiar referencias visuales directamente
* no debe agregar imágenes de terceros sin permiso
* no debe poner soluciones completas en slides student-facing sin autorización
* debe mantener estilo visual simple
* debe incluir notas TODO donde falte criterio del instructor
* debe evitar inventar resultados de demos

---

## TODO

* Definir tema visual Marp custom basado en las referencias
* Definir tipografías permitidas (poen source)
* Definir paleta visual (modo dark y dark de vscode para codigo)
* Crear template base para `slides/session.md`.
* Crear ejemplo de slide buena vs mala.
* Definir cuando exportar PDF y HTML
