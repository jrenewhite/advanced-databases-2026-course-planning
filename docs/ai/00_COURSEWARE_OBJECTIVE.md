# COURSEWARE_OBJECTIVE.md — Guía principal de courseware para IA

## Status

Draft inicial controlado por el instructor.

Este documento define la visión general, restricciones, alcance y criterios principales para crear el material de la materia **Sistemas Avanzados de Bases de Datos**.

Debe ser leído antes de cualquier tarea relacionada con planeación, generación de slides, demos, ejercicios, rúbricas, repositorios o materiales de clase.

---

## Purpose

Este documento funciona como la guía principal para Codex, ChatGPT u otras herramientas de IA al colaborar en la creación del curso.

Su propósito es evitar que la IA genere contenido genérico, excesivamente académico, demasiado teórico, sobrecomplicado o desconectado de la intención real del curso.

La IA debe apoyar como acelerador de producción, pero no debe reemplazar el criterio pedagógico ni técnico del instructor.

---

## 1. Contexto del curso

- Institución: TODO
- Materia: Sistemas Avanzados de Bases de Datos
- Nivel: posgrado
- Duración estimada: 10 sesiones
- Frecuencia: martes y jueves
- Horario: 19:00–21:00
- Duración por sesión: 2 horas
- Perfil esperado de estudiantes:
  - alumnos de posgrado
  - probablemente con formación académica sólida
  - posiblemente con experiencia limitada en ingeniería de software real
  - pueden conocer teoría, pero no necesariamente flujos reales de producción

---

## 2. Intención central del curso

El curso debe conectar la teoría académica de bases de datos con la práctica real de ingeniería.

La intención no es solo que los alumnos memoricen conceptos, sino que aprendan a razonar como engineers cuando trabajan con datos, sistemas transaccionales, rendimiento, concurrencia, diseño, analítica y modelos alternativos.

El curso debe responder preguntas como:

- ¿Por qué una base de datos funciona bien en desarrollo pero falla bajo carga?
- ¿Cómo se diagnostica una consulta lenta?
- ¿Qué tradeoffs tiene agregar un índice?
- ¿Cómo se razona sobre transacciones y concurrencia?
- ¿Cuándo conviene separar OLTP de OLAP?
- ¿Qué problemas resuelve un Data Warehouse?
- ¿Qué ideas de bases orientadas a objetos siguen vigentes y cuáles quedaron como contexto histórico?
- ¿Cómo se valida una sugerencia generada por IA antes de confiar en ella?

---

## 3. Filosofía pedagógica

El curso debe sentirse más como:

- workshop técnico
- engineering walkthrough
- architecture session
- live debugging session
- simulación ligera de trabajo real de ingeniería

Y menos como:

- clase tradicional basada solo en teoría
- presentación pesada de diapositivas
- lectura académica sin práctica
- curso de memorización
- curso donde copiar/pegar de IA sea suficiente

Priorizar:

- comprensión sobre memorización
- criterio profesional
- razonamiento técnico
- demos reproducibles
- visualizaciones
- problemas realistas
- debugging
- tradeoffs
- evidencia técnica
- explicación oral y escrita clara
- conexión entre teoría y producción

Evitar:

- walls of text
- slides saturadas
- exceso de definiciones sin aplicación
- teoría sin ejemplo
- demos frágiles
- dependencias innecesarias
- herramientas que requieran pago
- actividades que puedan resolverse copiando directamente de IA sin entender

---

## 4. Relación con el temario oficial

El curso debe cubrir el temario oficial de la materia.

El contenido puede modernizarse, contextualizarse y aterrizarse con ejemplos reales, pero no debe ignorar los bloques oficiales.

Bloques principales:

1. Bases de datos convencionales
2. Bases de datos multidimensionales
3. Bases de datos para la toma de decisiones
4. Bases de datos orientadas a objetos

La distribución de clases debe mapear explícitamente los temas oficiales contra las sesiones planeadas.

La cobertura detallada debe vivir en:

```txt
00-course-planning/docs/planning/SYLLABUS_COVERAGE_MATRIX.md
````

---

## 5. Principio de cobertura

No todos los temas requieren la misma profundidad.

La prioridad práctica del curso debe estar en:

* diseño lógico
* reglas de dominio
* transacciones
* concurrencia
* índices
* rendimiento
* vistas
* procedimientos almacenados
* triggers
* roles y seguridad
* connection pooling
* OLTP vs OLAP
* modelos multidimensionales
* Data Warehouse
* Data Mart
* OLAP
* Data Mining
* modelos orientados a objetos como contexto histórico y conceptual
* relación moderna con ORMs, documentos y otros modelos

Los temas más históricos, como ODMG u OO-DBMS clásicos, deben cubrirse con claridad, pero sin consumir tiempo desproporcionado si no aportan valor práctico equivalente.

---

## 6. Formato general de cada sesión

Cada sesión dura 2 horas.

Estructura sugerida:

### Primera parte

* contexto del problema
* concepto central
* explicación visual
* conexión con el temario oficial
* ejemplo real o production tale anonimizado

### Segunda parte

* demo o walkthrough
* ejercicio guiado
* discusión
* evidencia esperada
* recap

Las slides no deben ocupar toda la sesión.

La clase debe alternar entre explicación, visualización, demo y conversación.

---

## 7. Stack didáctico preferido

Usar preferentemente:

* Markdown para documentación
* Marp para presentaciones
* Docker Compose para demos reproducibles
* PostgreSQL como base principal de demos
* Dev Containers para reducir fricción de setup
* Git y ramas como parte del flujo didáctico
* GitHub Projects, issues y PRs para simular trabajo real
* Mermaid, Excalidraw, SVG o herramientas similares para diagramas
* animaciones solo cuando aporten claridad

Evitar:

* PowerPoint como fuente principal
* servicios de pago
* dependencias pesadas
* setups complejos
* frameworks innecesarios
* herramientas que distraigan del aprendizaje principal

---

## 8. Estrategia de repositorios

El curso se manejará con una estructura local base:

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

`00-course-planning/` contiene la planeación general, guardrails, matrices, decisiones y documentación transversal.

Cada carpeta `class-*` representa una sesión o módulo de clase y debe manejarse como su propio repositorio independiente.

Los repos `class-*` son para material de sesión:

* slides
* demos
* ejercicios guiados
* notas
* recursos de clase

Las tareas evaluables fuera de clase deben vivir en repos separados `assignment-*`.

En cada repo `assignment-*`, todos los alumnos parten de la misma base y cada alumno trabaja en su propia rama.

El proyecto final debe vivir en un repositorio separado creado o compartido por el alumno/equipo.

---

## 9. Estrategia de ramas

Cuando cada repo `class-*` sea independiente, usar ramas con intención pedagógica.

### main

Estado inicial o versión pública limpia.

Debe contener:

* README
* slides base
* setup mínimo
* ejercicios
* instrucciones
* TODOs razonables
* recursos necesarios para seguir la clase

No debe contener inicialmente:

* soluciones completas
* notas privadas del instructor
* spoilers
* respuestas finales
* material que invalide la práctica

### instructor

Rama privada o protegida.

Debe contener:

* solución completa
* notas del instructor
* fallback de demos
* scripts de recuperación
* animaciones completas
* resultados esperados
* explicación adicional
* posibles preguntas y respuestas

### live

Rama opcional para construir en clase.

Puede usarse para:

* trabajar incrementalmente
* hacer commits durante la sesión
* simular flujo real de ingeniería
* permitir que alumnos sigan el progreso
* recuperar con cherry-pick o commits preparados si algo falla

---

## 10. Estrategia de publicación

El contenido puede permanecer privado antes de la clase.

Después de impartir una sesión, se puede publicar:

* slides finales
* demo completada
* animaciones
* notas públicas
* ejercicios
* solución parcial o completa según convenga

La publicación posterior evita spoilers y permite ajustar el material con base en lo que ocurrió en clase.

---

## 11. Uso de IA en el curso

La IA está permitida como herramienta de aprendizaje y productividad.

La idea central es:

> La IA puede acelerar la implementación, pero el criterio profesional sigue siendo responsabilidad del engineer.

El curso debe enseñar a usar IA con criterio.

Los alumnos pueden usar IA, pero deben demostrar que entienden lo que hicieron.

La evaluación no debe basarse solo en si obtuvieron una respuesta, sino en si pueden:

* explicar la solución
* validar resultados
* medir antes y después
* detectar riesgos
* justificar decisiones
* discutir tradeoffs
* defender sus supuestos
* reconocer limitaciones

---

## 12. Reglas para actividades con IA

Diseñar actividades donde copiar/pegar de IA no sea suficiente.

Preferir problemas como:

* “esta consulta es lenta, diagnostica por qué”
* “este diseño produce inconsistencias, identifica el riesgo”
* “este índice mejora lectura pero afecta escrituras, explica el tradeoff”
* “esta transacción puede bloquear más de lo necesario, explica cómo reducir riesgo”
* “este modelo sirve para OLTP pero no para analítica, rediseña para reporting”

Pedir evidencia cuando aplique:

* consulta antes
* consulta después
* `EXPLAIN ANALYZE`
* tiempo antes/después
* diagrama
* hipótesis
* razonamiento
* tradeoffs
* limitaciones
* conclusión

---

## 13. Evaluación esperada

La evaluación debe ser fácil de revisar para el instructor y significativa para el alumno.

Debe favorecer:

* evidencia técnica
* razonamiento
* explicación
* proceso
* iteración
* defensa de decisiones
* conexión con conceptos del temario

Evitar depender solo de:

* PDFs largos
* definiciones memorizadas
* código sin explicación
* respuestas copiadas de IA
* entregables imposibles de revisar rápidamente

La guía detallada de evaluación debe vivir en:

```txt
00-course-planning/docs/ai/05_EVALUATION_GUIDELINES.md
```

---

## 14. GitHub Projects como simulación de ingeniería

GitHub Projects puede usarse como tablero tipo Kanban para representar actividades, prácticas y avances.

El tablero puede incluir columnas como:

* Backlog
* Ready
* In Progress
* Review
* Done
* Blocked

Las actividades pueden modelarse como issues.

Esto permite que los alumnos se acerquen a flujos reales:

* asignación de trabajo
* ownership
* avance incremental
* revisión
* evidencia
* cierre de tareas
* comunicación técnica

---

## 15. Demos

Las demos deben ser reproducibles y seguras.

Principios:

* deben poder correr localmente
* deben usar Docker Compose cuando sea útil
* deben tener datos seed
* deben incluir instrucciones claras
* deben tener fallback para el instructor
* deben evitar dependencias externas innecesarias
* deben ser entendibles aunque la demo falle

Preferir PostgreSQL para:

* transacciones
* concurrencia
* MVCC
* índices
* `EXPLAIN ANALYZE`
* views
* procedimientos / funciones
* triggers
* optimización

La guía detallada de demos debe vivir en:

```txt
00-course-planning/docs/ai/04_DEMO_GUIDELINES.md
```

---

## 16. Slides

Las slides deben hacerse con Markdown + Marp.

Principios:

* pocas ideas por slide
* una idea central por slide
* diagramas grandes
* texto mínimo
* visualizaciones antes que párrafos
* código solo cuando sea necesario
* memes permitidos con moderación
* recap claro al final

Las slides deben apoyar la explicación, no reemplazarla.

La guía detallada de slides debe vivir en:

```txt
00-course-planning/docs/ai/02_SLIDE_RULES.md
```

---

## 17. Tono y estilo

El curso debe mantener un tono:

* profesional
* claro
* práctico
* cercano
* orientado a ingeniería
* respetuoso del nivel de posgrado
* sin exceso de solemnidad

Se permite humor técnico moderado cuando refuerce el aprendizaje.

No usar humor ofensivo, excluyente o que distraiga.

---

## 18. Producción de contenido con Codex/IA

Cuando Codex o ChatGPT generen material, deben:

* leer primero los documentos en `00-course-planning/docs/ai/`
* respetar el plan en `00-course-planning/docs/planning/`
* producir mini-plan antes de cambios grandes
* no modificar archivos fuera del alcance solicitado
* no sobrescribir sin permiso
* no inventar requisitos institucionales
* no generar contenido excesivamente largo si se pidió estructura
* no generar soluciones finales en ramas o archivos student-facing sin instrucción explícita
* mantener el contenido en español salvo nombres técnicos, código o comandos
* explicar supuestos relevantes

---

## 19. Orden recomendado de construcción

Orden sugerido:

1. Definir guardrails del curso
2. Definir plan de 10 sesiones
3. Crear matriz de cobertura del temario oficial
4. Definir reglas de repositorios
5. Definir reglas de slides
6. Definir reglas de demos
7. Definir reglas de evaluación
8. Crear mapa clase → repo → tema → entregables
9. Preparar template base de clase
10. Crear contenido de clase 1
11. Validar estilo
12. Repetir para clases 2–10

No generar las 10 clases completas antes de validar la clase 1.

---

## 20. Restricciones importantes

No hacer:

* inventar requisitos institucionales
* cambiar el temario oficial
* ignorar temas del programa
* crear slides saturadas
* crear demos que dependan de servicios pagos
* sobrecomplicar con frameworks innecesarios
* asumir que todos los alumnos tienen experiencia real de ingeniería
* asumir que todos tienen setup local avanzado
* hacer que la IA sea el centro del curso
* generar soluciones completas sin autorización
* mezclar notas privadas del instructor con material público inicial

Sí hacer:

* mantener estructura clara
* mapear temario contra sesiones
* usar evidencia
* favorecer criterio profesional
* explicar tradeoffs
* usar demos reproducibles
* reducir fricción técnica
* preparar fallback
* diseñar actividades difíciles de resolver con copy/paste ciego

---

## 21. Definición de éxito

El curso será exitoso si los alumnos terminan con una mejor capacidad para:

* explicar conceptos avanzados de bases de datos
* relacionar teoría con problemas reales
* diagnosticar problemas de rendimiento
* razonar sobre transacciones y concurrencia
* distinguir OLTP, OLAP, Warehouse y modelos alternativos
* tomar decisiones técnicas con tradeoffs
* usar IA sin delegar criterio
* presentar evidencia técnica de sus decisiones
* defender soluciones de forma profesional
