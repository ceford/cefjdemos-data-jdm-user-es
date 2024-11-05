<!-- Filename: J6.x:Media_File_Locations / Display title: Ubicaciones de Archivos Multimedia -->

## Introducción

Por defecto, Joomla almacena tanto las imágenes de usuario como los archivos de documentos en la carpeta */images* de la instalación de Joomla. Cualquier enlace a dichos medios no es procesado directamente por Joomla. El servidor web los envía cuando son solicitados por el navegador.

Si tienes muchos documentos, podrías querer mantenerlos en una carpeta separada, la más obvia sería una carpeta */files* también en la raíz del sitio de Joomla.

Para configurar una ubicación para archivos que sea separada de las imágenes, primero crea una nueva carpeta en la raíz de tu instalación, por ejemplo **files**. Recuerda, formará parte de un enlace URL, así que usa minúsculas y no utilices espacios ni signos de puntuación.

### Plugin del Sistema de Archivos - Local

Encuentra el plugin *Sistema de Archivos - Local* en la lista de plugins y ábrelo. Añade tu recién creada carpeta *files* a la lista de lugares donde puedes mantener medios. Simplemente haz clic en el botón + y selecciona **files** de la lista de carpetas disponibles.

![Plugin del Sistema de Archivos](../../../en/images/plugins/plugin-group-file-system-local.png)

La opción **Crear Miniaturas** configurada en **Sí** provoca la creación de imágenes pequeñas con una altura o anchura máxima de 200 píxeles en media/cache/com_media/thumbs con la misma estructura de carpetas que la carpeta de medios. Debería incrementar en gran medida la velocidad de visualización de una carpeta con muchas imágenes. No es necesario para los archivos ya que son representados por iconos.

Asegúrate de que el plugin esté habilitado. **Guardar y cerrar**.

*Traducido por openai.com*

