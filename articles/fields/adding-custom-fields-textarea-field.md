<!-- Filename: J3.x:Adding_custom_fields/Textarea_Field / Display title: Campo de Área de Texto -->

## Propósito

El campo de área de texto es un área para la entrada de texto de varias líneas. Un área de texto simple no tiene un editor WYSIWYG.

### Opciones

Las opciones especiales dentro de este campo son:

- **Filas** La altura del área de texto visible en líneas. Si se omite, la altura se determina por el navegador. El valor no limita el número de líneas que se pueden ingresar. Las filas están activas en el backend al crear un artículo, un contacto o un componente de terceros que apoye campos personalizados. Esta opción no tiene impacto en el tamaño del campo en el frontend.
- **Columnas** El ancho del área de texto visible en caracteres. Si se omite, el ancho se determina por el navegador. El valor no limita el número de caracteres que se pueden ingresar. Las columnas están activas en el backend al crear un artículo, un contacto o un componente de terceros que apoye campos personalizados. Esta opción no tiene impacto en el tamaño del campo en el frontend.
- **Longitud máxima** El número máximo de caracteres que se pueden ingresar.
- **Filtro** Permitir al sistema guardar ciertas etiquetas html o datos sin procesar.

![creación de campo de área de texto](../../../en/images/fields/fields-textarea-edit.png)

**Nota:** En este ejemplo, la inclusión del tipo de campo en el título es solo para fines de demostración. Déjalo fuera de tus propios títulos de campo.

## Ingreso de Datos

Simple: ingrese el texto para mostrar.

![campo de área de texto ingreso de datos](../../../en/images/fields/fields-textarea-data-entry.png)

## Visualización de Datos

La siguiente captura de pantalla del sitio muestra el campo que se visualiza en un artículo. La opción *Visualización automática* es responsable de la posición del campo y tu plantilla se encarga del diseño del campo.

![visualización del campo de área de texto del sitio](../../../en/images/fields/fields-textarea-site.png)

La etiqueta del campo inicia un solo bloque de texto a menos que hayas introducido etiquetas HTML como `<p>...</p>`.

