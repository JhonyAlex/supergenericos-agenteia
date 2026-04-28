# Transferencia a humano

Matriz para administrar múltiples escenarios de transferencia a humano en una sola vista.

## Tabla de escenarios

| ID | Habilitar | Nombre del escenario | Condición de activación | Frases de ejemplo | Asignar a usuario específico | Omitir si ya tiene usuario asignado | Mensaje final del bot | Reactivar bot (horas) | Crear tarea en contacto | Etiquetas personalizadas |
|---|---|---|---|---|---|---|---|---|---|---|
| 01 | [x] | Human Requested | Direct request to speak with human | Quiero hablar con un asesor<br>Quiero hablar con un agente<br>Quiero hablar con un humano | Juan Jose Diaz Cadavid | [x] | ¡Claro! Te conecto con alguien del equipo, en breve te atenderá. | [x] 20 | [x] | asesor-humano |
| 02 | [x] | Lack of information | The AI cannot find the relevant information or lacks knowledge on the query | No visible en la captura<br>No visible en la captura<br>No visible en la captura | Juan Jose Diaz Cadavid | [x] | No puedo procesar tu solicitud ahora, pero el equipo te respondera en breve. | [x] 20 | [x] | asesor-humano |
| 03 | [x] | Failed to resolve issue | Multiple attempts to resolve the issue has failed | No visible en la captura<br>No visible en la captura<br>No visible en la captura | Juan Jose Diaz Cadavid | [x] | No puedo procesar tu solicitud ahora, pero el equipo te respondera en breve. | [x] 20 | [x] | asesor-humano |
| 04 | [x] | Specific Requirements | Customer has specific requirements such as complex returns or special cond... | Quiero hacer una devolución complicada<br>Tengo un requisito especial<br>Necesito un proceso diferente<br>¿Cómo gestionan casos complejos? | Juan Jose Diaz Cadavid | [x] | Entiendo tu solicitud. Te paso con un asesor para que te ayude a resolverla... | [ ] | [ ] | asesor-humano |
| 06 | [x] | Document Submission Refused | Prospect refuses to submit required documents such as RUT, etc | No quiero enviar el RUT<br>No tengo Cámara de Comercio<br>Prefiero no mandar documentos<br>No voy a compartir mis papeles | Juan Jose Diaz Cadavid | [x] | Entiendo tu decisión. Un asesor se comunicará contigo para dar seguimiento. | [ ] | [ ] | [ ] |
| XX | [ ] | [ ] | [ ] | [ ]<br>[ ]<br>[ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |

## Detalle del escenario 01

| Campo | Valor configurado |
|---|---|
| Habilitar escenario | [x] |
| Nombre del escenario | Human Requested |
| Condición de activación | Direct request to speak with human |
| Frase de ejemplo 1 | Quiero hablar con un asesor |
| Frase de ejemplo 2 | Quiero hablar con un agente |
| Frase de ejemplo 3 | Quiero hablar con un humano |
| Asignar conversación a usuario específico | Juan Jose Diaz Cadavid |
| Omitir asignación si el contacto ya tiene usuario asignado | [x] |
| Mensaje final | ¡Claro! Te conecto con alguien del equipo, en breve te atenderá. |
| Reactivar bot después de | [x] 20 horas |
| Crear tarea en el contacto | [x] |
| Etiquetas personalizadas | asesor-humano |

## Detalle del escenario 02

| Campo | Valor configurado |
|---|---|
| Habilitar escenario | [x] |
| Nombre del escenario | Lack of information |
| Condición de activación | The AI cannot find the relevant information or lacks knowledge on the query |
| Frase de ejemplo 1 | No visible en la captura |
| Frase de ejemplo 2 | No visible en la captura |
| Frase de ejemplo 3 | No visible en la captura |
| Asignar conversación a usuario específico | Juan Jose Diaz Cadavid |
| Omitir asignación si el contacto ya tiene usuario asignado | [x] |
| Mensaje final | No puedo procesar tu solicitud ahora, pero el equipo te respondera en breve. |
| Reactivar bot después de | [x] 20 horas |
| Crear tarea en el contacto | [x] |
| Etiquetas personalizadas | asesor-humano |

## Detalle del escenario 03

| Campo | Valor configurado |
|---|---|
| Habilitar escenario | [x] |
| Nombre del escenario | Failed to resolve issue |
| Condición de activación | Multiple attempts to resolve the issue has failed |
| Frase de ejemplo 1 | No visible en la captura |
| Frase de ejemplo 2 | No visible en la captura |
| Frase de ejemplo 3 | No visible en la captura |
| Asignar conversación a usuario específico | Juan Jose Diaz Cadavid |
| Omitir asignación si el contacto ya tiene usuario asignado | [x] |
| Mensaje final | No puedo procesar tu solicitud ahora, pero el equipo te respondera en breve. |
| Reactivar bot después de | [x] 20 horas |
| Crear tarea en el contacto | [x] |
| Etiquetas personalizadas | asesor-humano |

## Detalle del escenario 04

| Campo | Valor configurado |
|---|---|
| Habilitar escenario | [x] |
| Nombre del escenario | Specific Requirements |
| Condición de activación | Customer has specific requirements such as complex returns or special cond... |
| Frase de ejemplo 1 | Quiero hacer una devolución complicada |
| Frase de ejemplo 2 | Tengo un requisito especial |
| Frase de ejemplo 3 | Necesito un proceso diferente |
| Frase de ejemplo 4 | ¿Cómo gestionan casos complejos? |
| Asignar conversación a usuario específico | Juan Jose Diaz Cadavid |
| Omitir asignación si el contacto ya tiene usuario asignado | [x] |
| Mensaje final | Entiendo tu solicitud. Te paso con un asesor para que te ayude a resolverla... |
| Reactivar bot después de | [ ] |
| Crear tarea en el contacto | [ ] |
| Etiquetas personalizadas | asesor-humano |

## Detalle del escenario 06

| Campo | Valor configurado |
|---|---|
| Habilitar escenario | [x] |
| Nombre del escenario | Document Submission Refused |
| Condición de activación | Prospect refuses to submit required documents such as RUT, etc |
| Frase de ejemplo 1 | No quiero enviar el RUT |
| Frase de ejemplo 2 | No tengo Cámara de Comercio |
| Frase de ejemplo 3 | Prefiero no mandar documentos |
| Frase de ejemplo 4 | No voy a compartir mis papeles |
| Asignar conversación a usuario específico | Juan Jose Diaz Cadavid |
| Omitir asignación si el contacto ya tiene usuario asignado | [x] |
| Mensaje final | Entiendo tu decisión. Un asesor se comunicará contigo para dar seguimiento. |
| Reactivar bot después de | [ ] |
| Crear tarea en el contacto | [ ] |
| Etiquetas personalizadas | [ ] |

## Notas de uso

- Duplica la fila XX para cada nuevo escenario.
- En Condición de activación, define claramente cuándo el bot debe transferir la conversación.
- Mensaje final del bot es el último mensaje antes de que el bot quede inactivo.
- En Etiquetas personalizadas, agrega una o varias etiquetas separadas por coma.
