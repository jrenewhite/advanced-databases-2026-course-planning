# 05_EVALUATION_GUIDELINES.md — Reglas de evaluación y evidencia

## Status

Draft inicial controlado por el instructor.

Este documento define los principios, criterios y formatos recomendados para evaluar actividades, laboratorios, participación y proyecto final en el curso **Sistemas Avanzados de Bases de Datos** de **UniVO**.

Debe leerse después de:

```txt
00-course-planning/docs/ai/00_COURSEWARE_OBJECTIVE.md
00-course-planning/docs/ai/01_AI_COLLABORATION.md
00-course-planning/docs/ai/02_SLIDE_RULES.md
00-course-planning/docs/ai/03_REPOSITORY_RULES.md
00-course-planning/docs/ai/04_DEMO_GUIDELINES.md
````

---

## Purpose

El propósito de este documento es definir una evaluación práctica, clara y revisable, que mida comprensión real y criterio técnico.

La evaluación debe evitar depender únicamente de memorización, entregables largos o respuestas copiadas de IA.

Debe favorecer evidencia, razonamiento, explicación y defensa de decisiones.

---

## 1. Principio central

La regla principal es:

> Evaluar el criterio profesional, no solo el resultado final.

En bases de datos avanzadas, muchas decisiones no son absolutas.

Una buena evaluación debe observar si el alumno puede:

* explicar qué hizo
* justificar por qué lo hizo
* mostrar evidencia
* identificar tradeoffs
* reconocer riesgos
* conectar la solución con el temario
* defender su decisión técnicamente

---

## 2. Alineación con evaluación institucional

El documento oficial de la materia contempla una evaluación distribuida en:

* examen escrito
* elaboración de diagramas
* prácticas en laboratorio
* proyecto final
* reportes de lectura

Esta guía propone aterrizar esos rubros de forma práctica y orientada a ingeniería.

Distribución sugerida:

```txt 
Examen / defensa técnica       20%
Diagramas                      10%
Prácticas de laboratorio       30%
Proyecto final                 30%
Reportes / notas técnicas      10%
```

La distribución puede ajustarse si UniVO indica un criterio específico.

No inventar cambios institucionales sin autorización.

---

## 3. Evaluación basada en evidencia

Cuando una actividad sea técnica, el alumno debe entregar evidencia.

La evidencia puede incluir:

* query original
* query modificada
* `EXPLAIN`
* `EXPLAIN ANALYZE`
* plan antes
* plan después
* tiempos observados
* diagrama
* screenshots propios
* logs relevantes
* descripción de pasos
* hipótesis
* conclusión
* tradeoffs
* limitaciones

La evidencia debe ser suficiente para que el instructor revise sin tener que reconstruir todo desde cero.

---

## 4. Uso de IA por alumnos

La IA está permitida como herramienta de apoyo.

Pero el alumno debe demostrar comprensión.

No aceptar como suficiente:

```md 
Usé ChatGPT y me dijo que hiciera esto.
```

Aceptar mejor:

```md 
Usé IA para proponer alternativas, pero validé la solución con EXPLAIN ANALYZE.
Elegí este índice porque la consulta filtra por customer_id y ordena por created_at.
El plan cambió de sequential scan a index scan.
Tradeoff: aumenta costo de escritura y almacenamiento.
```

La evaluación debe penalizar dependencia ciega de IA cuando no exista explicación o validación.

---

## 5. Criterios transversales

En cualquier actividad, evaluar:

### Claridad

* ¿Se entiende qué hizo?
* ¿Explica el problema?
* ¿Explica la solución?

### Evidencia

* ¿Muestra datos, planes, diagramas o resultados?
* ¿La evidencia respalda la conclusión?

### Razonamiento

* ¿Justifica decisiones?
* ¿Conecta con conceptos del curso?

### Tradeoffs

* ¿Reconoce costos, riesgos o limitaciones?
* ¿Evita presentar la solución como universal?

### Profesionalismo

* ¿El entregable está ordenado?
* ¿Sigue instrucciones?
* ¿Usa nombres claros?
* ¿Puede defenderlo oralmente?

---

## 6. Prácticas de laboratorio

Las prácticas deben ser pequeñas, frecuentes y revisables.

Las prácticas guiadas dentro de `class-*` no son lo mismo que las tareas evaluables fuera de clase.

Los repos `class-*` se enfocan en material de sesión, demos y ejercicios guiados.

Las tareas evaluables fuera de clase deben vivir en repos `assignment-*`.

En cada repo `assignment-*`, todos los alumnos parten de la misma base.

Cada alumno debe trabajar en su propia rama dentro del repo de la tarea.

GitHub Issues puede usarse como apoyo cuando convenga, pero no debe asumirse como obligatorio para todos los alumnos/equipos mientras esa decisión siga pendiente.

Cada práctica debe tener:

* objetivo
* contexto
* instrucciones
* evidencia esperada
* criterios de aceptación
* relación con tema oficial

Ejemplo:

```md 
## Issue: Investigar consulta lenta

### Contexto
La búsqueda de órdenes por cliente tarda más de lo esperado.

### Tarea
Usa EXPLAIN ANALYZE para identificar el problema y propone una mejora.

### Evidencia
- Query original
- Plan antes
- Cambio propuesto
- Plan después
- Tradeoff identificado
```

---

## 7. Evaluación de prácticas

Rúbrica sugerida para práctica técnica:

```txt 
Comprensión del problema       20%
Evidencia técnica              30%
Solución propuesta             20%
Tradeoffs y riesgos            20%
Claridad de entrega            10%
```

No todas las prácticas necesitan rúbrica formal, pero sí deben tener criterios claros.

---

## 8. Diagramas

Los diagramas deben evaluar comprensión estructural.

Pueden incluir:

* modelo lógico
* ERD
* diagrama de transacciones
* diagrama de concurrencia
* diagrama OLTP vs OLAP
* modelo dimensional
* star schema
* flujo de warehouse
* mapa ORM / objeto-relacional
* arquitectura de acceso a datos

Evaluar:

* claridad
* correctitud
* nivel de abstracción
* relación con el problema
* explicación de decisiones
* supuestos

Rúbrica sugerida:

```txt 
Correctitud técnica            40%
Claridad visual                25%
Justificación                  25%
Supuestos / limitaciones       10%
```

---

## 9. Reportes / notas técnicas

Los reportes deben ser breves.

Preferir notas tipo engineering note o mini postmortem sobre ensayos largos.

Formato sugerido:

```md 
# Nota técnica

## Problema

## Observación

## Evidencia

## Decisión

## Tradeoffs

## Conclusión
```

Objetivo:

* fomentar pensamiento estructurado
* evitar texto innecesario
* facilitar revisión
* conectar teoría con práctica

---

## 10. Examen o defensa técnica

El componente de examen puede manejarse como:

* examen escrito breve
* quiz conceptual
* defensa oral
* revisión técnica de una práctica
* combinación de preguntas escritas y explicación

La evaluación debe medir:

* conceptos clave
* razonamiento
* capacidad de explicar
* identificación de tradeoffs
* lectura de evidencia técnica

Ejemplos de preguntas:

```txt 
¿Por qué un índice puede mejorar lecturas pero empeorar escrituras?
¿Qué diferencia práctica hay entre OLTP y OLAP?
¿Qué riesgo introduce un trigger?
¿Cómo detectarías un problema de concurrencia?
¿Por qué una solución generada por IA debe validarse?
```

---

## 11. Proyecto final

El proyecto final debe comprender alguno de los modelos de base de datos analizados en el curso.

Debe presentarse y defenderse.

Debe vivir en un repo separado del alumno/equipo.

No debe vivir dentro de `class-*` ni dentro de `assignment-*`, salvo instrucción futura explícita.

El proyecto no tiene que ser enorme.

Debe demostrar:

* diseño
* uso de conceptos del curso
* evidencia
* razonamiento
* tradeoffs
* claridad de comunicación

Opciones aceptables:

* mini sistema OLTP con transacciones, constraints e índices
* rediseño de una base para mejorar reporting
* modelo dimensional para toma de decisiones
* comparación OLTP vs OLAP
* análisis de performance de queries
* diseño con modelo alternativo y justificación
* caso integrador con PostgreSQL y documentación

---

## 12. Proyecto final desde el inicio

Aunque el documento oficial no exige explicar el proyecto desde la primera clase, es recomendable presentarlo temprano.

Objetivo:

* evitar sorpresas
* permitir que las prácticas alimenten el proyecto
* facilitar planeación
* mejorar calidad final
* reducir improvisación

Presentación sugerida:

* Clase 1: explicar expectativa general
* Clases 2–8: prácticas que pueden aportar al proyecto
* Clase 9: revisión de avance o preparación
* Clase 10: cierre, defensa o integración

Esto puede ajustarse según logística real del grupo.

---

## 13. Evaluación del proyecto final

Rúbrica sugerida:

```txt 
Problema y contexto            15%
Diseño de base de datos        20%
Uso de conceptos del curso     20%
Evidencia técnica              20%
Tradeoffs y justificación      15%
Presentación / defensa         10%
```

El proyecto debe penalizar:

* falta de explicación
* falta de evidencia
* dependencia ciega de IA
* diseño incoherente
* ausencia de tradeoffs
* entregable imposible de revisar

---

## 14. GitHub Projects como apoyo de evaluación

GitHub Projects puede usarse para dar seguimiento a:

* issues asignados
* estado de avance
* entregas
* bloqueos
* revisiones
* evidencia
* participación

Su uso como requisito para todos los alumnos/equipos sigue pendiente y no debe asumirse aquí.

Columnas sugeridas:

```txt 
Backlog
Ready
In Progress
Review
Done
Blocked
```

Evaluar con cuidado:

* no solo mover tarjetas
* revisar evidencia real
* revisar comentarios
* revisar entregables
* pedir defensa cuando sea necesario

---

## 15. Issues evaluables

Si se usan issues evaluables, deben asociarse preferentemente a repos `assignment-*` o al flujo de seguimiento del instructor, no al material base de `class-*`.

Un issue evaluable debe tener:

* título claro
* contexto
* tarea concreta
* evidencia esperada
* criterios de aceptación
* fecha o sesión asociada si aplica

Ejemplo:

```md 
# Issue: Diseñar modelo dimensional simple

## Contexto
El sistema OLTP permite registrar ventas, pero reporting es lento y difícil.

## Tarea
Diseña un modelo dimensional para analizar ventas por fecha, producto y sucursal.

## Evidencia esperada
- Diagrama star schema
- Tabla de hechos
- Dimensiones
- Granularidad
- 2 consultas analíticas ejemplo
- Tradeoffs
```

---

## 16. Criterios de aceptación

Los criterios de aceptación deben ser claros y revisables.

Ejemplo:

```md 
## Acceptance Criteria

- Incluye query original.
- Incluye EXPLAIN ANALYZE antes.
- Propone un cambio.
- Incluye EXPLAIN ANALYZE después.
- Explica al menos un tradeoff.
```

Evitar criterios vagos como:

```txt 
Que esté bien.
Que funcione.
Que investigue.
```

---

## 17. Defensa oral breve

Para evitar copy/paste ciego, usar defensas breves.

Preguntas útiles:

* ¿Por qué elegiste esa solución?
* ¿Qué alternativa descartaste?
* ¿Qué evidencia respalda tu conclusión?
* ¿Qué cambiaría con más datos?
* ¿Qué riesgo introduce tu solución?
* ¿Qué parte te ayudó a resolver la IA?
* ¿Cómo validaste que la IA no estaba equivocada?

Una defensa de 3–5 minutos puede revelar rápidamente comprensión real.

---

## 18. Penalizaciones comunes

Penalizar:

* no entregar evidencia
* no explicar decisiones
* no seguir instrucciones
* entregar contenido generado por IA sin validación
* inventar resultados
* copiar contenido sin citar
* usar datos reales no autorizados
* no poder defender la solución
* no reconocer tradeoffs
* entregar archivos desordenados o imposibles de correr

---

## 19. Qué no sobrepenalizar

No sobrepenalizar:

* errores honestos si hay buen razonamiento
* resultados de performance distintos por máquina
* sintaxis menor si el concepto es correcto
* soluciones diferentes si están bien justificadas
* uso declarado y validado de IA
* limitaciones técnicas razonables

El curso debe enseñar criterio, no castigar exploración razonable.

---

## 20. Evidencia mínima por tipo de tema

### Diseño lógico

* diagrama
* entidades
* relaciones
* constraints
* supuestos

### Reglas de dominio

* regla
* implementación
* ejemplo válido
* ejemplo inválido

### Transacciones

* pasos
* comportamiento observado
* explicación de aislamiento
* riesgo

### Concurrencia

* escenario
* bloqueo/conflicto
* evidencia
* mitigación

### Índices/performance

* query antes
* plan antes
* cambio
* plan después
* tradeoff

### Views/procedures/triggers

* objeto creado
* caso de uso
* ejemplo
* riesgo o limitación

### Seguridad/roles

* usuario/rol
* permisos
* prueba de acceso permitido/denegado

### Multidimensional/OLAP

* dimensiones
* medidas
* jerarquías
* consulta agregada

### Warehouse/Data Mart

* modelo
* fuente
* transformación
* granularidad
* consulta de decisión

### BDOO/modelos modernos

* concepto
* comparación
* caso de uso
* limitaciones

---

## 21. Formato recomendado de entrega

Preferir entregas en Markdown.

En tareas fuera de clase, la entrega debe vivir dentro del repo `assignment-*` correspondiente, en la rama del alumno.

En proyecto final, la entrega debe vivir en el repo separado del alumno/equipo.

Formato sugerido:

```md 
# Entrega — Clase XX

## Problema

## Solución propuesta

## Evidencia

## Tradeoffs

## Uso de IA

## Conclusión
```

La sección “Uso de IA” puede decir:

```md 
Usé IA para generar alternativas iniciales.
Validé la propuesta con EXPLAIN ANALYZE.
Descarté una alternativa porque...
```

O:

```md 
No usé IA en esta actividad.
```

---

## 22. Checklist de revisión rápida

Para revisar una entrega rápido:

* ¿Entendió el problema?
* ¿Incluyó evidencia?
* ¿La evidencia respalda la conclusión?
* ¿Explicó tradeoffs?
* ¿El entregable está ordenado?
* ¿Declaró uso de IA?
* ¿Puede defenderlo?
* ¿Está conectado al tema de clase?

---

## 23. Reglas para Codex/IA

Cuando Codex proponga evaluaciones:

* debe pedir evidencia
* debe evitar tareas memorísticas puras
* debe evitar actividades resolubles con copy/paste
* debe incluir criterios de aceptación
* debe facilitar revisión del instructor
* debe conectar con el temario oficial
* debe permitir uso de IA con validación
* debe incluir preguntas de defensa cuando aplique
* no debe inventar política institucional
* no debe crear rúbricas excesivamente complejas

---

## TODO

* Confirmar si la distribución institucional será exactamente 20/10/30/30/10.
* Definir si las prácticas serán individuales o por equipo.
* Definir si el proyecto final será individual o por equipo.
* Crear template de issue evaluable.
* Crear template de entrega en Markdown.
* Crear rúbrica corta para defensa oral.
* Definir convención exacta de ramas para alumnos en repos `assignment-*`.
