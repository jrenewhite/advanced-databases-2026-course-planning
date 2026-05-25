# 01_AI_COLLABORATION.md — Reglas de colaboración con IA

## Status

Draft inicial controlado por el instructor.

Este documento define cómo deben colaborar Codex, ChatGPT u otras herramientas de IA en la creación, mantenimiento y revisión del material del curso **Sistemas Avanzados de Bases de Datos** de **UniVO**.

Debe leerse después de:

```txt
00-course-planning/docs/ai/00_COURSEWARE_OBJECTIVE.md
````

---

## Purpose

El propósito de este documento es establecer límites claros para el uso de IA durante la creación del curso.

La IA debe funcionar como acelerador de producción, asistente de estructuración y apoyo técnico, pero no debe reemplazar:

* el criterio del instructor
* la intención pedagógica
* el alineamiento con el temario oficial
* la revisión técnica
* la toma de decisiones académicas
* la validación de exactitud

La IA debe ayudar a producir material consistente, simple, mantenible y útil para clase.

---

## 1. Principio central

La regla principal para cualquier colaboración con IA es:

> La IA puede acelerar la producción, pero el instructor conserva el criterio pedagógico y técnico.

Esto aplica tanto para el instructor como para los alumnos.

El curso debe modelar un uso profesional de IA: útil, pragmático, verificable y responsable.

---

## 2. Rol esperado de la IA

La IA puede ayudar con:

* estructurar documentos
* generar scaffolding de repositorios
* crear borradores de slides
* proponer demos
* generar datos seed ficticios
* crear diagramas iniciales
* escribir README iniciales
* proponer ejercicios
* proponer issues para GitHub Projects
* revisar claridad de instrucciones
* sugerir actividades de evidencia
* convertir ideas en Markdown
* generar comandos repetitivos
* preparar plantillas
* detectar inconsistencias en la planeación
* resumir contenido técnico
* proponer preguntas de discusión
* proponer rúbricas iniciales

La IA no debe ser tratada como fuente final de verdad.

---

## 3. Lo que la IA no debe hacer

La IA no debe:

* inventar requisitos institucionales
* alterar el temario oficial
* ignorar temas del programa
* generar clases completas sin validación previa
* crear soluciones finales en material student-facing sin autorización
* mezclar notas privadas del instructor con material público
* sobrecomplicar demos
* introducir herramientas pagas sin autorización
* asumir que todos los alumnos tienen experiencia real de industria
* asumir que todos dominan Docker, Git, SQL o programación avanzada
* usar IA como centro del curso
* producir slides saturadas de texto
* crear actividades que puedan resolverse solo con copiar/pegar
* modificar archivos fuera del alcance solicitado
* sobrescribir archivos existentes sin autorización
* hacer cambios masivos sin mini-plan
* inventar resultados de performance
* inventar comportamiento de PostgreSQL sin validarlo
* presentar tradeoffs como reglas absolutas

---

## 4. Modo de trabajo esperado

Antes de ejecutar cambios grandes, la IA debe producir un mini-plan.

El mini-plan debe incluir:

* objetivo de la tarea
* archivos que propone modificar
* archivos que propone crear
* decisiones asumidas
* riesgos o puntos por confirmar
* resultado esperado

Después de recibir aprobación, puede generar o modificar contenido.

Para cambios pequeños y explícitos, puede ejecutar directamente si el alcance está claro.

---

## 5. Regla de alcance

La IA debe respetar estrictamente el alcance de la tarea.

Ejemplos:

Si la tarea dice:

> Actualiza únicamente `01_AI_COLLABORATION.md`.

Entonces no debe modificar:

* otros documentos en `docs/ai`
* documentos en `docs/planning`
* carpetas `class-*`
* scripts
* slides
* demos

Si considera que otro archivo también debería cambiar, debe reportarlo como sugerencia, no modificarlo.

---

## 6. Regla de no sobrescritura

La IA no debe sobrescribir archivos existentes sin autorización explícita.

Cuando encuentre un archivo existente, debe:

1. reportarlo
2. resumir su contenido o propósito
3. proponer cambios
4. esperar confirmación si el cambio no fue solicitado explícitamente

Esta regla es especialmente importante para:

* guardrails
* documentos de planeación
* slides ya revisadas
* soluciones de instructor
* rúbricas
* materiales publicados

---

## 7. Relación con el temario oficial

La IA debe respetar el temario oficial cargado por el instructor.

Puede modernizar ejemplos, pero no debe eliminar cobertura.

Cuando proponga contenido, debe poder explicar qué parte del temario cubre.

Si un tema parece antiguo o poco usado en industria, la IA puede sugerir cubrirlo como:

* contexto histórico
* comparación con modelos modernos
* discusión conceptual
* puente hacia herramientas actuales

Pero no debe omitirlo sin instrucción explícita.

---

## 8. Idioma y tono

El contenido del curso debe estar principalmente en español.

Se permiten términos técnicos en inglés cuando sean naturales en ingeniería, por ejemplo:

* query plan
* connection pool
* deadlock
* rollback
* commit
* warehouse
* data mart
* issue
* pull request
* live demo
* production incident
* tradeoff

El tono debe ser:

* profesional
* claro
* directo
* práctico
* cercano
* orientado a ingeniería
* respetuoso del nivel de posgrado

Evitar:

* solemnidad excesiva
* chistes ofensivos
* lenguaje excluyente
* explicaciones innecesariamente largas
* tono condescendiente
* academicismo pesado cuando no aporte

---

## 9. Uso de IA para slides

Cuando la IA genere slides, debe seguir:

```txt
00-course-planning/docs/ai/02_SLIDE_RULES.md
```

Reglas generales:

* usar Marp
* usar Markdown
* evitar exceso de texto
* priorizar diagramas
* generar slides como apoyo, no como guion completo
* no crear decks enormes
* no abusar de memes
* no saturar con código
* incluir recap
* incluir conexión con demo o ejercicio

---

## 10. Uso de IA para repositorios

Cuando la IA genere estructura de repos, debe seguir:

```txt
00-course-planning/docs/ai/03_REPOSITORY_RULES.md
```

Reglas generales:

* mantener estructura simple
* no introducir dependencias innecesarias
* respetar nombres de carpetas
* separar material público de material del instructor
* no generar soluciones completas en ramas o carpetas públicas sin autorización
* preparar README claro
* usar commits pequeños cuando se trabaje con Git

---

## 11. Uso de IA para demos

Cuando la IA genere demos, debe seguir:

```txt
00-course-planning/docs/ai/04_DEMO_GUIDELINES.md
```

Reglas generales:

* preferir PostgreSQL
* preferir Docker Compose
* incluir datos seed
* incluir instrucciones claras
* evitar dependencias externas
* preparar fallback
* evitar demos demasiado frágiles
* no inventar resultados de performance
* incluir evidencia reproducible cuando aplique

---

## 12. Uso de IA para evaluación

Cuando la IA proponga actividades evaluables, debe seguir:

```txt
00-course-planning/docs/ai/05_EVALUATION_GUIDELINES.md
```

Reglas generales:

* evaluar razonamiento, no solo resultado
* pedir evidencia
* pedir explicación de tradeoffs
* permitir IA, pero exigir validación
* evitar tareas triviales de copiar/pegar
* facilitar revisión del instructor
* usar GitHub Issues/Projects cuando aporte claridad

---

## 13. Buenas tareas para IA

Son buenas tareas para IA:

* “Genera un primer borrador de README para esta clase usando la estructura aprobada.”
* “Propón 5 issues realistas para practicar índices.”
* “Crea un dataset pequeño para demostrar una query lenta.”
* “Convierte este plan en slides Marp minimalistas.”
* “Genera una matriz de cobertura entre estos temas y estas sesiones.”
* “Propón preguntas de defensa oral para este ejercicio.”
* “Revisa si este demo tiene dependencias innecesarias.”
* “Simplifica este texto para estudiantes con poca experiencia de industria.”
* “Genera un checklist de evidencia para esta práctica.”

---

## 14. Malas tareas para IA

Son malas tareas para IA:

* “Haz todo el curso.”
* “Genera las 10 clases completas.”
* “Llena todos los guardrails como consideres.”
* “Inventa una rúbrica.”
* “Crea una demo compleja con múltiples servicios sin explicar por qué.”
* “Haz slides muy completas para que no tenga que explicar.”
* “Optimiza esta query y asume que quedó mejor sin medir.”
* “Cambia todos los repos como creas conveniente.”
* “Agrega tecnologías modernas aunque no sean necesarias.”

---

## 15. Regla de evidencia

Cuando la IA proponga una solución técnica, debe incluir cómo validarla.

Ejemplos:

Para performance:

* query antes
* query después
* `EXPLAIN ANALYZE`
* comparación
* tradeoff

Para concurrencia:

* pasos para reproducir
* sesiones concurrentes
* comportamiento esperado
* posible riesgo
* estrategia de mitigación

Para diseño:

* diagrama
* supuestos
* justificación
* alternativas
* limitaciones

Para warehouse:

* modelo conceptual
* granularidad
* dimensiones
* hechos
* consultas esperadas

---

## 16. Regla de simplicidad

La IA debe preferir la solución más simple que cumpla el objetivo pedagógico.

No agregar:

* microservicios innecesarios
* colas innecesarias
* frameworks frontend innecesarios
* observabilidad compleja si no es el tema
* orquestación avanzada
* cloud services
* autenticación real si no es necesaria
* CI/CD complejo si no aporta a la clase

La complejidad solo se agrega cuando enseña explícitamente algo del temario.

---

## 17. Regla de separación público / instructor

La IA debe distinguir entre:

### Material student-facing

Puede incluir:

* README
* slides base
* ejercicios
* setup
* datos iniciales
* instrucciones
* TODOs

No debe incluir inicialmente:

* soluciones completas
* notas privadas
* respuestas
* scripts de shortcut
* resultados esperados detallados si invalidan la práctica

### Material instructor-facing

Puede incluir:

* soluciones
* respuestas esperadas
* notas de conducción
* fallback de demos
* troubleshooting
* preguntas para defensa
* criterios de revisión
* rutas alternativas

---

## 18. Regla de producción incremental

No generar demasiado contenido de una sola vez.

Preferir el flujo:

1. plan
2. estructura
3. borrador pequeño
4. revisión
5. ajuste
6. expansión
7. validación

Especialmente para:

* slides
* demos
* rúbricas
* templates de clase
* scripts
* actividades evaluables

---

## 19. Regla para prompts futuros

Cuando se pida a Codex trabajar sobre este curso, el prompt debe indicar:

* archivo(s) a leer primero
* archivo(s) a modificar
* archivo(s) que no debe tocar
* objetivo de la tarea
* nivel de detalle esperado
* si debe crear mini-plan antes
* si puede ejecutar cambios o solo proponer
* si el contenido es student-facing o instructor-facing

Ejemplo:

```md
Lee primero:

- 00-course-planning/docs/ai/00_COURSEWARE_OBJECTIVE.md
- 00-course-planning/docs/ai/01_AI_COLLABORATION.md

Modifica únicamente:

- 00-course-planning/docs/planning/00_COURSE_PLAN.md

No modifiques carpetas class-*.

Primero propón un mini-plan.
Después espera confirmación.
```

---

## 20. Checklist antes de aceptar contenido generado por IA

Antes de aceptar contenido generado por IA, revisar:

* ¿Respeta el temario oficial?
* ¿Respeta el objetivo del curso?
* ¿Está en español claro?
* ¿Es demasiado largo?
* ¿Es demasiado académico?
* ¿Tiene aplicación práctica?
* ¿Pide evidencia?
* ¿Evita copiar/pegar ciego?
* ¿Reduce fricción técnica?
* ¿No sobrecomplica?
* ¿Distingue material público de material instructor?
* ¿Incluye supuestos?
* ¿Evita inventar resultados?
* ¿Puede revisarse en poco tiempo?

---

## TODO

* Conectar estas reglas con prompts reutilizables.
* Crear ejemplos de prompts buenos y malos.
* Definir convenciones de nombres para tareas de Codex.
* Definir cuándo una tarea requiere mini-plan obligatorio.
