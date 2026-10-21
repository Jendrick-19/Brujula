# 0003. RAG con cita de fuente y consultas solo por funciones controladas

- Estado: aceptada
- Fecha: 2026-10

## Decisión
Las dudas normativas se responden con RAG citando el documento de origen. Los datos personales (turnos, compañeros) solo se consultan mediante funciones predefinidas con control de permisos. El modelo nunca genera ni ejecuta SQL libre.

## Consecuencias
Mayor seguridad y facilidad para auditar. Cada nueva consulta del asistente requiere implementar una función explícita.
