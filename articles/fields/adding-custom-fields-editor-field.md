<!-- Filename: J3.x:Adding_custom_fields/Editor_Field / Display title: Campo del Editor -->

## Propósito

El campo del Editor permite la entrada de datos WYSIWYG para contenido relacionado con algunos artículos, además del contenido principal.

## Creación de Campo

Las opciones especiales dentro de este campo son

- **Botones** Mostrar u Ocultar la lista desplegable de Contenido CMS. Para el texto suplementario del artículo, puede que no sea apropiado mostrar algunos o todos los botones de la lista. El valor predeterminado del complemento es Ocultar.
- **Ocultar Botones** Si *Botones* está configurado en *Sí* o el valor predeterminado del complemento es *Mostrar*, oculta los botones seleccionados en la lista desplegable de Contenido CMS.
- **Ancho y Altura** Los valores incluyen el espacio ocupado por la barra de herramientas del editor, por lo que probablemente sea mejor dejarlos vacíos inicialmente.
- **Ancho** El valor para el ancho define el ancho del editor WYSIWYG en % o píxeles. El valor predeterminado es 100%.
- **Altura** El valor para la altura define la altura (en píxeles) del editor WYSIWYG. El valor predeterminado para esto es 250px. El valor puede representarse como una fracción de la altura de la ventana gráfica, por ejemplo 50vh.
- **Filtro** Permitir que el sistema guarde ciertas etiquetas html o datos sin procesar.

## Entrada de Datos

En el formulario de edición de artículos, el campo de Editor suplementario es similar al campo del Editor principal de contenido.

![campo del editor](../../../en/images/fields/fields-editor-entry.png "Campo del Editor")


## Visualización de Datos

La siguiente captura de pantalla del sitio muestra el campo que se visualiza en un artículo. La opción *Visualización automática* es responsable de la posición del campo, y tu plantilla es responsable del diseño del campo.

En la visualización del artículo, el texto ingresado aparece debajo del encabezado pero como parte de la lista de viñetas para ese elemento de campo.

Busca el elemento **Notas de Cultivo**.

![Visualización de todos los campos](../../../en/images/fields/fields-display.png "Visualización de campos")

