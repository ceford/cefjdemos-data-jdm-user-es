<!-- Filename: J4.x:Media:_Uploading_SVG_files / Display title: Cargando archivos SVG  -->

## Introducción

Los archivos SVG (Gráficos Vectoriales Escalables) no son compatibles con Joomla de forma predeterminada. Son necesarios algunos pasos para permitir que el componente de Medios los soporte.

## Opciones de Medios

Desde el menú de Administrador:

* Selecciona **Medios** desde el *Panel de Inicio* o desde el menú de *Contenido*.
* Selecciona el botón **Opciones** desde la *Barra de Herramientas* de Medios.

Hay 3 campos para actualizar, todos son listas separadas por comas, por lo que solo necesitas añadir una coma y el valor correspondiente:

- En *Extensiones Permitidas*, añade al final de la lista ya disponible: `,svg`.
- En *Extensiones de Imagen Legales*, añade al final de la lista ya disponible: `,svg`.
- En *Tipos MIME Legales*, añade al final de la lista ya disponible: `,image/svg+xml`.
- **Guardar y Cerrar**

De ahora en adelante, deberías poder cargar archivos SVG en el Gestor de Medios. A menos que...

## ¿Joomla todavía impide la carga de archivos SVG?

SVG no es un formato de imagen ráster (como los archivos PNG, que contienen píxeles), está escrito en XML (Lenguaje de Marcado Extensible). Es un formato basado en texto, usable directamente dentro del DOM (Modelo de Objeto de Documento), CSS puede cambiar propiedades y JavaScript puede añadir interactividad.

Por lo tanto, los archivos SVG son susceptibles a todos los patrones de ataque relacionados con XML:

- Secuencias de comandos en sitios cruzados, o XSS (a través de su etiqueta `<script>` y eventos).
- Inyecciones HTML (a través del elemento `<foreignObject>` – foreignObject permite incluir elementos de un espacio de nombre XML diferente).
- Denegación de servicio (si se hace mal uso del elemento `<xlink:href>`).

A partir de Joomla 4.1, se utiliza una herramienta de desinfección para verificar el contenido de cualquier archivo SVG cargado a través del Gestor de Medios. Las reglas son estrictas y aseguran que los archivos no puedan dañar el sitio. Por lo tanto, algunos archivos pueden necesitar ser **limpiados** manualmente (recuerde, los archivos SVG son archivos de texto y se pueden editar en un editor de texto) o a través de una herramienta externa antes de que puedan subirse con éxito.

**Consejo:** estos sitios limpiarán archivos svg creados en *Inkscape*:

* [Prueba de Sanitización SVG](https://svg.enshrined.co.uk/)
* [Limpiador y Optimizador SVG](https://iconly.io/tools/svg-cleaner)
* [SVGminify.com](https://www.svgminify.com/)

