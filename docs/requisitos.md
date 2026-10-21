# Requisitos iniciales (borrador v0.1)

Estado: borrador. Los puntos marcados con ⚠ dependen de las respuestas de la dirección de la residencia o del tutor.

## Usuarios

| Rol | Descripción | Permisos principales |
|---|---|---|
| AUXILIAR | Personal de atención directa | Ver su turno, compañeros de turno, chat, biblioteca |
| COORDINADORA | Responsable de centro | Todo lo anterior + subir documentos, importar planillas, gestionar trabajadores de su centro |
| ADMIN | Administrador del sistema | Gestión global de centros, usuarios y configuración |
| EVALUADOR | Solo lectura (profesorado) | Consulta de todo, incluido Swagger; sin crear ni modificar |

## Requisitos funcionales (MVP)

- RF1. Autenticación con JWT y control de acceso por roles.
- RF2. Gestión de centros y trabajadores.
- RF3. Biblioteca de documentos con búsqueda.
- RF4. Ingesta automática: extracción de texto, troceado, generación de embeddings y almacenamiento en pgvector.
- RF5. Chatbot RAG que responde citando documento de origen (y página/artículo cuando sea posible).
- RF6. Consulta de turnos mediante funciones controladas (tool calling): "mi turno de hoy", "con quién trabajo".
- RF7. Importación de planillas desde Excel/CSV. ⚠ Formato real pendiente.
- RF8. Datos de demostración cargados solo en perfil `demo`.

## Requisitos no funcionales

- RNF1. Protección de datos: minimización, sin datos de salud, sin motivos de baja. Datos de demostración ficticios.
- RNF2. Seguridad: contraseñas con hash, secretos fuera del repositorio, HTTPS en despliegue.
- RNF3. El asistente no ejecuta SQL libre; solo funciones predefinidas con control de permisos.
- RNF4. El modelo de IA es configurable (local o API externa).
- RNF5. Despliegue reproducible con Docker Compose.
- RNF6. Documentación de la API con OpenAPI/Swagger.
- RNF7. Pruebas unitarias y de integración sobre los casos críticos (permisos, RAG, tool calling).

## Fuera del MVP (fase 2 / trabajo futuro)

Avisos por cambios de planilla, recordatorios, cambios de turno, informes PDF mensuales, estadísticas, alertas de documentos desactualizados, notificaciones push.

## Pendiente de confirmar

- ⚠ Con el tutor: formato de memoria, hitos, tecnologías obligatorias (JavaFX vs. Flutter de escritorio).
- ⚠ Con la residencia: convenio aplicable, formato de planillas, protocolos usables como ejemplo, organización de turnos y ratios.
