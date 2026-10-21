# Arquitectura (borrador v0.1)

```
App Flutter ──┐
              ├── HTTPS ── Reverse proxy ── Backend Spring Boot ── PostgreSQL + pgvector
Panel JavaFX ─┘                                   │
                                                  └── Spring AI ── Ollama (local) o API externa
```

## Módulos del backend (previstos)

- `auth`: login, JWT, roles.
- `centros` y `trabajadores`: gestión básica.
- `turnos`: modelo de planillas e importación Excel/CSV.
- `documentos`: subida, extracción, troceado, embeddings.
- `asistente`: RAG, tool calling, control de permisos.

## Principios

1. El asistente solo accede a datos mediante funciones controladas.
2. Cada respuesta del RAG incluye la fuente.
3. El modelo de IA se cambia por configuración, sin tocar código.
4. Lo que depende de datos reales de la residencia se aísla para poder cambiarlo sin rehacer el sistema.
