# Workflow: Chatbot Simulación de Conversación — Cliente Nuevo (Nonoi)

> **Objetivo:** Simular las interacciones completas del asistente virtual **Nonoi** con un contacto nuevo por WhatsApp, mostrando las opciones de respuesta del chatbot y las acciones internas correspondientes.
> **Basado en:** Documento Base inicial - Cliente.md, sección "CONTACTO NUEVO: ✅Workflow nuevo cliente"
> **Plataforma:** GoHighLevel (GHL) / CRM Super Genéricos del Valle

---

## 🧭 Vista General del Flujo

```
  ┌──────────────────────────────────────────┐
  │  📱 Mensaje recibido (contacto nuevo)    │
  └──────────────────┬───────────────────────┘
                     │
                     ▼
  ┌──────────────────────────────────────────┐
  │  💬 MENSAJE 1: Presentación Nonoi        │
  │  + texto de bienvenida empresa           │
  │  Botones: [Sí, quiero] [No, otra ocasión]│
  └────────────┬──────────────┬──────────────┘
               │              │
         [Sí, quiero]   [No, otra ocasión]
               │              │
               ▼              ▼
  ┌──────────────────┐ ┌────────────────────┐
  │  MENSAJE 2:      │ │  MENSAJE DESPEDIDA │
  │  Pedir nombre +  │ │  + link web        │
  │  ciudad          │ │  + palabra ASESOR  │
  └────────┬─────────┘ └────────────────────┘
           │
           ▼
  ┌──────────────────────────────────────────┐
  │  MENSAJE 3: Confirmar datos              │
  │  Pedir RUT / Cámara de Comercio          │
  │  + enlace política de datos              │
  └──────────────────┬───────────────────────┘
                     │
                     ▼
  ┌──────────────────────────────────────────┐
  │  MENSAJE 4: Confirmación final           │
  │  (internamente: asignar zona → asesor)   │
  │  + crear tarea al asesor                 │
  └──────────────────────────────────────────┘
```

---

## 💬 Simulación Completa de Conversación

### ⚡ ESCENARIO 1: Cliente Nuevo — Acepta Registrarse

#### **Mensajes Iniciales (Chatbot → Cliente)**

```
🤖 Nonoi (automático):

👋 ¡Hola! Soy Nonoi, el asistente virtual de Super Genéricos del Valle.

Veo que aún no estás registrado, así que déjame contarte un poco sobre nosotros:

Somos un distribuidor farmacéutico con más de 13 años de trayectoria, ubicado en Tuluá, Valle del Cauca, y con cobertura de envíos a nivel nacional.

Actualmente contamos con la confianza de más de 900 clientes en todo el país. En nuestro portafolio encontrarás más de 5.000 referencias, que incluyen: medicamentos, productos naturales, cuidado personal e insumos médicos.

También trabajamos con diferentes canales como droguerías, tiendas naturistas, cacharrerías y distribuidores, lo que nos permite ofrecer precios competitivos y ofertas exclusivas cada semana para tu negocio.

👉 ¿Quieres registrarte para acceder a nuestro portafolio y precios especiales? 🙌

[BOTÓN 1] ✅ Sí, quiero registrarme
[BOTÓN 2] 👋 No, en otra ocasión
```

---

#### **Opción A: Cliente hace clic en "No, en otra ocasión"**

```
🤖 Nonoi (automático):

👋 Entiendo, no hay problema.

Cuando quieras registrarte en Super Genéricos del Valle estaremos listos para atenderte. 💚

Mientras tanto, si deseas conocer más sobre nosotros, puedes visitar 👉
🔗 www.supergenericosdelvalle.com

Y si en cualquier momento prefieres hablar con un asesor, solo escribe la palabra ASESOR y te conectaré de inmediato.

¡Gracias por tu interés en nosotros! 🙌
```

**🔧 Acciones internas del CRM:**

| Acción | Detalle |
|---|---|
| 🏷️ Añadir etiqueta | `cliente-nuevo` + `prospecto-rechazado` |
| 📋 Crear tarea | "Contactar prospecto — Call Center" |
| 👤 Asignar a | Reparto equitativo (Call Center) |
| 📅 Límite tarea | Antes de 4:00 PM del día siguiente |
| Pipeline | Mover a "Prospecto — No listo aún" |

---

#### **Opción B: Cliente hace clic en "Sí, quiero registrarse"**

**Paso 1: Solicitud de nombre y ciudad**

```
🤖 Nonoi (automático):

👋 ¡Genial! Para registrarte necesito algunos datos básicos, con los cuales podré asignarte un asesor personalizado que te acompañará en todo el proceso.

1️⃣ Tu nombre y apellidos completos
2️⃣ Ciudad y departamento donde se encuentra tu negocio

Puedes responder ambos datos en un solo mensaje. 😊
```

**📥 Respuesta del cliente (ejemplo):**

```
👤 Cliente:

Carlos Andrés Mejía
Pereira, Risaralda
```

**Paso 2: Solicitud de RUT / Cámara de Comercio**

```
🤖 Nonoi (automático):

✅ ¡Gracias por tu información, Carlos!

📎 Para completar tu registro y ofrecerte los mejores precios y condiciones comerciales adaptadas a tu negocio, necesito que me compartas tu RUT o tu certificado de Cámara de Comercio.

👉 No te preocupes, tu información será tratada de manera segura y confidencial. Solo la utilizamos para validar tu negocio y asignarte un asesor comercial personalizado que te acompañará en todo momento.

🔒 Puedes consultar nuestra Política de Tratamiento de Datos aquí:
📄 https://supergenericosdelvalle.com/wp-content/uploads/2023/12/POLITICA-DE-TRATAMIENTO-DE-DATOS-2022.pdf

Puedes enviar el documento como imagen o PDF directamente por aquí. 👇
```

**🔧 Acciones internas tras recibir nombre y ciudad:**

| Acción | Detalle |
|---|---|
| 📝 Actualizar campo | Nombre = "Carlos Andrés Mejía" |
| 📝 Actualizar campo | Ciudad = "Pereira" |
| 📝 Actualizar campo | Departamento = "Risaralda" |
| 🔀 Lookup | Pereira → Zona: **Risaralda** |
| 👤 Lookup | Zona Risaralda → Asesor: **Erika García Grajales** |
| 🏷️ Añadir etiqueta | `zona-risaralda` |
| 🏷️ Añadir etiqueta | `registro-en-proceso` |

**📥 Respuesta del cliente (ejemplo):**

```
👤 Cliente:
[Adjunta imagen/PDF del RUT]
```

**Paso 3: Confirmación final**

```
🤖 Nonoi (automático):

✅ ¡Gracias por tu información, Carlos!

La estoy procesando para asignarte el asesor comercial ideal que te acompañará en todo el proceso.

🤝 Gracias por confiar en Super Genéricos del Valle.

📋 Tu asesor asignado es: **Erika García Grajales**
📧 Contacto: callcenter1@supergenericosdelvalle.com

En las próximas horas recibirás una llamada o mensaje de tu asesor para completar el proceso y enviarte nuestro portafolio completo con precios.

¡Que tengas un excelente día! 💚
```

**🔧 Acciones internas tras recibir RUT:**

| Acción | Detalle |
|---|---|
| 📝 Adjuntar archivo | RUT al perfil del contacto |
| 📝 Actualizar campo | RUT = [documento recibido] |
| 🏷️ Quitar etiqueta | `cliente-nuevo` |
| 🏷️ Añadir etiqueta | `cliente-exist` |
| 🏷️ Añadir etiqueta | `cliente-prospecto` |
| 🏷️ Añadir etiqueta | `zona-risaralda` |
| 👤 Asignar contacto | Erika García Grajales (asesor de zona) |
| 📋 Crear tarea | "Seguir prospecto nuevo — Risaralda" |
| 📅 Límite tarea | Antes de 4:00 PM del día siguiente |
| Pipeline | Mover a "Prospecto Nuevo" |
| 📊 Estado | `prospecto-validado` |

---

### ⚡ ESCENARIO 2: Cliente Nuevo — No Proporciona Ciudad Válida

Si el cliente envía una ciudad que **no está en el mapeo de zonas**:

**📥 Respuesta del cliente:**

```
👤 Cliente:

María López
Leticia, Amazonas
```

**🤖 Respuesta del Chatbot:**

```
🤖 Nonoi (automático):

✅ ¡Gracias por tu información, María!

📎 Para completar tu registro y ofrecerte los mejores precios y condiciones comerciales adaptadas a tu negocio, necesito que me compartas tu RUT o tu certificado de Cámara de Comercio.

[texto continúa normal...]
```

**🔧 Acciones internas:**

| Acción | Detalle |
|---|---|
| 🔀 Lookup | Leticia → **Sin match** |
| 👤 Asignar | **Call Center** (reparto equitativo) |
| 🏷️ Añadir etiqueta | `zona-callcenter` |
| 📋 Crear tarea | Asignar equitativamente a Call Center |

---

### ⚡ ESCENARIO 3: Cliente Escribe "ASESOR" Durante Flujo Nuevo

Si en cualquier momento del flujo el cliente escribe la palabra clave:

**📥 Mensaje del cliente:**

```
👤 Cliente:
ASESOR
```

**🤖 Respuesta del Chatbot:**

```
🤖 Nonoi (automático):

👋 ¡Claro que sí! Te estoy conectando con un asesor comercial ahora mismo.

Un momento por favor, mientras transfiero tu conversación... 🔄

---
⚠️ [TRANSFERENCIA A HUMANO ACTIVADA]
El bot se ha detenido. Un asesor atenderá este contacto.
---
```

**🔧 Acciones internas:**

| Acción | Detalle |
|---|---|
| 🏷️ Añadir etiqueta | `asesor-humano` |
| 🤖 Detener bot | Desactivar respuestas automáticas |
| 📋 Crear tarea | "Contacto solicitó asesor humano — URGENTE" |
| 👤 Asignar | Call Center (reparto equitativo) |
| 📅 Límite tarea | Inmediata |
| Pipeline | Mover a "Transferido a humano" |

---

## 📊 Tabla de Decisiones y Respuestas del Chatbot

| # | Momento | Botón / Input | Respuesta del Bot | Acción CRM |
|---|---------|---------------|-------------------|------------|
| 1 | Bienvenida | [Sí, quiero] | Ir a Paso 2 (pedir datos) | Mantener `cliente-nuevo` |
| 2 | Bienvenida | [No, otra ocasión] | Mensaje despedida | Crear tarea Call Center |
| 3 | Pedir datos | Texto con nombre + ciudad | Ir a Paso 3 (pedir RUT) | Actualizar campos |
| 4 | Pedir datos | Texto sin ciudad | Repetir solicitud de ciudad | Esperar respuesta |
| 5 | Pedir RUT | Documento adjunto | Ir a Paso 4 (confirmación) | Completar registro |
| 6 | Pedir RUT | "no tengo" / "después" | Repetir solicitud amablemente | Mantener `registro-en-proceso` |
| 7 | Cualquier momento | "ASESOR" | Transferir a humano | Detener bot + tarea urgente |
| 8 | Cualquier momento | "ofertas" | "Te las enviaré cuando estés registrado" | Mantener flujo actual |

---

## ⚙️ Configuración Técnica en GHL

### Campos Personalizados Requeridos

| Campo | Tipo | Opciones | Obligatorio |
|---|---|---|---|
| `Nombre Establecimiento` | Texto | — | No |
| `Persona de Contacto` | Texto | — | Sí |
| `Ciudad` | Texto | — | Sí |
| `Zona` | Dropdown | Quindío, Risaralda, Gerencia, Tuluá, Cauca, Cundinamarca, Sur Valle, Centro Valle, Nariño, Call Center | No (auto) |
| `Catálogo del Cliente` | Dropdown | Minorista, Mayorista, Cacharrero, Minorista Tuluá | No |
| `Aplica Ofertas` | Dropdown | Sí, No | No |
| `RUT` | File Upload | PDF, imagen | Sí |
| `Cámara de Comercio` | File Upload | PDF, imagen | No |

### Tags (Etiquetas) Necesarias

```
cliente-nuevo
cliente-exist
cliente-prospecto
registro-en-proceso
prospecto-rechazado
zona-quindio
zona-risaralda
zona-gerencia
zona-tulua
zona-cauca
zona-cundinamarca
zona-sur-valle
zona-centro-valle
zona-narino
zona-callcenter
asesor-humano
```

---

## 🔀 Mapeo Ciudad → Zona → Asesor (Resumen)

| Ciudad Principal | Zona | Asesor | Email |
|---|---|---|---|
| Armenia, Calarcá, Montenegro, etc. | Quindío | Erika García | callcenter1@... |
| Pereira, Dosquebradas, Santa Rosa, etc. | Risaralda | Erika García | callcenter1@... |
| Manizales, Chinchiná, etc. | Risaralda | Erika García | callcenter1@... |
| Clientes gerencia (sin zona fija) | Gerencia | Erika García | callcenter1@... |
| Tuluá, La Victoria | Tuluá | Luz Cenaida | callcenter3@... |
| Popayán, Santander de Quilichao, etc. | Cauca | Luz Cenaida | callcenter3@... |
| Bogotá, Soacha, Chía, Zipaquirá, etc. | Cundinamarca | Luz Cenaida | callcenter3@... |
| Cali, Palmira, Jamundí, Yumbo, etc. | Sur Valle | Angie Heredia | callcenter2@... |
| Buga, Cartago, Zarzal, etc. | Centro Valle | Angie Heredia | callcenter2@... |
| Pasto, Ipiales, Tumaco, etc. | Nariño | Angie Heredia | callcenter2@... |
| Ciudad sin match en zonas | Call Center | Reparto equitativo | — |

---

## 📋 Checklist de Implementación

- [ ] Configurar mensaje de bienvenida inicial con botones
- [ ] Configurar respuesta para "No, en otra ocasión"
- [ ] Configurar captura de nombre + ciudad (Paso 2)
- [ ] Configurar captura de RUT / Cámara de Comercio (Paso 3)
- [ ] Configurar mensaje de confirmación final (Paso 4)
- [ ] Configurar palabra clave "ASESOR" → transferencia a humano
- [ ] Configurar lookup table: Ciudad → Zona
- [ ] Configurar asignación: Zona → Asesor
- [ ] Configurar asignación equitativa para Call Center
- [ ] Configurar creación automática de tareas
- [ ] Configurar actualización de pipeline stages
- [ ] Configurar etiquetado automático por estado
- [ ] Configurar detención del bot al transferir a humano
- [ ] Probar flujo completo con contacto nuevo
- [ ] Probir flujo con ciudad sin match
- [ ] Probar transferencia a humano en cada etapa

---

## ⚠️ Notas Importantes

1. **Un solo mensaje para datos:** El bot debe permitir que el cliente envíe nombre y ciudad en un solo mensaje. No es necesario pedirlos por separado.

2. **RUT es obligatorio:** Sin RUT o Cámara de Comercio, el registro no se considera completo. El bot debe insistir amablemente.

3. **Política de datos:** Siempre incluir el enlace a la política de tratamiento de datos al solicitar documentos.

4. **Asignación por zona, no por asesor:** Los clientes se ligan a una ZONA. Si cambia el asesor, solo se reasigna la zona completa.

5. **Call Center = reparto equitativo:** Cuando la ciudad no coincide con ninguna zona, el cliente va a Call Center y se reparte equitativamente entre los asesores disponibles.

6. **Detener bot al transferir:** Cuando se activa "ASESOR", el bot debe detenerse completamente para que el humano tome el control sin interferencia.

7. **Tareas con límite:** Las tareas creadas deben tener un límite de tiempo (antes de las 4:00 PM del día siguiente) para garantizar seguimiento oportuno.

---

*Documento creado el 13 de mayo de 2026 — Basado en especificaciones del cliente Super Genéricos del Valle S.A.S.*
