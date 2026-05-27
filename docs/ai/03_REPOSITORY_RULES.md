# 03_REPOSITORY_RULES.md — Reglas de repositorios y estructura

## Status

Draft inicial controlado por el instructor.

Este documento define las reglas para organizar, nombrar, mantener y publicar los repositorios/carpetas del curso **Sistemas Avanzados de Bases de Datos**.

Debe leerse después de:

```txt
00-course-planning/docs/ai/00_COURSEWARE_OBJECTIVE.md
00-course-planning/docs/ai/01_AI_COLLABORATION.md
00-course-planning/docs/ai/02_SLIDE_RULES.md
````

---

## Purpose

El propósito de este documento es mantener una estructura consistente, simple y reusable para el material del curso.

La organización debe facilitar:

* preparación rápida del instructor
* seguimiento por parte de alumnos
* uso de Codex/ChatGPT sin ambigüedad
* demos reproducibles
* publicación gradual después de cada clase
* separación entre material público y material del instructor
* reutilización futura del contenido

---

## 1. Principio central

La regla principal es:

> Cada clase debe ser autocontenida, reproducible y fácil de entender.

Un alumno debe poder entrar a una carpeta `class-*`, leer el `README.md`, levantar el entorno si aplica y entender qué se verá en esa sesión.

El instructor debe poder preparar, ejecutar y recuperar demos con fricción mínima.

---

## 2. Estructura raíz del curso

La estructura local base del curso es:

```txt
advanced-databases-2026/
├── 00-course-planning/
├── class-01-course-intro-oltp-olap/
├── class-02-logical-design-domain-rules/
├── class-03-transactions-concurrency/
├── class-04-indexes-query-performance/
├── class-05-views-procedures-triggers/
├── class-06-security-roles-pooling/
├── class-07-multidimensional-modeling/
├── class-08-data-warehouse-datamart/
├── class-09-olap-data-mining/
├── class-10-object-oriented-databases-modern-models/
├── assignment-XX-topic-name/
└── final-project-<student-or-team>/
```

`00-course-planning/` contiene planeación, guardrails, referencias y documentos transversales.

Cada `class-*` representa una sesión/módulo de clase y debe manejarse como repositorio independiente.

Los repos `assignment-*` se reservan para tareas evaluables fuera de clase.

Los repos de proyecto final pertenecen al alumno/equipo y se comparten con el instructor para revisión.

---

## 3. Reglas para `00-course-planning`

`00-course-planning/` debe contener documentación transversal, no demos completas de clase.

Estructura esperada:

```txt
00-course-planning/
├── docs/
│   ├── ai/
│   └── planning/
└── references/
```

### `docs/ai/`

Contiene reglas y guardrails para IA.

Ejemplos:

```txt
00_COURSEWARE_OBJECTIVE.md
01_AI_COLLABORATION.md
02_SLIDE_RULES.md
03_REPOSITORY_RULES.md
04_DEMO_GUIDELINES.md
05_EVALUATION_GUIDELINES.md
```

### `docs/planning/`

Contiene planeación académica y operativa.

Nombres recomendados:

```txt
00_COURSE_PLAN.md
01_SYLLABUS_COVERAGE_MATRIX.md
02_CLASS_REPOSITORY_MAP.md
```

### `references/`

Contiene referencias privadas de estilo, ritmo visual o inspiración.

No debe tratarse como carpeta de assets públicos.

---

## 4. Reglas para referencias

El material en:

```txt
00-course-planning/references/
```

es únicamente referencia interna.

Puede usarse para inspirar:

* estilo visual
* ritmo
* densidad de texto
* estructura narrativa
* uso moderado de humor técnico
* claridad de explicación

No debe copiarse directamente a materiales públicos.

No redistribuir:

* videos de terceros
* capturas de terceros
* transcripciones
* imágenes
* layouts idénticos
* frases exactas
* marcas visuales distintivas

Si Codex/IA lee material en `references/`, debe tratarlo como inspiración, no como fuente reutilizable.

---

## 5. Estructura estándar de cada clase

Los repos `class-*` son para material de sesión:

* slides
* demos
* ejercicios guiados
* notas
* recursos de clase

No deben usarse para tareas evaluables fuera de clase ni para alojar el proyecto final.

Cada carpeta `class-*` debe seguir esta estructura base:

```txt
class-XX-topic-name/
├── animations/
├── assets/
├── demo/
│   └── init.sql
├── .devcontainer/
│   └── devcontainer.json
├── diagrams/
├── docker-compose.yml
├── exercises/
│   └── README.md
├── .github/
│   └── workflows/
├── .gitignore
├── Makefile
├── notes/
│   └── instructor.md
├── README.md
├── scripts/
└── slides/
    └── session.md
```

No todas las carpetas necesitan estar llenas desde el inicio.

Es válido mantener carpetas vacías si forman parte de la convención.

---

## 6. Propósito de cada carpeta

### `slides/`

En cada repo `class-*`, `slides/` debe funcionar como destino de exports student-facing.

Archivos esperados cuando existan:

```txt
slides/session.html
slides/session.pdf
```

La fuente editable en Marp debe vivir centralizada en:

```txt
00-course-planning/slides/NN-topic-name.md
```

### `demo/`

Contiene material ejecutable o reproducible de la demo.

Puede incluir:

* SQL
* seed data
* scripts
* queries
* archivos de apoyo

Debe evitar mezclarse con solución final si es material student-facing.

### `exercises/`

Contiene instrucciones para actividades de estudiantes.

Debe incluir:

* objetivo
* instrucciones
* evidencia esperada
* criterios de revisión cuando aplique

### `notes/`

Contiene notas del instructor.

Archivo principal:

```txt
notes/instructor.md
```

Puede incluir:

* flujo sugerido
* respuestas esperadas
* fallback
* preguntas para discusión
* riesgos de demo
* tiempos estimados

Este contenido no necesariamente debe publicarse.

### `assets/`

Contiene assets propios del curso.

Ejemplos:

* imágenes originales
* SVG propios
* exports de diagramas propios
* screenshots generados por demos propias

No debe contener material de terceros sin licencia compatible.

### `animations/`

Contiene animaciones propias o código fuente para generarlas.

Debe usarse solo si aporta valor pedagógico.

### `diagrams/`

Contiene diagramas fuente o exportados.

Ejemplos:

* Mermaid
* Excalidraw
* SVG
* diagrams.net

### `scripts/`

Contiene scripts de apoyo.

Deben ser simples, claros y seguros.

### `.devcontainer/`

Contiene configuración para Dev Containers.

Debe reducir fricción, no introducir complejidad innecesaria.

### `.github/workflows/`

Puede contener workflows mínimos si son útiles.

No agregar CI/CD complejo sin necesidad pedagógica.

---

## 7. README por clase

Cada clase debe tener un `README.md` claro.

Debe incluir, como mínimo:

* título de la clase
* objetivo
* temas cubiertos
* relación con el temario oficial
* estructura de la sesión
* quick start
* comandos útiles
* archivos importantes
* evidencia esperada
* notas de uso de IA si aplica

Ejemplo de secciones:

```md
# Class 04 — Indexes and Query Performance

## Objetivo

## Temas cubiertos

## Quick Start

## Estructura de la sesión

## Demo

## Ejercicio

## Evidencia esperada

## Uso de IA

## Troubleshooting
```

---

## 8. Reglas de nombres

Usar nombres en inglés para carpetas técnicas y nombres de clase, manteniendo contenido en español.

Formato de clase:

```txt
class-XX-topic-name
```

Reglas:

* usar minúsculas
* usar guiones
* evitar espacios
* evitar acentos
* evitar nombres demasiado largos
* incluir número de clase con dos dígitos

Ejemplos válidos:

```txt
class-03-transactions-concurrency
class-04-indexes-query-performance
class-08-data-warehouse-datamart
```

Ejemplos no deseados:

```txt
Clase 3 - Transacciones
class-3-transacciones
class-04-indexes-and-query-performance-and-optimization-and-plans
```

---

## 9. Reglas para ramas

Cada repo `class-*` debe usar una estrategia de ramas pedagógica.

### `main`

Rama pública o student-facing.

Debe contener:

* setup inicial
* slides base
* README
* ejercicios
* datos necesarios
* instrucciones
* TODOs razonables

No debe contener inicialmente:

* soluciones completas
* respuestas esperadas
* notas privadas
* shortcuts del instructor
* spoilers

### `instructor`

Rama privada/protegida del instructor.

Puede contener:

* soluciones
* notas privadas
* scripts de fallback
* respuestas esperadas
* demos completas
* animaciones finales
* troubleshooting
* preguntas de defensa
* criterios internos de revisión

### `live`

Rama opcional para clase en vivo.

Puede usarse para:

* construir ejemplos durante la sesión
* hacer commits incrementales
* simular flujo real
* permitir que alumnos sigan el proceso

---

## 10. Reglas para repos `assignment-*`

Los repos `assignment-*` son separados de `class-*`.

Su propósito es alojar entregables evaluables fuera de clase.

Reglas iniciales:

* todos los alumnos parten de la misma base
* cada alumno trabaja en su propia rama dentro del repo de la tarea
* no mezclar material de sesión dentro de `assignment-*` salvo lo estrictamente necesario como contexto
* no usar `assignment-*` para publicar notas privadas del instructor
* cada repo debe tener `README.md` con instrucciones, evidencia esperada y criterios de aceptación

La convención exacta de nombres de ramas por alumno sigue pendiente y debe definirse en `03_INSTRUCTOR_DECISIONS.md`.

---

## 11. Reglas para repos de proyecto final

El proyecto final no debe vivir dentro de `class-*` ni dentro de `assignment-*`.

Debe vivir en un repo separado creado o compartido por el alumno/equipo.

Reglas iniciales:

* el repo es propiedad del alumno/equipo
* el repo debe compartirse con el instructor o entregarse mediante enlace, según se defina
* debe incluir `README.md` obligatorio
* debe documentar evidencia técnica
* debe documentar uso de IA

La decisión sobre si el proyecto será individual o por equipo sigue pendiente y no debe asumirse aquí.

---

## 12. Reglas para commits

Los commits deben ser pequeños y significativos.

Preferir commits que narren el aprendizaje:

```txt
initial class setup
add baseline schema
seed sample data
reproduce slow query
inspect query plan
add targeted index
compare performance before and after
document tradeoffs
```

Evitar commits gigantes tipo:

```txt
update
changes
final
misc
stuff
```

Los commits pueden ser parte de la enseñanza.

---

## 13. Publicación de contenido

El contenido puede permanecer privado antes de impartir la clase.

Después de la clase puede publicarse:

* slides revisadas
* demo final
* ejercicios
* notas públicas
* animaciones propias
* solución parcial o completa, si no afecta evaluación

Antes de publicar revisar:

* no incluir notas privadas
* no incluir contenido con derechos de terceros
* no incluir respuestas que invaliden entregas pendientes
* no incluir credenciales
* no incluir datos personales
* no incluir material institucional sensible

---

## 14. Separación student-facing / instructor-facing

### Student-facing

Contenido visible para alumnos:

* `README.md`
* `slides/session.html`
* `slides/session.pdf`
* `demo/` inicial
* `exercises/README.md`
* assets necesarios
* scripts seguros
* instrucciones

### Instructor-facing

Contenido privado o rama `instructor`:

* `notes/instructor.md`
* soluciones
* resultados esperados
* scripts de fallback
* respuestas de ejercicios
* rúbricas internas
* observaciones sobre alumnos
* shortcuts para demo

No mezclar contenido privado en material público sin revisión.

---

## 15. Regla para soluciones

No colocar soluciones completas en `main` antes de la clase o mientras la actividad esté vigente.

Opciones aceptables:

* mantener soluciones en rama `instructor`
* liberar soluciones después de clase
* liberar solución parcial
* liberar solo explicación conceptual
* liberar solución completa después de evaluación

---

## 16. Reglas para Docker

Cada clase que use base de datos debe incluir `docker-compose.yml`.

Debe ser simple y reproducible.

Preferir:

* PostgreSQL 16
* nombres de servicio claros
* variables simples
* volumen nombrado
* seed script en `demo/init.sql`

Evitar:

* múltiples servicios innecesarios
* puertos aleatorios sin documentar
* dependencias externas
* secretos reales
* configuraciones frágiles

La guía detallada vive en:

```txt
00-course-planning/docs/ai/04_DEMO_GUIDELINES.md
```

---

## 17. Reglas para Dev Containers

Los Dev Containers deben facilitar la clase, no complicarla.

Pueden incluir:

* Marp CLI
* cliente PostgreSQL
* Docker CLI
* extensiones útiles de VS Code
* herramientas Markdown

No deben incluir tooling pesado salvo que sea necesario para la sesión.

---

## 18. Reglas para GitHub Projects

GitHub Projects puede usarse como simulación ligera de flujo real de ingeniería.

Su uso obligatorio para alumnos/equipos sigue pendiente.

Issues sugeridos por clase deben ser:

* concretos
* evaluables
* conectados al tema
* con evidencia clara
* razonablemente pequeños

Ejemplos:

```txt
Investigate slow query using EXPLAIN ANALYZE
Create domain constraints for invalid data
Diagnose a transaction conflict
Model a star schema for reporting
Compare OLTP and OLAP query shapes
```

Evitar issues demasiado vagos:

```txt
Learn indexes
Research databases
Do project
```

---

## 19. Reglas para Codex/IA al modificar estructura

Cuando Codex modifique repos/carpetas:

* debe leer primero los guardrails
* debe respetar estructura existente
* debe reportar archivos que planea cambiar
* no debe modificar carpetas no solicitadas
* no debe borrar archivos sin autorización
* no debe sobrescribir material existente sin permiso
* debe crear mini-plan para cambios grandes
* debe mantener nombres consistentes
* debe evitar overengineering

---

## 20. Checklist antes de aceptar cambios estructurales

Antes de aceptar cambios propuestos por IA, revisar:

* ¿Respeta nombres existentes?
* ¿Tocó solo archivos solicitados?
* ¿Mantuvo separación student/instructor?
* ¿No agregó dependencias innecesarias?
* ¿No agregó contenido de terceros?
* ¿No generó soluciones en lugar público?
* ¿El setup sigue siendo simple?
* ¿El README es claro?
* ¿La demo se puede correr?
* ¿La estructura sigue siendo reusable?

---

## 21. Estado actual esperado

La estructura actual esperada incluye:

```txt
00-course-planning/
class-01-course-intro-oltp-olap/
class-02-logical-design-domain-rules/
class-03-transactions-concurrency/
class-04-indexes-query-performance/
class-05-views-procedures-triggers/
class-06-security-roles-pooling/
class-07-multidimensional-modeling/
class-08-data-warehouse-datamart/
class-09-olap-data-mining/
class-10-object-oriented-databases-modern-models/
assignment-XX-topic-name/
final-project-<student-or-team>/
```

Si una tarea futura detecta desviaciones, debe reportarlas antes de corregirlas.

---

## TODO

* Definir si existirá un template repo formal.
* Definir cuándo crear rama `instructor`.
* Definir cuándo publicar repos públicamente.
* Definir convención para tags/releases por clase.
* Definir convención exacta de ramas para alumnos en repos `assignment-*`.
