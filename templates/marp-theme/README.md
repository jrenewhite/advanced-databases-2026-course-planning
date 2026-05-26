# Marp Theme Reusable

## Status

Theme reusable para presentaciones del curso **Sistemas Avanzados de Bases de Datos**.

## Purpose

Proveer un theme Marp oscuro, tecnico, limpio y legible para las presentaciones del curso.

El objetivo es:

* mantener consistencia visual entre clases
* reducir friccion al crear nuevas presentaciones
* priorizar claridad, ritmo y lectura en pantalla
* evitar dependencia de internet o assets externos

## Archivos

* `univo-advanced-db.css`: theme Marp principal
* `example.md`: ejemplo generico para validar estilos

## Como Usarlo Desde Una Clase

Dentro de `slides/session.md`, usar frontmatter compatible con Marp:

```yaml
---
marp: true
theme: univo-advanced-db
paginate: true
---
```

Luego exportar indicando explicitamente el archivo CSS del theme.

Ejemplos:

```bash
marp slides/session.md --theme ../../00-course-planning/templates/marp-theme/univo-advanced-db.css --html --output slides/session.html
marp slides/session.md --theme ../../00-course-planning/templates/marp-theme/univo-advanced-db.css --pdf --output slides/session.pdf
```

La ruta puede requerir ajuste segun la ubicacion real del archivo `session.md`.

## Clases CSS Disponibles

* `lead`: portada o slide de apertura
* `section`: separador de seccion
* `two-columns`: layout de dos columnas
* `quote`: callout neutro o cita
* `warning`: advertencia o riesgo
* `success`: resultado correcto o takeaway positivo
* `exercise`: actividad o reto
* `recap`: cierre y resumen
* `small`: reducir tipografia sin perder legibilidad
* `tiny`: contenido muy corto con tipografia mas compacta

## Reglas de Estilo

* dark theme por defecto
* alta legibilidad sobre fondo oscuro
* tipografia local del sistema, sin descargas externas
* acento visual tecnico, sobrio y limpio
* codigo corto y tablas simples deben leerse bien
* usar referencias externas solo como inspiracion general
* no copiar layouts, frases, screenshots, imagenes ni marcas visuales de terceros

## Exportacion Recomendada

Para validar rapido el theme:

```bash
marp 00-course-planning/templates/marp-theme/example.md --theme 00-course-planning/templates/marp-theme/univo-advanced-db.css --html --output /tmp/marp-theme-example.html
```

## Limitaciones

* el theme no incluye fuentes externas ni logos
* el theme no incluye imagenes ni assets remotos
* `two-columns` funciona mejor con contenido breve por columna
* `tiny` debe usarse solo en casos puntuales
* el theme no reemplaza el criterio pedagogico sobre densidad de contenido

## TODO

* TODO: ajustar detalles finos despues de ver exportaciones reales.
* TODO: revisar contraste final en proyector o pantalla de aula.
