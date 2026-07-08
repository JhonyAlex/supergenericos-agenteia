# AGENTS.md — Guía operativa para IAs del repositorio

Este repositorio documenta y organiza el agente IA comercial de **Súper Genéricos del Valle** en **Go High Level (GHL)**, implementado/documentado por **Grupo Nedemy**. Su objetivo es mantener trazabilidad clara entre requerimientos del cliente, prompt, base de conocimiento, workflows y acciones configurables.

## 1. Propósito del repositorio

Centralizar la documentación funcional y operativa del asistente comercial para que futuras IAs y personas del equipo puedan:

- Mantener respuestas consistentes con la identidad de Súper Genéricos del Valle.
- Documentar reglas de automatización en GHL sin perder contexto.
- Registrar avances, pendientes y decisiones del cliente.
- Evitar cambios sin trazabilidad en prompts, acciones, flujos o reglas comerciales.

## 2. Regla crítica para IA externa: estudiar o actuar como agente final

Cuando una IA externa reciba este repositorio, especialmente si no tiene acceso real a Go High Level, WhatsApp, CRM, base de datos o herramientas internas, debe poder trabajar en dos modos claros:

1. **Modo estudio documental**: analizar la documentación, detectar inconsistencias, resumir capacidades, identificar pendientes y proponer mejoras sin simular atención al cliente.
2. **Modo agente final simulado**: asumir el rol del asistente comercial final de **Súper Genéricos del Valle** y responder pruebas conversacionales como si fuera el producto en operación, usando únicamente la información confirmada del repositorio.

Esta condición es obligatoria: **si el usuario pide probar el agente, simular conversaciones, validar respuestas o “actuar como el bot”, la IA debe activar el modo agente final simulado**.

### Cómo debe iniciar una IA externa

Antes de responder contenido operativo, la IA debe decirle al usuario que puede ayudar de dos formas:

```text
Puedo ayudarte de dos maneras:
1. Estudiar la documentación del repositorio y darte hallazgos, pendientes o recomendaciones.
2. Asumir el rol del agente IA comercial final de Súper Genéricos del Valle para simular pruebas conversacionales.

¿Quieres que analice la documentación o que actúe como el agente final?
```

Si el usuario elige actuar como agente final, la IA debe leer como mínimo:

- `Prompt Inicial.md`
- `objetivo.md`
- `personalidad.md`
- `informacion-adicional.md`
- `preguntas-frecuentes.md`
- `acciones/Transferencia a humano.md`
- Los archivos de `acciones/` relacionados con la prueba solicitada.

### Reglas del modo agente final simulado

- Responder como representante comercial senior de **Súper Genéricos del Valle**, con tono profesional, cálido, consultivo y claro.
- Usar solo datos confirmados en los archivos del repositorio.
- No inventar precios, disponibilidad, rutas, tiempos de entrega, políticas, SLA, responsables, horarios ni condiciones comerciales.
- Si falta información, pedir el dato mínimo necesario o indicar que el caso debe ser validado por un asesor humano.
- Si una acción depende de GHL, decirlo internamente como simulación, no como ejecución real. Ejemplo: `[simulación GHL: se transferiría el caso a humano según el escenario documentado]`.
- No afirmar que una tarea, etiqueta, transferencia, cita, workflow o actualización de contacto fue ejecutada realmente si no hay acceso a GHL.
- En temas farmacéuticos, orientar comercialmente y escalar; no dar recomendaciones médicas.
- Mantener separación entre “respuesta al cliente final” y “nota de simulación” cuando el usuario esté probando automatizaciones.

### Formato recomendado para pruebas simuladas

Cuando el usuario pida una prueba, responde así:

```text
Respuesta al cliente:
<mensaje que enviaría el agente final>

Nota de simulación:
<acción GHL que se activaría, estado de confirmación y pendientes si aplica>
```

Esta regla no reemplaza la trazabilidad documental: cualquier hallazgo, pendiente o inconsistencia detectada durante una simulación debe registrarse o recomendarse para registro en `Resumen-estado-y-requerimientos-cliente.md`.

## 3. Regla principal de trazabilidad

**No agregues, cambies ni elimines información operativa sin indicar su fuente o estado.**

Toda IA que trabaje aquí debe registrar avances relevantes, especialmente:

- Hitos completados, mejoras aplicadas y correcciones documentales.
- Cambios en prompts, reglas de negocio, acciones o automatizaciones.
- Pendientes detectados, dudas para el cliente y decisiones tomadas.
- Suposiciones realizadas, problemas encontrados y recomendaciones futuras.

Usa estas marcas cuando corresponda:

- `[confirmado]`: aparece en los archivos actuales o fue validado por cliente/equipo.
- `[pendiente]`: falta completar el dato o parámetro.
- `[requiere cliente]`: depende de decisión o aprobación del cliente.
- `[requiere prueba en GHL]`: debe validarse dentro de Go High Level antes de considerarse estable.

Si un dato no está confirmado, NO lo presentes como hecho. Esto no es burocracia: es lo que evita que el bot prometa cosas falsas al cliente final.

## 4. Dónde registrar avances y pendientes

Registra el estado operativo en `Resumen-estado-y-requerimientos-cliente.md`. Si el cambio afecta una automatización, actualiza también el archivo correspondiente en `acciones/`. Si afecta conversación o comportamiento del asistente, revisa `Prompt Inicial.md`, `objetivo.md`, `personalidad.md` y `preguntas-frecuentes.md`.

### Registro operativo del proyecto

Usa esta tabla para dejar trazabilidad de avances relevantes. Mantén las filas más recientes arriba.

| Fecha | Tipo | Descripción | Archivo afectado | Estado | Responsable/IA | Próximo paso |
|---|---|---|---|---|---|---|
| 2026-07-08 | Regla operativa | Se agregó la regla crítica para que una IA externa pueda elegir entre estudiar la documentación o actuar como agente final simulado para pruebas conversacionales. | `AGENTS.md` | Completado | Codex | Usar esta regla cuando se comparta el repositorio con ChatGPT u otra IA externa. |
| 2026-07-08 | Hito | Se creó el plan formal de trabajo de implementación de dos semanas para impresión, revisión y firma. | `Plan de trabajo - Implementacion agente IA GHL.md` | Completado | Codex | Confirmar si el número de WhatsApp del viernes será de prueba o real. |
| 2026-07-08 | Hito | Se consolidó esta guía operativa para futuras IAs del repositorio. | `AGENTS.md` | Completado | Codex | Usarla como primer archivo de lectura antes de nuevos cambios. |
| 2026-07-08 | Cambio de prompt | El repositorio ya contiene objetivo, personalidad, FAQ, información adicional y prompt inicial. | `objetivo.md`, `personalidad.md`, `informacion-adicional.md`, `preguntas-frecuentes.md`, `Prompt Inicial.md` | Completado | Repositorio actual | Mantener sincronía si cambia una regla comercial. |
| 2026-07-08 | Acción Go High Level | Transferencia a humano ya tiene escenarios activos y asignación documentada. | `acciones/Transferencia a humano.md` | Requiere prueba en GHL | IA/agente futuro | Validar reactivación, tareas, etiquetas y asignación real en GHL. |
| 2026-07-08 | Pendiente | Faltan etapas oficiales del embudo comercial y reglas para mover contactos. | `Resumen-estado-y-requerimientos-cliente.md` | Requiere cliente | Cliente / Grupo Nedemy | Solicitar definición antes de automatizar movimientos. |
| 2026-07-08 | Validación cliente | Faltan responsables por área: comercial, cartera, contabilidad, logística y PQRSF. | `Resumen-estado-y-requerimientos-cliente.md` | Requiere cliente | Cliente / Grupo Nedemy | Confirmar responsables, condiciones de escalamiento y SLA. |
| 2026-07-08 | Pendiente | Faltan datos obligatorios por tipo de solicitud, horarios, reactivación del bot y límites de seguimiento. | `Resumen-estado-y-requerimientos-cliente.md`, `acciones/` | Pendiente | Cliente / IA futura | Completar matriz antes de pasar a producción. |
| 2026-07-08 | Riesgo | Otras acciones están documentadas como matriz, pero requieren parametrización final. | `acciones/*.md` | Requiere prueba en GHL | IA/agente futuro | Completar condiciones, mensajes, etiquetas, tiempos y pruebas. |

## 5. Mapa de archivos del repositorio

| Ruta | Uso operativo |
|---|---|
| `README.md` | Vista general del repositorio, capacidades y estado resumido. No lo dupliques en otros archivos. |
| `objetivo.md` | Objetivo principal del asistente. Debe guiar cambios de alcance. |
| `personalidad.md` | Tono, estilo y criterios de atención del agente. |
| `informacion-adicional.md` | Datos institucionales, productos, canales y propuesta de valor. |
| `preguntas-frecuentes.md` | Respuestas base para consultas recurrentes. |
| `Prompt Inicial.md` | Prompt operativo principal del asistente. Cambiarlo exige revisión cruzada. |
| `Resumen-estado-y-requerimientos-cliente.md` | Registro principal de estado, pendientes y requerimientos del cliente. |
| `acciones/` | Matrices de acciones GHL: transferencia, seguimiento, detener bot, citas, flujos y actualización de contacto. |
| `workflow-chatbot-cliente-nuevo.md` | Simulación del flujo para contacto nuevo. |
| `workflow-clasificacion-clientes-ghl.md` | Clasificación de contactos por etiquetas en GHL. |
| `bot ia asignación Zona-ciudades.md` | Reglas de asignación por ciudad, zona y asesor. |
| `Plan de Acción - Super Genéricos.md` | Plan operativo amplio CRM + IA; úsalo como referencia, no como única fuente de verdad. |
| `Documento Base inicial - Cliente.md` | Insumo original del cliente; úsalo para contrastar decisiones. |

## 6. Clasificación de nueva información

Antes de escribir, clasifica el dato:

| Tipo de información | Dónde debe ir | Validación mínima |
|---|---|---|
| Objetivo, alcance o límites del agente | `objetivo.md` y resumen operativo | Confirmación del cliente/equipo. |
| Tono, personalidad o estilo de respuesta | `personalidad.md` y `Prompt Inicial.md` | Consistencia con atención profesional y cálida. |
| Datos de empresa, productos, canales, horarios | `informacion-adicional.md` o `preguntas-frecuentes.md` | Fuente confirmada; si no, marcar `[requiere cliente]`. |
| Respuestas frecuentes | `preguntas-frecuentes.md` | No contradecir datos institucionales. |
| Instrucciones del bot | `Prompt Inicial.md` | Revisar objetivo, personalidad, FAQ y acciones relacionadas. |
| Automatizaciones GHL | Archivo correspondiente en `acciones/` | Probar o marcar `[requiere prueba en GHL]`. |
| Avances, pendientes, decisiones | `Resumen-estado-y-requerimientos-cliente.md` | Registrar estado y fuente. |

## 7. Reglas para trabajar con acciones de Go High Level

- Mantén cada acción como matriz de escenarios; no reemplaces tablas por texto largo.
- Duplica la fila `XX` para nuevos escenarios y asigna un ID consecutivo.
- Completa, cuando aplique:
  - ID del escenario.
  - Estado habilitado/no habilitado.
  - Nombre del escenario.
  - Condición exacta de activación.
  - Frases de ejemplo del usuario.
  - Acción en Go High Level.
  - Responsable o usuario asignado.
  - Etiquetas.
  - Tareas a crear.
  - Mensaje final del agente.
  - Tiempo de reactivación del bot.
  - Reglas anti-duplicidad.
  - Dependencias con otros flujos.
  - Pruebas pendientes.
- No actives escenarios sin condición clara ni mensaje aprobado.
- Si una acción depende de configuración real de GHL, marca `[requiere prueba en GHL]`.
- Diferencia bien:
  - `Transferencia a humano`: pasa a una persona/equipo.
  - `Transferencia de Bot`: pasa a otro asistente/agente automatizado.
  - `Detener Bot`: pausa sin transferir necesariamente.
  - `Seguimiento automático`: continúa contacto con límites para evitar sobrecontacto.

## 8. Reglas para cambios en prompts

- No edites `Prompt Inicial.md` de forma aislada.
- Antes de cambiar el prompt, revisa objetivo, personalidad, información adicional, FAQ y acciones afectadas.
- Mantén el rol del asistente como representante senior/comercial de Súper Genéricos del Valle.
- No agregues promesas sobre precios, disponibilidad, rutas, tiempos, devoluciones o SLA si no están confirmadas.
- Si el prompt necesita una regla nueva, registra también el motivo en `Resumen-estado-y-requerimientos-cliente.md`.
- Si hay conflicto entre documentos, no improvises: marca el conflicto y pide confirmación.

## 9. Reglas de seguridad y calidad

- No inventes datos comerciales, legales, médicos, financieros ni logísticos.
- No sobreescribas cambios del usuario ni modifiques archivos no solicitados.
- No incluyas atribución de IA, `Co-Authored-By` ni firmas automáticas.
- Usa español neutro, claro y profesional en archivos técnicos.
- Protege datos personales: no agregues documentos, teléfonos, correos o identificadores nuevos sin fuente.
- En contenido farmacéutico, evita recomendaciones médicas; el agente debe orientar comercialmente y escalar cuando corresponda.
- Revisa consistencia entre años de trayectoria, número de clientes, referencias, horarios, canales y políticas antes de publicarlos.
- En pruebas simuladas, deja claro qué parte es respuesta del agente y qué parte es una nota de simulación para evitar confundir una acción real con una acción hipotética.

## 10. Flujo obligatorio antes de trabajar

1. Leer `AGENTS.md`.
2. Revisar `README.md`.
3. Revisar `Resumen-estado-y-requerimientos-cliente.md`.
4. Revisar `git status` para detectar cambios del usuario.
5. Identificar qué archivo corresponde modificar.
6. Leer los archivos relacionados con el cambio, no solo el archivo destino.
7. Identificar si el dato es `[confirmado]`, `[pendiente]`, `[requiere cliente]` o `[requiere prueba en GHL]`.
8. Aplicar el cambio mínimo necesario.
9. Actualizar el registro operativo y dejar próximos pasos claros.
10. Marcar si algo requiere validación del cliente o prueba en Go High Level.
11. Revisar el diff final antes de responder.

## 11. Pendientes actuales conocidos

| Pendiente | Estado | Archivo base | Riesgo si se ignora |
|---|---|---|---|
| Definir etapas oficiales del embudo comercial. | [requiere cliente] | `Resumen-estado-y-requerimientos-cliente.md` | Automatizaciones moverán contactos sin criterio validado. |
| Definir reglas exactas para mover contactos entre etapas. | [requiere cliente] | `Resumen-estado-y-requerimientos-cliente.md` | Pérdida de trazabilidad comercial. |
| Definir reglas de reversa o recategorización. | [requiere cliente] | `Resumen-estado-y-requerimientos-cliente.md`, `acciones/` | Un contacto podría quedar en una etapa incorrecta sin ruta de corrección. |
| Confirmar áreas destino, responsables y SLA. | [requiere cliente] | `Resumen-estado-y-requerimientos-cliente.md` | Derivaciones incorrectas o sin seguimiento. |
| Definir condiciones de escalamiento por área. | [requiere cliente] | `acciones/Transferencia a humano.md`, `Resumen-estado-y-requerimientos-cliente.md` | El bot podría transferir casos al área equivocada. |
| Completar datos obligatorios por tipo de solicitud. | [requiere cliente] | `Resumen-estado-y-requerimientos-cliente.md` | El bot puede pedir datos incompletos o innecesarios. |
| Confirmar horarios de atención. | [requiere cliente] | `informacion-adicional.md`, `Prompt Inicial.md` | El agente podría prometer disponibilidad no validada. |
| Definir cuándo detener y reactivar el bot. | [requiere cliente] | `acciones/Detener Bot.md`, `acciones/Transferencia a humano.md` | El bot podría intervenir cuando debe guardar silencio, o no reactivarse. |
| Definir frecuencia y límite de seguimientos automáticos. | [requiere cliente] | `acciones/Seguimiento automático.md` | Riesgo de sobrecontacto o abandono del lead. |
| Confirmar mensajes aprobados para transferencias y cierres. | [requiere cliente] | `acciones/Transferencia a humano.md`, `preguntas-frecuentes.md`, `Prompt Inicial.md` | Mensajes inconsistentes o no aprobados por el cliente. |
| Definir dónde crear tareas/tickets. | [requiere cliente] | `acciones/` | Seguimientos sin responsable operativo claro. |
| Definir etiquetas y estados para seguimiento. | [requiere cliente] | `acciones/`, `workflow-clasificacion-clientes-ghl.md` | Reportes y automatizaciones perderán consistencia. |
| Definir reportes necesarios. | [requiere cliente] | `Resumen-estado-y-requerimientos-cliente.md` | No habrá medición clara del desempeño del agente. |
| Parametrizar acciones distintas a transferencia humana. | [pendiente] | `acciones/` | Matrices existen, pero no están listas para producción. |
| Validar reglas de pausa/reactivación del bot. | [requiere prueba en GHL] | `acciones/Detener Bot.md`, `acciones/Transferencia a humano.md` | El bot podría reactivarse tarde, pronto o nunca. |
| Confirmar consistencia de datos comerciales variables. | [requiere cliente] | `informacion-adicional.md`, `Prompt Inicial.md`, workflows | Pueden aparecer diferencias como años de trayectoria, clientes o referencias. |
| Validar mapeo ciudad → zona → asesor en GHL. | [requiere prueba en GHL] | `bot ia asignación Zona-ciudades.md` | Asignación incorrecta de clientes o tareas. |

## 12. Formato recomendado para commits o cambios

Usa commits convencionales, sin atribución de IA:

```text
docs: actualiza reglas del agente
docs: agrega escenario de transferencia a humano
docs: completa matriz de seguimiento automático
docs: actualiza pendientes del cliente
prompt: ajusta prompt inicial del agente
acciones: documenta flujo de trabajo en GHL
docs: actualiza matriz de transferencia a humano
docs: ajusta prompt inicial del agente comercial
docs: registra pendientes de configuración GHL
chore: organiza documentación operativa del agente
```

En la descripción del cambio, incluye:

- Qué archivo cambió.
- Qué dato se confirmó o quedó pendiente.
- Fuente usada.
- Si requiere prueba en GHL o aprobación del cliente.

## 13. Criterio final de calidad

Un cambio está listo cuando otra IA o persona puede responder estas preguntas sin reconstruir todo desde cero:

- ¿Qué se cambió y por qué?
- ¿De dónde salió el dato?
- ¿Está confirmado, pendiente, requiere cliente o requiere prueba en GHL?
- ¿Qué archivo queda como fuente operativa?
- ¿Qué riesgo queda abierto?

Si no puedes responder eso, todavía no está listo. Sé riguroso: una automatización mal documentada después se convierte en una operación rota.
