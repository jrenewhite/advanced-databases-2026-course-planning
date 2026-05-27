# 02_CLASS_REPOSITORY_MAP.md — Mapa de carpetas, clases y entregables

## Status

Draft inicial controlado por el instructor.

Este documento mapea cada carpeta `class-*` del curso **Sistemas Avanzados de Bases de Datos** contra su sesión, tema principal, entregables esperados y relación con demos/evaluación.

Debe leerse junto con:

```txt
00-course-planning/docs/planning/00_COURSE_PLAN.md
00-course-planning/docs/planning/01_SYLLABUS_COVERAGE_MATRIX.md
````

---

## Purpose

El propósito de este documento es mantener una visión operativa de los materiales de clase.

Sirve para:

* saber qué debe contener cada carpeta
* guiar a Codex/ChatGPT al generar contenido
* mantener consistencia entre clases
* evitar que una sesión se sobrecargue
* distinguir entregables student-facing e instructor-facing
* facilitar publicación gradual después de cada clase

---

## 1. Estructura raíz esperada

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
└── class-10-object-oriented-databases-modern-models/
```

---

## 2. Estructura estándar por carpeta de clase

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
    ├── session.html
    └── session.pdf
```

No todas las carpetas deben llenarse desde el inicio.

La estructura existe para mantener consistencia y permitir crecimiento incremental.

---

## 3. Convención student-facing vs instructor-facing

### Student-facing

Material que puede estar en `main` o publicarse después de clase:

* `README.md`
* `slides/session.html`
* `slides/session.pdf`
* `demo/init.sql`
* `demo/queries/*` cuando no sean solución completa
* `exercises/README.md`
* `assets/` propios y autorizados
* `diagrams/` públicos
* `docker-compose.yml`
* `.devcontainer/devcontainer.json`
* `Makefile`

### Instructor-facing

Material que debe mantenerse privado, en rama `instructor` o revisarse antes de publicar:

* `notes/instructor.md`
* soluciones completas
* respuestas esperadas
* scripts de fallback
* resultados esperados que invaliden ejercicios
* rúbricas internas
* notas de conducción
* troubleshooting avanzado
* observaciones sobre alumnos

---

## 4. Mapa general de clases

| Clase | Carpeta                                            | Tema                         | Tipo de demo                        | Evidencia principal       |
| ----: | -------------------------------------------------- | ---------------------------- | ----------------------------------- | ------------------------- |
|    01 | `class-01-course-intro-oltp-olap`                  | Intro, OLTP vs OLAP          | Comparación conceptual / SQL simple | Diferencia OLTP/OLAP      |
|    02 | `class-02-logical-design-domain-rules`             | Diseño lógico y reglas       | Constraints y datos inválidos       | Diagrama + reglas         |
|    03 | `class-03-transactions-concurrency`                | Transacciones y concurrencia | Dos sesiones concurrentes           | Pasos + comportamiento    |
|    04 | `class-04-indexes-query-performance`               | Índices y performance        | `EXPLAIN ANALYZE`                   | Antes/después + tradeoff  |
|    05 | `class-05-views-procedures-triggers`               | Views/SP/triggers            | Objetos de BD                       | Caso de uso + riesgo      |
|    06 | `class-06-security-roles-pooling`                  | Roles, pooling, operación    | Roles/permisos + diagramas          | Acceso permitido/denegado |
|    07 | `class-07-multidimensional-modeling`               | Modelado multidimensional    | Cubo conceptual / agregación        | Dimensiones + medidas     |
|    08 | `class-08-data-warehouse-datamart`                 | Warehouse/Data Mart          | Star schema                         | Hechos + dimensiones      |
|    09 | `class-09-olap-data-mining`                        | OLAP/Data Mining             | Consultas analíticas                | Pregunta + resultado      |
|    10 | `class-10-object-oriented-databases-modern-models` | BDOO/modelos modernos        | Comparación de modelos              | Tradeoffs                 |

---

## 5. Detalle por clase

## Clase 01 — Course Intro, OLTP vs OLAP

### Carpeta

```txt
class-01-course-intro-oltp-olap
```

### Objetivo

Introducir dinámica del curso, uso de IA con criterio profesional y diferencia entre sistemas OLTP y OLAP.

### Material esperado

Student-facing:

* `README.md`
* `slides/session.html`
* `slides/session.pdf`
* `exercises/README.md`
* demo simple opcional

Instructor-facing:

* `notes/instructor.md`
* preguntas para diagnosticar nivel del grupo
* notas para explicar proyecto final
* plan para discutir horario de jueves si aplica

### Demo sugerida

Comparar una consulta operativa con una consulta agregada.

Ejemplo:

* buscar una orden específica
* agrupar ventas por mes

### Ejercicio sugerido

Identificar en un sistema conocido:

* datos operativos
* preguntas analíticas
* posible separación OLTP/OLAP

### Evidencia esperada

* breve explicación
* ejemplo operativo
* ejemplo analítico
* reflexión sobre uso de IA

---

## Clase 02 — Logical Design and Domain Rules

### Carpeta

```txt
class-02-logical-design-domain-rules
```

### Objetivo

Modelar datos con reglas explícitas de dominio y restricciones que prevengan inconsistencias.

### Material esperado

Student-facing:

* slides de diseño lógico
* demo con schema inicial
* ejercicio de modelado
* README con quick start

Instructor-facing:

* solución del modelo
* ejemplos válidos e inválidos
* preguntas para defensa

### Demo sugerida

Crear una tabla permisiva, insertar datos inválidos y luego agregar constraints.

### Ejercicio sugerido

Diseñar entidades y reglas de dominio para un caso pequeño.

### Evidencia esperada

* diagrama lógico
* SQL de constraints
* datos válidos
* datos inválidos
* supuestos

---

## Clase 03 — Transactions and Concurrency

### Carpeta

```txt
class-03-transactions-concurrency
```

### Objetivo

Entender cómo las transacciones y la concurrencia afectan consistencia y comportamiento observable.

### Material esperado

Student-facing:

* slides sobre ACID, locks, MVCC
* scripts para dos sesiones
* ejercicio guiado
* README con pasos claros

Instructor-facing:

* fallback de demo
* solución explicada
* posibles resultados por isolation level
* troubleshooting de locks/deadlocks

### Demo sugerida

Dos terminales ejecutando transacciones concurrentes.

### Ejercicio sugerido

Reproducir bloqueo o conflicto y explicar lo observado.

### Evidencia esperada

* pasos ejecutados
* comportamiento observado
* explicación
* riesgo
* mitigación posible

---

## Clase 04 — Indexes and Query Performance

### Carpeta

```txt
class-04-indexes-query-performance
```

### Objetivo

Diagnosticar consultas lentas con evidencia y razonar sobre índices.

### Material esperado

Student-facing:

* slides sobre índices y query plans
* dataset seed
* queries antes/después
* ejercicio de optimización

Instructor-facing:

* índices esperados
* resultados aproximados
* explicación de planes
* fallback si performance varía

### Demo sugerida

`EXPLAIN ANALYZE` antes y después de agregar índice.

### Ejercicio sugerido

Optimizar una consulta específica y explicar tradeoff.

### Evidencia esperada

* query original
* plan antes
* cambio propuesto
* plan después
* tradeoff

---

## Clase 05 — Views, Stored Procedures and Triggers

### Carpeta

```txt
class-05-views-procedures-triggers
```

### Objetivo

Usar objetos de base de datos con criterio y entender sus riesgos.

### Material esperado

Student-facing:

* slides sobre views/SP/triggers
* scripts de creación
* ejercicio de decisión técnica

Instructor-facing:

* solución
* explicación de riesgos
* casos donde no usar triggers

### Demo sugerida

Crear:

* una view
* una función/procedimiento
* un trigger de auditoría

### Ejercicio sugerido

Decidir qué objeto usar para un caso dado y justificar.

### Evidencia esperada

* objeto creado
* ejemplo de uso
* ventaja
* riesgo
* alternativa

---

## Clase 06 — Security, Roles, Pooling and Operational Concerns

### Carpeta

```txt
class-06-security-roles-pooling
```

### Objetivo

Comprender permisos, roles, connection pooling y aspectos operativos básicos.

### Material esperado

Student-facing:

* slides sobre mínimo privilegio
* demo de roles/permisos
* diagramas de pooling/memoria
* ejercicio de política de acceso

Instructor-facing:

* comandos para reset de roles
* notas sobre segmentos/tablespaces/buffers
* fallback conceptual

### Demo sugerida

Crear usuarios/roles con permisos diferenciados.

### Ejercicio sugerido

Diseñar roles para aplicación con lectura, escritura y reporting.

### Evidencia esperada

* roles
* permisos
* prueba de acceso permitido/denegado
* explicación de mínimo privilegio
* reflexión sobre operación

---

## Clase 07 — Multidimensional Modeling

### Carpeta

```txt
class-07-multidimensional-modeling
```

### Objetivo

Diseñar modelos multidimensionales con dimensiones, medidas, jerarquías y agregaciones.

### Material esperado

Student-facing:

* slides visuales sobre cubos
* diagrama dimensional
* demo de agregación simple
* ejercicio de cubo conceptual

Instructor-facing:

* modelo esperado
* ejemplos de jerarquías
* preguntas de discusión

### Demo sugerida

Modelo simple de ventas con dimensiones y medidas.

### Ejercicio sugerido

Diseñar cubo conceptual para un caso de negocio.

### Evidencia esperada

* dimensiones
* medidas
* jerarquías
* consulta agregada
* explicación del análisis

---

## Clase 08 — Data Warehouse and Data Mart

### Carpeta

```txt
class-08-data-warehouse-datamart
```

### Objetivo

Transformar necesidades de reporting en un modelo tipo Warehouse/Data Mart.

### Material esperado

Student-facing:

* slides sobre warehouse/datamart
* demo de star schema
* ejercicio de Data Mart
* README con criterios de granularidad

Instructor-facing:

* solución de star schema
* notas de ETL/ELT
* tradeoffs esperados

### Demo sugerida

Convertir datos operativos simples en tabla de hechos y dimensiones.

### Ejercicio sugerido

Diseñar Data Mart para una pregunta de decisión.

### Evidencia esperada

* tabla de hechos
* dimensiones
* granularidad
* query analítica
* tradeoffs frente a OLTP

---

## Clase 09 — OLAP and Data Mining

### Carpeta

```txt
class-09-olap-data-mining
```

### Objetivo

Usar consultas analíticas y patrones simples para apoyar toma de decisiones.

### Material esperado

Student-facing:

* slides sobre OLAP y Data Mining
* queries agregadas
* ejercicio de pregunta de negocio
* evidencia de interpretación

Instructor-facing:

* ejemplos de resultados
* riesgos de mala interpretación
* notas para no convertir en clase de ML

### Demo sugerida

Resolver preguntas analíticas sobre modelo dimensional.

### Ejercicio sugerido

Formular 3 preguntas de negocio y responder una con SQL.

### Evidencia esperada

* pregunta
* consulta
* resultado
* interpretación
* limitación

---

## Clase 10 — Object-Oriented Databases and Modern Models

### Carpeta

```txt
class-10-object-oriented-databases-modern-models
```

### Objetivo

Contextualizar bases orientadas a objetos y conectarlas con ORMs, documentos y modelos modernos.

### Material esperado

Student-facing:

* slides sobre BDOO/ODMG/OO-DBMS
* comparación relacional vs objeto/documento
* ejercicio de elección de modelo

Instructor-facing:

* notas históricas
* explicación de impedance mismatch
* preguntas de defensa
* ejemplos de tradeoffs

### Demo sugerida

Comparar modelado relacional contra objeto/documento para el mismo caso.

PostgreSQL puede usarse como contraste, pero no debe presentarse como OO-DBMS pura.

### Ejercicio sugerido

Elegir modelo de datos para un escenario y justificar.

### Evidencia esperada

* comparación
* caso de uso
* ventajas
* limitaciones
* tradeoffs

---

## 6. Relación con GitHub Projects

Cada carpeta puede generar issues para el tablero del curso.

Formato recomendado de issue:

```md
# [Class XX] Título de actividad

## Contexto

## Tarea

## Evidencia esperada

## Acceptance Criteria

## Uso de IA
```

Labels sugeridas:

```txt
class-01
class-02
database
design
transactions
concurrency
performance
indexes
security
warehouse
olap
data-mining
models
exercise
project
review
blocked
```

---

## 7. Estado de avance sugerido por carpeta

Usar este checklist para controlar progreso:

```md
## Class readiness checklist

- [ ] README actualizado
- [ ] Slides base listas
- [ ] Demo reproducible
- [ ] Ejercicio definido
- [ ] Evidencia esperada definida
- [ ] Notas del instructor listas
- [ ] Fallback preparado
- [ ] Relación con temario clara
- [ ] Material revisado para no incluir contenido de terceros
```

---

## 8. Reglas para Codex/IA

Cuando Codex trabaje sobre una carpeta `class-*`:

* debe leer primero documentos en `00-course-planning/docs/ai/`
* debe consultar `00_COURSE_PLAN.md`
* debe consultar `01_SYLLABUS_COVERAGE_MATRIX.md`
* debe consultar este mapa
* debe modificar solo la clase solicitada
* debe producir mini-plan antes de cambios grandes
* no debe generar soluciones completas en student-facing sin autorización
* no debe copiar referencias externas
* no debe agregar complejidad innecesaria
* debe mantener evidencia y tradeoffs como parte de la actividad

---

## 9. Reglas para publicación posterior

Antes de publicar una clase:

* revisar que no incluya notas privadas
* revisar que no incluya soluciones que invaliden evaluación pendiente
* revisar que no incluya material de terceros sin permiso
* revisar que Docker/README estén actualizados
* revisar que slides estén exportadas si se publicarán
* revisar que links funcionen
* revisar que la demo pueda resetearse

---

## TODO

* Confirmar cuándo se inicializará cada `class-*` como repositorio Git independiente y si se hará antes de preparar la clase 1 o conforme avance el curso.
* Confirmar convención de ramas cuando se inicialicen repos.
* Crear templates finales para `README.md`, `exercises/README.md` y `notes/instructor.md`.
* Crear lista inicial de issues por clase.
* Definir qué clases tendrán demo obligatoria y cuáles demo conceptual.
