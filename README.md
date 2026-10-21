# Brújula

Plataforma de información y asistencia para el personal de centros de atención a mayores y dependientes (residencias, centros de día y ayuda a domicilio).

> Proyecto final de 2º de CFGS Desarrollo de Aplicaciones Multiplataforma (DAM), IES Las Fuentezuelas (Jaén), curso 2026/2027.
> Autor: Alejandro Montilla Aguilar. Proyecto independiente con **datos ficticios**; no usa datos reales ni marcas de ninguna empresa.

## Propuesta de valor

Los programas de gestión organizan el centro y registran cuidados. Brújula **complementa** esos programas: responde en el momento las dudas normativas y laborales del personal (convenio, normativa, protocolos), **citando el documento de origen**, y permite consultar "mi turno de hoy" y "con quién trabajo".

## Funciones del MVP

- Login con roles (auxiliar, coordinadora, administrador y evaluador de solo lectura).
- Gestión de centros y trabajadores.
- Biblioteca de documentos con búsqueda e ingesta automática (extracción, troceado, embeddings).
- Chatbot con IA (RAG) que cita la fuente y consulta turnos mediante funciones controladas (tool calling), nunca SQL libre.
- Importación de planillas desde Excel/CSV.

La fase 2 (avisos, recordatorios, cambios de turno, informes PDF, estadísticas) está descrita en `docs/requisitos.md`.

## Stack

| Capa | Tecnología |
|---|---|
| Backend | Java 21, Spring Boot 3, Spring Data JPA, Spring Security + JWT |
| Base de datos | PostgreSQL con pgvector |
| IA | Spring AI (Ollama local o API externa configurable) |
| Documentos | Apache PDFBox / Tika |
| App móvil | Flutter + Dart |
| Panel de coordinación | JavaFX (pendiente de confirmar con el tutor) |
| Despliegue | Docker Compose, Proxmox, Tailscale, reverse proxy HTTPS |
| Calidad | JUnit, Mockito, Swagger/OpenAPI, GitHub Actions |

## Estructura del repositorio

```
backend/   API REST (Spring Boot)
mobile/    App Flutter para auxiliares
desktop/   Panel de gestión para coordinación
infra/     Docker Compose, scripts de despliegue y copias de seguridad
docs/      Requisitos, arquitectura, decisiones y bitácora
```

## Arranque rápido (entorno de desarrollo)

```bash
cp .env.example .env        # edita los valores
docker compose -f infra/docker-compose.yml --env-file .env up -d
```

Esto levanta PostgreSQL con pgvector. El backend se añadirá en cuanto exista el proyecto Spring Boot.

## Flujo de trabajo

- `main`: estable. `develop`: integración. `feature/...`: trabajo de cada tarea.
- Commits pequeños y descriptivos (por ejemplo `feat: ingesta de PDF con Tika`).
- Nunca se suben secretos: todo va en `.env` (ignorado por Git).

## Licencia

Todos los derechos reservados. Consulta `LICENSE`.
