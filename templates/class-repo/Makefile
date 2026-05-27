.PHONY: up down reset psql slides

SLIDES_SOURCE ?= ../../00-course-planning/slides/TODO-class-name.md

up:
	docker compose up -d

down:
	docker compose down

reset:
	docker compose down -v
	docker compose up -d

psql:
	psql postgresql://postgres:postgres@localhost:5432/demo

slides:
	marp $(SLIDES_SOURCE) --theme-set ../../00-course-planning/templates/marp-theme/advanced-db-dark.css --html --output slides/session.html
