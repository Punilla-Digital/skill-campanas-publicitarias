# Meta Pixel y catálogos

## Pixel y eventos
Confirmar negocio, cuenta, dominio, conjunto de datos/Pixel y permisos. Revisar integración existente de tienda/plugin/GTM antes de agregar otra. Guiar desde la pantalla observada del Administrador de eventos, verificando nomenclatura actual.

Definir eventos estándar según acción real (PageView, ViewContent, AddToCart, InitiateCheckout, Purchase, Lead) y verificar su documentación. Un clic de contacto no equivale automáticamente a Lead confirmado. Para Pixel más Conversions API revisar deduplicación usando event_name y event_id correspondientes a la misma acción. No atribuir a CAPI una instalación que solo tiene Pixel. No exponer tokens en capturas ni respuestas.

Probar en herramientas de eventos de prueba y diagnósticos, confirmar IDs correctos, parámetros y disparos sin duplicados. Considerar consentimiento y requisitos vigentes pertinentes al proyecto.

## Catálogos: módulo inicial ampliable
Confirmar finalidad (anuncios de catálogo, tienda u otra), tipo de artículos, mercado, permisos y elegibilidad actual. No asumir que todo servicio es elegible como producto ni prometer tienda aprobada.

Elegir carga manual, feed o integración según origen y cantidad. Revisar especificación actual de campos; validar IDs estables, títulos, descripciones, disponibilidad, precio/moneda, enlaces e imágenes cuando corresponda. Comprobar que content_ids de eventos coincidan con IDs de catálogo. Revisar actualizaciones de feed y errores de importación. Asociar activos correctos cuando corresponda y verificar permisos. Diferenciar catálogo cargado, vinculado y aprobado para su uso.

Reconsultar fuentes oficiales antes de instrucciones:
- https://www.facebook.com/business/help
- https://developers.facebook.com/docs/meta-pixel/
- https://developers.facebook.com/docs/marketing-api/conversions-api/deduplicate-pixel-and-server-events/
- https://www.facebookblueprint.com/student/path/220458-primeros-pasos-con-los-catalogos-en-meta

Ampliar este módulo con pantallas reales y fuentes vigentes cuando el usuario lo solicite.
