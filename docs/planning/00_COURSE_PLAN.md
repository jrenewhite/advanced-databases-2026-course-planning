# 00_COURSE_PLAN.md — Plan general del curso

## Status

Draft inicial controlado por el instructor.

Este documento define la estructura general de la materia **Sistemas Avanzados de Bases de Datos**.

Debe leerse junto con:

```txt
00-course-planning/docs/ai/00_COURSEWARE_OBJECTIVE.md
00-course-planning/docs/ai/01_AI_COLLABORATION.md
00-course-planning/docs/ai/02_SLIDE_RULES.md
00-course-planning/docs/ai/03_REPOSITORY_RULES.md
00-course-planning/docs/ai/04_DEMO_GUIDELINES.md
00-course-planning/docs/ai/05_EVALUATION_GUIDELINES.md
````

---

## Purpose

El propósito de este documento es establecer el plan de 10 sesiones del curso, manteniendo alineación con el temario oficial y con la filosofía práctica definida para la materia.

El curso debe conectar teoría académica con problemas reales de ingeniería, usando ejemplos, demos, discusión, evidencia y razonamiento técnico.

---

## 1. Contexto general

* Programa: Maestría en Sistemas Computacionales
* Materia: Sistemas Avanzados de Bases de Datos
* Nivel: posgrado
* Duración: 10 sesiones
* Duración total: 20 horas
* Frecuencia: martes y jueves
* Horario: 19:00–21:00
* Duración por sesión: 2 horas
* Modalidad: sincrónica por Google Meet
* Plataforma administrativa: Classroom
* Grupo actual: 5 estudiantes
* Perfil esperado:

  * alumnos con formación académica
  * experiencia industrial posiblemente limitada
  * interés en conectar teoría con práctica

### Nota operativa

El curso operará con sesiones sincrónicas por Meet y seguimiento administrativo por Classroom.

Cada sesión debe dejar evidencia mínima de participación o asistencia.

Cuando exista actividad técnica asociada a la sesión, también debe quedar evidencia revisable de trabajo.

---

## 1.1 Calendario real 2026

```txt
Clase 01 — Martes 2 de junio de 2026
Clase 02 — Jueves 4 de junio de 2026
Clase 03 — Martes 9 de junio de 2026
Clase 04 — Jueves 11 de junio de 2026
Clase 05 — Martes 16 de junio de 2026
Clase 06 — Jueves 18 de junio de 2026
Clase 07 — Martes 23 de junio de 2026
Clase 08 — Jueves 25 de junio de 2026
Clase 09 — Martes 30 de junio de 2026
Clase 10 — Jueves 2 de julio de 2026
```

---

## 2. Intención del curso

La intención principal es que los alumnos entiendan cómo se usan, diseñan, diagnostican y justifican sistemas de bases de datos en escenarios cercanos a la vida real.

El curso no debe limitarse a definiciones.

Debe ayudar a que los alumnos puedan:

* diseñar modelos lógicos razonables
* aplicar reglas de dominio
* entender transacciones y concurrencia
* diagnosticar problemas de performance
* razonar sobre índices
* usar vistas, procedimientos y triggers con criterio
* entender usuarios, roles, conexión y operación básica
* distinguir OLTP, OLAP, Data Warehouse y Data Mart
* comprender bases multidimensionales
* contextualizar BDOO y modelos modernos
* usar IA sin delegar el criterio profesional

---

## 3. Narrativa del curso

La historia del curso será:

> Primero entendemos cómo se modela y opera una base transaccional.
> Luego vemos cómo falla bajo carga, concurrencia o mal diseño.
> Después aprendemos a optimizar, proteger y operar mejor.
> Finalmente conectamos esos datos con analítica, toma de decisiones y modelos alternativos.

Secuencia conceptual:

```txt
Diseño → Reglas → Transacciones → Concurrencia → Performance
→ Objetos de BD → Seguridad/operación → OLAP → Warehouse
→ Data Mining → Modelos alternativos
```

---

## 4. Estructura recomendada por sesión

Cada sesión dura 2 horas.

Estructura sugerida:

### Primera parte

* contexto del tema
* problema real
* conceptos clave
* visualización o diagrama
* discusión guiada

### Segunda parte

* demo
* ejercicio corto
* evidencia esperada
* recap
* conexión con proyecto final

No se debe usar toda la clase para slides.

---

## 5. Plan de sesiones

## Clase 01 — Course Intro, OLTP vs OLAP

Repositorio/carpeta:

```txt
class-01-course-intro-oltp-olap
```

Este repo `class-*` corresponde a material de sesión. Las tareas evaluables fuera de clase deben vivir en repos separados `assignment-*`. El proyecto final debe vivir en un repo separado del alumno/equipo.

### Objetivo

Introducir la materia, explicar la dinámica de trabajo y establecer la diferencia entre bases transaccionales, analíticas y otros modelos de datos.

### Temas

* Presentación del curso
* Expectativas
* Uso responsable de IA
* Qué significa “bases de datos avanzadas”
* OLTP vs OLAP
* Sistemas transaccionales vs sistemas analíticos
* Introducción al proyecto final
* Introducción a la separación entre repos `class-*`, `assignment-*` y proyecto final
* Introducción a GitHub Projects / issues como herramienta posible de seguimiento

### Pregunta guía

> ¿Por qué una base que funciona bien para registrar operaciones puede ser mala para analizar decisiones?

### Demo sugerida

Comparar dos tipos de consultas:

* consulta transaccional simple
* consulta analítica agregada

No necesita ser una demo compleja.

### Ejercicio sugerido

Identificar, para un sistema conocido, qué datos son operativos y qué datos serían útiles para toma de decisiones.

### Evidencia esperada

* breve explicación OLTP vs OLAP
* ejemplo de consulta operativa
* ejemplo de pregunta analítica
* comprensión inicial de cómo se separará material de sesión, tareas fuera de clase y proyecto final

---

## Clase 02 — Logical Design and Domain Rules

Repositorio/carpeta:

```txt
class-02-logical-design-domain-rules
```

### Objetivo

Reforzar diseño lógico de bases de datos y reglas de dominio, conectando normalización, restricciones y calidad de datos con problemas reales.

### Temas

* Diseño lógico
* Entidades y relaciones
* Reglas de dominio
* Constraints
* Llaves primarias
* Llaves foráneas
* Unicidad
* `CHECK`
* `NOT NULL`
* Calidad de datos
* Supuestos del modelo

### Pregunta guía

> ¿Qué errores deberíamos impedir desde el modelo de datos y no desde código externo?

### Demo sugerida

Diseñar una base pequeña con datos inválidos y luego agregar constraints para prevenir inconsistencias.

### Ejercicio sugerido

Modelar un caso simple y definir reglas de dominio explícitas.

### Evidencia esperada

* diagrama lógico
* reglas de dominio
* SQL de constraints
* ejemplos válidos e inválidos
* explicación de supuestos

---

## Clase 03 — Transactions and Concurrency

Repositorio/carpeta:

```txt
class-03-transactions-concurrency
```

### Objetivo

Explicar cómo las transacciones protegen consistencia y cómo aparecen problemas reales de concurrencia.

### Temas

* Transacciones
* ACID
* `BEGIN`
* `COMMIT`
* `ROLLBACK`
* Isolation levels
* Concurrencia
* Locks
* Bloqueos
* Deadlocks
* MVCC
* Consistencia bajo acceso simultáneo

### Pregunta guía

> ¿Qué puede salir mal cuando dos usuarios hacen lo correcto al mismo tiempo?

### Demo sugerida

Dos sesiones concurrentes modificando datos relacionados.

Posibles escenarios:

* bloqueo por actualización
* lectura consistente
* deadlock controlado
* diferencia entre niveles de aislamiento

### Ejercicio sugerido

Reproducir un problema simple de concurrencia y explicar qué ocurrió.

### Evidencia esperada

* pasos ejecutados
* comportamiento observado
* explicación de transacción/concurrencia
* riesgo identificado
* posible mitigación

---

## Clase 04 — Indexes and Query Performance

Repositorio/carpeta:

```txt
class-04-indexes-query-performance
```

### Objetivo

Entender cómo los índices afectan planes de ejecución, tiempos de respuesta y tradeoffs de lectura/escritura.

### Temas

* Mejora de desempeño
* Índices
* Definición algorítmica de índices
* B-tree como modelo conceptual
* Selectividad
* Cardinalidad
* `EXPLAIN`
* `EXPLAIN ANALYZE`
* Query plans
* Sequential scan vs index scan
* Tradeoffs de índices

### Pregunta guía

> ¿Por qué agregar un índice puede arreglar una query y empeorar otras partes del sistema?

### Demo sugerida

Crear una tabla con datos suficientes para observar una consulta lenta, analizar el plan, agregar índice y comparar.

### Ejercicio sugerido

Diagnosticar una query lenta y proponer un índice con evidencia.

### Evidencia esperada

* query original
* plan antes
* índice propuesto
* plan después
* comparación
* tradeoff identificado

---

## Clase 05 — Views, Stored Procedures and Triggers

Repositorio/carpeta:

```txt
class-05-views-procedures-triggers
```

### Objetivo

Comprender cuándo usar vistas, procedimientos almacenados y triggers, y qué riesgos introducen en mantenibilidad y claridad del sistema.

### Temas

* Vistas
* Stored procedures
* Triggers / desencadenadores
* Encapsulamiento de lógica
* Automatización de reglas
* Lógica en base vs lógica en aplicación
* Riesgos de comportamiento implícito
* Testing y observabilidad

### Pregunta guía

> ¿Cuándo conviene mover lógica a la base de datos y cuándo se vuelve deuda técnica?

### Demo sugerida

Crear:

* una vista para simplificar una consulta
* una función/procedimiento para encapsular lectura o agregación
* un trigger para auditoría simple

### Ejercicio sugerido

Elegir entre vista, procedimiento o trigger para un caso dado y justificar.

### Evidencia esperada

* objeto creado
* caso de uso
* ejemplo de ejecución
* ventaja
* riesgo o limitación

---

## Clase 06 — Security, Roles, Pooling and Operational Concerns

Repositorio/carpeta:

```txt
class-06-security-roles-pooling
```

### Objetivo

Introducir aspectos operativos de bases transaccionales: usuarios, roles, permisos, connection pools, memoria/buffers y límites prácticos.

### Temas

* Usuarios
* Roles
* Permisos
* Principio de mínimo privilegio
* Connection pools / data pools
* Configuración de memoria
* Buffers
* Tablespaces
* Segmentos
* Consideraciones operativas
* Saturación de conexiones
* Diferencia entre diseño y operación

### Pregunta guía

> ¿Qué pasa cuando la base no falla por SQL, sino por cómo la estamos usando?

### Demo sugerida

Crear roles con permisos diferenciados y mostrar acceso permitido/denegado.

Opcional: simular saturación conceptual de conexiones o explicar pooling con diagrama.

### Ejercicio sugerido

Diseñar una política simple de roles para una aplicación con usuarios de lectura, escritura y analítica.

### Evidencia esperada

* roles definidos
* permisos
* prueba de acceso permitido/denegado
* explicación de mínimo privilegio
* reflexión sobre pooling o límites operativos

---

## Clase 07 — Multidimensional Modeling

Repositorio/carpeta:

```txt
class-07-multidimensional-modeling
```

### Objetivo

Explicar modelos multidimensionales, cubos, jerarquías y agregaciones como base conceptual para análisis de datos.

### Temas

* Bases de datos multidimensionales
* Modelos conceptuales multidimensionales
* Cubos
* Hipercubos
* Dimensiones
* Medidas
* Jerarquías
* Estructuras jerárquicas y no jerárquicas
* Operadores de agregación
* Slice
* Dice
* Drill-down
* Roll-up

### Pregunta guía

> ¿Cómo cambia el modelo cuando la pregunta principal deja de ser “qué ocurrió” y pasa a ser “qué patrón vemos”?

### Demo sugerida

Construir un modelo simple de ventas con dimensiones y medidas.

Mostrar agregaciones por fecha, producto o sucursal.

### Ejercicio sugerido

Diseñar un cubo conceptual para un caso de negocio sencillo.

### Evidencia esperada

* dimensiones
* medidas
* jerarquías
* consulta agregada
* explicación del análisis posible

---

## Clase 08 — Data Warehouse and Data Mart

Repositorio/carpeta:

```txt
class-08-data-warehouse-datamart
```

### Objetivo

Comprender por qué surgen los repositorios de datos, Data Warehouse y Data Mart, y cómo se relacionan con sistemas OLTP.

### Temas

* Repositorios de datos
* Data Warehouse
* Data Mart
* ETL / ELT como contexto
* Star schema
* Fact tables
* Dimension tables
* Granularidad
* Separación entre operación y analítica
* Calidad e integración de datos

### Pregunta guía

> ¿Por qué no deberíamos hacer todo el reporting pesado sobre la base transaccional?

### Demo sugerida

Transformar datos operativos simples en un modelo dimensional.

Crear tabla de hechos y dimensiones básicas.

### Ejercicio sugerido

Diseñar un Data Mart para una necesidad de análisis específica.

### Evidencia esperada

* modelo dimensional
* tabla de hechos
* dimensiones
* granularidad
* consulta analítica
* tradeoffs frente a modelo OLTP

---

## Clase 09 — OLAP and Data Mining

Repositorio/carpeta:

```txt
class-09-olap-data-mining
```

### Objetivo

Conectar OLAP y Data Mining con toma de decisiones, sin convertir la clase en un curso de machine learning.

### Temas

* Procesamiento analítico en línea / OLAP
* Consultas multidimensionales
* Agregaciones
* Indicadores
* Data Mining
* Patrones
* Segmentación simple
* Análisis exploratorio
* Limitaciones
* Riesgos de interpretación

### Pregunta guía

> ¿Cómo pasamos de almacenar datos a extraer señales útiles para decidir?

### Demo sugerida

Ejecutar consultas analíticas sobre un modelo dimensional y derivar observaciones simples.

Opcional: segmentación básica o detección de patrones con SQL.

### Ejercicio sugerido

Proponer 3 preguntas de negocio y resolver una con consulta agregada.

### Evidencia esperada

* pregunta de análisis
* consulta OLAP/agregada
* resultado observado
* interpretación
* limitación o riesgo

---

## Clase 10 — Object-Oriented Databases and Modern Models

Repositorio/carpeta:

```txt
class-10-object-oriented-databases-modern-models
```

### Objetivo

Cubrir bases de datos orientadas a objetos como modelo conceptual e histórico, conectándolas con ORMs, documentos y otros modelos modernos.

### Temas

* Bases de datos orientadas a objetos
* Modelo de datos orientado a objetos
* ODMG
* Encapsulamiento
* Herencia
* Polimorfismo
* Persistencia
* Concurrencia
* Recuperación
* OO-DBMS
* Impedance mismatch
* ORMs
* Document databases
* Otros modelos

### Pregunta guía

> ¿Por qué el mundo intentó guardar objetos directamente y por qué muchas soluciones modernas tomaron otros caminos?

### Demo sugerida

Comparar un modelo relacional con un modelo orientado a objetos/documentos para el mismo problema.

No requiere usar una OO-DBMS real si no aporta valor práctico.

### Ejercicio sugerido

Analizar un caso y decidir si conviene relacional, objeto/documento u otro modelo, justificando tradeoffs.

### Evidencia esperada

* comparación de modelos
* caso de uso
* ventajas
* limitaciones
* tradeoffs
* conexión con persistencia/concurrencia

---

## 6. Proyecto final

El proyecto final debe presentarse desde el inicio como expectativa general, aunque su desarrollo formal pueda ocurrir más adelante.

Debe comprender alguno de los modelos de bases de datos analizados en el curso.

Opciones posibles:

* mini sistema OLTP con reglas de dominio, transacciones e índices
* análisis de performance de una base existente
* modelo dimensional para reporting
* Data Mart para un caso de decisión
* comparación entre modelo relacional y modelo alternativo
* diseño de arquitectura de datos para un caso académico o profesional

El proyecto debe incluir:

* problema
* modelo
* justificación
* evidencia
* tradeoffs
* presentación o revisión oral breve

No debe ser innecesariamente grande.

Debe poder revisarse y defenderse con claridad.

Dado que el grupo actual es de 5 estudiantes, el escenario más probable es proyecto individual.

Si el alcance real lo justifica, podrán permitirse parejas en casos puntuales.

---

## 7. Uso de GitHub Projects

GitHub Projects puede usarse para simular trabajo real.

Se usará principalmente para:

* repos `assignment-*`
* checkpoints de proyecto final
* revisión de entregas
* bloqueos
* revisión o defensa final

Los repos `class-*` no son el foco del tablero por default.

Columnas sugeridas:

```txt
Backlog
Ready
In Progress
Review
Done
Blocked
```

El objetivo no es enseñar agile formalmente.

El objetivo es que los alumnos practiquen:

* ownership
* seguimiento
* evidencia
* comunicación técnica
* cierre de actividades
* revisión

---

## 8. Evaluación oficial aterrizada al curso

Alineada al documento oficial y aterrizada al flujo operativo del curso:

```txt
Examen escrito                 20%
Diagramas                      10%
Prácticas de laboratorio       30%
Proyecto final                 30%
Reportes de lectura            10%
```

Interpretación operativa:

* Examen escrito: evaluación conceptual breve, con apoyo de revisión técnica corta cuando convenga.
* Diagramas: modelado, arquitectura, concurrencia o esquemas dimensionales.
* Prácticas de laboratorio: trabajo fuera de clase en repos `assignment-*`.
* Proyecto final: repositorio separado con evidencia y posible defensa breve.
* Reportes de lectura: notas de lectura, reflexión o research técnico breve.

---

## 9. Ritmo de trabajo

No intentar cubrir todos los temas con la misma profundidad.

Dar más profundidad a:

* diseño lógico
* reglas de dominio
* transacciones
* concurrencia
* índices
* performance
* OLTP vs OLAP
* Data Warehouse
* Data Mart
* modelo dimensional
* criterio profesional con IA

Dar cobertura contextual a:

* ODMG
* OO-DBMS clásicos
* segmentos
* tablespaces
* configuración fina de memoria/buffers

Estos temas deben cubrirse, pero no necesariamente con demos extensas.

---

## 10. Criterios para ajustar en vivo

Durante la primera clase, confirmar con el grupo:

* experiencia previa con SQL
* experiencia con Docker
* experiencia con Git/GitHub
* nivel de programación
* disponibilidad para trabajo fuera de clase
* interés en proyecto individual o en parejas si hiciera falta

Con base en eso, ajustar:

* complejidad de demos
* profundidad de prácticas
* nivel de uso de GitHub Projects
* expectativas de proyecto final

---

## 11. Riesgos del curso

Riesgos principales:

### Demasiada teoría

Mitigación:

* usar demos
* usar visualizaciones
* usar casos reales
* limitar slides densas

### Demasiada complejidad técnica

Mitigación:

* Docker Compose
* Dev Containers
* README claro
* demos pequeñas
* fallback

### Dependencia excesiva de IA

Mitigación:

* pedir evidencia
* pedir explicación
* pedir defensa
* evaluar tradeoffs

### Tiempo insuficiente

Mitigación:

* priorizar conceptos clave
* dejar lecturas opcionales
* mantener ejercicios pequeños
* no hacer demos demasiado largas

### Diferencia de nivel entre alumnos

Mitigación:

* ejercicios con core obligatorio y extras opcionales
* explicación visual
* trabajo por equipos si conviene
* revisión guiada

---

## 12. Resultado esperado del curso

Al finalizar, los alumnos deberían poder:

* explicar diferencias entre OLTP, OLAP, Warehouse y modelos alternativos
* diseñar modelos lógicos con restricciones razonables
* interpretar problemas básicos de transacciones y concurrencia
* diagnosticar una consulta lenta con evidencia
* justificar índices y tradeoffs
* explicar uso y riesgo de vistas/procedimientos/triggers
* diseñar un modelo multidimensional simple
* plantear un Data Mart o Warehouse básico
* contextualizar BDOO y ORMs
* usar IA como apoyo, no como sustituto del criterio
* defender decisiones técnicas con claridad

---

## TODO

* Definir herramientas permitidas para alumnos.
* Definir entregables mínimos por clase.
* Ajustar plan después de confirmar nivel real del grupo.
