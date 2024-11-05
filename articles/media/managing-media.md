<!-- Filename: J4.x:Managing_Media / Display title: Gestión de Medios -->

## Introducción

En Joomla, los medios son imágenes y archivos que aparecen como ilustraciones o enlaces en artículos, módulos, plantillas, etc. Una característica importante de los medios es que son entregados directamente por el servidor web sin ser procesados por el código de Joomla. Esto es rápido y eficiente. Además, ten en cuenta que los medios generalmente se almacenan en la carpeta **images** de tu sitio web Joomla. No la confundas con la carpeta **media**, que contiene archivos javascript y hojas de estilo.

Los medios de imágenes y archivos se gestionan con el componente de Medios de Joomla. Este permite organizar el contenido multimedia en un árbol de carpetas, cargar elementos individuales, realizar algunas funciones elementales de edición de imágenes y colocar imágenes y enlaces directamente en los artículos.

## Cómo Acceder

Desde la interfaz de administrador de Joomla hay varias formas de abrir el componente de Medios:

- Selecciona **Contenido → Medios** desde el menú del Administrador.
- Selecciona **Panel del sitio → Medios** desde el Panel de inicio.
- Selecciona **Contenido del CMS → Medios** desde una pantalla de edición de artículos.

En los dos primeros casos, el componente de Medios aparece en una pantalla de componente normal. En el último, aparece en un cuadro de diálogo modal.

## Captura de pantalla

La siguiente imagen muestra la página de Medios justo después de la instalación de Joomla, pero con la carpeta cassiopeia/sampledata seleccionada. Se agregó una carpeta *archivos* para almacenar archivos que no son imágenes y se añadió una carpeta extra llamada *basura* para ilustrar la eliminación de carpetas:

![Página de Medios mostrando datos de muestra cassiopeia](../../../en/images/media/media-sample-data-cassiopeia.png)

## Gestión de Carpetas

Los nombres de las subcarpetas en tu árbol de carpetas de imágenes se convierten en parte de la URL de la imagen, por lo que es importante para fines de enlace y optimización para motores de búsqueda que los nombres sigan una convención:

- todo en minúsculas
- sin espacios ni puntuación
- si es necesario, utiliza un guion para crear palabras legibles por humanos, por ejemplo, árboles-de-hoja-caduca en lugar de arboles_de_hoja_caduca.

Antes de crear mucho contenido para tu sitio, puede ser útil pensar con anticipación en cómo podrías categorizar tu contenido y tal vez crear un árbol de carpetas de imágenes que sea similar a tu árbol de categorías. De lo contrario, podrías terminar con un gran número de imágenes y archivos en la raíz de tu árbol de imágenes y eso se volverá difícil de gestionar. Si decides mover imágenes a una mejor estructura más adelante, tendrás que encontrar los enlaces a esas imágenes en tus artículos y cambiarlos. ¡Eso podría ser una tarea que consume mucho tiempo y abrumadora!

### Navegación de Carpetas

Utiliza el árbol de carpetas en la columna **Local** para seleccionar una carpeta. En el caso ilustrado arriba, se seleccionó primero la carpeta cassiopeia. Eso reveló la carpeta *sampledata*, que luego se seleccionó para mostrar su contenido.

La ubicación actual también se indica en las migas de pan (breadcrumbs) sobre las imágenes. En este caso **imágenes → cassiopeia → sampledata**.

Si seleccionas una carpeta diferente, la carpeta anterior al mismo nivel se cerrará.

### Creación de una carpeta

- Selecciona la carpeta principal bajo la cual se debe crear la nueva carpeta.
- Selecciona el botón **Crear Nueva Carpeta**.
- En la ventana emergente *Crear Nueva Carpeta*, ingresa un nombre para la carpeta en el campo **Nombre de Carpeta**.
- Haz clic en el botón **Crear**.
- La nueva carpeta aparecerá en la carpeta principal seleccionada junto con un mensaje de sistema de éxito en verde.

### Borrado de una carpeta

**Advertencia: borrar una carpeta también eliminará todo el contenido de la carpeta!**

- Selecciona la carpeta principal de la carpeta que se va a eliminar utilizando el árbol de directorios mostrado en **Local**. Eso mostrará todas las carpetas y archivos en el principal.
- Mueve el cursor sobre la carpeta que se va a eliminar en el área de medios. Se volverá gris y aparecerá un botón cerca de la parte superior izquierda.
- Selecciona el botón. Aparecerá una marca para indicar que está seleccionada.
- Selecciona el botón **Eliminar** de la barra de herramientas.
- En el diálogo emergente **Confirmar Eliminación**, selecciona el botón **Eliminar**. La carpeta será eliminada junto con todos sus archivos, subcarpetas y sus archivos.

La carpeta seleccionada para eliminación se ilustra a continuación:

![Página de medios mostrando la carpeta de basura](../../../en/images/media/media-sample-data-garbage-select.png)

## Barra de Herramientas del Área de Medios

Esta es la barra encima de la lista de imágenes, archivos y carpetas que contiene botones para una variedad de tareas.

### Caja de selección

Una casilla de verificación que te permite seleccionar todos los elementos en la carpeta mostrada en el área de medios. Puedes querer usarla para eliminar todos los elementos actuales sin borrar la carpeta.

### Ruta de navegación

Usa los nombres de las carpetas sobre el área de medios para retroceder en la jerarquía de carpetas.

Haz doble clic en el nombre de una carpeta en el área de medios para abrir esa carpeta.

### Búsqueda

Si tienes una lista larga de imágenes y archivos, puedes buscar elementos que contengan cualquier grupo de caracteres. La búsqueda es progresiva: a medida que añades caracteres al término de búsqueda, la lista se reduce hasta contener solo aquellos que tienen esa cadena de caracteres.

### Aumentar

Usa los botones de aumentar para agrandar o reducir el tamaño de la miniatura. Dependiendo del tamaño de tu pantalla, puedes ver 2, 4, 6 u 8 imágenes en miniatura una al lado de la otra.

### Vistas de Lista o Miniaturas

En la vista de miniaturas, selecciona el símbolo de lista para cambiar a la vista de lista. En la vista de lista, selecciona el símbolo de miniatura para cambiar a la vista de miniaturas. En la vista de lista verás información sobre el tamaño y las dimensiones de la imagen, entre otros datos.

### Icono de Información

Selecciona el icono de Información para abrir un panel lateral que muestra información sobre lo que esté seleccionado.

*Traducido por openai.com*

