# Agente IA Comercial | Super Genericos del Valle

> Asistente virtual para atencion comercial, soporte de solicitudes y automatizacion de flujos con escalamiento inteligente.

## Vista general

El objetivo de este repositorio es centralizar la documentacion funcional del agente IA para que el equipo pueda:

- Atender clientes con respuestas consistentes y profesionales.
- Activar acciones automaticas segun reglas del negocio.
- Escalar casos a humano o a otras areas cuando aplique.
- Medir, ajustar y mejorar el desempeno en ciclos de prueba.

## Que contiene este repositorio

| Documento | Proposito |
|---|---|
| `objetivo.md` | Define el objetivo principal del agente. |
| `personalidad.md` | Establece tono, estilo y forma de atencion. |
| `informacion-adicional.md` | Consolida datos institucionales, productos y canales. |
| `preguntas-frecuentes.md` | Estandariza respuestas para consultas recurrentes. |
| `Prompt Inicial.md` | Define el prompt base operativo del asistente. |
| `acciones/` | Matrices de escenarios para automatizaciones y derivaciones. |
| `Resumen-estado-y-requerimientos-cliente.md` | Estado actual y requerimientos pendientes del cliente. |

## Capacidades del agente

### Atencion y soporte
- Respuesta a preguntas comerciales frecuentes.
- Orientacion sobre productos, pagos, devoluciones y PQRSF.
- Transferencia a asesor humano cuando se requiere.

### Automatizacion de procesos
- Inicio de flujos de trabajo por intencion o condicion.
- Seguimiento automatico con secuencia y limite de intentos.
- Reserva de citas por escenario.
- Pausa y reactivacion del asistente segun reglas.

### Derivacion inteligente
- Transferencia a humano.
- Transferencia entre agentes/bots.
- Enrutamiento por tipo de caso (comercial, cartera, contabilidad, logistica, etc.).

## Estado actual (snapshot)

- `Transferencia a humano`: configurada con escenarios activos.
- Otras acciones en `acciones/`: disponibles en formato matriz para completar parametros.
- Base documental principal: lista para fase de pruebas, ajustes y mejora continua.

## Que falta para completar la automatizacion

- Definir etapas oficiales del embudo comercial.
- Acordar reglas exactas para mover contactos entre etapas.
- Definir criterios de derivacion por area interna.
- Confirmar datos obligatorios por tipo de solicitud.
- Alinear mensajes finales, SLA y politicas de seguimiento.

## Flujo sugerido de trabajo

1. Completar parametros pendientes en las matrices de `acciones/`.
2. Validar escenarios con el cliente en entorno de pruebas.
3. Medir resultados y ajustar reglas de activacion.
4. Activar automatizaciones por fases hasta estabilizar operacion.

## Proximas mejoras recomendadas

- Dashboard de metricas (volumen, tiempos de respuesta, derivaciones).
- Priorizacion automatica por urgencia o valor comercial.
- Plantillas de respuesta por tipo de cliente (drogueria/distribuidor).
- Reglas anti-duplicidad para evitar activaciones repetidas.

## Referencia rapida de acciones

- `acciones/Añadir Información de Contacto.md`
- `acciones/Detener Bot.md`
- `acciones/Iniciar un flujo de trabajo.md`
- `acciones/Reserva de citas.md`
- `acciones/Seguimiento automático.md`
- `acciones/Transferencia a humano.md`
- `acciones/Transferencia de Bot.md`