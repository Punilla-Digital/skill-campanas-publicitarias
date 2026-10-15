# GTM, GA4 y conversiones

## Instalación
Inventariar scripts, plugins, contenedores y propiedades existentes. En WordPress elegir integración comprobada compatible con la instalación; Site Kit puede ser una opción, no imponerlo ni suponer servicios conectados. Si GTM administra GA4, revisar que el plugin no inserte adicionalmente la misma medición. En Drupal/HTML preferir integración central del tema o generador y verificar páginas representativas. No confundir GTM- (contenedor), G- (medición GA4) y AW- (Ads).

## Eventos
1. Definir señal real: enlace WhatsApp, formulario confirmado, compra confirmada.
2. Elegir tipo de etiqueta actual y activador adecuado; usar etiqueta de Google como base y eventos GA4 según documentación vigente.
3. Para WhatsApp inspeccionar enlaces reales antes de proponer condiciones; contemplar wa.me y api.whatsapp.com solo si están presentes. Excluir otros dominios. Habilitar variables necesarias.
4. Para formularios AJAX preferir evento de éxito real en dataLayer o callback fiable. No recomendar activador genérico de envío sin comprobar que detecta éxito. Si usar página de gracias, revisar acceso directo y recargas.
5. Enviar parámetros útiles sin nombres, correos, teléfonos, DNI, CUIL ni texto libre sensible a GA4.
6. Si hay comercio electrónico, revisar esquema, moneda, valor e ID de transacción y evitar repetir compras.

## Google Ads
Elegir medición directa Ads o importación desde GA4 para la acción objetivo; no poner ambas como principales para el mismo resultado sin diseño explícito. Distinguir evento, evento clave GA4 y acción conversión Ads. Revisar vinculación, objetivos de cuenta/campaña, principal/secundaria, método de recuento, valor, ventana y atribución según caso y opciones actuales. No imponer valores ficticios ni marcar toda interacción como principal. Evaluar Conversion Linker y requisitos de etiqueta Google según implementación vigente.

## Verificación
En GTM Preview/Tag Assistant verificar evento, variables, disparo esperado y no disparo en controles negativos. En GA4 DebugView comprobar nombre y parámetros. Probar éxito, fallo del formulario, clic irrelevante y repeticiones pertinentes. Comprobar consentimiento según configuración real. Publicar una versión descriptiva cuando autorizado y probar sitio publicado. Separar recepción técnica de evento del diagnóstico/atribución Ads, que puede tardar. No prometer resultados inmediatos.

Fuentes de partida (reconsultar al usar):
- https://support.google.com/tagmanager/answer/9442095
- https://support.google.com/tagmanager/answer/13034206
- https://developers.google.com/tag-platform/devguides/conversions
- https://support.google.com/google-ads/answer/7548399
