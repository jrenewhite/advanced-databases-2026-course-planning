# 03_INSTRUCTOR_DECISIONS.md — Decisiones pendientes del instructor

## Status

Documento vivo.

Este archivo contiene preguntas, decisiones abiertas y respuestas del instructor para el curso **Sistemas Avanzados de Bases de Datos** de **UniVO**.

Codex/ChatGPT debe consultar este documento antes de asumir decisiones importantes.

---

## Purpose

El propósito de este documento es evitar que la IA invente decisiones pedagógicas, operativas o técnicas.

Cuando una decisión no esté definida, Codex debe:

1. identificarla como decisión pendiente
2. formular una pregunta concreta
3. esperar respuesta del instructor
4. actualizar este documento cuando el instructor responda

---

## Regla principal

> Si una decisión afecta evaluación, repositorios, publicación, herramientas, dinámica con alumnos o alcance del curso, Codex no debe asumirla.

Debe preguntar.

---

## Decisiones ya tomadas

### Repositorios por clase

**Decisión:** cada carpeta `class-*` debe convertirse en su propio repositorio independiente.

**Implicación:**

- `00-course-planning/` será el espacio de planeación general.
- Cada `class-*` podrá tener su propio Git.
- Cada clase podrá publicarse, versionarse y mantenerse de forma independiente.
- La estrategia de ramas `main`, `instructor` y opcionalmente `live` aplica por repositorio de clase.

**Estado:** decidido.

---

## Preguntas pendientes de alta prioridad

### 1. Evaluación institucional

**Pregunta:** ¿Se mantendrá exactamente la distribución del documento oficial?

```txt
Examen escrito          20%
Diagramas               10%
Prácticas laboratorio   30%
Proyecto final          30%
Reportes lectura        10%
````

**Estado:** pendiente.

---

### 2. Prácticas individuales o por equipo

**Decisión:** las prácticas seguirán un esquema mixto.

**Estrategia:**

- Las prácticas cortas serán individuales.
- Las prácticas más grandes podrán hacerse por equipo.
- El uso de equipos en prácticas grandes dependerá del tamaño y nivel real del grupo.

**Estado:** decidido.

---

### 3. Proyecto final individual o por equipo

**Decisión:** el proyecto final tendrá como default equipos de 2–3.

**Estrategia:**

- El formato por defecto será por equipos de 2–3.
- Si el grupo es pequeño, el proyecto final podrá hacerse de manera individual.
- La decisión final se tomará después de conocer al grupo.

**Estado:** decidido.

---

### 4. Herramientas permitidas para alumnos

**Pregunta:** ¿Qué herramientas serán obligatorias o recomendadas para alumnos?

Opciones posibles:

* GitHub
* GitHub Projects
* Docker
* Dev Containers
* VS Code
* DBeaver
* psql
* Marp
* IA generativa

**Estado:** pendiente.

---

### 5. Uso de GitHub Projects

**Decisión:** GitHub Projects será inicialmente herramienta del instructor.

**Estrategia:**

- No será obligatorio para alumnos al inicio.
- Puede incorporarse más adelante para alumnos/equipos si el grupo responde bien.

**Estado:** decidido.

---

### 6. Publicación de repositorios

**Decisión:** la publicación dependerá del tipo de repositorio y del momento del curso.

**Estrategia:**

- Los repos `class-*` pueden permanecer privados antes de clase.
- Los repos `class-*` se publicarán después de impartir y limpiar cada sesión, si conviene.
- Los repos `assignment-*` deben mantenerse privados o bajo acceso controlado.
- Los repos de proyecto final serán compartidos por alumnos/equipos con el instructor.

**Estado:** decidido.

---

### 7. Ramas por repositorio

**Decisión:** la rama `instructor` se creará cuando cada `class-*` se inicialice como repositorio independiente.

**Estado:** decidido.

---

### 8. Template repository

**Decisión:** por ahora se usarán templates locales en `00-course-planning/templates/`.

**Implicación:**

- No se creará un template repo formal todavía.
- La estrategia actual seguirá basada en templates locales dentro del repositorio de planeación.

**Estado:** decidido.

---

### 9. Herramienta principal para SQL

**Pregunta:** ¿La herramienta principal para ejecutar SQL será `psql`, DBeaver, VS Code SQLTools u otra?

**Estado:** pendiente.

---

### 10. Nivel real del grupo

**Pregunta:** ¿Qué tanto saben los alumnos de SQL, Docker, Git/GitHub y programación?

**Estado:** pendiente hasta primera clase.

---

### 11. Fechas reales del calendario

**Pregunta:** ¿Cuáles son las fechas exactas de clase y entregas?

**Estado:** pendiente.

---

### 12. Ajuste de horario jueves

**Pregunta:** ¿Se conservará jueves 19:00–21:00 o se ajustará con el grupo por posible conflicto laboral?

**Estado:** pendiente hasta primera clase.

---

## Preguntas pendientes de prioridad media

### 13. Marp theme

**Pregunta:** ¿Se usará un tema Marp custom desde el inicio o primero se trabajará con theme básico?

**Estado:** pendiente.

---

### 14. Paleta visual

**Pregunta:** ¿Qué paleta visual se usará para las slides?

**Estado:** pendiente.

---

### 15. Tipografías

**Pregunta:** ¿Se usarán tipografías default o alguna fuente específica disponible/legalmente redistribuible?

**Estado:** pendiente.

---

### 16. Animaciones

**Pregunta:** ¿Qué clases tendrán animaciones obligatorias y cuáles solo diagramas estáticos?

**Estado:** pendiente.

---

### 17. Datasets grandes

**Pregunta:** ¿Se permitirán datasets grandes generados localmente para demos de performance?

**Estado:** pendiente.

---

### 18. Defensa oral

**Pregunta:** ¿Habrá defensa oral breve para prácticas/proyecto o solo entrega escrita?

**Estado:** pendiente.

---

### 19. Actividades fuera de clase

**Decisión:** las actividades fuera de clase/tareas no vivirán dentro de los repos `class-*`.

**Estrategia:**

- Cada tarea o práctica fuera de clase podrá tener su propio repositorio `assignment-*`.
- Todos los alumnos partirán de la misma base.
- Cada alumno trabajará en su propia rama dentro del repo de la tarea.
- Esto facilita comparar avances, revisar ramas y evaluar con una base común.

**Estado:** decidido.

**Implicación:**

- Los repos `class-*` se enfocan en material de sesión, slides, demos y ejercicios guiados.
- Los repos `assignment-*` se enfocan en entregables evaluables fuera de clase.
- Las instrucciones de cada tarea deben indicar convención de rama por alumno.

---

### 20.  Proyecto final

**Decisión:** cada proyecto final debe ser un repositorio separado creado o compartido por los alumnos.

**Estrategia:**

- Cada alumno o equipo tendrá su propio repo de proyecto.
- El alumno/equipo debe compartir el repo con el instructor o enviar el enlace según se defina.
- El proyecto final no debe vivir dentro de los repos `class-*`.
- El proyecto final puede reutilizar aprendizajes, estructura o ideas de las clases, pero debe tener ownership propio.

**Estado:** decidido.

**Implicación:**

- La evaluación del proyecto se hará sobre el repo compartido por el alumno/equipo.
- Debe existir un template o checklist mínimo de proyecto final.
- Debe definirse convención de entrega: link al repo, README, evidencia, defensa y uso de IA.

---

### 21. Convención de ramas para tareas

**Decisión:** la convención para ramas de alumnos en repos `assignment-*` será:

```txt
student/<github-username>
```

**Estado:** decidido.

---

## Regla para Codex

Cuando Codex encuentre un TODO relacionado con una decisión pendiente:

* no debe resolverlo por su cuenta
* debe agregar una pregunta clara en este documento
* puede proponer opciones
* debe esperar respuesta del instructor
* después de recibir respuesta, debe actualizar la sección correspondiente

---

## Formato para nuevas decisiones

Usar este formato:

```md
### N. Nombre de la decisión

**Pregunta:** texto de la pregunta.

**Opciones:**

- Opción A
- Opción B
- Opción C

**Respuesta del instructor:** pendiente.

**Estado:** pendiente / decidido.

**Implicación:** pendiente.
