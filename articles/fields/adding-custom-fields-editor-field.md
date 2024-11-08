<!-- Filename: J3.x:Adding_custom_fields/Editor_Field / Display title: Campo del Editor -->

## Propósito

El campo del editor permite la entrada de datos WYSIWYG para algunos contenidos relacionados con el artículo además del contenido principal.


## Creación de Campos

Las opciones especiales dentro de este campo son

- **Botones** Mostrar u ocultar la lista desplegable del contenido del CMS. Para el texto complementario de artículos, puede no ser apropiado mostrar algunos o todos los botones de la lista. El valor predeterminado del plugin es Ocultar.
- **Ocultar Botones** Si *Botones* está configurado en *Sí* o el valor predeterminado del plugin es *Mostrar*, ocultar los botones seleccionados en la lista desplegable de contenido del CMS.
- **Ancho y Altura** los valores incluyen el espacio ocupado por la barra de herramientas del editor, por lo que probablemente sea mejor dejarlos vacíos inicialmente.
- **Ancho** El valor para el ancho define el ancho del editor WYSIWYG en % o píxeles. El valor predeterminado es 100%.
- **Altura** El valor para la altura define la altura (en píxeles) del editor WYSIWYG. El valor predeterminado para esto es 250px. El valor puede representarse como una fracción de la altura de la ventana gráfica, por ejemplo, 50vh.
- **Filtro** Permitir que el sistema guarde ciertas etiquetas html o datos sin procesar.

![Creación de campo de editor](../../../en/images/fields/fields-editor-edit.png)

**Nota:** En este ejemplo, la inclusión del tipo de campo en el Título es solo para fines de demostración. Omite esta parte en los títulos de tus propios campos.


## Entrada de Datos

En el formulario de edición del artículo, el campo adicional del Editor es similar al campo del Editor del contenido principal.

![entrada de datos del campo del editor](../../../en/images/fields/fields-editor-data-entry.png)

## Visualización de Datos

La siguiente captura de pantalla del sitio muestra el campo exhibido en un artículo. La opción *Visualización automática* es responsable de la posición del campo y tu plantilla es responsable del diseño del campo.

En la visualización del artículo, el texto ingresado aparece debajo del encabezado, pero forma parte de la lista con viñetas para ese elemento de campo.

Busca el elemento **Notas de Cultivo**.

![visualización del campo del editor del sitio](../../../en/images/fields/fields-editor-site.png)

*Traducido por openai.com*

