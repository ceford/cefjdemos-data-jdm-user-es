<!-- Filename: J4.x:Favicons / Display title: Favicons  -->

## Los Favicons de Joomla!

Los favicons son los pequeños íconos que aparecen en la pestaña del navegador junto al nombre de tu sitio. Cerca de la parte superior del archivo index.php de la plantilla hay tres instrucciones para cargar favicons en la página:
```php
    // Los navegadores soportan favicons SVG
    $this->addHeadLink(HTMLHelper::_('image', 'joomla-favicon.svg', '', [], true, 1), 'icon', 'rel', ['type' => 'image/svg+xml']);
    $this->addHeadLink(HTMLHelper::_('image', 'favicon.ico', '', [], true, 1), 'alternate icon', 'rel', ['type' => 'image/vnd.microsoft.icon']);
    $this->addHeadLink(HTMLHelper::_('image', 'joomla-favicon-pinned.svg', '', [], true, 1), 'mask-icon', 'rel', ['color' => '#000']);
```
Para la plantilla Cassiopeia, Joomla buscará los favicons en las siguientes ubicaciones:

1.  **media/templates/site/cassiopeia/images** - no están allí, por lo que Joomla buscará en la siguiente ubicación.
2.  **media/system/images** - están allí, así que Joomla los usará desde allí.

Si deseas usar tus propios favicons en lugar de los favicons de Joomla, debes cargarlos en la primera ubicación: **media/templates/site/cassiopeia/images**. Puedes hacerlo utilizando el formulario "Templates: Customise". No se verán afectados por ninguna actualización de la plantilla Cassiopeia.

Los favicons a veces se usan en tamaños más grandes y en lugares distintos a la pestaña del navegador. Por ejemplo, esta es una captura de pantalla de parte de una página de inicio de Firefox que muestra algunas de las ubicaciones favoritas del usuario:

![ejemplos de favicons de la página de inicio de firefox](../../../en/images/templates/favicons-firefox-start-collection.png)

Todos los navegadores modernos soportan íconos SVG, por lo que deberías dar prioridad a la creación de un ícono SVG.

## Sobre SVG

SVG es un acrónimo de Scalable Vector Graphics (Gráficos Vectoriales Escalables). Un archivo SVG contiene texto en un formato que define las ubicaciones y formas de las líneas con colores de línea, colores de relleno, etc. La siguiente captura de pantalla muestra el archivo *joomla-favicon.svg* abierto en un editor de texto. Los números de línea son creados por el editor de texto y no están presentes en el archivo. Las líneas largas representan curvas y aquí están truncadas para fines de visualización.

![contenido de texto del favicon de joomla](../../../en/images/templates/favicons-joomla-favicon-svg-text.png)

Para crear un archivo SVG, necesitas usar una aplicación adecuada, como Inkscape. Aplicaciones de gráficos rasterizados como Photoshop o GIMP no sirven. Si prefieres diseñar un icono en una aplicación de gráficos rasterizados, o si tienes un logotipo gráfico rasterizado existente que se puede adaptar para un icono, puedes importar el archivo PNG resultante en Inkscape y luego trazarlo para producir un archivo SVG. La imagen trazada debe eliminarse después de trazarla.

La creación real de un favicon SVG está fuera del alcance de este artículo. La creación de un archivo estándar *favicon.ico* a partir de un archivo *joomla-favicon.svg* es muy sencilla; muchos sitios lo hacen en línea de forma gratuita.

## Cómo Crear Favicons

Si deseas crear tus propios favicons, la mejor manera de hacerlo es crear un favicon SVG y luego usar una herramienta en línea para generar todos los otros formatos con ese como entrada. En este ejemplo se necesita un ícono que se adapte a una plantilla secundaria llamada Cassiopeia Green. Un ícono debe ser cuadrado y no muy elaborado, ya que el tamaño mínimo de visualización es de 16x16 píxeles. Algunos dispositivos necesitan resoluciones más altas, como 32x32 o 180x180, y Google recomienda múltiplos de 48x48 píxeles. Si comienzas con un SVG, no necesitas preocuparte por ninguno de esos, simplemente crea una imagen casi cuadrada con un diseño adecuado. En este ejemplo, el favicon será las letras *J4* en verde oscuro.

### Inkscape

Inkscape es una aplicación de gráficos vectoriales gratuita, de código abierto y multiplataforma usada para trabajar con archivos SVG. Funciona en Linux, Mac y Windows. Ve al sitio de Inkscape (inkscape.org) para descargar una copia para tu plataforma. Las siguientes ilustraciones muestran la pantalla de Inkscape a mitad de las siguientes instrucciones.

![inkscape con favicon en preparación](../../../en/images/templates/favicons-inkscape-favicon.png)

### Crear un SVG

1.  Inicia Inkscape y ajusta la ventana a un tamaño cómodo: selecciona Ver / Zoom / Zoom de página
2.  Selecciona la Herramienta de Texto, marcada con la letra A en la barra de herramientas izquierda
3.  Selecciona Arial, Normal, 48 y px
4.  Arrastra para definir el cuadro en cualquier lugar de la página
5.  Escribe en Texto: J4
6.  Selecciona Ver / Selección de Zoom
7.  Selecciona Ruta / Objeto a Ruta - no hay cambio visible pero las palabras ya no son texto
8.  Selecciona Archivo / Propiedades del Documento
9.  Selecciona Ajustar al Contenido
10. Haz un zoom para una mejor vista, pero asegúrate de que todas las letras siguen seleccionadas
11. Establece el cuadro de altura al mismo valor que el cuadro de ancho. ¡Escríbelo!
12. Cierra el cuadro de diálogo de Propiedades del Documento
13. Ver / Zoom de Página de nuevo - los caracteres necesitan estar centrados
14. Editar / Seleccionar Todo
15. Objetos / Alinear y Distribuir
16. Mover selección como grupo / Relativo a Página / Centro en el eje horizontal - deberías ver a J4 moverse al punto medio vertical
17. Selecciona el panel de Relleno y Trazado a la derecha - el panel de la derecha tiene una lista desplegable marcada con un cheurón abajo
18. En el panel de Relleno y Trazado, selecciona Relleno y el primer cuadrado lleno
19. En el panel RGB introduce 006400ff en el campo RGBA cerca de la parte inferior derecha - el código para el estilo CSS *verde oscuro*
20. Archivo / Guardar
21. En el cuadro de diálogo de Guardar, introduce un nombre de archivo adecuado, por ejemplo green-favicon-j4.svg
22. Selecciona una ubicación adecuada, por ejemplo *~/Documents/joomla-dev/svgs*
23. Selecciona SVG Optimizado (*.svg*) de la lista desplegable en la parte inferior del formulario.
24. Selecciona *Guardar*
25. Selecciona *OK* para todos los valores predeterminados en el formulario de Salida de SVG Optimizado
26. Cierra el SVG en el que estás trabajando - hay una oportunidad para guardar la imagen en formato Inkscape pero realmente no necesitas hacer eso.

### Editar el SVG con un Editor de Texto

Inicia tu editor de texto favorito para hacer algunos cambios que no fueron posibles en Inkscape.

1.  Abre tu archivo SVG recién creado - nota que la primera línea es una especificación de XML
2.  Puedes eliminar la segunda línea - un comentario que contiene Creado con Inkscape
3.  Si está presente, puedes eliminar la línea que contiene ya que no hay texto
4.  Abre el archivo original joomla-favicon.svg - está en *joomla_root/media/system/images*
5.  Copia el bloque de estilo y pégalo en tu SVG en la línea siguiente a la declaración SVG
6.  Cierra el archivo original *joomla-favicon-svg* para evitar cambios accidentales en él
7.  En el bloque de estilo de tu propio archivo SVG cambia path {fill: \#000;} a path {fill: \#006400;}, el valor en la línea
8.  Elimina *fill="#006400"* de la línea
9.  Guarda
10. Abre la imagen en tu navegador. Para Firefox es Archivo / Abrir Archivo...

Deberías ver la imagen en tu navegador. El ejemplo muestra J4 en 47 píxeles cuadrados. La siguiente etapa es crear el otro tipo de iconos que necesitas usando tu SVG recién creado como maestro.

### Procesamiento en Línea

Visita el sitio de Real Favicon Generator. Hay otros sitios disponibles, pero este parece particularmente completo.

1.  Selecciona el botón etiquetado *Selecciona tu imagen de Favicon*
2.  El sitio te mostrará tu Imagen Maestra. También dice *Tu imagen no es cuadrada (688x512). Podemos solucionar esto agregando márgenes transparentes*
3.  Selecciona el botón *Continuar con esta imagen* debajo de la Imagen Maestra.
4.  Hay subformularios con fondos azul claro para varios tipos de ícono - llena cada uno verificando que la vista previa te convenga.
5.  Es mejor quedarse con las opciones predeterminadas de Opciones del Generador de Favicon a menos que sepas algo mejor. Excepto:
6.  Ruta, selecciona la opción No puedo ... y escribe:
    *media/templates/site/cassiopeia-green/images*
7.  Selecciona el botón *Genera tus Favicons y Código HTML*
8.  Después de un breve retraso, hay un nuevo formulario, selecciona el botón Descargar tu paquete: *Paquete de Favicon*
9.  Guarda la descarga ...
10. Selecciona y copia el bloque de enlaces para guardarlo en algún lado.
11. Cierra el sitio de procesamiento en línea

La descarga es un archivo *zip* que contiene 10 elementos: *favicon.ico*, *safari-pinned-tab.svg*, seis archivos PNG, *browserconfig.xml* y *site.webmanifest*.

### Despliegue

Para usar el conjunto estándar de favicons de Joomla necesitas renombrar y mover los iconos a *joomla_root/media/templates/yourtemplate/images*:

- Tu imagen SVG maestra, *green-favicon-j4.svg*, debe ser renombrada a *joomla-favicon.svg*
- El archivo descargado *safari-pinned-tab.svg* necesita ser renombrado a *joomla-favicon-pinned.svg*
- El archivo descargado *favicon.ico* solo necesita ser movido

### El Bloque de Enlace

El bloque de enlace copiado previamente contiene:

```html
<link rel="apple-touch-icon" sizes="180x180" href="media/templates/site/cassiopeia-green/images/apple-touch-icon.png">
<link rel="icon" type="image/png" sizes="32x32" href="media/templates/site/cassiopeia-green/images/favicon-32x32.png">
<link rel="icon" type="image/png" sizes="16x16" href="media/templates/site/cassiopeia-green/images/favicon-16x16.png">
<link rel="manifest" href="media/templates/site/cassiopeia-green/images/site.webmanifest">
<link rel="mask-icon" href="media/templates/site/cassiopeia-green/images/safari-pinned-tab.svg" color="#5bbad5">
<link rel="shortcut icon" href="media/templates/site/cassiopeia-green/images/favicon.ico">
<meta name="msapplication-TileColor" content="#ffc40d">
<meta name="msapplication-config" content="media/templates/site/cassiopeia-green/images/browserconfig.xml">
<meta name="theme-color" content="#ffffff">
```

¡Probablemente no necesites hacer uso de él!

*Traducido por openai.com*

