# Resumen general del agente IA: estado actual y requerimientos pendientes

## 1) ¿Qué está documentado actualmente?

### Base del asistente

- Objetivo del agente definido: atención comercial y soporte a clientes/prospectos.
- Personalidad definida: profesional, cálida, consultiva, proactiva y confiable.
- Información institucional cargada: empresa, productos destacados, canales de contacto, servicios digitales y propuesta de valor.
- Preguntas frecuentes completas: empresa, productos, horarios, cobertura, devoluciones, PQRSF, pagos y escalamiento a humano.
- Prompt inicial estructurado con rol, contexto, instrucciones y ejemplo de respuesta.

### Acciones/automatizaciones ya contempladas (estructura)

- Añadir información de contacto.
- Detener bot/asistente virtual.
- Iniciar flujo de trabajo.
- Reserva de citas.
- Seguimiento automático.
- Transferencia a humano.
- Transferencia a otro bot/agente.

### Acciones parcialmente configuradas o activas

- Transferencia a humano: sí tiene escenarios activos (solicitud de asesor, falta de información, no resolución, requisitos especiales, rechazo de documentos).
- Otras acciones: tienen plantilla/matriz, pero falta parametrización final por escenario.

## 2) ¿Qué necesitamos del cliente para completar y mejorar?

Para avanzar sin suposiciones, requerimos la siguiente definición:

### A. Embudo comercial y movimiento de etapas

- Etapas oficiales del embudo (ejemplo: Nuevo lead -> Contactado -> Interesado -> Cotización -> Negociación -> Cierre ganado/perdido).
- Reglas exactas para mover etapa: qué mensaje/disparador mueve cada contacto a cada etapa.
- Reglas de reversa o recategorización (por ejemplo, si no responde en X días).

### B. Derivación por áreas internas (enrutamiento)

- Áreas destino y responsables: Comercial, Contabilidad, Cartera, Logística, PQRSF, etc.
- Condiciones para escalar a cada área (frases, intención detectada, tipo de solicitud).
- SLA esperado por área (tiempo máximo de primera respuesta).

### C. Casos de negocio clave para automatizar

- Cobranza/pagos pendientes -> Contabilidad/Cartera.
- Solicitud de factura o soporte de pago -> Contabilidad.
- Novedades de entrega/pedido -> Logística.
- Reclamos formales -> PQRSF.
- Negociación especial o volumen -> Comercial senior.

### D. Datos obligatorios por tipo de solicitud

- Qué campos pedir de forma obligatoria (NIT, razón social, número de pedido/factura, ciudad, teléfono, correo, documento soporte).
- Qué validaciones aplicar (formatos, obligatoriedad, completitud).

### E. Reglas operativas de automatización

- Horarios de atención por área.
- Cuándo detener bot, cuándo reactivar y en cuánto tiempo.
- Frecuencia y límite de seguimientos automáticos por caso.
- Mensajes aprobados para confirmaciones, transferencias y cierres.

### F. Integraciones y trazabilidad

- Dónde crear tareas/tickets (CRM, mesa de ayuda, otro).
- Qué etiquetas/estados usar para seguimiento.
- Qué reportes necesitan: volumen por tipo de caso, tiempos de atención, conversiones, casos transferidos.
