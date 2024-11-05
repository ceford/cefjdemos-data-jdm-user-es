<!-- Filename: J4.x:Template_Overrides / Display title: Sobrescritura de Plantillas -->

## Introducción

Las extensiones de Joomla definen su apariencia de salida con archivos de plantilla, que contienen HTML y marcado HTML generado por PHP, y archivos CSS que definen el diseño, esquema de color, fuentes, etc. Eso puede adaptarse perfectamente a tus necesidades, especialmente porque puedes alterar la apariencia con tus propios estilos CSS. A veces quieres mostrar información adicional o quizás menos información. Para eso necesitas crear una sobrescritura de plantilla.

Muchas de las extensiones de Joomla tienen plantillas de salida bastante complejas que son difíciles de leer. Necesitas un buen entendimiento de HTML, PHP y CSS para abordar algunas de ellas. Así que este artículo ilustra el proceso creando una sobrescritura para el formulario de cierre de sesión, que en realidad está en el módulo de inicio de sesión, mod_login. Al propietario del sitio le gustaría que el formulario de cierre de sesión mostrara la hora en la que se producirá el cierre de sesión automático después de un período de inactividad.

## Ejemplo: Sobrescritura de Plantilla para mod_login

Comienza seleccionando **Sistema → Plantillas → Plantillas del Sitio** en el menú del Administrador y luego selecciona el elemento Detalles y Archivos de Cassiopeia. Eso abrirá el formulario de Personalización de Plantillas (Cassiopeia):

![personalización de plantilla cassiopeia pestaña del sitio](../../../en/images/templates/templates-customise-cassiopeia.png)

**Importante:** no edites ninguno de los archivos suministrados como parte de la plantilla Cassiopeia. En la próxima actualización de Joomla, esos archivos pueden ser sobrescritos y tus ediciones se perderán.

La carpeta html es donde se ubican las sobrescrituras. Si expandes la carpeta html, verás que ya existen sobrescrituras para los layouts, mod_custom, mod_menu y tinymce. Expande cada uno para ver qué contienen. No hay mod_login en esta fase.

## Crear Sobrescrituras

Seleccione la pestaña Crear Sobrescrituras para ver la lista de Módulos, Componentes, Plugins y Diseños para los cuales puede crear sobrescrituras:

![plantillas personalizar pestaña de sobrescrituras de cassiopeia](../../../en/images/templates/cassiopeia-customisation-create-overrides.png)

Seleccione el elemento mod_login. Los archivos php de la plantilla mod_login se copiarán en la carpeta html y será redirigido a la pestaña Editor. Expanda las carpetas html y mod_login. Verá default.php y default_logout.php.

No necesita el archivo default.php ya que es una sobrescritura para el formulario de inicio de sesión. Selecciónelo y luego el botón **Eliminar Archivo** en la barra de herramientas. En el cuadro de diálogo de alerta, confirme que desea eliminar el archivo.

Observe lo fácil que es eliminar archivos si cambia de opinión. Y con el botón Administrar Carpetas, puede eliminar carpetas enteras también. Tenga cuidado de no eliminar algo que no haya creado usted mismo.

## Editar default_logout.php

En la pestaña del Editor, selecciona el archivo default_logout.php. Observa los botones en la parte superior derecha: Mostrar archivo original y Mostrar diferencias. Este último se ha configurado en Sí para la siguiente captura de pantalla para mostrar algunas líneas de código añadidas cerca de la parte superior del archivo. Estas líneas de código calculan cuándo expirará la sesión del usuario después de cargar la página que contiene el formulario de cierre de sesión.

![modificar plantillas personalizar pestaña de sobreposiciones de Cassiopeia](../../../en/images/templates/cassiopeia-customisation-edit-logout-override.png)

El área de diferencias muestra las líneas añadidas con un fondo verde y las líneas eliminadas con un fondo rojo. No hay líneas eliminadas en este caso. Aquí se muestra el código en caso de que desees copiarlo para probarlo tú mismo.

```php
    use Joomla\CMS\Factory;

    date_default_timezone_set('Europe/London');
    $config = Factory::getContainer()->get('config');
    $lifetime = $config->get('lifetime', 0);
    $time = time() + $lifetime * 60;
    $endTime = date('H:i:s', $time); // time() devuelve un tiempo en segundos ya
```

Más abajo en el archivo de sobreposición, línea 36, se han añadido algunas líneas más para mostrar el mensaje deseado:

```html
<p class="text-center">
Su sesión expirará a las <br><?php echo $endTime; ?>
</p>
```

Guarda y recarga la página del sitio que contiene el formulario de cierre de sesión.

![modificar plantillas personalizar pestaña de sobreposiciones de Cassiopeia](../../../en/images/templates/cassiopeia-customisation-logout-override-result.png)

Deberías ver que el formulario de cierre de sesión cambia cada vez que la página se vuelve a cargar. Pero, ¿y si cambias de opinión? ¿O tienes opciones diferentes para distintos grupos de Usuarios? Bienvenido a Layouts, el tema de un artículo aparte.

## Otras Sobrescrituras

La pestaña Crear Sobrescrituras del formulario Plantillas: Personalizar (Cassiopeia) se utiliza para crear cualquiera de los elementos de salida de Joomla para los cuales es posible crear sobrescrituras. Los nombres de las carpetas de sobrescritura generalmente comienzan con com\_, mod\_ o plg\_. Tenga en cuenta que la segunda parte de una carpeta de sobrescritura de plugin indica el grupo del plugin. Aquí hay una selección de ejemplo de carpetas de sobrescritura:

![plantillas personalizar pestaña de sobrescrituras de cassiopeia](../../../en/images/templates/templates-customise-example-override-folder.png)

## Anulaciones de Diseño

Los archivos de diseño pequeños a menudo se utilizan para elementos individuales de las páginas de Joomla!. El botón Leer Más de los artículos, la imagen de introducción y la imagen completa son ejemplos de elementos que se generan por sus propios archivos de diseño. Estos micro-diseños se encuentran en la carpeta /layouts. Por ejemplo, en la vista Blog de Categoría, el archivo blog_item.php contiene el código para colocar el título del artículo, una imagen de introducción, el texto de introducción, así como varias otras partes relevantes de la página. Esto se realiza mediante una llamada a LayoutHelper pasando el diseño a utilizar como un parámetro. Este es un ejemplo, la llamada para insertar el Título del Artículo en el diseño del blog:

```php
<?php echo LayoutHelper::render('joomla.content.blog_style_default_item_title', $this->item); ?>
```

La ubicación del archivo para este elemento en particular se encuentra reemplazando los puntos con barras diagonales, anteponiendo /layouts/ y agregando .php:

```php
    JOOMLAROOT/layouts/joomla/content/blog_style_default_item_title.php
```

Cuando se crea un archivo de anulación se encuentra en:

```php
    JOOMLAROOT/templates/cassiopeia/html/layouts/joomla/content/blog_style_default_item_title.php
```

## Información Adicional

- Conceptos Básicos de Plantillas
- Carpetas y Archivos de la Plantilla Cassiopeia
- Personalización de la Plantilla Cassiopeia
- Sobrescrituras de Plantillas
- Diseños de Plantillas
- Plantilla Cassiopeia Simplificada - Un Estudio de Caso - una plantilla simple basada en Cassiopeia

*Traducido por openai.com*

