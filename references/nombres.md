# Convención de nombres

Respetar una convención existente coherente. En cuentas compartidas incluir cliente; en contenedores exclusivos se puede omitir para simplificar. Usar títulos humanos descriptivos y eventos técnicos en minúsculas sin espacios ni tildes. No renombrar eventos activos sin revisar integraciones e informes.

| Objeto | Patrón | Ejemplo |
|---|---|---|
| Contenedor web | Cliente - Web - Dominio | Alquilo Seguro - Web - [dominio confirmado] |
| Etiqueta Google base | Google - Etiqueta base - Cliente | Google - Etiqueta base - Alquilo Seguro |
| Evento GA4 | GA4 - Evento - Acción | GA4 - Evento - Clic WhatsApp |
| Conversión Ads | Ads - Conversión - Acción | Ads - Conversión - Formulario enviado |
| Activador clic | Clic - Destino - Condición | Clic - WhatsApp - Enlaces |
| Activador evento | Evento - Señal | Evento - lead_success |
| Activador página | Página - Ruta | Página - Gracias - [ruta confirmada] |
| Variable constante | CONST - Dato | CONST - ID de medición GA4 |
| Variable dataLayer | DLV - Clave | DLV - form_id |
| Evento técnico de contacto | click_whatsapp | click_whatsapp |
| Evento técnico de lead validado | generate_lead | generate_lead |
| Acción conversión visible Ads | Cliente - Acción | Alquilo Seguro - Formulario enviado |
| Campaña | Cliente - Red - Servicio - Zona - Objetivo | Compara Seguros - Búsqueda - Auto - Córdoba - Leads |
| Grupo de anuncios | Servicio - Intención | Auto - Cotizar |
| Pixel/conjunto de datos | Cliente - Web | Alquilo Seguro - Web |
| Etiqueta Meta | Meta - Evento - Acción | Meta - Evento - Lead |
| Catálogo | Cliente - Tipo - Mercado | Cliente - Productos - Argentina |
| Versión GTM | Acción - Alcance | Medición - WhatsApp y formularios |

Usar generate_lead solo cuando exista señal de lead exitoso; para compras respetar purchase y su esquema. Mantener eventos estándar Meta con su capitalización oficial; no traducir Lead a un identificador inventado. Resolver IDs de plataformas desde la cuenta, nunca desde nombres administrativos.

Para “¿qué título pongo?” entregar por ejemplo:
- Etiqueta: **GA4 - Evento - Clic WhatsApp**
- Activador: **Clic - WhatsApp - Enlaces**
- Evento GA4: `click_whatsapp`
No repetir configuraciones que el usuario no pidió.

Al publicar GTM, entregar también la descripción exacta de la versión siguiendo [versiones-y-flujo-meta.md](versiones-y-flujo-meta.md).
