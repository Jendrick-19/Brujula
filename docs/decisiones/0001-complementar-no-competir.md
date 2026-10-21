# 0001. Brújula complementa a los programas de gestión

- Estado: aceptada
- Fecha: 2026-10

## Contexto
Existen suites de gestión para residencias (por ejemplo Intergen/Codegest, ResiPlus, Soft4Care, ISECO) que ya cubren turnos, cuadrantes, fichajes y registro de cuidados. No se ha encontrado en sus webs una biblioteca de convenio con búsqueda ni un asistente con IA.

## Decisión
El producto no compite en gestión. Su valor es la capa de conocimiento y el asistente para el personal. Las planillas se importan desde Excel/CSV; el CRUD de turnos se mantiene solo para datos de demostración.

## Consecuencias
Menos alcance en turnos, más esfuerzo en RAG y calidad de las respuestas. La propuesta de valor se formula frente a los programas de gestión, no como sustituto.
