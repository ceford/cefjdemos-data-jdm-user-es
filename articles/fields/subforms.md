<!-- Filename: jdocmanual?manual=user&heading=fields&filename=subform.md / Display title: Campo de Subformulario -->

## Propósito

El campo de subformulario permite agrupar una selección de campos en una lista repetible.

## Creación de Campos

Primero, crea los campos necesarios en el subformulario. En el ejemplo descrito aquí, hay un campo de Calendario (Fecha de Adquisición), un campo de Texto (Precio) y un campo de Color (Color de la Flor) para ser usados en una lista de varios especímenes.

**Error:** Hay un error en el código del campo de Calendario que provoca un error fatal al guardar un artículo por segunda vez. Para evitar este problema, ajusta el valor *Mostrar Hora* del campo de Calendario a *Sí*.

Opciones especiales para este campo:

- **Título** y **Etiqueta** En este ejemplo, estos se configuran como *Especímenes*.
- **Campos** Agrega los campos necesarios en el subformulario uno por uno. Cada fila tiene una lista desplegable de campo disponible y un interruptor de alternancia para Renderizar Valores Sí/No. El orden de los elementos se puede cambiar con el ícono de arrastrar.

![Creación de subformulario](../../../en/images/fields/fields-subform.png "Creación de subformulario")

## Entrada de Datos

En el formulario de entrada de datos, necesitas agregar filas para cada espécimen. Cada fila contiene un campo de Calendario, un campo de Texto y un campo de Color.

![Entrada de datos de subformulario](../../../en/images/fields/fields-subform-entry.png "Entrada de datos de subformulario")

## Visualización de Datos

En el artículo, el subformulario titulado Muestras tiene una fila para cada muestra.
Busca el elemento **Muestras** en esta captura de pantalla:

![Visualización de todos los campos](../../../en/images/fields/fields-display.png "Visualización de campos")

*Traducido por openai.com*

