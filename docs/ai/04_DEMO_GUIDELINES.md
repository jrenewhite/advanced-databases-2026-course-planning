
# 04_DEMO_GUIDELINES.md — Reglas para demos y laboratorios

## Status

Draft inicial controlado por el instructor.

Este documento define las reglas para diseñar, crear, ejecutar y mantener demos/laboratorios del curso **Sistemas Avanzados de Bases de Datos**.

Debe leerse después de:

```txt
00-course-planning/docs/ai/00_COURSEWARE_OBJECTIVE.md
00-course-planning/docs/ai/01_AI_COLLABORATION.md
00-course-planning/docs/ai/02_SLIDE_RULES.md
00-course-planning/docs/ai/03_REPOSITORY_RULES.md
````

---

## Purpose

El propósito de este documento es asegurar que las demos del curso sean reproducibles, claras, simples y pedagógicamente útiles.

Las demos deben ayudar a conectar teoría con práctica real de ingeniería.

No deben convertirse en proyectos complejos que distraigan del objetivo principal de la clase.

---

## 1. Principio central

La regla principal es:

> Una demo debe enseñar un concepto técnico observable, no impresionar por complejidad.

Una buena demo permite que el alumno vea algo como:

* una consulta lenta
* un plan de ejecución
* una transacción bloqueada
* un índice que cambia el comportamiento
* una vista que simplifica lectura
* un trigger que automatiza una regla
* una diferencia entre OLTP y OLAP
* un modelo dimensional en acción
* una mala decisión de diseño y su consecuencia

---

## 2. Objetivo de cada demo

Cada demo debe tener un objetivo claro.

Antes de crearla, definir:

* qué concepto enseña
* qué parte del temario cubre
* qué debe observar el alumno
* qué evidencia puede generar
* qué tradeoff o decisión técnica se quiere discutir

Ejemplo:

```md
## Objetivo de demo

Mostrar cómo un índice cambia el plan de ejecución y reduce el tiempo de una consulta frecuente, pero introduce costo adicional en escrituras.
```

Evitar demos cuyo objetivo sea ambiguo como:

```md
Ver algo de SQL.
Probar PostgreSQL.
Hacer una base de datos.
```

---

## 3. Tecnología preferida

La tecnología base preferida es:

```txt
PostgreSQL + Docker Compose
```

Usar PostgreSQL porque permite demostrar bien:

* transacciones
* aislamiento
* MVCC
* locks
* deadlocks
* índices
* `EXPLAIN`
* `EXPLAIN ANALYZE`
* vistas
* funciones
* triggers
* roles
* optimización básica
* modelos relacionales y analíticos

Docker Compose debe usarse para reducir fricción de setup.

---

## 4. Regla de simplicidad

Preferir la demo más simple que permita observar el concepto.

No agregar:

* microservicios
* frontend
* colas
* autenticación
* Kubernetes
* cloud
* observabilidad avanzada
* múltiples bases de datos
* frameworks innecesarios
* datasets enormes

A menos que el objetivo de la clase lo justifique explícitamente.

La complejidad debe existir solo si enseña algo del temario.

---

## 5. Reproducibilidad

Toda demo debe poder ejecutarse de forma reproducible.

Idealmente:

```bash
docker compose up -d
```

Debe haber instrucciones claras para:

* levantar ambiente
* conectarse a PostgreSQL
* ejecutar scripts
* resetear demo
* apagar ambiente

Ejemplo mínimo:

```bash
docker compose up -d
docker compose down -v
```

Cuando aplique, incluir comandos en el `README.md` de la clase.

---

## 6. Estructura recomendada

Cada demo debe vivir principalmente en:

```txt
demo/
```

Estructura sugerida:

```txt
demo/
├── init.sql
├── seed.sql
├── queries/
│   ├── 01-baseline.sql
│   ├── 02-problem.sql
│   ├── 03-fix.sql
│   └── 04-compare.sql
└── README.md
```

No todas las clases necesitan esta estructura completa.

Si una clase solo necesita `init.sql`, está bien.

---

## 7. Docker Compose

Cada clase que use PostgreSQL debe tener un `docker-compose.yml` simple.

Ejemplo base:

```yaml
services:
  postgres:
    image: postgres:16
    container_name: class-demo-postgres
    ports:
      - "5432:5432"
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: postgres
      POSTGRES_DB: demo
    volumes:
      - postgres-data:/var/lib/postgresql/data
      - ./demo/init.sql:/docker-entrypoint-initdb.d/init.sql:ro

volumes:
  postgres-data:
```

Reglas:

* usar credenciales demo obvias, nunca reales
* documentar puerto usado
* evitar servicios innecesarios
* usar volumen nombrado
* permitir reset con `docker compose down -v`
* evitar imágenes raras o poco mantenidas

---

## 8. Dev Containers

Los Dev Containers deben reducir fricción.

Pueden incluir:

* PostgreSQL client
* Marp CLI
* Git
* Docker CLI
* extensiones útiles de VS Code
* herramientas Markdown

No deben ser obligatorios si Docker Compose basta.

Si se usan, documentar claramente:

* cómo abrir el devcontainer
* qué herramientas incluye
* qué comandos correr

---

## 9. Datos seed

Las demos deben usar datos ficticios.

Nunca usar:

* datos reales de empresas
* datos personales
* información sensible
* dumps reales
* credenciales reales
* datos de alumnos

Los datos seed deben ser:

* pequeños al inicio
* suficientemente grandes cuando se requiera performance
* fáciles de regenerar
* entendibles

Para demos de performance, se puede generar volumen artificial de datos, pero debe documentarse.

Ejemplo:

```sql
INSERT INTO orders (customer_id, amount, created_at)
SELECT
  (random() * 10000)::int,
  (random() * 1000)::numeric(10,2),
  now() - (random() * interval '365 days')
FROM generate_series(1, 100000);
```

---

## 10. Performance demos

Para demos de rendimiento, siempre incluir evidencia antes/después.

Usar:

```sql
EXPLAIN ANALYZE
```

Cuando aplique, también:

```sql
EXPLAIN (ANALYZE, BUFFERS)
```

La demo debe mostrar:

* query inicial
* plan inicial
* problema observado
* cambio realizado
* plan posterior
* comparación
* tradeoff

No afirmar “mejoró” sin evidencia.

Evitar inventar tiempos exactos en slides o README.

Los tiempos pueden variar por máquina.

Preferir lenguaje como:

```md
En una máquina local típica deberíamos observar reducción notable en el costo/tiempo, pero los valores exactos pueden variar.
```

---

## 11. Transacciones y concurrencia

Para demos de concurrencia, documentar pasos con sesiones separadas.

Ejemplo:

```txt
Terminal A:
BEGIN;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;

Terminal B:
BEGIN;
UPDATE accounts SET balance = balance - 50 WHERE id = 1;
```

La demo debe indicar:

* qué terminal ejecuta qué
* cuándo se espera bloqueo
* qué consulta permite observar locks
* cómo liberar la transacción
* cómo limpiar estado

Incluir siempre instrucciones de recuperación.

---

## 12. Deadlocks

Las demos de deadlock deben ser cuidadosamente guiadas.

Incluir:

* pasos numerados
* dos sesiones o terminales
* comportamiento esperado
* explicación del error
* estrategia de mitigación
* reset del ambiente

No improvisar deadlocks sin fallback.

---

## 13. Views, stored procedures y triggers

Para demos de vistas, procedimientos y triggers:

* explicar cuándo son útiles
* explicar riesgos de abuso
* mostrar caso pequeño y claro
* evitar lógica de negocio excesiva
* conectar con mantenibilidad
* discutir testing y observabilidad

Para triggers:

* mostrar efecto visible
* mostrar riesgo de comportamiento implícito
* discutir cuándo evitarlo

---

## 14. Seguridad, roles y permisos

Para demos de usuarios y roles:

* usar usuarios ficticios
* no usar credenciales reales
* documentar permisos
* mostrar acceso permitido y denegado
* explicar principio de mínimo privilegio

Ejemplo:

```sql
CREATE ROLE analyst LOGIN PASSWORD 'analyst';
GRANT SELECT ON reporting_view TO analyst;
```

---

## 15. OLAP, Data Warehouse y Data Mart

Para demos analíticas:

* mantener dataset simple
* distinguir hechos y dimensiones
* mostrar granularidad
* mostrar consulta agregada
* comparar forma OLTP vs forma analítica
* explicar por qué el modelo cambia

Ejemplo de evidencia:

* diagrama star schema
* query de agregación
* explicación de dimensión/hecho
* tradeoff frente al modelo normalizado

---

## 16. Data Mining

Para Data Mining, evitar prometer demasiado.

El curso no debe convertirse en curso de machine learning.

Enfocar en:

* concepto
* preparación de datos
* patrones
* agregaciones
* segmentación simple
* toma de decisiones
* límites del análisis

Usar ejemplos simples y explicables.

---

## 17. Bases orientadas a objetos y modelos modernos

Para BDOO/ORM/NoSQL:

* cubrir el contexto histórico
* explicar motivación
* conectar con impedance mismatch
* comparar con ORMs
* comparar con documentos u otros modelos
* discutir persistencia, identidad, relaciones y consultas

No gastar demasiado tiempo en frameworks específicos salvo que ayuden al concepto.

---

## 18. Fallback obligatorio

Toda demo importante debe tener fallback.

Opciones de fallback:

* script ya listo
* resultado esperado en archivo
* screenshot propio
* explicación con diagrama
* branch `instructor`
* commit preparado
* consulta alternativa más simple

El instructor debe poder continuar la clase si:

* Docker falla
* el contenedor no levanta
* el puerto está ocupado
* la query tarda demasiado
* la máquina del alumno no soporta el volumen de datos
* una animación no carga

---

## 19. Reset de ambiente

Toda demo con Docker debe poder resetearse.

Comando esperado:

```bash
docker compose down -v
docker compose up -d
```

Si hay scripts adicionales:

```bash
make reset
```

o:

```bash
./scripts/reset-demo.sh
```

deben ser simples y documentados.

---

## 20. Makefile

Cada clase puede incluir `Makefile` para comandos comunes.

Ejemplo:

```makefile
.PHONY: up down reset logs psql slides

up:
	docker compose up -d

down:
	docker compose down

reset:
	docker compose down -v
	docker compose up -d

logs:
	docker compose logs -f

psql:
	docker exec -it class-demo-postgres psql -U postgres -d demo

slides:
	marp slides/session.md --html --output slides/session.html
```

No agregar targets que no se usen.

---

## 21. Evidencia esperada

Cada demo que derive en ejercicio debe indicar evidencia.

Ejemplos:

Para índices:

* query inicial
* `EXPLAIN ANALYZE` antes
* índice propuesto
* `EXPLAIN ANALYZE` después
* tradeoff

Para transacciones:

* pasos ejecutados
* comportamiento observado
* explicación del aislamiento
* riesgo identificado

Para warehouse:

* modelo dimensional
* query analítica
* explicación de granularidad
* decisión de diseño

---

## 22. Uso de IA en demos

Los alumnos pueden usar IA para pedir ideas o ayuda.

Pero deben validar.

Las prácticas deben pedir:

* explicación propia
* evidencia
* comparación
* tradeoffs
* límites

No aceptar como suficiente:

```md
ChatGPT dijo que agregara este índice.
```

Aceptar mejor:

```md
Probé este índice porque la consulta filtra por customer_id.
El plan cambió de sequential scan a index scan.
El tiempo bajó en mi entorno de X a Y.
Tradeoff: aumenta costo de escritura y almacenamiento.
```

---

## 23. Prohibiciones

No usar en demos:

* credenciales reales
* datos reales de empresas
* servicios de paga obligatorios
* dependencias cloud obligatorias
* software no redistribuible sin permiso
* contenido de terceros como si fuera propio
* scripts destructivos fuera del ambiente demo
* comandos que afecten el sistema del alumno fuera del repo

---

## 24. Buenas demos

Una buena demo:

* tiene objetivo claro
* corre localmente
* tiene instrucciones cortas
* muestra algo observable
* conecta con el temario
* genera discusión
* permite evidencia
* tiene fallback
* no depende de suerte
* no requiere demasiado setup

---

## 25. Malas demos

Evitar demos que:

* requieren instalar muchas cosas
* dependen de internet
* no tienen reset
* no tienen datos seed
* solo muestran sintaxis
* no conectan con problema real
* tardan demasiado
* fallan fácilmente
* no tienen salida observable
* no tienen explicación de tradeoff

---

## 26. Checklist antes de aceptar una demo

Antes de aceptar una demo, revisar:

* ¿Cubre un tema oficial?
* ¿Tiene objetivo claro?
* ¿Se puede ejecutar localmente?
* ¿Tiene instrucciones?
* ¿Tiene datos seed?
* ¿Tiene reset?
* ¿Tiene fallback?
* ¿No usa datos reales?
* ¿No usa servicios de paga?
* ¿No está sobrecomplicada?
* ¿Genera evidencia?
* ¿Permite discusión de tradeoffs?
* ¿Se puede explicar aunque falle?

---

## 27. Reglas para Codex/IA

Cuando Codex genere demos:

* debe leer primero los guardrails
* debe proponer mini-plan antes de crear demos nuevas
* debe mantener el setup simple
* debe preferir PostgreSQL
* debe preferir Docker Compose
* debe incluir datos ficticios
* debe incluir reset
* debe incluir README o instrucciones
* no debe inventar resultados medidos
* no debe agregar dependencias innecesarias
* no debe generar soluciones finales student-facing sin autorización
* debe separar demo base de solución instructor cuando aplique

---

## TODO

* Definir plantilla final de `demo/README.md`.
* Definir plantilla final de `Makefile`.
* Definir estrategia para datasets grandes.
* Definir convención para scripts `01-*`, `02-*`, etc.
* Definir si se usará `psql`, DBeaver, Azure Data Studio u otra herramienta principal.

