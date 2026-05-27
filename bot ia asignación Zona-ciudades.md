# Bot IA — Asignación por Zona y Ciudades

> **Fuente:** Documento Base inicial - Cliente.md
> **Propósito:** Documento técnico del flujo de asignación del bot IA basado en ciudad → zona → asesor

---

## Flujo de Asignación del Bot

```
Cliente proporciona CIUDAD
        │
        ▼
¿La ciudad existe en una zona definida?
        │
    ┌───┴───┐
    │       │
   SÍ      NO
    │       │
    ▼       ▼
 Asignar  CALL CENTER
 ZONA     (reparto equitativo)
    │
    ▼
 Asesor responsable de esa zona
```

---

## Regla de Asignación

- Los clientes se asignan a una **zona** según su ciudad.
- Cada zona tiene un **asesor responsable**.
- Si la ciudad **NO** corresponde a ninguna zona definida → se asigna a **CALL CENTER** (reparto equitativo entre asesores disponibles).
- Los clientes **NO** se ligan directamente a un usuario; se ligan a la zona. Esto permite que, si se cambia un asesor, basta con reasignar la zona completa sin modificar cliente por cliente.

- OJO TENER EN CUENTA QUE LA ZONA CALL CENTER SI NO ESTA ASIGNADA A UN SOLO ASESOR, SINO QUE EN ESA ZONA EN PARTICULAR SI SE DEBE ASIGNAR POR USUARIO 

---

## Tabla Maestra: Ciudad → Zona → Asesor

### ZONA: QUINDÍO → Asesor: GARCIA GRAJALES ERIKA VANESSA

| Ciudad |
|---|
| Armenia |
| Buenavista |
| Calarcá |
| Circasia |
| Córdoba |
| Filandia |
| Génova |
| La Tebaida |
| Montenegro |
| Pijao |
| Quimbaya |
| Salento |
| Alcalá |
| Andalucía |
| Bugalagrande |
Barcelona


### ZONA: RISARALDA → Asesor: GARCIA GRAJALES ERIKA VANESSA

| Ciudad |
|---|
| Apía |
| Balboa |
| Belén de Umbría |
| Dosquebradas |
| Guática |
| La Celia |
| La Virginia |
| Marsella |
| Mistrató |
| Pereira |
| Pueblo Rico |
| Quinchía |
| Santa Rosa de Cabal |
| Santuario |
| Aguadas |
| Anserma |
| Aranzazu |
| Belalcázar |
| Chinchiná |
| Filadelfia |
| La Dorada |
| La Merced |
| Manizales |
| Manzanares |
| Marmato |
| Marquetalia |
| Marulanda |
| Neira |
| Norcasia |
| Pácora |
| Palestina |
| Pensilvania |
| Riosucio |
| Risaralda |
| Salamina |
| Samaná |
| San José |
| Supía |
| Victoria |
| Villamaría |
| Viterbo |
La hermosa

### ZONA: GERENCIA → Asesor: GARCIA GRAJALES ERIKA VANESSA

- Clientes puntuales que no se agrupan por ciudad.
- Asignación de manejo interno.

### ZONA: TULUÁ → Asesor: LLANTEN MONTERO LUZ CENAIDA

| Ciudad |
|---|
| Tuluá |
| La Marina |
| Nariño |

### ZONA: CAUCA → Asesor: LLANTEN MONTERO LUZ CENAIDA

| Ciudad |
|---|
| Popayán |
| Aguablanca |
| Argelia |
| Balboa |
| Bolívar |
| Buenos Aires |
| Cajibío |
| Caldono |
| Caloto |
| Corinto |
| El Tambo |
| Florencia |
| Guachené |
| Guapi |
| Inzá |
| Jambaló |
| La Sierra |
| La Vega |
| López de Micay |
| Mercaderes |
| Miranda |
| Morales |
| Padilla |
| Páez |
| Patía |
| Piamonte |
| Piendamó |
| Puerto Tejada |
| Puracé |
| Rosas |
| San Sebastián |
| Santander de Quilichao |
| Santa Rosa |
| Silvia |
| Sotará |
| Suárez |
| Timbío |
| Timbiquí |
| Toribío |
| Totoró |
| Villa Rica |

### ZONA: CUNDINAMARCA → Asesor: LLANTEN MONTERO LUZ CENAIDA

| Ciudad |
|---|
| Agua de Dios |
| Albán |
| Anapoima |
| Anolaima |
| Apulo |
| Arbeláez |
| Beltrán |
| Bituima |
| Bojacá |
| Cabrera |
| Cachipay |
| Cajicá |
| Caparrapí |
| Cáqueza |
| Carmen de Carupa |
| Chaguaní |
| Chía |
| Chipaque |
| Choachí |
| Chocontá |
| Cogua |
| Cota |
| Cucunubá |
| El Colegio |
| El Peñón |
| El Rosal |
| Fomeque |
| Fosca |
| Funza |
| Fúquene |
| Fusagasugá |
| Gachalá |
| Gachancipá |
| Gachetá |
| Girardot |
| Granada |
| Guachetá |
| Guaduas |
| Guasca |
| Guataquí |
| Guatavita |
| Guayabal de Síquima |
| Guayabetal |
| Gutiérrez |
| Jerusalén |
| Junín |
| La Calera |
| La Mesa |
| La Palma |
| La Peña |
| La Vega |
| Lenguazaque |
| Machetá |
| Madrid |
| Manta |
| Medina |
| Mosquera |
| Nariño |
| Nemocón |
| Nilo |
| Nimaima |
| Nocaima |
| Pacho |
| Paime |
| Pandi |
| Paratebueno |
| Pasca |
| Puerto Salgar |
| Pulí |
| Quebradanegra |
| Quetame |
| Quipile |
| Ricaurte |
| San Antonio del Tequendama |
| San Bernardo |
| San Cayetano |
| San Francisco |
| San Juan de Rioseco |
| Sasaima |
| Sesquilé |
| Sibaté |
| Silvania |
| Simijaca |
| Soacha |
| Sopó |
| Subachoque |
| Suesca |
| Supatá |
| Susa |
| Sutatausa |
| Tabio |
| Tausa |
| Tena |
| Tenjo |
| Tibacuy |
| Tibirita |
| Tocaima |
| Tocancipá |
| Topaipí |
| Ubalá |
| Une |
| Útica |
| Venecia |
| Vergara |
| Vianí |
| Villagómez |
| Villapinzón |
| Villeta |
| Viotá |
| Yacopí |
| Zipacón |
| Zipaquirá |

### ZONA: SUR VALLE → Asesor: HEREDIA HURTADO ANGIE VANESSA

| Ciudad |
|---|
|  |
| Buenaventura |
| Buga |
| Candelaria |
| Dagua |
| El Cerrito |
| Florida |
| Ginebra |
| Guacarí |
| Jamundí |
| La Cumbre |
| Palmira |
| Pradera |
| Vijes |
| Yotoco |
| Yumbo |
Amaime 
El placer 
La magdalena 
Santa Helena
Costa rica 


### ZONA: CENTRO VALLE → Asesor: HEREDIA HURTADO ANGIE VANESSA

| Ciudad |
|---|
Cali
| Ansermanuevo |
| Bolívar |
| Caicedonia |
| Calima-Darién |
| Cartago |
| El Dovio |
| La Unión |
| La Victoria |
| Obando |
| Restrepo |
| Riofrío |
| Roldanillo |
| San Pedro |
| Sevilla |
| Toro |
| Trujillo |
| Ulloa |
| Versalles |
| Zarzal |
La paila
Loboguerrero 
Ceilan 
Venecia 
La primavera 
Salonica 


### ZONA: NARIÑO → Asesor: HEREDIA HURTADO ANGIE VANESSA

| Ciudad |
|---|
| Pasto |
| Albán |
| Aldana |
| Ancuya |
| Arboleda |
| Barbacoas |
| Belén |
| Berruecos |
| Buesaco |
| Chachagüí |
| Colón |
| Consacá |
| Contadero |
| Córdoba |
| Cuaspud |
| Cumbal |
| Cumbitara |
| El Charco |
| El Peñol |
| El Rosario |
| El Tablón |
| El Tambo |
| Funes |
| Guachucal |
| Guaitarilla |
| Gualmatán |
| Imués |
| Ipiales |
| La Cruz |
| La Florida |
| La Llanada |
| La Tola |
| La Unión |
| Leiva |
| Linares |
| Los Andes |
| Magüí |
| Mallama |
| Mosquera |
| Nariño |
| Olaya Herrera |
| Ospina |
| Francisco Pizarro |
| Policarpa |
| Potosí |
| Providencia |
| Puerres |
| Pupiales |
| Ricaurte |
| Roberto Payán |
| Samaniego |
| San Bernardo |
| San Lorenzo |
| San Pablo |
| San Pedro de Cartago |
| Sandoná |
| Santa Bárbara |
| Santacruz |
| Sapuyes |
| Taminango |
| Tangua |
| Tumaco |
| Túquerres |
| Yacuanquer |

### ZONA: CALL CENTER → Reparto Equitativo

| Criterio |
|---|
| Clientes que **NO** están ubicados en ninguno de los municipios de las zonas anteriores |
| Se asigna de forma **equitativa** entre los asesores disponibles |

---

## Resumen de Asesores y Zonas

| Asesor | Email | Zonas |
|---|---|---|
| GARCIA GRAJALES ERIKA VANESSA | callcenter1@supergenericosdelvalle.com | Quindío, Risaralda, Gerencia |
| LLANTEN MONTERO LUZ CENAIDA | callcenter3@supergenericosdelvalle.com | Tuluá, Cauca, Cundinamarca |
| HEREDIA HURTADO ANGIE VANESSA | callcenter2@supergenericosdelvalle.com | Sur Valle, Centro Valle, Nariño |

---

## Lógica del Bot durante Registro

1. El bot solicita **nombre y apellidos completos**.
2. El bot solicita **ciudad y departamento**.
3. El bot busca la ciudad en la tabla de zonas:
   - **Si encuentra coincidencia:** asigna la zona correspondiente → asigna el asesor de esa zona.
   - **Si NO encuentra coincidencia:** asigna a **Call Center** (reparto equitativo).
4. El bot solicita **RUT o certificado de Cámara de Comercio**.
5. Tras recibir documentos, el bot crea el contacto en el CRM y lo marca como *prospecto nuevo*.

SE DEBE CREAR UN EMBUDO PARA ESTOS CLIENTES NUEVOS
---

## Casos Especiales

- **Nariño:** aparece tanto en la zona Tuluá (municipio Nariño) como en la zona NariÑO (departamento con municipio Nariño). El bot debe manejar esta ambigüedad según el contexto (departamento vs municipio).
- **Andalucía, Bugalagrande, Riofrío, San Pedro, Trujillo:** aparecen en múltiples días del calendario de rutas. El bot debe asignar la zona según la ciudad, no según el día de ruta.
- **Dosquebradas, La Virginia, Pereira, Santa Rosa de Cabal:** pertenecen a la zona Risaralda pero aparecen en rutas de lunes, miércoles y viernes.
- **Calima-Darién:** pertenece a Centro Valle pero aparece en ruta del jueves (además de Cali, Buga, etc.).
- **Restrepo:** pertenece a Centro Valle pero aparece en ruta del jueves.
