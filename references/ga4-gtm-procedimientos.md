# Procedimientos GA4 y GTM — ampliación 2026-10-16

Este módulo amplía, sin reemplazar, las referencias de Google Ads, Meta Pixel, conversiones y catálogos.

## Principios
Auditar etiquetas, variables y activadores antes de agregar otros. Confirmar etiqueta base e ID de GA4. En GTM Vista previa/Tag Assistant revisar capa de datos, variables, activadores y etiquetas; execute_succeeded no garantiza recepción. Validar en DebugView/Tiempo real, publicar en GTM y probar fuera de vista previa. Los parámetros para informes requieren dimensiones personalizadas de ámbito Evento; GA4 puede tardar 24–48 h y no recupera automáticamente datos previos a la dimensión. Diferenciar page_view, service_view, whatsapp_click, skill_github_click y conversiones reales.

## Ejemplo exclusivo Punilla Digital
Sitio https://punilladigital.com.ar/; GTM-KQDZM568; GA4 G-0QHL7KP88J. **Nunca reutilizar estos IDs en otros clientes.**

## A. Informe panorámico
GA4 > Informes > Informe panorámico > editar (si hay permisos). Comparar plantillas Rendimiento del marketing, Comportamiento de los usuarios, Ventas e ingresos. Para servicios sin ecommerce priorizar Comportamiento de los usuarios: activos, nuevos, tiempo de interacción, eventos, páginas y fuentes. No priorizar carritos, compras, ingresos ni ARPPU sin ecommerce. Revisar siempre períodos distintos entre Inicio, Informes y Exploraciones.

## B. Visualización de servicios
Prerequisito: el sitio ya emite dataLayer event=service_view con service.content_id, service.content_name y service.content_type (y opcionalmente value/currency). **No duplicar el push**. Ejemplo:
```javascript
window.dataLayer = window.dataLayer || [];
window.dataLayer.push({event:'service_view',service:{content_id:'pd-service-chat-bot-whatsapp',content_name:'Chat Bot WhatsApp con Inteligencia Artificial',content_type:'product',value:1411509,currency:'ARS'}});
```
En GTM Vista previa abrir ficha y revisar service_view. Variables de capa de datos v2: DLV - Service - Content ID → service.content_id; DLV - Service - Content Name → service.content_name; DLV - Service - Content Type → service.content_type. Activador Evento personalizado CE - service_view (nombre service_view). Etiqueta GA4 - Service View, tipo evento GA4, evento service_view, parámetros service_id={{DLV - Service - Content ID}}, service_name={{DLV - Service - Content Name}}, service_type={{DLV - Service - Content Type}}. Asociar activador, probar valores, publicar y confirmar recepción. GA4 > Administrar > Definiciones personalizadas: dimensión Service Name, ámbito Evento, parámetro service_name, descripción «Nombre del servicio consultado por el visitante». value no representa ingresos ni es necesario para ranking.

## C. WhatsApp
Auditar Click - WhatsApp y URLs wa.me, api.whatsapp.com y variantes reales; excluir enlaces ajenos. Habilitar Click URL, Page Path, Click Text. Etiqueta GA4 - Click WhatsApp, evento whatsapp_click: link_url={{Click URL}}, page_path={{Page Path}}, button_text={{Click Text}}; activador Click - WhatsApp. En Tag Assistant pulsar enlace y comprobar gtm.linkClick, URL, ruta, texto y activación; comprobar Meta Pixel Lead por separado si existe. Publicar y confirmar en GA4. Clic no significa mensaje enviado. Para origen usar dimensión integrada Ruta de página y clase de pantalla.

## D. Salidas Skills → GitHub
Activador Clic – Solo enlaces Click - Skills GitHub: Click URL contiene github.com/Punilla-Digital/skill- y Page Path contiene /skils (adaptar a cada sitio). Variable JavaScript personalizado JS - Skill Name:
```javascript
function() {
  var url = {{Click URL}} || '';
  var match = url.match(/github\.com\/Punilla-Digital\/(skill-[^/?#]+)/i);
  return match ? match[1] : undefined;
}
```
Etiqueta GA4 - Click Skills GitHub, evento skill_github_click, parámetros skill_name={{JS - Skill Name}}, link_url={{Click URL}}. Probar que skill_name sea slug, no URL; publicar y confirmar GA4. Crear dimensión personalizada Skill Name, ámbito Evento, parámetro skill_name. Clic saliente no equivale a vistas, clones o descargas GitHub.

## E. Exploraciones de formato libre
GA4 > Explorar > Exploración en blanco > Formato libre. Importar dimensiones y métricas con + en Variables y arrastrar a Configuración. Guardado automático.
- Ranking Skills: Filas Skill Name; Valores Número de eventos; filtro Nombre del evento coincide exactamente skill_github_click; columnas vacías; hasta 50 filas.
- Ranking Servicios: Filas Service Name; Valores Número de eventos; filtro Nombre del evento coincide exactamente service_view; columnas vacías; hasta 50 filas.
- Contactos WhatsApp: Filas Ruta de página y clase de pantalla; Valores Número de eventos; filtro Nombre del evento coincide exactamente whatsapp_click; columnas vacías; hasta 50 filas.

Si aparece «No hay datos», revisar: métrica en Valores, dimensión en Filas, filtro exacto, etiqueta publicada, evento recibido, fecha de creación de dimensión, rango de fechas posterior a configuración y procesamiento GA4. No atribuirlo automáticamente a GTM.

## F. Auditoría y publicación
Capturar etiqueta/activador; probar página de servicio, WhatsApp y GitHub en Tag Assistant; inspeccionar dataLayer, variables, activación y estados; comprobar recepción GA4 por separado; GTM > Enviar > Publicar con título y descripción de versión, sin publicar cambios ajenos; probar fuera de vista previa y registrar fecha. Configurar dimensiones y exploraciones. No marcar service_view automáticamente como evento clave: una vista no es lead; whatsapp_click solo si el criterio comercial lo justifica.

## Entregable
Tabla de etiquetas/activadores creados o reutilizados, nombres exactos de eventos y parámetros, evidencia GTM separada de evidencia GA4, estado de publicación, dimensiones, exploraciones, pendientes y límites de interpretación. Guiar pantalla por pantalla cuando el usuario comparte capturas.
