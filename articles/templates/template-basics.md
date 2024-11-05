<!-- Filename: J4.x:Template_Basics / Display title: Conceptos Básicos de Plantillas -->

## Introducción

En Joomla!, una plantilla es una colección de archivos que juntos definen la apariencia del sitio web. Joomla 4 proporciona dos plantillas: Atum es la plantilla de Administrador utilizada para la gestión del sitio; y Cassiopeia es la plantilla del Sitio utilizada para los visitantes del sitio. Hay muchas más plantillas de sitio disponibles de proveedores independientes, ya sea de forma gratuita o por un cargo modesto. De hecho, hay toda una industria basada en la provisión de plantillas de sitio especializadas.

Una plantilla típica del sitio contiene archivos PHP para organizar el contenido y archivos CSS para estilizar el contenido. A menudo hay archivos adicionales como imágenes utilizadas en el diseño y archivos JavaScript utilizados para interactuar con características del sitio, como enlaces y botones. La siguiente captura de pantalla muestra las carpetas y archivos de la plantilla Cassiopeia en una nueva instalación de Joomla 4:

![personalizar la página de Cassiopeia de las plantillas](../../../en/images/templates/templates-customise-cassiopeia.png)

Observe que los archivos php están en la carpeta del sitio /templates y los archivos multimedia están en la carpeta del sitio /media.

## Posiciones de la Plantilla

La plantilla del sitio define las posiciones del contenido principal, por ejemplo, un artículo individual o un diseño de blog con artículos destacados, y cualquier módulo para ser mostrado arriba, abajo, a la izquierda o a la derecha del contenido principal. La siguiente ilustración muestra las posiciones disponibles en Cassiopeia:

![diagrama de posiciones de plantilla](../../../en/images/templates/cassiopeia-template-positions.png)

Además, puedes ver las posiciones de la plantilla en cualquier plantilla activando la opción "Vista Previa de Posiciones de Módulo" en el formulario de Opciones de la Plantilla y luego añadiendo ?tp=1 a la URL. Si ya hay una cadena de consulta añadida a la URL, entonces añade &tp=1 en su lugar.

## Estilo de Usuario

Cassiopeia tiene algunas opciones que puedes cambiar para modificar la apariencia del sitio (hay un artículo separado sobre la Personalización de Cassiopeia). Eso puede no ser suficiente para tus propósitos. Puedes hacer tus propios cambios de apariencia con una hoja de estilo user.css. Tienes que crear esto tú mismo en el formulario Plantillas:Personalizar. Solo selecciona Nuevo Archivo e ingresa Nombre de Archivo: user, selecciona Tipo de Archivo: .css, y selecciona css de la lista de carpetas. Luego selecciona el archivo user.css recién creado en el formulario Editar e ingresa algunos estilos, por ejemplo, para hacer que los encabezados sean verde oscuro:
```css
    h1, h2, h3, h4, h5, h6 {
      color: darkgreen;
    }
```

## Sobrescrituras de Plantillas

Además del diseño general definido por la plantilla del sitio, cada componente o módulo tiene una plantilla para definir su apariencia dentro del diseño general. Dichas plantillas se encuentran en una carpeta tmpl dentro del componente o módulo. Algunos plugins también tienen plantillas. Y hay diseños que se pueden llamar desde cualquier tipo de extensión.

A veces una de estas plantillas de *extensión* no es completamente de tu agrado. En tal caso, puedes crear una sobrescritura de plantilla. Esto es una copia del código utilizado para generar el diseño de la extensión que puedes modificar según tus propios propósitos. La siguiente captura de pantalla muestra el formulario de Sobrescrituras Personalizadas de Plantilla:

![sobrescrituras de plantilla](../../../en/images/templates/cassiopeia-customisation-create-overrides.png)

Cassiopeia ya tiene algunas sobrescrituras instaladas. Eso puede parecer un problema. Si cambias alguno de los archivos predeterminados de Cassiopeia, tus cambios serán sobrescritos (y por lo tanto perdidos) en la próxima actualización de Joomla. La solución son las plantillas hijas.

## Diseños Alternativos

Una plantilla, o una sobrescritura de plantilla, define la apariencia de una extensión en un archivo específico, como default.php. En algunos casos, es posible que desees elegir entre el diseño predeterminado y un diseño alternativo. Por ejemplo, un menú en una posición superior generalmente necesita un diseño diferente al mismo menú en una posición lateral. En un módulo de menú, hay un parámetro de Diseño en la pestaña Avanzado del formulario de edición del módulo que te permite seleccionar entre los diseños alternativos disponibles. Hay un tutorial separado sobre Diseños Alternativos de Plantilla.

## Plantillas Hijas

Una plantilla hija utiliza los archivos de su plantilla madre, excepto aquellos archivos que están en la plantilla hija. Por ejemplo, podrías tener diferentes archivos user.css en la madre y en la hija para que diferentes páginas puedan tener diferentes esquemas de color. O podrías copiar el archivo index.php de la madre a la hija y cambiar el hijo para producir un diseño diferente al de la madre. Hay un tutorial separado sobre plantillas hijas.

