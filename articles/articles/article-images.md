<!-- Filename: Adding_an_image_to_an_article / Display title: Artículo: Edición - Imágenes -->

## Introducción

Es importante entender que las imágenes para documentos web se almacenan por separado del texto HTML. Cuando se solicita una página web, el navegador primero recupera el texto y archivos de apoyo separados, como hojas de estilo y scripts de JavaScript. Las imágenes se recuperan más tarde. A menudo, el navegador y el servidor web negocian qué versión de una imagen recuperar para adaptarse al tamaño y la resolución de la pantalla del navegador. Incluso hay una extensión de Joomla disponible que crea varias versiones de una imagen principal en diferentes tamaños y formatos para mejorar la velocidad de entrega y renderizado.

Las imágenes se incrustan en las páginas web mediante la inclusión de enlaces con el formato adecuado. Hay dos mecanismos diferentes para incluir imágenes en artículos:

- La pestaña *Contenido* del formulario de edición permite la inserción de uno o más enlaces de imágenes directamente en el texto del artículo. Ese es el tema de este artículo.
- La pestaña *Imágenes y Enlaces* del formulario de edición permite la inclusión de una imagen como una *Imagen de Introducción* o una *Imagen Completa del Artículo* o ambas. Eso se cubre en un artículo separado sobre [Imágenes y Enlaces](jdocmanual?article=user/articles/article-images-and-links).

Vale la pena hacer una distinción entre imágenes locales e imágenes remotas:

- **Imágenes Locales** están ubicadas en el mismo sitio que la instalación de Joomla, usualmente en la carpeta *imágenes*. Los enlaces de imágenes no necesitan incluir el protocolo y el nombre de dominio, ya que se toman de la configuración del sitio.
- **Imágenes Remotas** están ubicadas en otro lugar de internet. Necesitan incluir el protocolo y el nombre de dominio en el enlace. El uso de imágenes remotas mediante este *hot-linking* puede estar permitido hoy pero no mañana. El uso de imágenes remotas sin permiso se considera mala etiqueta o incluso robo.

## Añadiendo una imagen local

La mejor manera de insertar imágenes locales es utilizando el botón **CMS Content → Media** en la barra de herramientas de edición de TinyMCE. Se abre un diálogo de medios que permite seleccionar cualquier imagen en la carpeta de imágenes del sitio.

**Importante:** Primero coloca el cursor donde deseas que aparezca la imagen. Eso podría ser al principio o al final de un párrafo o en un párrafo vacío.

![El diálogo emergente de medios](../../../en/images/articles/articles-edit-images-media.png)

En el diálogo emergente, navega hasta la imagen que deseas usar y selecciónala. Al seleccionarla, aparecerá un formulario que solicitará datos adicionales.

- **Descripción de Imagen (Texto Alternativo)** Esto es importante para fines de accesibilidad y cumplimiento con los estándares web.
- **Clase de Imagen** Si una imagen se utiliza sin un pie de foto, es posible que se apliquen algunas clases personalizadas aquí. Por ejemplo, *float-end ms-2 mb-1* alineará la imagen a la derecha y hará que el texto flote alrededor de ella con márgenes a la izquierda y debajo para evitar que el texto toque la imagen.
- **Clase de Figura** Si se establece un pie de foto, se puede aplicar una clase de alineación, si la hay, a la Figura. Tenga en cuenta que en Cassiopeia los márgenes se aplican a la figura mediante la hoja de estilo de la plantilla, por lo que *float-start* o *float-end* son suficientes.
- **Pie de Figura** Permite el pie de foto que muestra el contenido de este campo como un pie de foto debajo de la imagen.

**Importante:** Si el campo *Pie de Figura* está vacío, la imagen se insertará dentro de una etiqueta `<img...>` y no se usará el campo *Clase de Figura*. Si el campo *Pie de Figura* contiene texto, la etiqueta `<img...>` se envolverá en etiquetas `<figure>...</figure>`. Las clases más útiles para agregar son *float-start* y *float-end* para colocar la imagen a la izquierda o derecha de la página con el texto fluyendo alrededor de ella.

Selecciona el botón *Insert Media* para insertar la imagen. La pantalla de Insertar Imagen se cerrará y la imagen se mostrará en el editor. O selecciona el botón *Cancelar* para salir de la pantalla de Insertar Imagen.

**Consejo** selecciona el botón Toggle Editor para ver los estilos aplicados de Imagen y Figura. Es posible que necesites cortar y pegar una figura o img para moverla.

### Usando Arrastrar y Soltar para Imágenes Locales

Puedes arrastrar una imagen desde el escritorio o un navegador de archivos directamente al texto del artículo y la imagen se cargará en la carpeta de medios y se ubicará en el artículo. El único inconveniente es que todas las imágenes cargadas de esta manera se colocarán en la misma carpeta de medios.

La ubicación del *Directorio de Imágenes* utilizado para la carga y si esta función está habilitada (activada por defecto) se configuran en las Opciones de configuración de TinyMCE.

## Añadir un enlace de imagen remota

Si la imagen que deseas usar no está en la carpeta de imágenes de tu instalación de Joomla, se necesita un procedimiento ligeramente diferente.

- Selecciona **Insertar → Imagen** en la barra de herramientas de TinyMCE para abrir un cuadro de diálogo.
- En el campo **Fuente**, inserta la URL de la imagen.
- Completa los otros campos según sea necesario.
- La pestaña **Avanzado** ofrece algunas opciones de formato aplicadas como estilos en línea. Experimenta con 1rem, 2, groove.

![El cuadro de diálogo emergente para insertar imagen](../../../en/images/articles/articles-edit-images-external-image.png)

### Usar arrastrar y soltar para insertar enlaces de imágenes remotas

Puedes arrastrar y soltar un enlace de imagen desde un sitio web remoto directamente en el texto de tu artículo. Pero ten en cuenta que esto también puede copiar el contenedor HTML de la imagen con declaraciones de clase no válidas para tu sitio.

## Carga de imágenes usando el cuadro de diálogo de Medios

Puedes cargar nuevas imágenes en tu carpeta de imágenes desde la página *CMS Contenido -> Medios*.

- Abre el cuadro de diálogo de Medios y navega hasta la carpeta donde deseas almacenar nuevas imágenes para el artículo actual.
- Selecciona el botón Subir en la parte superior izquierda de la pantalla de Medios para abrir un navegador de archivos.
- Selecciona los archivos de imagen que deseas cargar. Selecciona Abrir en el navegador de archivos para confirmar la selección. Nota: El estilo y el diseño del navegador de archivos dependen del navegador y del sistema operativo que estés usando.
- El/los archivo(s) seleccionado(s) aparecerán en orden alfabético en la pantalla de Medios/Imagen.
- Cuando se complete la carga, aparecerá una notificación de confirmación en verde en la parte superior de la pantalla.

Ahora puedes seleccionar e insertar la imagen cargada como antes.

