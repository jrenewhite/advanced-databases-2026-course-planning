# Template Class Repo

## Status

Template local reutilizable para repos `class-*`.

## Purpose

Servir como base para material de sesion:

* slides
* demos
* ejercicios guiados
* notas
* recursos de clase

## Quick Start

Levantar el entorno:

```bash
docker compose up -d
```

Entrar con `psql`:

```bash
psql postgresql://postgres:postgres@localhost:5432/demo
```

Alternativa visual opcional:

* DBeaver, si el instructor o alumno prefiere una interfaz grafica

## Estructura

* `slides/`: presentacion en Marp
* `demo/`: scripts SQL y apoyo reproducible
* `exercises/`: actividad guiada
* `notes/`: material instructor-facing
* `assets/`, `diagrams/`, `animations/`: recursos visuales

## Demo

TODO: describir objetivo de la demo.

## Ejercicio

TODO: describir ejercicio guiado.

## Evidencia Esperada

TODO: describir evidencia minima.

## Uso de IA

TODO: indicar uso permitido y validacion requerida.

## Troubleshooting

TODO: agregar problemas comunes y fallback.
