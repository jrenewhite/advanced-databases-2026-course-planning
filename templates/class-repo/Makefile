.PHONY: up down reset psql

up:
	docker compose up -d

down:
	docker compose down

reset:
	docker compose down -v
	docker compose up -d

psql:
	psql postgresql://postgres:postgres@localhost:5432/demo
