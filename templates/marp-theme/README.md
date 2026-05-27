# Theme Marp Reusable

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

* `advanced-db-dark.css`: theme Marp principal
* `example.md`: demostracion visual del theme con layout editorial
* `patterns.md`: libreria reusable de patrones genericos para copiar hacia `slides/session.md`

## Como Usarlo Desde Una Clase

Dentro de `slides/session.md`, usar frontmatter compatible con Marp:

```yaml
---
marp: true
theme: advanced-db-dark
paginate: true
---
```

Luego exportar registrando explicitamente el archivo CSS del theme.

Ejemplos:

```bash
marp slides/session.md --theme-set ../../00-course-planning/templates/marp-theme/advanced-db-dark.css --html --output slides/session.html
marp slides/session.md --theme-set ../../00-course-planning/templates/marp-theme/advanced-db-dark.css --pdf --output slides/session.pdf
```

La ruta puede requerir ajuste segun la ubicacion real del archivo `session.md`.

## Clases CSS Disponibles

* `lead`: portada o slide de apertura
* `hero`: portada editorial o slide de statement grande
* `agenda`: ruta o agenda de sesion
* `section`: separador de seccion
* `two-columns`: layout de dos columnas
* `guide-question`: pregunta guia
* `quote`: callout neutro o cita
* `real-world`: problema real o contexto de produccion
* `incident`: production tale o incidente anonimizado
* `tradeoff`: comparacion beneficio vs costo
* `before-after`: comparaciones antes/despues u OLTP/OLAP
* `demo`: setup o pasos de demo
* `evidence`: evidencia esperada
* `ai-judgment`: uso permitido de IA con criterio obligatorio
* `workflow`: workflow tecnico, repo workflow o timeline simple
* `checklist`: checklist de validacion o revision
* `anti-pattern`: warning o anti-pattern
* `warning`: advertencia o riesgo
* `success`: resultado correcto o takeaway positivo
* `exercise`: actividad o reto
* `recap`: cierre y resumen
* `next`: teaser de la siguiente clase
* `small`: reducir tipografia sin perder legibilidad
* `tiny`: contenido muy corto con tipografia mas compacta
* `kicker`: subtitulo pequeno con tracking
* `meta`: metadato editorial pequeño
* `grid`: grid reusable de 2 columnas
* `grid-lines`: grid base de lineas horizontales y verticales
* `grid-lines-small`: grid mas denso con celdas pequenas
* `grid-dots`: fondo con puntos sutiles
* `card`: tarjeta translúcida reusable
* `cards`: grupo de tarjetas
* `metric-card`: tarjeta para numero / señal
* `dashboard`: layout de 3 cards
* `split`: layout asimetrico o 2 paneles
* `statement`: frase grande o afirmacion central
* `big-number`: numero protagonista
* `muted`: texto secundario
* `pill`: etiqueta breve
* `terminal`: bloque visual de terminal
* `terminal right-controls`: variante de terminal con controles visuales alineados a la derecha
* `diagram-placeholder`: placeholder visual para diagramas

## Que Es `example.md`

`example.md` es una demo compacta del theme en accion.

Sirve para:

* validar rapidamente el look and feel
* revisar contraste, espaciado y ritmo
* confirmar que Marp reconoce el theme

## Que Es `patterns.md`

`patterns.md` es la libreria reusable de patrones de slide.

Sirve para:

* copiar bloques base hacia `slides/session.md`
* evitar rediseñar tipos de slide clase por clase
* mantener consistencia entre decks

## Cuando Usar Cada Uno

Usa `example.md` cuando quieras:

* revisar si el theme sigue funcionando
* inspeccionar rapidamente el resultado visual
* detectar compresion rara o cajas demasiado estrechas

Usa `patterns.md` cuando quieras:

* armar una nueva deck
* copiar una slide tipo ya resuelta
* mantener estructura consistente de workshop tecnico
* evitar rediseñar slides editoriales una por una
* revisar variantes de grid/fondo antes de armar una deck nueva

## Como Copiar Patrones a `slides/session.md`

Proceso sugerido:

1. Abre `patterns.md`
2. Identifica el patron que necesitas
3. Copia solo la slide o bloque relevante
4. Pegalo en `slides/session.md`
5. Reemplaza los `TODO`
6. Reduce texto si la slide quedo densa

## Reglas de Estilo

* dark theme por defecto
* fondo negro o casi negro
* `grid-lines` es el fondo default del theme
* los grids deben ser sutiles pero visibles
* lineas en gris-blanco de baja opacidad
* alta legibilidad sobre fondo oscuro
* tipografia local del sistema, sin descargas externas
* tipografia grande, limpia y con mucho espacio negativo
* tarjetas translúcidas gris/beige
* look editorial tecnico, no de documentacion ni PowerPoint academico
* codigo corto y tablas simples deben leerse bien
* terminales pueden usar controles a la izquierda o a la derecha segun convenga al layout
* usar referencias externas solo como inspiracion general
* no copiar layouts, frases, screenshots, imagenes ni marcas visuales de terceros

## Variantes de Grid

Usa estas clases directamente en una slide Marp:

```md
<!-- _class: grid-lines -->
<!-- _class: grid-lines-small -->
<!-- _class: grid-dots -->
```

Recomendaciones:

* `grid-lines`: fondo general por defecto
* `grid-lines-small`: slides mas tecnicas o mas densas
* `grid-dots`: recaps, preguntas guia, slides con mucho espacio negativo

## Opacidad y Legibilidad

Para que el fondo no compita con el contenido:

* mantener lineas alrededor de `rgba(255,255,255,0.055)` a `rgba(255,255,255,0.075)`
* reservar opacidades mayores solo para grids de prueba o variantes mas abstractas
* mantener cards, terminales y bloques de codigo con fondo mas solido que el grid
* si una slide se siente ruidosa, volver a `grid-lines` o `grid-dots`

## Exportacion Recomendada

Para validar rapido el theme:

```bash
marp 00-course-planning/templates/marp-theme/example.md --theme-set 00-course-planning/templates/marp-theme/advanced-db-dark.css --html --output /tmp/marp-theme-example.html
marp 00-course-planning/templates/marp-theme/example.md --theme-set 00-course-planning/templates/marp-theme/advanced-db-dark.css --pdf --output /tmp/marp-theme-example.pdf
marp 00-course-planning/templates/marp-theme/patterns.md --theme-set 00-course-planning/templates/marp-theme/advanced-db-dark.css --html --output /tmp/marp-theme-patterns.html
```

Para exportar una clase:

```bash
marp slides/session.md --theme-set ../../00-course-planning/templates/marp-theme/advanced-db-dark.css --html --output slides/session.html
marp slides/session.md --theme-set ../../00-course-planning/templates/marp-theme/advanced-db-dark.css --pdf --output slides/session.pdf
```

Para preview en VS Code, el workspace debe registrar el theme dentro de `markdown.marp.themes`.

## Limitaciones

* el theme no incluye fuentes externas ni logos
* el theme no incluye imagenes ni assets remotos
* `two-columns`, `cards` y `dashboard` funcionan mejor con contenido breve por bloque
* `tiny` debe usarse solo en casos puntuales
* el theme no reemplaza el criterio pedagogico sobre densidad de contenido

## TODO

* TODO: ajustar detalles finos despues de ver exportaciones reales.
* TODO: revisar contraste final en proyector o pantalla de aula.
