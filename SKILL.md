---
name: configurar-medicion-y-campanas
description: Guiar paso a paso la configuración de Google Tag Manager, GA4, conversiones y campañas de Google Ads, Meta Pixel y catálogos de Facebook e Instagram. Usar ante capturas de pantallas de configuración, consultas sobre qué nombre o título poner, instalación de etiquetas en WordPress/Drupal/HTML, medición de formularios/WhatsApp/compras y creación o revisión de campañas. Adaptar instrucciones a la interfaz observada y verificar cambios actuales.
---

# Medición y Campañas Google y Meta

## Forma de trabajar
Responder en español claro, como compañero que guía al usuario mientras configura. Dar nombres y valores listos para copiar. Avanzar una pantalla o bloque por vez, normalmente con 3–6 pasos, sin adelantar un tutorial completo cuando el usuario está siguiendo capturas. Si pide solo títulos, devolver solo los nombres necesarios con su correspondencia.

Identificar cliente, dominio, plataforma, cuenta/propiedad/contenedor correctos y objetivo comercial. Reutilizar datos explícitos de la sesión; preguntar únicamente por los que afectan el próximo paso. No inventar IDs, presupuestos, selectores, URLs ni valores de conversión. Mantener separación entre clientes.

Leer solo los módulos necesarios:
- [Nombres](references/nombres.md): siempre que se creen objetos.
- [Google](references/google.md): GTM, GA4, conversiones, instalación y pruebas.
- [Campañas](references/campanas.md): planificación y creación de Google Ads.
- [Meta](references/meta.md): Pixel, eventos y catálogos.
- [Versiones GTM y flujo Meta](references/versiones-y-flujo-meta.md): al instalar Pixel, conectar catálogo o publicar versiones; conservar títulos y descripciones listos para copiar.

- [GA4 y GTM: procedimientos avanzados](references/ga4-gtm-procedimientos.md): informe panorámico, service_view, whatsapp_click, skill_github_click, dimensiones, exploraciones y auditoría. Leer al configurar estos flujos; es una ampliación, no sustituye los módulos anteriores.
- [Pantallas y fuentes](references/pantallas.md): navegación, cambios y actualización de la skill.

## Pantallas y evidencia
Priorizar la captura actual del usuario o la interfaz realmente observada. Diferenciar texto visible de ruta orientativa. Antes de indicar rutas no observadas, configuraciones actuales o límites de anuncios, consultar documentación oficial reciente. No simular recordar una pantalla ni afirmar que un botón existe si no hay evidencia. Si falta el campo necesario, pedir captura de esa sección sin datos sensibles.

Al responder una pantalla, incluir según corresponda:
1. Dónde entrar o qué botón pulsar.
2. Tabla Campo | Valor exacto | Motivo breve, sin llenar campos irrelevantes.
3. Qué guardar y cuál será la señal de éxito.
4. Próximo paso o captura requerida para continuar.

Distinguir nombre administrativo, nombre técnico del evento, ID de plataforma y texto público del anuncio. Explicar esa diferencia solo cuando sea útil. No usar un nombre de etiqueta como si fuera el evento enviado.

## Medición antes de campañas
Definir acción real y señal verificable antes del activador. Separar visita, clic, formulario exitoso, conversación y venta. Un clic en WhatsApp no confirma una conversación; un clic en Enviar no confirma que el formulario se envió. Evitar optimizar automáticamente por visitas o clics auxiliares cuando el objetivo son clientes potenciales.

Revisar instalaciones existentes antes de agregar código o plugins. Elegir una fuente responsable de cada evento y evitar duplicados. No trasladar IDs ni decisiones de otros clientes. Mantener los estados: propuesto, configurado, probado, publicado; afirmar cada estado solo con evidencia o atribuirlo al reporte del usuario.

## Cierre y continuidad
Resumir qué quedó hecho, nombres utilizados, prueba realizada y pendientes. No afirmar publicación ni ausencia de duplicados por una captura del editor. Si el usuario dice “instalado y probado”, registrar ese reporte sin agregar pruebas específicas que no mencionó.

Trabajar como guía por defecto. Operar cuentas solo cuando la solicitud lo autorice y existan herramientas adecuadas. No exigir otra confirmación para acciones ya autorizadas; no activar campañas con gasto si el alcance autorizado es únicamente preparar una guía.

Guardar nuevos aprendizajes generales en esta skill cuando el usuario pida actualizarla, siguiendo skill-creator. Las capturas de una ocasión orientan esa sesión pero no actualizan automáticamente la skill. Conservar información particular de clientes fuera del conocimiento general.

## Procedimientos GA4/GTM ampliados (16/10/2026)
Antes de crear etiquetas, auditar las existentes y verificar la etiqueta base, propiedad y contenedor. Diferenciar ejecución en Tag Assistant de recepción en GA4 DebugView/Tiempo real y de publicación efectiva. No equiparar vistas, clics o salidas hacia GitHub con leads, mensajes enviados, ventas o descargas. Para eventos personalizados, definir dimensiones de ámbito Evento y advertir sobre procesamiento de 24–48 horas y ausencia de retroactividad. Seguir [la referencia detallada](references/ga4-gtm-procedimientos.md) para nombres, parámetros, pruebas y exploraciones. Mantener intactos los flujos de Google Ads, Meta Pixel, catálogos y campañas.
