# Plan de Acción — Super Genéricos del Valle (CRM + IA)

> **Documento base:** Documento Base inicial - Cliente.md
> **Cliente:** Juan José — Super Genéricos del Valle S.A.S.
> **Fecha:** 2026-05-13

---

## Tabla de Contenidos

1. [Estructura Organizacional: Zonas y Asesores](#1-estructura-organizacional-zonas-y-asesores)
2. [Configuración del CRM: Contactos y Campos Personalizados](#2-configuración-del-crm-contactos-y-campos-personalizados)
3. [Embudo de Ventas](#3-embudo-de-ventas)
4. [Asistente Virtual Nonoi: Identidad, Tono y Flujos de Conversación](#4-asistente-virtual-nonoi-identidad-tono-y-flujos-de-conversación)
5. [Automatización de Tareas para Asesores](#5-automatización-de-tareas-para-asesores)
6. [Calendario de Rutas de Entrega](#6-calendario-de-rutas-de-entrega)
7. [Ofertas Semanales — Envío Automatizado](#7-ofertas-semanales--envío-automatizado)
8. [Política de WhatsApp, Bot y Matriz de Accesos](#8-política-de-whatsapp-bot-y-matriz-de-accesos)
9. [Elementos Pendientes, Dependencias y Fases Futuras](#9-elementos-pendientes-dependencias-y-fases-futuras)

---

## 1. Estructura Organizacional: Zonas y Asesores

### 1.1 Filosofía de Asignación

- Los clientes se asignan a una **zona**, y cada zona tiene un **asesor responsable**. ✅ El workflow: "Actualizar Zona/Usuarios responsables"
- Los clientes **NO** se ligan directamente a un usuario. ✅
- Ventaja: si se cambia un asesor, basta con reasignar la zona completa sin modificar cliente por cliente.
- *(Referencia cruzada: ver [Sección 2.3 — Zona y Asignación de clientes](#23-zona-y-asignación-de-clientes) y [Sección 4.3 — Flujo de registro de cliente nuevo](#43-flujo-de-registro-de-cliente-nuevo) donde la ciudad determina la zona y ésta el asesor).*

### 1.2 Mapeo de Asesores Comerciales

(✅usuarios creados - por confirmar ⚠️)

| Asesor                        | C.C.       | Email                                  | Zonas Asignadas                  |
| ----------------------------- | ---------- | -------------------------------------- | -------------------------------- |
| GARCIA GRAJALES ERIKA VANESSA | 1116240839 | callcenter1@supergenericosdelvalle.com | Quindío, Risaralda, Gerencia    |
| LLANTEN MONTERO LUZ CENAIDA   | 1060867317 | callcenter3@supergenericosdelvalle.com | Tuluá, Cauca, Cundinamarca      |
| HEREDIA HURTADO ANGIE VANESSA | 1010144834 | callcenter2@supergenericosdelvalle.com | Sur Valle, Centro Valle, Nariño |

> **Nota:** Se deben indicar zonas sin asesor y asesores con múltiples zonas.

### 1.3 Zonas Comerciales y Municipios

✅ Campos y opciones creados - revisar que estén todas ⚠️ Consultar si realmente se requiere poner todo.

#### ZONA: QUINDÍO

Armenia, Buenavista, Calarcá, Circasia, Córdoba, Filandia, Génova, La Tebaida, Montenegro, Pijao, Quimbaya, Salento, Alcalá, Andalucía, Bugalagrande.

#### ZONA: RISARALDA

Apía, Balboa, Belén de Umbría, Dosquebradas, Guática, La Celia, La Virginia, Marsella, Mistrató, Pereira, Pueblo Rico, Quinchía, Santa Rosa de Cabal, Santuario.
Aguadas, Anserma, Aranzazu, Belalcázar, Chinchiná, Filadelfia, La Dorada, La Merced, Manizales, Manzanares, Marmato, Marquetalia, Marulanda, Neira, Norcasia, Pácora, Palestina, Pensilvania, Riosucio, Risaralda, Salamina, Samaná, San José, Supía, Victoria, Villamaría, Viterbo.

#### ZONA: GERENCIA

Clientes puntuales que no se agrupan por ciudad. Asignación de manejo interno.

#### ZONA: TULUÁ

Tuluá, La Marina, Nariño.

#### ZONA: CAUCA

Popayán, Aguablanca, Argelia, Balboa, Bolívar, Buenos Aires, Cajibío, Caldono, Caloto, Corinto, El Tambo, Florencia, Guachené, Guapi, Inzá, Jambaló, La Sierra, La Vega, López de Micay, Mercaderes, Miranda, Morales, Padilla, Páez, Patía, Piamonte, Piendamó, Puerto Tejada, Puracé, Rosas, San Sebastián, Santander de Quilichao, Santa Rosa, Silvia, Sotará, Suárez, Timbío, Timbiquí, Toribío, Totoró, Villa Rica.

#### ZONA: CUNDINAMARCA

Agua de Dios, Albán, Anapoima, Anolaima, Apulo, Arbeláez, Beltrán, Bituima, Bojacá, Cabrera, Cachipay, Cajicá, Caparrapí, Cáqueza, Carmen de Carupa, Chaguaní, Chía, Chipaque, Choachí, Chocontá, Cogua, Cota, Cucunubá, El Colegio, El Peñón, El Rosal, Fomeque, Fosca, Funza, Fúquene, Fusagasugá, Gachalá, Gachancipá, Gachetá, Girardot, Granada, Guachetá, Guaduas, Guasca, Guataquí, Guatavita, Guayabal de Síquima, Guayabetal, Gutiérrez, Jerusalén, Junín, La Calera, La Mesa, La Palma, La Peña, La Vega, Lenguazaque, Machetá, Madrid, Manta, Medina, Mosquera, Nariño, Nemocón, Nilo, Nimaima, Nocaima, Pacho, Paime, Pandi, Paratebueno, Pasca, Puerto Salgar, Pulí, Quebradanegra, Quetame, Quipile, Ricaurte, San Antonio del Tequendama, San Bernardo, San Cayetano, San Francisco, San Juan de Rioseco, Sasaima, Sesquilé, Sibaté, Silvania, Simijaca, Soacha, Sopó, Subachoque, Suesca, Supatá, Susa, Sutatausa, Tabio, Tausa, Tena, Tenjo, Tibacuy, Tibirita, Tocaima, Tocancipá, Topaipí, Ubalá, Une, Útica, Venecia, Vergara, Vianí, Villagómez, Villapinzón, Villeta, Viotá, Yacopí, Zipacón, Zipaquirá.

#### ZONA: SUR VALLE

Cali, Buenaventura, Buga, Candelaria, Dagua, El Cerrito, Florida, Ginebra, Guacarí, Jamundí, La Cumbre, Palmira, Pradera, Vijes, Yotoco, Yumbo.

#### ZONA: CENTRO VALLE

Ansermanuevo, Bolívar, Caicedonia, Calima-Darién, Cartago, El Dovio, La Unión, La Victoria, Obando, Restrepo, Riofrío, Roldanillo, San Pedro, Sevilla, Toro, Trujillo, Ulloa, Versalles, Zarzal.

#### ZONA: NARIÑO

Pasto, Albán, Aldana, Ancuya, Arboleda, Barbacoas, Belén, Berruecos, Buesaco, Chachagüí, Colón, Consacá, Contadero, Córdoba, Cuaspud, Cumbal, Cumbitara, El Charco, El Peñol, El Rosario, El Tablón, El Tambo, Funes, Guachucal, Guaitarilla, Gualmatán, Imués, Ipiales, La Cruz, La Florida, La Llanada, La Tola, La Unión, Leiva, Linares, Los Andes, Magüí, Mallama, Mosquera, Nariño, Olaya Herrera, Ospina, Francisco Pizarro, Policarpa, Potosí, Providencia, Puerres, Pupiales, Ricaurte, Roberto Payán, Samaniego, San Bernardo, San Lorenzo, San Pablo, San Pedro de Cartago, Sandoná, Santa Bárbara, Santacruz, Sapuyes, Taminango, Tangua, Tumaco, Túquerres, Yacuanquer.

#### ZONA: CALL CENTER (Asignación Equitativa)

Corresponde a clientes que **NO** están ubicados en ninguno de los municipios de las zonas anteriores. Se asigna de forma **equitativa** entre los asesores disponibles.
*(Referencia cruzada: ver [Sección 4.3.1 — Respuesta &#34;No, en otra ocasión&#34;](#431-respuesta-no-en-otra-ocasión), donde internamente se redirige a un embudo de asignación equitativa o se crea una tarea de llamarlo).*

---

## 2. Configuración del CRM: Contactos y Campos Personalizados

### 2.1 Campos Personalizados en Contacto

| Campo                      | Tipo/Valores                                               |
| -------------------------- | ---------------------------------------------------------- |
| NOMBRE ESTABLECIMIENTO     | Texto                                                      |
| NOMBRE PERSONA DE CONTACTO | Texto                                                      |
| CIUDAD                     | Texto                                                      |
| ZONA                       | Texto/Select*(se deriva de la ciudad)*                     |
| CATÁLOGO DEL CLIENTE      | Select: Minorista, Mayorista, Cacharrero, Minorista Tuluá |
| CORREO DE CONTACTO         | Email                                                      |
| APLICA OFERTAS             | Select: Sí, No                                            |

### 2.2 Datos Obligatorios para "Cliente Nuevo"

Durante el flujo de registro por IA/WhatsApp se deben capturar:

1. Nombre y apellidos completos
2. Ciudad y departamento
3. RUT o certificado de Cámara de Comercio

### 2.3 Zona y Asignación de Clientes

- Los clientes se asignan a una **zona** según su ciudad.
- La zona determina automáticamente el **asesor responsable**.
- Si no existe coincidencia de ciudad en ninguna zona, se asigna al **Call Center** (reparto equitativo).
- *(Referencia cruzada: ver [Sección 1.1 — Filosofía de Asignación](#11-filosofía-de-asignación) y [Sección 1.2 — Mapeo de Asesores](#12-mapeo-de-asesores-comerciales)).*

---

## 3. Embudo de Ventas

### 3.1 Requerimiento

- Definir **etapas del embudo de ventas**.
- Si aplica, definir etapas también para **Finanzas / Logística / Cartera**.

> **Estado:** Pendiente de definición por parte del cliente. El documento menciona el tema pero no detalla las etapas.

---

## 4. Asistente Virtual Nonoi: Identidad, Tono y Flujos de Conversación

### 4.1 Identidad y Personalidad

| Atributo               | Valor                                                                             |
| ---------------------- | --------------------------------------------------------------------------------- |
| **Nombre**       | Nonoi                                                                             |
| **Rol**          | Asistente virtual oficial de Super Genéricos del Valle S.A.S.                    |
| **Personalidad** | Cercano, confiable, servicial y resolutivo. Representa calidez y profesionalismo. |
| **Objetivo**     | Redirigir al usuario al área que requiere según su necesidad y captar datos.    |

### 4.2 Tono de Voz

| Dimensión            | Especificación                                                                                                      |
| --------------------- | -------------------------------------------------------------------------------------------------------------------- |
| **Registro**    | Informal-profesional (tuteo)                                                                                         |
| **Lenguaje**    | Español neutro, apto para toda Colombia                                                                             |
| **Formato**     | Frases cortas y fáciles de leer                                                                                     |
| **Evitar**      | Regionalismos                                                                                                        |
| **Expresiones** | Amables y proactivas:*"¡Claro que sí!"*, *"Listo, ya quedó registrado"*, *"Déjame revisarlo de inmediato"* |
| **Actitud**     | Empática y positiva (incluso en reclamos); directa; proactiva (ofrece opciones, no solo respuestas)                 |

### 4.3 Flujo de Conversación: Contacto Nuevo (No registrado en CRM)

#### 4.3.1 Mensaje de Bienvenida

> 👋 ¡Hola! Soy **Nonoi**, el asistente virtual de **Super Genéricos del Valle**.
> Veo que aún no estás registrado, así que déjame contarte un poco sobre nosotros:
>
> Somos un **distribuidor farmacéutico** con más de **13 años de trayectoria**, ubicado en **Tuluá, Valle del Cauca**, y con cobertura de **envíos a nivel nacional**.
> Actualmente contamos con la confianza de más de **900 clientes** en todo el país. En nuestro portafolio encontrarás más de **5.000 referencias**, que incluyen: medicamentos, productos naturales, cuidado personal e insumos médicos.
>
> También trabajamos con diferentes canales como **droguerías, tiendas naturistas, cacharrerías y distribuidores**, lo que nos permite ofrecer **precios competitivos** y **ofertas exclusivas cada semana** para tu negocio.
>
> 👉 ¿Quieres registrarte para acceder a nuestro portafolio y precios especiales? 🙌

**Botones:**

- `Sí, quiero registrarme`
- `No, en otra ocasión`

#### 4.3.2 Respuesta: "No, en otra ocasión"

> 👋 Entiendo, no hay problema.
> Cuando quieras registrarte en **Super Genéricos del Valle** estaremos listos para atenderte. 💚
> Mientras tanto, si deseas conocer más sobre nosotros, puedes visitar 👉 [**www.supergenericosdelvalle.com**](http://www.supergenericosdelvalle.com/).
>
> Y si en cualquier momento prefieres hablar con un asesor, solo escribe la palabra **ASESOR** y te conectaré de inmediato.
> ¡Gracias por tu interés en nosotros! 🙌

**Acción interna:** Redirigir a un embudo de asignación equitativa (ya que aún no se conoce la ciudad) O crear una tarea de llamarlo.
*(Referencia cruzada: ver [Sección 1.3 — Zona: CALL CENTER](#zona-call-center-asignación-equitable) para asignación equitativa, y [Sección 5 — Automatización de Tareas](#5-automatización-de-tareas-para-asesores) para creación de tareas).*

#### 4.3.3 Respuesta: "Sí, quiero registrarme"

> 👋 ¡Genial! Para registrarte necesito algunos datos básicos, con los cuales podré asignarte un **asesor personalizado** que te acompañará en todo el proceso.
>
> 1⃣ **Tu nombre y apellidos completos**
> 2⃣ **Ciudad y departamento** donde se encuentra tu negocio

**Cuando el cliente envía estos datos:**

> ✅ ¡Gracias por tu información!
> 📎 Para completar tu registro y ofrecerte los **mejores precios y condiciones comerciales adaptadas a tu negocio**, necesito que me compartas tu **RUT** o tu **certificado de Cámara de Comercio**.
>
> 👉 No te preocupes, tu información será tratada de manera **segura y confidencial**. Solo la utilizamos para validar tu negocio y asignarte un **asesor comercial personalizado** que te acompañará en todo momento.
>
> 🔒 Puedes consultar nuestra **Política de Tratamiento de Datos** aquí: [Política de Tratamiento de Datos – Super Genéricos del Valle](https://supergenericosdelvalle.com/wp-content/uploads/2023/12/POLITICA-DE-TRATAMIENTO-DE-DATOS-2022.pdf)

**Cuando el cliente envía el documento:**

> ✅ ¡Gracias por tu información! La estoy procesando para asignarte el **asesor comercial ideal** que te acompañará en todo el proceso.
> 🤝 Gracias por confiar en **Super Genéricos del Valle**

**Acciones internas tras completar el registro:**

1. Crear el contacto en el CRM
2. Marcarlo como *prospecto nuevo* para seguimiento comercial
3. Asignar zona según ciudad → asignar asesor correspondiente
   *(Referencia cruzada: ver [Sección 1.3 — Mapeo de Zonas](#13-zonas-comerciales-y-municipios) y [Sección 2.3 — Zona y Asignación de Clientes](#23-zona-y-asignación-de-clientes)).*

### 4.4 Flujo de Conversación: Contacto Creado en CRM

> **Estado:** Pendiente de definición. El documento indica que debe existir un mensaje de bienvenida diferenciado para contactos ya creados, pero no proporciona el contenido del mensaje.

**Comportamiento esperado:**

- Al identificar que el contacto ya existe en el CRM, mostrar un mensaje de bienvenida diferente al de contacto nuevo.
- *(Nota: en una versión futura con plugin, se mostraría un menú interactivo con opciones: Cartera, Logística, Ventas — ver [Sección 9 — Fases Futuras](#92-integración-futura-con-erp)).*

### 4.5 Palabra Clave para Transferencia a Humano

- El cliente puede escribir la palabra **`ASESOR`** en cualquier momento para solicitar ser transferido a un asesor humano.
- *(Referencia cruzada: ver [Sección 8.3 — Reglas del Bot por Área](#83-reglas-del-bot-por-área)).*

---

## 5. Automatización de Tareas para Asesores

### 5.1 Objetivo

Implementar en el CRM la **asignación automática de tareas** a los asesores comerciales para garantizar comunicación oportuna con los clientes antes de las entregas. Las tareas consisten en **llamadas o mensajes** a los clientes.

### 5.2 Tareas por Ruta de Entrega (Clientes con Ruta)

| Requisito              | Detalle                                                                                         |
| ---------------------- | ----------------------------------------------------------------------------------------------- |
| **Generación**  | Automática, el día**anterior** a la ruta de entrega                                     |
| **Granularidad** | Cada cliente se lista como una tarea individual                                                 |
| **Deadline**     | Antes de las**4:00 p.m.** del día anterior a la ruta (horario de cierre de facturación) |
| **Acción**      | Asesor contacta al cliente por llamada o mensaje                                                |

**Ejemplo:**

- Asignar tarea a Erika para contactar clientes de Pereira el **martes** antes de las 4:00 p.m., ya que la ruta de entrega para Pereira sale el **miércoles**.
  *(Referencia cruzada: ver [Sección 6.2 — Cronograma: Miércoles](#62-cronograma-semanal) — Pereira aparece en la ruta del miércoles).*

### 5.3 Tareas Recurrentes (Clientes sin Ruta)

| Requisito            | Detalle                                                          |
| -------------------- | ---------------------------------------------------------------- |
| **Target**     | Clientes en municipios no incluidos en el cronograma de entregas |
| **Frecuencia** | Mínimo**dos veces al mes**                                |
| **Objetivo**   | Mantener relacionamiento y estimular pedidos                     |

### 5.4 Modificación Rápida y Masiva de Tareas

Se requiere capacidad para modificar tareas de forma **rápida y masiva** en los siguientes escenarios:

- Semanas con días festivos
- Cambios extraordinarios en las rutas
- Eventos fortuitos que afecten la operación

**Objetivo:** Los cambios se aplican de forma global, sin editar tarea por tarea manualmente.
*(Referencia cruzada: ver [Sección 6.1 — Flexibilidad del Calendario](#61-flexibilidad)).*

---

## 6. Calendario de Rutas de Entrega

### 6.1 Flexibilidad

- Existe un cronograma de entregas previamente establecido.
- Cuando hay **días festivos** o **situaciones imprevistas**, es necesario realizar ajustes en las rutas.
  *(Referencia cruzada: ver [Sección 5.4 — Modificación Masiva de Tareas](#54-modificación-rápida-y-masiva-de-tareas)).*

### 6.2 Cronograma Semanal

| Día                 | Municipios                                                                                                                                                                                                                                                                                                                                                                              |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **LUNES**      | Armenia, Buenavista, Calarcá, Circasia, Córdoba, Filandia, Génova, La Tebaida, Montenegro, Pijao, Quimbaya, Salento, Alcalá, Caicedonia, Sevilla. Ansermanuevo, Bolívar, Cartago, El Dovio, La Unión, La Victoria, Obando, Roldanillo, Toro, Versalles, Zarzal. Dosquebradas, La Virginia, Pereira, Santa Rosa de Cabal. Andalucía, Bugalagrande, Riofrío, San Pedro, Trujillo. |
| **MARTES**     | Cali, Buga, Candelaria, El Cerrito, Ginebra, Guacarí, Palmira, Pradera, Vijes, Yotoco, Yumbo. Andalucía, Bugalagrande, Riofrío, San Pedro, Trujillo.                                                                                                                                                                                                                                 |
| **MIÉRCOLES** | Armenia, Buenavista, Calarcá, Circasia, Córdoba, Filandia, Génova, La Tebaida, Montenegro, Pijao, Quimbaya, Salento, Alcalá, Caicedonia, Sevilla. Ansermanuevo, Bolívar, Cartago, El Dovio, La Unión, La Victoria, Obando, Roldanillo, Toro, Versalles, Zarzal. Dosquebradas, La Virginia, Pereira, Santa Rosa de Cabal. Andalucía, Bugalagrande, Riofrío, San Pedro, Trujillo. |
| **JUEVES**     | Cali, Buga, Candelaria, El Cerrito, Ginebra, Guacarí, Palmira, Pradera, Vijes, Yotoco, Yumbo. Calima-Darién, Restrepo. Andalucía, Bugalagrande, Riofrío, San Pedro, Trujillo.                                                                                                                                                                                                       |
| **VIERNES**    | Armenia, Buenavista, Calarcá, Circasia, Córdoba, Filandia, Génova, La Tebaida, Montenegro, Pijao, Quimbaya, Salento, Alcalá, Caicedonia, Sevilla. Ansermanuevo, Bolívar, Cartago, El Dovio, La Unión, La Victoria, Obando, Roldanillo, Toro, Versalles, Zarzal. Dosquebradas, La Virginia, Pereira, Santa Rosa de Cabal. Andalucía, Bugalagrande, Riofrío, San Pedro, Trujillo. |
| **SÁBADO**    | Cali, Buga, Candelaria, El Cerrito, Ginebra, Guacarí, Palmira, Pradera, Vijes, Yotoco, Yumbo. Andalucía, Bugalagrande, Riofrío, San Pedro, Trujillo.                                                                                                                                                                                                                                 |

*(Referencia cruzada: las tareas de los asesores se generan el día anterior a cada ruta — ver [Sección 5.2](#52-tareas-por-ruta-de-entrega-clientes-con-ruta)).*

---

## 7. Ofertas Semanales — Envío Automatizado

### 7.1 Contexto

- El área comercial genera ofertas semanales en dos formatos:
  - Imágenes para estados de WhatsApp y redes sociales
  - Documento PDF (actualmente enviado de forma manual)

### 7.2 Campo Personalizado "Recibe Ofertas"

| Atributo              | Detalle                                                                     |
| --------------------- | --------------------------------------------------------------------------- |
| **Ubicación**  | Campo personalizado en cada contacto                                        |
| **Definición** | Puede establecerse al crear el contacto o actualizarse manualmente después |
| **Valores**     | `Sí` → incluido en difusión / `No` o vacío → excluido              |
| **Edición**    | Debe poder editarse en cualquier momento                                    |

*(Referencia cruzada: ver [Sección 2.1 — Campos Personalizados](#21-campos-personalizados-en-contacto) donde este campo se define como "APLICA OFERTAS").*

### 7.3 Automatización Semanal

- Cada **lunes**, cuando se actualizan las ofertas, el CRM debe enviar masivamente el **PDF de ofertas** solo a los clientes con el campo "Recibe ofertas" = `Sí`.
- Se debe enviar un **link** a las ofertas semanales en lugar de adjuntar PDF pesado.
  *(Referencia cruzada: ver requisito inicial — "Enviar link a las ofertas semanales (en lugar de adjuntar PDF pesado)").*

---

## 8. Política de WhatsApp, Bot y Matriz de Accesos

### 8.1 Política de Línea de WhatsApp

| Pregunta                                                             | Estado/Decisión                                                                                                                         |
| -------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| ¿Una sola línea para toda la empresa o números por área?         | **POR AHORA SOLO SE DEJA EL CRM**, a la espera del plugin.                                                                         |
| Si es una sola línea, ¿menú de bienvenida con opciones por área? | **No aplica en esta fase** — el CRM se enfoca solo en el área comercial. No se requiere menú de opciones con las demás áreas. |

### 8.2 Enfoque Actual: Solo Área Comercial

- El CRM y el bot se enfocan **únicamente en el área comercial** en esta primera fase.
- El mensaje de bienvenida se divide según si el contacto es **nuevo** o **ya existe en el CRM** (ver [Sección 4.3](#43-flujo-de-conversación-contacto-nuevo-no-registrado-en-crm) y [Sección 4.4](#44-flujo-de-conversación-contacto-creado-en-crm)).

### 8.3 Reglas del Bot por Área

- Definir **cuándo responde el bot** y **cuándo pasa a humano**.
- Evaluar si **desactivar bot con proveedores**, si aplica.
- El cliente puede escribir **`ASESOR`** en cualquier momento para transferencia a humano.
  *(Referencia cruzada: ver [Sección 4.5 — Palabra Clave para Transferencia](#45-palabra-clave-para-transferencia-a-humano)).*

### 8.4 Matriz de Privacidad / Accesos

- Definir **quién ve qué** en el sistema.
- Ejemplo: proveedores solo ven Contabilidad; visibilidad por zona.
- **Estado:** Pendiente a definición del plugin.

---

## 9. Elementos Pendientes, Dependencias y Fases Futuras

### 9.1 Pendientes de Definición por el Cliente

| Ítem                                     | Descripción                                                                              |
| ----------------------------------------- | ----------------------------------------------------------------------------------------- |
| **Embudo de ventas**                | Definir etapas del embudo de ventas y, si aplica, etapas para Finanzas/Logística/Cartera |
| **Mensaje para contacto existente** | Definir el mensaje de bienvenida para contactos ya creados en el CRM                      |
| **Matriz de privacidad/accesos**    | Definir quién ve qué (pendiente a plugin)                                               |
| **Reglas del bot por área**        | Definir cuándo responde el bot, cuándo pasa a humano                                    |
| **Tareas vs. mensajes**             | Elegir si iniciar con tareas, mensajes o ambos                                            |

### 9.2 Integración Futura con ERP

- A futuro se planea integrar el CRM con el **sistema ERP** de la empresa.
- Capacidades previstas post-integración:
  - Realizar cotizaciones
  - Consulta de cartera
  - Estado de pedidos o guías

### 9.3 Fase Futura: Menú Interactivo para Contactos Registrados

Cuando se implemente el plugin, los clientes ya registrados en el CRM verán un menú interactivo con:

- **Cartera** — consultar saldos y facturas
- **Logística** — estado de pedidos o guías
- **Ventas** — realizar pedido o cotización

La solicitud se enviará directamente al área indicada, creando o actualizando el registro correspondiente en el CRM.

### 9.4 IA de Asesoría (Opcional, a Futuro)

- Si a futuro se desea una IA de asesoría (no solo redirección), se debe preparar:
  - FAQ
  - Catálogo de productos
  - Políticas de la empresa

### 9.5 IA Básica — Foco Confirmado (Fase Actual)

- Capturar datos para **clientes nuevos**.
- Aplicar **criterios de asignación** (por zona o reparto equitativo).
- *(Referencia cruzada: ver [Sección 4.3](#43-flujo-de-conversación-contacto-nuevo-no-registrado-en-crm) para el flujo completo y [Sección 1.3 — CALL CENTER](#zona-call-center-asignación-equitable) para reparto equitativo).*

---

## Mapa de Dependencias y Referencias Cruzadas

```
[Zona del cliente] ──────► [Asesor responsable] ──────► [Tareas automáticas]
       │                         │                            │
       ▼                         ▼                            ▼
  [Campo CIUDAD]          [Mapeo §1.2]              [Generación día anterior §5.2]
       │                         │                            │
       ▼                         ▼                            ▼
  [Zona §1.3] ────────────► [Asignación §2.3]         [Deadline 4pm §5.2]


[Contacto NUEVO] ───────► [Flujo registro §4.3] ──────► [Crear contacto CRM]
       │                         │                            │
       ▼                         ▼                            ▼
  [Capturar datos] ──────► [Ciudad → Zona → Asesor] ──► [Prospecto nuevo]


[Contacto EXISTENTE] ───► [Mensaje diferenciado §4.4] ──► [Menú interactivo (futuro §9.3)]


[Ofertas semanales] ────► [Campo "Recibe ofertas" §2.1] ──► [Envío masivo lunes §7.3]


[WhatsApp] ─────────────► [Solo comercial §8.2] ───────► [Bot → ASESOR → Humano §4.5]
```

---

## Resumen de Acciones Requeridas

| #  | Acción                                               | Sección | Estado                |
| -- | ----------------------------------------------------- | -------- | --------------------- |
| 1  | Configurar zonas y mapeo de asesores en CRM           | §1      | ✅ Definido           |
| 2  | Crear campos personalizados en contactos              | §2      | ✅ Definido           |
| 3  | Definir etapas del embudo de ventas                   | §3      | ⏳ Pendiente cliente  |
| 4  | Configurar flujos de Nonoi (contacto nuevo)           | §4.3    | ✅ Definido           |
| 5  | Definir mensaje de bienvenida para contacto existente | §4.4    | ⏳ Pendiente cliente  |
| 6  | Configurar automatización de tareas por ruta         | §5.2    | ✅ Definido           |
| 7  | Configurar tareas recurrentes sin ruta                | §5.3    | ✅ Definido           |
| 8  | Implementar modificación masiva de tareas            | §5.4    | ✅ Definido           |
| 9  | Cargar calendario de rutas semanal                    | §6      | ✅ Definido           |
| 10 | Configurar campo "Recibe ofertas" y envío semanal    | §7      | ✅ Definido           |
| 11 | Definir reglas del bot por área                      | §8.3    | ⏳ Pendiente cliente  |
| 12 | Definir matriz de privacidad/accesos                  | §8.4    | ⏳ Pendiente a plugin |
| 13 | Decidir: iniciar con tareas, mensajes o ambos         | §9.1    | ⏳ Pendiente cliente  |
