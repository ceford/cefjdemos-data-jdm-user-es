<!--
{
    "source": "https://docs.joomla.org/localhost",
    "title": "Campo de nota",
    "description": "",
    "author": ""
}
-->

## Propósito

El tipo de campo de formulario de nota permite crear títulos, textos, descripciones e incluso cuadros de alerta. También permite poner orden en la configuración de las extensiones, separándola con títulos útiles. O añadir descripciones para determinadas opciones de configuración (sin tener que depender de la información sobre herramientas). O añadir cualquier otro texto que desee.

## Creación del campo

### Pestaña General

![Creación del campo de nota](../../../en/images/fields/adding-custom-fields-note-field/01-fields-note-edit.png
)

- **Tipo** Número, que no se puede cambiar después de la selección.
- **Nombre** El nombre único del campo.
- **Etiqueta** Una etiqueta traducible para el campo.
- **Descripción** Una descripción traducible opcional del campo.
- **Usar solo en el subformulario** *Sí o *No*.
- **Encabezado de la nota** Esto se verá en el formulario de introducción de datos.
- **Contenido de la nota** El texto de la nota.
- **Clase de la nota** Cualquier clase existente o nueva. La clase predeterminada *alert alert-info* produce un cuadro de alerta de Boostrap.
- **Etiqueta de encabezado** Seleccione de la lista de niveles de encabezado.
- **Mostrar botón de cierre** Este campo controla la visualización de una «x» para cerrar la nota. Toma un valor de «true» (para las alertas) o el valor de data-dismiss del icono de cierre de Bootstrap.### Pestaña Opciones
- **Visualización automática** Si se debe mostrar el campo y dónde:
    - **Después del título**
    - **Antes del contenido mostrado**
    - **Después del contenido mostrado**
    - **No mostrar automáticamente**
- **Diseño** una lista de diseños disponibles.
- **Mostrar en la interfaz pública** *Sí* o *No*.

## Introducción de datos

En el formulario de introducción de datos, el campo de nota aparece entre los demás campos como texto con el estilo configurado según las opciones de estilo establecidas en el campo. Puede contener instrucciones o información.

![Introducción de datos del campo numérico](../../../en/images/fields/adding-custom-fields-note-field/02-fields-note-data-entry.png
)

**Consejo:** Utilice el mecanismo de ordenación de campos para ordenar la nota entre los demás campos. Puede tener varios campos de nota diferentes para proporcionar estructura e información a sus campos.

## Visualización de datos

Si *Mostrar en la interfaz pública* está establecido en *Sí*, el campo de nota aparece entre los demás campos en la interfaz pública. Allí puede contener información general común a un grupo de artículos.

![Note field site display](../../../en/images/fields/adding-custom-fields-note-field/03-fields-note-site.png)

*Traducido por openai.com*