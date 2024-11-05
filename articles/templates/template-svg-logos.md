<!-- Filename: J4.x:Template_SVG_Logos / Display title: Plantillas de logotipos SVG  -->

## Logo de Cassiopeia

La plantilla predeterminada del sitio de Joomla 4, Cassiopeia, utiliza la palabra CASSIOPEIA como un logo de marca. Aparece en la parte superior de cada página a menos que configures Marca en No en el formulario de Plantillas: Editar estilo, pestaña Avanzado, o uses una palabra como título en lugar de un gráfico. Esa palabra en realidad es un archivo de Gráfico Vectorial Escalado (SVG). Puedes elegir un gráfico alternativo, pero es bastante difícil crear y usar un logo SVG alternativo. Este breve conjunto de instrucciones puede ayudar.

## Inkscape

Inkscape es una aplicación de gráficos vectoriales de código abierto y multiplataforma, lo que significa que puedes descargarla gratis y usarla en Linux, Mac o Windows. Para comenzar, dirígete al sitio web de Inkscape y descarga la versión para tu laptop o computadora de escritorio. Inicia Inkscape y estarás listo para crear un logotipo de marca en SVG. La captura de pantalla a continuación muestra Inkscape a medio camino en la creación de un nuevo logotipo SVG.

![creación de logo en inkscape](../../../en/images/templates/templates-svg-logos-inkscape.png)

## Instrucciones

Para este artículo se necesita un logo que muestre **GREEN CASSIOPEIA** al mismo tamaño que **CASSIOPEIA** en el logo predeterminado, que es de 32 píxeles de alto:

1. Iniciar Inkscape, ajustar la ventana a un tamaño cómodo, seleccionar Ver / Zoom / Zoom al documento
2. Seleccionar la Herramienta de Texto, marcada con la letra A en el Barra de herramientas de la izquierda
3. Seleccionar Arial, Negrita, 40 y px
4. Arrastrar para definir un cuadro que ocupe la mayor parte del ancho de la página
5. Escribir en el Texto: GREEN CASSIOPEIA
6. Seleccionar Ver / Zoom a Selección
7. Seleccionar la herramienta de Selección, marcada con una flecha - en la parte superior de la Barra de herramientas izquierda
8. Bloquear los valores de tamaño Horizontal y Vertical - el símbolo de candado en la barra superior
9. Configurar la unidad de medida a px
10. Cambiar la altura a 32 - verás el logo cambiar al nuevo tamaño
11. Seleccionar Ruta / Objeto a Ruta - no hay cambio visible pero las palabras ya no son texto
12. Seleccionar Archivo / Propiedades del documento
13. Seleccionar Ajustar a Contenido
14. Zoom fuera para una mejor vista
15. Configurar el Relleno a blanco - hacer clic en el cuadro blanco en la paleta de colores inferior
16. Archivo / Guardar en
    local-site-root/images/headers/green-cassiopeia-optimizado.svg
    1. Si guardas en otro lugar tendrás que usar un gestor de archivos o ftp para subir archivos svg. El componente Media puede usar archivos SVG pero actualmente no los subirá.
17. Seleccionar SVG optimizado (.svg) de la lista de tipo de archivo al final de la ventana de Guardar.
18. Guardar, marcar OK para todos los valores predeterminados en el formulario de Salida SVG Optimizado
19. Configurar algunas Opciones de Administrador de Joomla para permitir el uso de archivos SVG
20. Ir a Contenido / Media / Opciones
    1. Agregar a las extensiones permitidas: ,svg
    2. Agregar a las Extensiones de Imágenes Legales (Tipos de Archivo): ,svg
    3. Agregar a los Tipos de MIME Legales: ,image/svg+xml
21. Guardar y Cerrar
22. Ir a Sistema / Plantillas del Sitio / Opciones
    1. Agregar a los Formatos de Imagen Válidos: ,svg
23. Guardar y Cerrar
24. Ir a Sistema / Estilos de Plantillas del Sitio
25. Seleccionar tu plantilla
26. En la pestaña Avanzado, en el campo de Logo usar Seleccionar para encontrar tu nuevo Logo creado
27. Guardar y recargar la página de tu Sitio

![resultado de creación del logo en inkscape](../../../en/images/templates/templates-svg-logos-inkscape-result.png)

