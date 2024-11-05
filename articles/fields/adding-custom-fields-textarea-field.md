<!-- Filename: J3.x:Adding_custom_fields/Textarea_Field / Display title: Campo de área de texto -->

## Propósito

El campo de área de texto es un área para la entrada de texto de varias líneas. Un área de texto simple no tiene un editor WYSIWYG.

### Opciones

Las opciones especiales dentro de este campo son:

- **Filas** La altura del área de texto visible en líneas. Si se omite, la altura es determinada por el navegador. El valor no limita la cantidad de líneas que se pueden ingresar. Las filas están activas en el backend al crear un artículo, un contacto o un componente de terceros que admite campos personalizados. Esta opción no tiene impacto en el tamaño del campo en el frontend.
- **Columnas** El ancho del área de texto visible en caracteres. Si se omite, el ancho es determinado por el navegador. El valor no limita la cantidad de caracteres que se puedan ingresar. Las columnas están activas en el backend al crear un artículo, un contacto o un componente de terceros que admite campos personalizados. Esta opción no tiene impacto en el tamaño del campo en el frontend.
- **Longitud Máxima** El número máximo de caracteres que se pueden ingresar.
- **Filtro** Permite al sistema guardar ciertas etiquetas HTML o datos sin procesar.

## Entrada de Datos

Simple: ingresa el texto para mostrar.  

## Visualización de Datos

La siguiente captura de pantalla del Sitio muestra el campo que se muestra en un artículo. La opción *Visualización automática* es responsable de la posición del campo y tu plantilla es responsable del diseño del campo.

Busca el elemento **Clasificación**.

![Visualización de todos los campos](../../../en/images/fields/fields-display.png "Visualización de campos")

La etiqueta del campo comienza un solo bloque de texto a menos que hayas insertado etiquetas HTML como `<p>...</p>`.

