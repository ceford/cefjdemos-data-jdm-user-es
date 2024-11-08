<!-- Filename: jdocmanual?manual=user&heading=fields&filename=subform.md / Display title: Campo de Subformulario  -->

## Propósito

El Campo de Subformulario permite agrupar una selección de campos en una lista repetible.

## Creación de Campos

Primero crea los campos necesarios en el subformulario. En el ejemplo descrito aquí, hay un campo de Calendario (Fecha de Adquisición), un campo de Texto (Precio) y un campo de Color (Color de la Flor) para ser utilizados en una lista de varios especímenes.

**Error:** Hay un error en el código del campo de Calendario que causa un error fatal al guardar un artículo por segunda vez. Para evitar este problema, establece el valor *Mostrar Hora* del campo de Calendario en *Sí*.

Opciones especiales para este campo:

- **Título** y **Etiqueta** En este ejemplo, estos están establecidos como *Especímenes*.
- **Campos** Añade los campos requeridos en el subformulario uno por uno. Cada fila tiene una lista desplegable de campos disponibles y un conmutador de Mostrar Valores Sí/No. El orden de los elementos puede cambiarse con el icono de arrastre.

![Creación de subformulario](../../../en/images/fields/fields-subform-edit.png)

**Nota:** En este ejemplo, la inclusión del tipo de campo en el Título es solo para efectos de demostración. Déjalo fuera en tus propios títulos de campos.

## Entrada de Datos

En el formulario de entrada de datos, necesitas agregar filas para cada espécimen. Cada fila contiene un campo de Calendario, un campo de Texto y un campo de Color.

![Entrada de datos de subformulario](../../../en/images/fields/fields-subform-data-entry.png)

## Visualización de Datos

En el artículo, el subformulario titulado Especímenes tiene una fila para cada espécimen.
Busca el elemento **Especímenes** en esta captura de pantalla:

![visualización del sitio de subformulario](../../../en/images/fields/fields-subform-site.png)

*Traducido por openai.com*

