<!-- Filename: J4.x:Media:_Options / Display title: Medios: Opciones -->

## Introducción

La página de *Medios: Opciones* se utiliza para controlar la carga y almacenamiento de medios, tanto imágenes como archivos. **Cuidado:** hay implicaciones de seguridad asociadas con algunos tipos de archivo, que pueden ser una puerta de entrada para un hacker.

Para acceder al formulario de *Medios: Opciones*, selecciona el botón **Opciones** en la barra de herramientas en la página de Medios. Los campos están bien comentados y proporcionan valores predeterminados que deberían ser adecuados para casi todos los sitios. Generalmente, solo necesitas usar el formulario de opciones si deseas mantener los archivos separados de las imágenes o si tienes un formato de archivo inusual no incluido en la lista predeterminada.

## Captura de pantalla

![El formulario de Opciones de medios](../../../en/images/media/media-options.png)

## Ruta a Archivos y Carpetas

Estos son elementos separados en el formulario de configuración, pero ambos apuntan a la carpeta *images* en una nueva instalación de Joomla. Si deseas almacenar medios que no sean imágenes por separado (por ejemplo, PDFs, Hojas de cálculo y Archivos de texto), utiliza los siguientes pasos:

1. Crea una carpeta llamada *files* en la raíz de tu instalación de Joomla.
2. Habilita el plugin *FileSystem - Local* y configúralo, como se describe en el 
   artículo sobre [Ubicaciones de Archivos de Medios](jdocmanual?article=user/media/media-file-locations).
3. Ingresa el nombre de la carpeta, *files*, en el campo *Ruta a la Carpeta de Archivos* en el formulario de Opciones de Medios.

En el formulario de Opciones, ingresa el nombre de la carpeta en el campo **Ruta a la Carpeta de Archivos**. Asegúrate de no usar el nombre de una carpeta central existente de Joomla.

Cuando esté configurado, podrás elegir entre las carpetas de imágenes y archivos en la parte Local de la vista de Medios.

![La página de los medios](../../../en/images/media/media-sample-data-cassiopeia.png)

## Tipos de Imágenes o Documentos Adicionales

Puede que encuentres que una Imagen o Documento no se puede cargar. Si es así, verifica que su extensión esté entre las *Extensiones Permitidas*, que su extensión esté entre los *Tipos de Extensiones Legales* para el medio, y que esté entre los *Tipos MIME Legales* (puede que necesites buscar esto). Los tres deben ser correctos o se rechazará la carga.
*Traducido por openai.com*

