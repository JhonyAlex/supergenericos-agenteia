# Transferencia a humano

Matriz para administrar múltiples escenarios de transferencia a humano en una sola vista.

## Tabla de escenarios

| ID | Habilitar | Nombre del escenario | Condición de activación | Frases de ejemplo | Asignar a usuario específico | Omitir si ya tiene usuario asignado | Mensaje final del asistente virtual | Reactivar asistente virtual (horas) | Crear tarea en contacto | Etiquetas personalizadas |
|---|---|---|---|---|---|---|---|---|---|---|
| 01 | [x] | Solicitud de atención humana | Solicitud directa de hablar con una persona | Quiero hablar con un asesor<br>Quiero hablar con un agente<br>Quiero hablar con un humano | Juan Jose Diaz Cadavid | [x] | ¡Claro! Te conecto con alguien del equipo, en breve te atenderá. | [x] 20 | [x] | asesor-humano |
| 02 | [x] | Falta de información | La IA no encuentra la información relevante o no tiene conocimiento suficiente sobre la consulta | No visible en la captura<br>No visible en la captura<br>No visible en la captura | Juan Jose Diaz Cadavid | [x] | No puedo procesar tu solicitud ahora, pero el equipo te responderá en breve. | [x] 20 | [x] | asesor-humano |
| 03 | [x] | No se logró resolver el caso | Varios intentos para resolver el caso han fallado | No visible en la captura<br>No visible en la captura<br>No visible en la captura | Juan Jose Diaz Cadavid | [x] | No puedo procesar tu solicitud ahora, pero el equipo te responderá en breve. | [x] 20 | [x] | asesor-humano |
| 04 | [x] | Requisitos específicos | El cliente tiene requisitos específicos como devoluciones complejas o condiciones especiales | Quiero hacer una devolución complicada<br>Tengo un requisito especial<br>Necesito un proceso diferente<br>¿Cómo gestionan casos complejos? | Juan Jose Diaz Cadavid | [x] | Entiendo tu solicitud. Te paso con un asesor para que te ayude a resolverla... | [ ] | [ ] | asesor-humano |
| 06 | [x] | Rechazo de envío de documentos | El prospecto se niega a enviar documentos requeridos como RUT, etc. | No quiero enviar el RUT<br>No tengo Cámara de Comercio<br>Prefiero no mandar documentos<br>No voy a compartir mis papeles | Juan Jose Diaz Cadavid | [x] | Entiendo tu decisión. Un asesor se comunicará contigo para dar seguimiento. | [ ] | [ ] | [ ] |
| XX | [ ] | [ ] | [ ] | [ ]<br>[ ]<br>[ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |

## Detalle del escenario 01

| Campo | Valor configurado |
|---|---|
| Habilitar escenario | [x] |
| Nombre del escenario | Solicitud de atención humana |
| Condición de activación | Solicitud directa de hablar con una persona |
| Frase de ejemplo 1 | Quiero hablar con un asesor |
| Frase de ejemplo 2 | Quiero hablar con un agente |
| Frase de ejemplo 3 | Quiero hablar con un humano |
| Asignar conversación a usuario específico | Juan Jose Diaz Cadavid |
| Omitir asignación si el contacto ya tiene usuario asignado | [x] |
| Mensaje final | ¡Claro! Te conecto con alguien del equipo, en breve te atenderá. |
| Reactivar asistente virtual después de | [x] 20 horas |
| Crear tarea en el contacto | [x] |
| Etiquetas personalizadas | asesor-humano |

## Detalle del escenario 02

| Campo | Valor configurado |
|---|---|
| Habilitar escenario | [x] |
| Nombre del escenario | Falta de información |
| Condición de activación | La IA no encuentra la información relevante o no tiene conocimiento suficiente sobre la consulta |
| Frase de ejemplo 1 | No visible en la captura |
| Frase de ejemplo 2 | No visible en la captura |
| Frase de ejemplo 3 | No visible en la captura |
| Asignar conversación a usuario específico | Juan Jose Diaz Cadavid |
| Omitir asignación si el contacto ya tiene usuario asignado | [x] |
| Mensaje final | No puedo procesar tu solicitud ahora, pero el equipo te responderá en breve. |
| Reactivar asistente virtual después de | [x] 20 horas |
| Crear tarea en el contacto | [x] |
| Etiquetas personalizadas | asesor-humano |

## Detalle del escenario 03

| Campo | Valor configurado |
|---|---|
| Habilitar escenario | [x] |
| Nombre del escenario | No se logró resolver el caso |
| Condición de activación | Varios intentos para resolver el caso han fallado |
| Frase de ejemplo 1 | No visible en la captura |
| Frase de ejemplo 2 | No visible en la captura |
| Frase de ejemplo 3 | No visible en la captura |
| Asignar conversación a usuario específico | Juan Jose Diaz Cadavid |
| Omitir asignación si el contacto ya tiene usuario asignado | [x] |
| Mensaje final | No puedo procesar tu solicitud ahora, pero el equipo te responderá en breve. |
| Reactivar asistente virtual después de | [x] 20 horas |
| Crear tarea en el contacto | [x] |
| Etiquetas personalizadas | asesor-humano |

## Detalle del escenario 04

| Campo | Valor configurado |
|---|---|
| Habilitar escenario | [x] |
| Nombre del escenario | Requisitos específicos |
| Condición de activación | El cliente tiene requisitos específicos como devoluciones complejas o condiciones especiales |
| Frase de ejemplo 1 | Quiero hacer una devolución complicada |
| Frase de ejemplo 2 | Tengo un requisito especial |
| Frase de ejemplo 3 | Necesito un proceso diferente |
| Frase de ejemplo 4 | ¿Cómo gestionan casos complejos? |
| Asignar conversación a usuario específico | Juan Jose Diaz Cadavid |
| Omitir asignación si el contacto ya tiene usuario asignado | [x] |
| Mensaje final | Entiendo tu solicitud. Te paso con un asesor para que te ayude a resolverla... |
| Reactivar asistente virtual después de | [ ] |
| Crear tarea en el contacto | [ ] |
| Etiquetas personalizadas | asesor-humano |

## Detalle del escenario 06

| Campo | Valor configurado |
|---|---|
| Habilitar escenario | [x] |
| Nombre del escenario | Rechazo de envío de documentos |
| Condición de activación | El prospecto se niega a enviar documentos requeridos como RUT, etc. |
| Frase de ejemplo 1 | No quiero enviar el RUT |
| Frase de ejemplo 2 | No tengo Cámara de Comercio |
| Frase de ejemplo 3 | Prefiero no mandar documentos |
| Frase de ejemplo 4 | No voy a compartir mis papeles |
| Asignar conversación a usuario específico | Juan Jose Diaz Cadavid |
| Omitir asignación si el contacto ya tiene usuario asignado | [x] |
| Mensaje final | Entiendo tu decisión. Un asesor se comunicará contigo para dar seguimiento. |
| Reactivar asistente virtual después de | [ ] |
| Crear tarea en el contacto | [ ] |
| Etiquetas personalizadas | [ ] |

## Notas de uso

- Duplica la fila XX para cada nuevo escenario.
- En Condición de activación, define claramente cuándo el asistente virtual debe transferir la conversación.
- Mensaje final del asistente virtual es el último mensaje antes de que el asistente virtual quede inactivo.
- En Etiquetas personalizadas, agrega una o varias etiquetas separadas por coma.
