# 01_SYLLABUS_COVERAGE_MATRIX.md — Matriz de cobertura del temario oficial

## Status

Draft inicial controlado por el instructor.

Este documento mapea los temas oficiales de la materia **Sistemas Avanzados de Bases de Datos** de **UniVO** contra el plan de 10 sesiones definido en:

```txt
00-course-planning/docs/planning/00_COURSE_PLAN.md
````

---

## Purpose

El propósito de este documento es asegurar que el curso cubra el temario oficial sin perder la orientación práctica definida para la materia.

Este documento debe usarse para:

* validar cobertura
* evitar omisiones
* justificar la distribución de sesiones
* guiar a Codex/ChatGPT al generar contenido
* mantener alineación académica con UniVO

---

## 1. Resumen de sesiones

| Clase | Carpeta                                            | Tema principal                        |
| ----- | -------------------------------------------------- | ------------------------------------- |
| 01    | `class-01-course-intro-oltp-olap`                  | Introducción, OLTP vs OLAP            |
| 02    | `class-02-logical-design-domain-rules`             | Diseño lógico y reglas de dominio     |
| 03    | `class-03-transactions-concurrency`                | Transacciones y concurrencia          |
| 04    | `class-04-indexes-query-performance`               | Índices y rendimiento                 |
| 05    | `class-05-views-procedures-triggers`               | Vistas, procedimientos y triggers     |
| 06    | `class-06-security-roles-pooling`                  | Seguridad, roles, pooling y operación |
| 07    | `class-07-multidimensional-modeling`               | Modelado multidimensional             |
| 08    | `class-08-data-warehouse-datamart`                 | Data Warehouse y Data Mart            |
| 09    | `class-09-olap-data-mining`                        | OLAP y Data Mining                    |
| 10    | `class-10-object-oriented-databases-modern-models` | BDOO y modelos modernos               |

---

## 2. Cobertura por bloque oficial

## Bloque 1 — Bases de datos convencionales

| Tema oficial                                                    | Clase principal | Clases relacionadas | Enfoque de cobertura                                                            |
| --------------------------------------------------------------- | --------------: | ------------------- | ------------------------------------------------------------------------------- |
| Diseño lógico de bases de datos                                 |              02 | 01, 08              | Modelo relacional, entidades, relaciones, normalización práctica y supuestos    |
| Reglas de dominio de atributos                                  |              02 | 05                  | Constraints, validaciones, `CHECK`, `NOT NULL`, unicidad, integridad            |
| Desencadenadores                                                |              05 | 02                  | Triggers para auditoría/reglas automáticas, riesgos de comportamiento implícito |
| Procedimientos almacenados                                      |              05 | 09                  | Encapsulamiento de lógica, consultas reutilizables, agregaciones controladas    |
| Mejora del desempeño de una base de datos                       |              04 | 03, 06, 08          | Query plans, índices, lectura/escritura, operación, separación OLTP/OLAP        |
| Definición algorítmica de índices                               |              04 | 02                  | Concepto B-tree, selectividad, cardinalidad, tradeoffs                          |
| Especificación de segmentos                                     |              06 | 04                  | Cobertura conceptual/operativa; almacenamiento físico y organización            |
| Especificación de espacios de tabla                             |              06 | 04                  | Cobertura conceptual/operativa; cuándo importa en administración                |
| Definición de vistas                                            |              05 | 08, 09              | Views para simplificar acceso, reporting y encapsulamiento de consultas         |
| Gestión de transacciones                                        |              03 | 05                  | ACID, `BEGIN`, `COMMIT`, `ROLLBACK`, consistencia                               |
| Definición de usuarios y roles                                  |              06 | 05                  | Roles, permisos, mínimo privilegio                                              |
| Control de concurrencia                                         |              03 | 04, 06              | Locks, MVCC, deadlocks, isolation levels                                        |
| Definición de Data-Pools para acceso a bases de datos           |              06 | 03, 04              | Connection pools, saturación, límites operativos                                |
| Configuración de memoria y buffer para un sistema transaccional |              06 | 04                  | Cobertura conceptual/operativa; buffers, memoria, impacto en performance        |

### Notas del bloque

Este bloque ocupa la mayor parte del curso porque es el más cercano a problemas reales de ingeniería backend y operación de sistemas transaccionales.

Las clases 02–06 cubren la base convencional con profundidad práctica.

---

## Bloque 2 — Bases de datos multidimensionales

| Tema oficial                                          | Clase principal | Clases relacionadas | Enfoque de cobertura                                         |
| ----------------------------------------------------- | --------------: | ------------------- | ------------------------------------------------------------ |
| Definición y conceptos de las BDM                     |              07 | 01, 08              | Diferencia frente a modelo transaccional; objetivo analítico |
| Modelos conceptuales multidimensionales               |              07 | 08                  | Dimensiones, medidas, hechos, granularidad                   |
| Cubos e hipercubos de datos                           |              07 | 09                  | Cubos conceptuales, análisis por múltiples dimensiones       |
| Estructuras no jerárquicas y jerárquicas de los datos |              07 | 08                  | Jerarquías de fecha, producto, región; dimensiones planas    |
| Operadores para datos agregados multidimensionales    |              07 | 09                  | Roll-up, drill-down, slice, dice, agregaciones               |
| Consultas multidimensionales de datos                 |              09 | 07, 08              | Consultas agregadas y análisis OLAP                          |

### Notas del bloque

El bloque multidimensional se concentra principalmente en clase 07, pero se refuerza en clases 08 y 09 mediante Data Warehouse, Data Mart y consultas OLAP.

---

## Bloque 3 — Bases de datos para la toma de decisiones

| Tema oficial                             | Clase principal | Clases relacionadas | Enfoque de cobertura                                                 |
| ---------------------------------------- | --------------: | ------------------- | -------------------------------------------------------------------- |
| Surgimiento de los repositorios de datos |              08 | 01, 07              | Por qué separar sistemas transaccionales de repositorios analíticos  |
| Almacenes de Datos / Data Warehouse      |              08 | 07, 09              | Integración, modelo dimensional, hechos, dimensiones                 |
| Mercado de Datos / Data Mart             |              08 | 09                  | Data marts por necesidad de negocio o área                           |
| Procesamiento analítico en línea / OLAP  |              09 | 07, 08              | Consultas multidimensionales, agregaciones, indicadores              |
| Minería de Datos / Data Mining           |              09 | 08                  | Patrones, segmentación simple, decisiones, límites de interpretación |

### Notas del bloque

Este bloque debe mantenerse práctico y enfocado en toma de decisiones. No debe convertirse en curso de machine learning.

---

## Bloque 4 — Bases de datos orientadas a objetos

| Tema oficial                                      | Clase principal | Clases relacionadas | Enfoque de cobertura                                               |
| ------------------------------------------------- | --------------: | ------------------- | ------------------------------------------------------------------ |
| Definición y conceptos de las BDOO                |              10 | 02                  | Contexto histórico y motivación                                    |
| El Modelo de Datos Orientado a Objetos            |              10 | 02                  | Identidad, objetos, relaciones, persistencia                       |
| El estándar ODMG                                  |              10 | —                   | Cobertura conceptual/histórica                                     |
| Encapsulamiento, herencia y polimorfismo en BDOO  |              10 | —                   | Conceptos OO aplicados a persistencia                              |
| Persistencia, Concurrencia y Recuperación en BDOO |              10 | 03                  | Comparación con transacciones/concurrencia en modelos relacionales |
| Gestores de Bases de Datos OO / OO-DBMS           |              10 | —                   | Cobertura conceptual/histórica                                     |
| Otros modelos                                     |              10 | 01, 08              | ORMs, documentos, NoSQL como evolución/contexto moderno            |

### Notas del bloque

Este bloque se cubre principalmente en clase 10.

BDOO/ODMG/OO-DBMS deben tratarse con claridad, pero como contexto histórico y conceptual. El valor práctico se refuerza conectando con ORMs, document databases, impedance mismatch y modelos modernos.

---

## 3. Cobertura por clase

## Clase 01 — Course Intro, OLTP vs OLAP

Cubre o introduce:

* diferencia entre sistemas transaccionales y analíticos
* motivación de repositorios de datos
* motivación de bases convencionales vs analíticas
* uso responsable de IA
* dinámica de proyecto/prácticas

Temario relacionado:

* Bases de datos convencionales
* Bases de datos multidimensionales
* Bases de datos para toma de decisiones
* Otros modelos

Nivel de cobertura:

```txt
Introductorio
```

---

## Clase 02 — Logical Design and Domain Rules

Cubre:

* diseño lógico de bases de datos
* reglas de dominio de atributos
* constraints
* integridad
* supuestos de modelado

Temario relacionado:

* diseño lógico
* reglas de dominio

Nivel de cobertura:

```txt
Principal
```

---

## Clase 03 — Transactions and Concurrency

Cubre:

* gestión de transacciones
* control de concurrencia
* ACID
* locks
* deadlocks
* MVCC
* isolation levels

Temario relacionado:

* gestión de transacciones
* control de concurrencia
* persistencia/concurrencia en BDOO como comparación posterior

Nivel de cobertura:

```txt
Principal
```

---

## Clase 04 — Indexes and Query Performance

Cubre:

* mejora del desempeño
* definición algorítmica de índices
* query plans
* `EXPLAIN ANALYZE`
* tradeoffs de lectura/escritura

Temario relacionado:

* índices
* performance
* buffers/memoria como contexto operativo

Nivel de cobertura:

```txt
Principal
```

---

## Clase 05 — Views, Stored Procedures and Triggers

Cubre:

* definición de vistas
* procedimientos almacenados
* desencadenadores
* encapsulamiento de lógica
* riesgos de lógica implícita

Temario relacionado:

* vistas
* stored procedures
* triggers

Nivel de cobertura:

```txt
Principal
```

---

## Clase 06 — Security, Roles, Pooling and Operational Concerns

Cubre:

* usuarios y roles
* permisos
* connection pools / data pools
* memoria y buffers
* segmentos
* tablespaces
* operación básica

Temario relacionado:

* usuarios y roles
* data pools
* memoria/buffers
* segmentos
* espacios de tabla

Nivel de cobertura:

```txt
Mixto: principal para roles/pooling; conceptual para segmentos/tablespaces/memoria
```

---

## Clase 07 — Multidimensional Modeling

Cubre:

* BDM
* modelos multidimensionales
* cubos e hipercubos
* dimensiones
* medidas
* jerarquías
* operadores multidimensionales

Temario relacionado:

* bases multidimensionales completas

Nivel de cobertura:

```txt
Principal
```

---

## Clase 08 — Data Warehouse and Data Mart

Cubre:

* repositorios de datos
* Data Warehouse
* Data Mart
* modelo dimensional
* facts/dimensions
* granularidad
* separación OLTP/analítica

Temario relacionado:

* bases para toma de decisiones
* Data Warehouse
* Data Mart

Nivel de cobertura:

```txt
Principal
```

---

## Clase 09 — OLAP and Data Mining

Cubre:

* OLAP
* consultas multidimensionales
* agregaciones
* indicadores
* Data Mining
* patrones y segmentación simple
* límites de interpretación

Temario relacionado:

* OLAP
* Data Mining
* consultas multidimensionales

Nivel de cobertura:

```txt
Principal
```

---

## Clase 10 — Object-Oriented Databases and Modern Models

Cubre:

* BDOO
* modelo orientado a objetos
* ODMG
* encapsulamiento/herencia/polimorfismo
* persistencia
* concurrencia
* recuperación
* OO-DBMS
* otros modelos
* ORMs/documentos/NoSQL como contexto moderno

Temario relacionado:

* bases de datos orientadas a objetos
* otros modelos

Nivel de cobertura:

```txt
Principal, con enfoque conceptual/histórico y puente moderno
```

---

## 4. Temas con cobertura conceptual

Algunos temas del temario oficial son importantes, pero no requieren demo extensa por el tiempo disponible.

Estos temas se cubrirán principalmente de forma conceptual, visual o contextual:

| Tema                            | Clase | Justificación                                                     |
| ------------------------------- | ----: | ----------------------------------------------------------------- |
| Segmentos                       |    06 | Tema operativo/físico; requiere contexto DBA                      |
| Tablespaces / espacios de tabla |    06 | Tema operativo/físico; se explica como criterio de administración |
| Configuración de memoria/buffer |    06 | Se cubre a nivel conceptual para entender impacto operativo       |
| ODMG                            |    10 | Relevancia histórica; baja presencia práctica actual              |
| OO-DBMS                         |    10 | Relevancia histórica; se conecta con ORMs/modelos modernos        |
| Data Mining avanzado            |    09 | El curso no es de ML; se cubre concepto, uso y límites            |

---

## 5. Temas con mayor profundidad práctica

Estos temas tendrán mayor profundidad y actividades prácticas:

| Tema                       | Clases     |
| -------------------------- | ---------- |
| Diseño lógico              | 02         |
| Reglas de dominio          | 02         |
| Transacciones              | 03         |
| Concurrencia               | 03         |
| Índices                    | 04         |
| Performance                | 04         |
| Vistas                     | 05         |
| Procedimientos             | 05         |
| Triggers                   | 05         |
| Roles/permisos             | 06         |
| OLTP vs OLAP               | 01, 08, 09 |
| Modelado multidimensional  | 07         |
| Data Warehouse / Data Mart | 08         |
| OLAP                       | 09         |
| Modelos alternativos       | 10         |

---

## 6. Posibles huecos o riesgos

### Riesgo 1: Clase 06 puede sentirse muy amplia

Incluye roles, pooling, memoria, buffers, segmentos y tablespaces.

Mitigación:

* profundizar en roles/pooling
* cubrir memoria/buffers/segmentos/tablespaces de forma conceptual
* usar diagramas, no demo extensa para todo

### Riesgo 2: Clase 10 puede sentirse histórica

BDOO/ODMG puede parecer antiguo.

Mitigación:

* explicar motivación histórica
* conectar con ORMs
* conectar con document databases
* discutir impedance mismatch

### Riesgo 3: OLAP aparece en clases 07, 08 y 09

Puede sentirse repetitivo.

Mitigación:

* Clase 07: modelo conceptual
* Clase 08: arquitectura de Warehouse/Data Mart
* Clase 09: consultas, análisis y toma de decisiones

### Riesgo 4: Data Mining puede desviarse hacia ML

Mitigación:

* mantener enfoque de datos, patrones y decisiones
* no convertir en clase de algoritmos ML
* usar ejemplos simples

---

## 7. Validación final de cobertura

Estado de cobertura por bloque:

| Bloque                                 | Estado                     |
| -------------------------------------- | -------------------------- |
| Bases de datos convencionales          | Cubierto en clases 02–06   |
| Bases de datos multidimensionales      | Cubierto en clases 07 y 09 |
| Bases de datos para toma de decisiones | Cubierto en clases 08–09   |
| Bases de datos orientadas a objetos    | Cubierto en clase 10       |

Conclusión:

```txt
El plan de 10 sesiones cubre el temario oficial completo.
```

La profundidad varía por tema para respetar el límite de 20 horas y priorizar valor práctico.

---

## 8. Reglas para Codex/IA

Cuando Codex genere material de una clase, debe consultar esta matriz y asegurar que:

* el contenido se alinee con la clase correcta
* no se omitan temas oficiales asignados
* no se sobrecargue una clase con temas no asignados
* se mantenga el nivel de profundidad esperado
* se respeten los temas conceptuales vs prácticos
* se indique qué tema oficial se está cubriendo cuando sea relevante

---

## TODO

* Validar esta matriz con el instructor después de revisar el calendario real.
* Ajustar si UniVO solicita énfasis distinto.
* Ajustar después de conocer nivel real del grupo.
* Conectar cada tema oficial con prácticas concretas.

