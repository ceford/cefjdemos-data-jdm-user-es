<!-- Filename: jdocmanual?manual=user&heading=performance&filename=page-analysis.md / Display title: Análisis de Página  -->

## Lighthouse

> Lighthouse es una herramienta automatizada y de código abierto para mejorar la calidad de las páginas web. Puedes ejecutarla en cualquier página web, pública o que requiera autenticación. Realiza auditorías de rendimiento, accesibilidad, aplicaciones web progresivas, SEO y más.

Está disponible como una herramienta adicional para Google Chrome y Firefox y se puede ejecutar desde la línea de comandos. Esto es útil para realizar pruebas en un entorno de desarrollo local.

Más información en el sitio web de Chrome for Developers: Lighthouse.

Puedes utilizar la herramienta en línea desde el sitio de PageSpeed Insights.

La siguiente captura de pantalla muestra la primera parte del informe de PageSpeed Insights:

![Informe de PageSpeed Insights](../../../en/images/performance/performance-pagespeed-insights.png)

## Mejoras de Rendimiento

La segunda parte del informe sugiere métodos para mejorar el rendimiento:

* **Eliminar recursos que bloquean el renderizado** - Ahorro potencial de 540 ms. Francamente, esto es demasiado trabajo para muy poca recompensa.
* **Habilitar la compresión de texto** - Ahorro potencial de 11 KiB. En la Configuración Global, en el panel del Servidor, establece la Compresión de Página GZip en *Sí*. Esto deja archivos pequeños de JavaScript y CSS por minimizar y comprimir.
* **Reducir CSS no utilizado** - Ahorro potencial de 62 KiB. Los culpables son template.min.css y joomla-fontawesome.min.css, pero eso implica adaptar el CSS para cada página del sitio, lo cual es un trabajo muy propenso a errores para muy poca recompensa.
* **Servir activos estáticos con una política de caché eficiente** - Se encontraron 21 recursos. Se proporcionan referencias, incluidas referencias específicas de Joomla.

El mensaje general es que algunas sugerencias valen la pena corregir y otras no.

## Informe de Móvil vs Escritorio

El informe de Escritorio generalmente difiere del informe de Móvil. Algunos problemas adicionales identificados en este caso:

* **Dimensionar correctamente las imágenes** - Ahorro potencial de 48 KiB. La etiqueta de imagen está realmente optimizada con imágenes webp de 768 y 1200 píxeles de ancho. Parece que se necesita algo intermedio.

## Accesibilidad

* **Los enlaces no tienen un nombre discernible** Esto se refiere a las flechas de Izquierda y Derecha en la parte inferior de la página que navegan hacia adelante o hacia atrás. Se dejó fuera el texto para evitar problemas de traducción. ¡Necesitamos reconsiderarlo!
* **Los objetivos táctiles no tienen tamaño o espaciado suficiente** Esto se refiere al tamaño de los elementos del menú en las columnas de la izquierda y derecha. Necesitan más espacio vertical; se requiere un ajuste de CSS.

## Mejores prácticas y SEO

Aunque ambos obtuvieron una puntuación de 100 para Móvil y Escritorio, deben volver a ser revisados después de cada cambio de diseño.

## Resumen

Todos los problemas en este sitio están resueltos, excepto el desmantelamiento de los archivos CSS y la minificación de los archivos Javascript y CSS de pequeños componentes.
*Traducido por openai.com*

