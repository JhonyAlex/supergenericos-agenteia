# Workflow: Clasificación de Contactos por Etiqueta en GHL

> **Objetivo:** Identificar automáticamente si un contacto es **cliente nuevo** o **cliente existente** al recibir un mensaje por WhatsApp y dirigirlo al flujo correspondiente.
> **Plataforma:** GoHighLevel (GHL) — Nonoi, Asistente Virtual de Super Genéricos del Valle

---

## 🧭 Flujo de Decisión Visual

```
  ┌─────────────────────────────────────────┐
  │  📱 Contacto escribe por WhatsApp       │
  └──────────────────┬──────────────────────┘
                     │
                     ▼
  ┌─────────────────────────────────────────┐
  │  🔍 GHL: ¿El contacto ya existe en CRM? │
  │  (búsqueda por número de teléfono)      │
  └──────────┬──────────────────┬───────────┘
             │                  │
        ✅ SÍ EXISTE       ❌ NO EXISTE
             │                  │
             ▼                  ▼
  ┌──────────────────┐ ┌──────────────────────────┐
  │ Tiene etiqueta   │ │ Contact created          │
  │ `cliente-exist`? │ │ (disparador del workflow)│
  └──┬───────┬───────┘ └───────────┬──────────────┘
     │       │                      │
    SÍ      NO                      ▼
     │       │        ┌──────────────────────────┐
     │       │        │ 🏷️ Añadir etiqueta:      │
     │       │        │ `cliente-nuevo`           │
     │       │        └───────────┬──────────────┘
     │       │                    │
     │       ▼                    ▼
     │  ┌──────────────────┐ ┌──────────────────────────┐
     │  │ 🏷️ Añadir etiq:  │ │ 💬 Enviar mensaje        │
     │  │ `cliente-exist`  │ │ de bienvenida → NUEVO    │
     │  └───────┬──────────┘ │ (Flujo §4.3)             │
     │          │            └───────────┬──────────────┘
     │          ▼                        │
     │  ┌──────────────────┐             │
     │  │ 💬 Enviar mensaje│             ▼
     │  │ de bienvenida →  │      ┌──────────────────┐
     │  │ EXISTENTE        │      │ 📋 Capturar datos│
     │  │ (Flujo §4.4)     │      │ 1. Nombre        │
     │  └──────────────────┘      │ 2. Ciudad/Depto  │
                                 │ 3. RUT/Cámara    │
                                 └────────┬─────────┘
                                          │
                                          ▼
                                   ┌──────────────────┐
                                   │ 🏷️ Quitar etiq:  │
                                   │ `cliente-nuevo`   │
                                   │ 🏷️ Añadir etiq:  │
                                   │ `cliente-exist`   │
                                   └────────┬─────────┘
                                            │
                                            ▼
                                     ┌──────────────────┐
                                     │ 📍 Asignar ZONA  │
                                     │ Ciudad → Zona    │
                                     │ Zona → Asesor    │
                                     └──────────────────┘
```

---

## 🏷️ Diccionario de Etiquetas

| Etiqueta | Significado | Cuándo se añade | Cuándo se quita |
|---|---|---|---|
| `cliente-nuevo` | Contacto sin registro en CRM | Al crear el contacto por primera vez | Cuando completa el registro |
| `cliente-exist` | Contacto ya registrado y validado | Cuando completa su registro con RUT | **Nunca se quita** (marcador permanente) |
| `cliente-prospecto` | Nuevo registro en proceso de seguimiento | Tras completar registro inicial | Cuando realiza su primera compra |
| `recibe-ofertas-si` | Cliente que acepta recibir ofertas semanales | Al confirmar que desea ofertas | Si el cliente pide ser excluido |
| `recibe-ofertas-no` | Cliente que NO desea ofertas | Al rechazar recibir ofertas | Si el cliente cambia de opinión |
| `asesor-humano` | Solicitó ser transferido a un humano | Al escribir "ASESOR" o disparar transferencia | Tras ser atendido por humano |
| `zona-quindio` | Cliente asignado a zona Quindío | Tras completar registro y mapeo ciudad | Si cambia de zona |
| `zona-risaralda` | Cliente asignado a zona Risaralda | Tras completar registro y mapeo ciudad | Si cambia de zona |
| `zona-tulua` | Cliente asignado a zona Tuluá | Tras completar registro y mapeo ciudad | Si cambia de zona |
| `zona-cauca` | Cliente asignado a zona Cauca | Tras completar registro y mapeo ciudad | Si cambia de zona |
| `zona-cundinamarca` | Cliente asignado a zona Cundinamarca | Tras completar registro y mapeo ciudad | Si cambia de zona |
| `zona-sur-valle` | Cliente asignado a zona Sur Valle | Tras completar registro y mapeo ciudad | Si cambia de zona |
| `zona-centro-valle` | Cliente asignado a zona Centro Valle | Tras completar registro y mapeo ciudad | Si cambia de zona |
| `zona-narino` | Cliente asignado a zona Nariño | Tras completar registro y mapeo ciudad | Si cambia de zona |
| `zona-gerencia` | Cliente asignado a zona Gerencia | Tras completar registro y mapeo ciudad | Si cambia de zona |
| `zona-callcenter` | Cliente sin ciudad en mapa → reparto equitativo | Cuando la ciudad no coincide con ninguna zona | Si se reasigna después |

---

## 🔀 Workflow Completo en GHL

### Paso 1: Disparador de Entrada

```
📥 TRIGGER: Contact Created O Incoming Message
   │
   ├── Si "Contact Created" → va directo a Paso 2
   └── Si "Incoming Message" → busca contacto por teléfono
         ├── ✅ Encontrado → va a Paso 3
         └── ❌ No encontrado → crea contacto → va a Paso 2
```

### Paso 2: Contacto NO Existe en CRM (Flujo Nuevo)

```
🆕 FLUJO: "Registro Cliente Nuevo"
   │
   ├── 🏷️ Add Tag: `cliente-nuevo`
   │
   ├── 💬 Mensaje 1: Bienvenida + presentación Nonoi (§4.3.1)
   │     "👋 ¡Hola! Soy Nonoi, el asistente virtual de Super Genéricos..."
   │     Botones: [Sí, quiero registrarme] [No, en otra ocasión]
   │
   ├── 📥 If "Sí" → Mensaje 2: Pedir datos (§4.3.3)
   │     1️⃣ Nombre y apellidos
   │     2️⃣ Ciudad y departamento
   │
   ├── 📥 Recibe datos → Mensaje 3: Pedir RUT
   │     "📎 Para completar tu registro, necesito tu RUT..."
   │
   ├── 📥 Recibe RUT → Mensaje 4: Confirmación
   │     "✅ ¡Gracias! Tu información está siendo procesada..."
   │
   ├── 🔄 Acciones internas:
   │     ├── Crear/actualizar contacto en CRM
   │     ├── Campo CIUDAD → derivar ZONA (mapeo §1.3)
   │     ├── ZONA → asignar ASESOR (mapeo §1.2)
   │     ├── 🏷️ Remove Tag: `cliente-nuevo`
   │     ├── 🏷️ Add Tag: `cliente-exist`
   │     ├── 🏷️ Add Tag: `zona-{nombre-zona}`
   │     ├── 🏷️ Add Tag: `cliente-prospecto`
   │     ├── Pipeline: Mover a "Prospecto Nuevo"
   │     └── 📋 Crear tarea al asesor asignado
   │
   └── 📥 If "No" → Mensaje despedida (§4.3.2)
         "👋 Entiendo, no hay problema..."
         └── 📋 Crear tarea Call Center (reparto equitativo)
```

### Paso 3: Contacto YA Existe en CRM (Flujo Existente)

```
✅ FLUJO: "Atención Cliente Existente"
   │
   ├── 🏷️ Add Tag: `cliente-exist` (si no la tiene)
   │
   ├── 💬 Mensaje de bienvenida diferenciado (§4.4)
   │     "👋 ¡Hola de nuevo! Bienvenido/a a Super Genéricos..."
   │     "¿En qué puedo ayudarte hoy?"
   │
   ├── 📥 Menú de opciones (actual: solo comercial):
   │     ├── [🛒 Ver ofertas semanales] → si `recibe-ofertas-si`
   │     ├── [📞 Hablar con mi asesor] → transferencia al asesor de su zona
   │     └── [🙋 Hablar con ASESOR] → transferencia general
   │
   └── 🔍 Verificar zona asignada:
         ├── Si tiene `zona-{*}` → todo OK
         └── Si NO tiene zona → re-evaluar ciudad → asignar zona
```

---

## 🗺️ Mapeo Ciudad → Zona → Asesor → Etiqueta

```
┌─────────────────┐    ┌──────────────────┐    ┌────────────────────┐    ┌─────────────────┐
│    CIUDAD       │───▶│      ZONA        │───▶│     ASESOR         │───▶│    ETIQUETA     │
├─────────────────┤    ├──────────────────┤    ├────────────────────┤    ├─────────────────┤
│ Armenia        │    │ Quindío          │    │ Erika Garcia       │    │ zona-quindio   │
│ Pereira        │    │ Risaralda        │    │ Erika Garcia       │    │ zona-risaralda │
│ Dosquebradas   │    │ Risaralda        │    │ Erika Garcia       │    │ zona-risaralda │
│ Tuluá          │    │ Tuluá            │    │ Luz Caicedo        │    │ zona-tulua     │
│ Popayán        │    │ Cauca            │    │ Luz Caicedo        │    │ zona-cauca     │
│ Cali           │    │ Sur Valle        │    │ Angie Heredia      │    │ zona-sur-valle │
│ Palmira        │    │ Sur Valle        │    │ Angie Heredia      │    │ zona-sur-valle │
│ Pasto          │    │ Nariño           │    │ Angie Heredia      │    │ zona-narino    │
│ Bogotá         │    │ Cundinamarca     │    │ Luz Caicedo        │    │ zona-cundinam. │
│ [Sin match]    │    │ Call Center      │    │ Reparto equitativo │    │ zona-callcenter│
│ [Gerencia]     │    │ Gerencia         │    │ Erika Garcia       │    │ zona-gerencia  │
└─────────────────┘    └──────────────────┘    └────────────────────┘    └─────────────────┘
```

---

## ⚙️ Configuración en GHL — Paso a Paso

### 1. Crear Etiquetas Personalizadas

```
Settings → Tags → Add Tag

  [ ] cliente-nuevo
  [ ] cliente-exist
  [ ] cliente-prospecto
  [ ] recibe-ofertas-si
  [ ] recibe-ofertas-no
  [ ] asesor-humano
  [ ] zona-quindio
  [ ] zona-risaralda
  [ ] zona-tulua
  [ ] zona-cauca
  [ ] zona-cundinamarca
  [ ] zona-sur-valle
  [ ] zona-centro-valle
  [ ] zona-narino
  [ ] zona-gerencia
  [ ] zona-callcenter
```

### 2. Crear Workflow: "Clasificación Inicial de Contacto"

```
Automation → Workflows → Create Workflow → Start from Scratch

📥 TRIGGER:
  └── Contact Created
  └── Incoming Message (WhatsApp)

🔀 IF / ELSE BRANCH:
  ├── Condition: Contact Tag IS `cliente-exist`
  │     └── YES → Go to "Flujo Existente"
  │     └── NO  → Continue...
  │
  ├── Condition: Contact already exists in CRM?
  │     └── YES → Add Tag: `cliente-exist` → Go to "Flujo Existente"
  │     └── NO  → Continue...
  │
  └── Default (Nuevo):
        ├── Add Tag: `cliente-nuevo`
        ├── Start Workflow: "Registro Cliente Nuevo"
        └── END
```

### 3. Crear Workflow: "Registro Cliente Nuevo"

```
📥 TRIGGER: Tag Added → `cliente-nuevo`

  1. 💬 Send WhatsApp: Mensaje bienvenida (§4.3.1)
  2. ⏳ Wait for Reply
  3. 🔀 IF Reply contains "sí" / "quiero":
     ├── 💬 Send WhatsApp: Pedir nombre + ciudad (§4.3.3)
     ├── ⏳ Wait for Reply
     ├── 📝 Update Contact Field: Name, Ciudad
     ├── 💬 Send WhatsApp: Pedir RUT
     ├── ⏳ Wait for Reply / Document Upload
     ├── 📝 Update Contact Field: RUT (file attachment)
     ├── 💬 Send WhatsApp: Confirmación
     ├── 🏷️ Remove Tag: `cliente-nuevo`
     ├── 🏷️ Add Tag: `cliente-exist`
     ├── 🔀 IF/ELSE: Ciudad → Zona (lookup table)
     │     └── Add Tag: `zona-{zona}`
     ├── 👤 Assign Contact: Asesor de la zona
     ├── 📋 Create Task: "Seguir contacto nuevo"
     └── END

  🔀 IF Reply contains "no" / "otra":
     ├── 💬 Send WhatsApp: Despedida (§4.3.2)
     ├── 📋 Create Task: "Llamar prospecto" → Call Center
     └── END
```

### 4. Crear Workflow: "Atención Cliente Existente"

```
📥 TRIGGER: Tag Added → `cliente-exist` O Contact already has `cliente-exist`

  1. 💬 Send WhatsApp: Mensaje bienvenida existente (§4.4)
  2. ⏳ Wait for Reply
  3. 🔀 IF Reply contains "ASESOR" / "humano":
     ├── 🏷️ Add Tag: `asesor-humano`
     ├── 👤 Assign: Asesor de su zona (por etiqueta `zona-{*}`)
     ├── 📋 Create Task: "Contacto solicitó asesor humano"
     └── END

  4. 🔀 IF Reply contains "oferta" / "catalogo":
     ├── 🔍 IF Contact Tag IS `recibe-ofertas-si`:
     │     └── 💬 Send: Link ofertas semanales
     │     └── END
     ├── 🔍 IF Contact Tag IS NOT `recibe-ofertas-si`:
     │     ├── 💬 Send: "¿Deseas recibir ofertas semanales?"
     │     ├── ⏳ Wait for Reply
     │     ├── 🔀 IF "sí":
     │     │     ├── 🏷️ Add Tag: `recibe-ofertas-si`
     │     │     ├── 🏷️ Remove Tag: `recibe-ofertas-no`
     │     │     └── 💬 Send: Link ofertas
     │     └── 🔀 IF "no":
     │           ├── 🏷️ Add Tag: `recibe-ofertas-no`
     │           └── END

  5. 🔀 IF Reply contiene "pedido" / "cotización":
     ├── 👤 Assign: Asesor de su zona
     ├── 📋 Create Task: "Atender solicitud de pedido"
     └── END
```

---

## 📊 Resumen de Estados del Contacto

```
Estado              │ Etiqueta(s) activa(s)            │ Acción esperada
────────────────────┼──────────────────────────────────┼────────────────────
Desconocido         │ (ninguna)                        │ Iniciar flujo nuevo
En registro         │ `cliente-nuevo`                  │ Capturar datos
Registrado          │ `cliente-exist`                  │ Flujo existente
Prospecto activo    │ `cliente-exist` + `prospecto`   │ Seguimiento asesor
Cliente activo      │ `cliente-exist` (+ zona)         │ Atención normal
Recibe ofertas      │ `recibe-ofertas-si`              │ Envío lunes automático
No recibe ofertas   │ `recibe-ofertas-no`              │ Excluido de difusión
Solicitó humano     │ `asesor-humano`                  │ Transferir a humano
```

---

## 🔄 Flujo de Ofertas Semanales (Automático)

```
📅 TRIGGER: Every Monday at 8:00 AM

  1. 🔍 Filter: Contacts with Tag `recibe-ofertas-si`
  2. 🔍 Filter: AND Tag `cliente-exist`
  3. 💬 Send WhatsApp: "🔥 ¡Ofertas de la semana!"
     └── Include: Link al PDF de ofertas
  4. END
```

---

## ⚠️ Reglas de Oro de Etiquetado

| # | Regla | Por qué |
|---|---|---|
| 1 | **`cliente-nuevo` y `cliente-exist` son mutuamente excluyentes** | Un contacto NO puede tener ambas etiquetas al mismo tiempo |
| 2 | **Al completar registro: quitar `cliente-nuevo`, poner `cliente-exist`** | Garantiza transición limpia entre estados |
| 3 | **`cliente-exist` NUNCA se quita** | Es marcador permanente de que ya fue validado |
| 4 | **La etiqueta de zona siempre refleja la ciudad actual del contacto** | Si cambia la ciudad, se actualiza la zona |
| 5 | **Un contacto solo puede tener UNA etiqueta `zona-{*}`** | Múltiples zonas causan conflicto de asignación |
| 6 | **Si no hay match de ciudad → `zona-callcenter`** | Garantiza que ningún contacto queda sin asesor |

---

## 📋 Checklist de Implementación

- [ ] Crear todas las etiquetas personalizadas en GHL
- [ ] Configurar campo personalizado ZONA con opciones
- [ ] Configurar campo personalizado CIUDAD
- [ ] Configurar campo personalizado APLICA OFERTAS (Sí/No)
- [ ] Crear workflow "Clasificación Inicial de Contacto"
- [ ] Crear workflow "Registro Cliente Nuevo"
- [ ] Crear workflow "Atención Cliente Existente"
- [ ] Crear workflow "Ofertas Semanales" (trigger: lunes)
- [ ] Configurar lookup table: Ciudad → Zona
- [ ] Configurar asignación: Zona → Asesor
- [ ] Probar con contacto nuevo (número no existente)
- [ ] Probar con contacto existente (número ya en CRM)
- [ ] Probar transición nuevo → existente
- [ ] Probar asignación de zona por ciudad
- [ ] Probar flujo de ofertas semanales
- [ ] Probar transferencia a humano (palabra "ASESOR")
