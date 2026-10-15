# Versiones GTM y flujo Meta

## Preferencia del usuario
Al indicar “Enviar/Publicar” en GTM, proporcionar siempre **Título de la versión** y **Descripción de la versión**, separados y listos para copiar. El título resume plataforma + evento + alcance. La descripción indica qué se implementó, cómo y dónde se activa; agregar validaciones únicamente si se hicieron. Respetar nombres existentes. Evitar descripciones vagas como “cambios” o “actualización”.

## Ejemplos recuperados de “Conectar catálogo Meta”
Origen: conversación del usuario del 2 de octubre de 2026, recuperada al actualizar la skill. Son ejemplos históricos; sustituir el cliente al reutilizarlos.

**Título:** Meta Pixel - Base - PageView
**Descripción:** Instalación inicial del Meta Pixel de Punilla Digital mediante GTM. Evento PageView en todas las páginas.

**Título:** Meta Lead - WhatsApp
**Descripción:** Medición de clics en enlaces de WhatsApp como evento Lead de Meta mediante Google Tag Manager.

Mantener la descripción de WhatsApp explícita sobre clics. En ese caso se usó etiqueta “Meta Pixel - Lead - WhatsApp”, activador “Click - WhatsApp” y evento Meta Lead. No describirlo como conversación, formulario enviado ni cliente captado. Para nuevas implementaciones elegir la semántica según objetivo real.

Título recuperado para ViewContent: **Meta Pixel - ViewContent - Servicios**.
Descripción modelo nueva, no cita literal del chat:
**Medición de vistas de fichas de servicios mediante el evento service_view del dataLayer. Envío de ViewContent a Meta con ID, nombre, tipo, valor y moneda del servicio, vinculados a los IDs del catálogo.**
Añadir “Validado en GTM y Meta” solo si hay evidencia de esas pruebas.

Otros títulos sugeridos en el chat: “GA4 - Configuración”, “GA4 - Evento - WhatsApp”, “Google Ads - Conversión - Contacto”. Son nombres administrativos; no implican que esas configuraciones hayan sido realizadas.

## Flujo reutilizable Pixel + catálogo mediante GTM
1. Revisar instalación central de GTM y ausencia de Pixel duplicado. En el caso recuperado, GTM estaba instalado en 57 páginas; no usar esa cifra como requisito.
2. Configurar Pixel base/PageView con el ID de la cuenta actual y activación en todas las páginas conforme al consentimiento configurado. Si usar HTML personalizado, verificar código oficial, disponibilidad de fbq y orden de carga antes de eventos.
3. Mantener catálogo e información web desde una fuente coherente. El caso tenía data/services.json y meta/catalog.csv; no asumir esas rutas en otros proyectos.
4. Emitir service_view solo en fichas individuales. El caso lo implementó en 25 fichas, no en listados ni páginas generales, con content_id, content_name, content_type, value y currency.
5. Crear variables dataLayer para esas claves y activador de evento personalizado service_view. Proponer nombres explícitos: DLV - content_id, DLV - content_name, DLV - content_type, DLV - value, DLV - currency; Evento - service_view.
6. Mapear content_id de la web a content_ids de Meta como lista de IDs; mantener content_name, content_type, value numérico y currency. En el caso se usó product y ARS; verificar especificación y elegibilidad actual antes de reutilizarlo.
7. Comprobar coincidencia exacta de cada ID con el catálogo, sin duplicados y con precio/moneda coherentes. No copiar IDs ni precios de Punilla Digital a otro cliente.
8. Probar varias fichas distintas en GTM Preview para demostrar que los valores cambian dinámicamente; comprobar que no dispara en páginas excluidas.
9. Publicar con título y descripción. Preview prueba la sesión conectada; para navegación ordinaria Meta recibe la versión publicada. Después verificar ViewContent y parámetros en Meta.
10. Configurar contacto WhatsApp por separado, habilitar variables de clic necesarias, inspeccionar URL real y probar clics positivos/negativos.
11. Revisar diagnósticos y eventos automáticos sin confundirlos con las etiquetas propias.

## Catálogo y diagnósticos: límites de lo recuperado
Se recuperó la coincidencia 25/25 entre IDs de fichas y meta/catalog.csv y la recepción dinámica de ViewContent según la respuesta del asistente en aquel chat. No se recuperó el detalle completo de carga/asociación del catálogo ni la solución final de diagnósticos. No presentar esos pasos como históricamente confirmados; guiar con el módulo Meta y capturas actuales.

El usuario pidió limpiar SubscribedButtonClick y corregir un diagnóstico, y cerró esperando resultados. Antes de desactivar eventos, identificar si provienen de detección automática, herramienta de configuración, plugin, código o GTM. No desactivar todo el Pixel ni borrar eventos útiles para resolver un evento automático. Verificar nombres/rutas actuales y comprobar resultados tras el cambio. No afirmar diagnóstico resuelto por haber guardado un ajuste ni imponer un plazo sin documentación.
