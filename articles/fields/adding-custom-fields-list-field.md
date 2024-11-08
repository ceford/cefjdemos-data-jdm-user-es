<!-- Filename: J3.x:Adding_custom_fields/List_Field / Display title: Campo de lista -->

## Propósito

El tipo de campo de lista proporciona un menú desplegable o una lista de entradas definidas por el usuario. Si el campo tiene un valor guardado, este se selecciona cuando la página se carga por primera vez. Si no, se selecciona el valor predeterminado (si lo hay).

## Creación de Campo

Las opciones especiales dentro de este campo son:

- **Múltiple** Permitir la selección de múltiples valores. Si se configura en *No* se muestra un elemento en la lista. Si se configura en *Sí* se muestran tres elementos. La lista se desplaza para permitir que se seleccione uno o más elementos.
- **Valores de la lista** Agrega elementos según sea necesario y usa el ícono de arrastre para cambiar su orden. Comienza la lista con Texto configurado en *- Seleccionar -* y Valor vacío. Esto proporciona un valor predeterminado vacío, lo que resulta en que esta lista esté ausente en el Artículo.
- **Clase del Campo** Configura en *w-auto* para hacer que la lista sea lo suficientemente ancha para su conjunto de etiquetas.

![Creación de campo de lista](../../../en/images/fields/fields-list-edit.png)

**Nota:** En este ejemplo, la inclusión del tipo de campo en el Título es solo con fines de demostración. Omítelo en los títulos de tus propios campos.

## Entrada de Datos

Simple: solo selecciona un elemento de la lista o más elementos si *Multiple* es *Sí*.

![Entrada de datos en campo de lista](../../../en/images/fields/fields-list-data-entry.png)

## Visualización de Datos

La siguiente captura de pantalla del Sitio muestra el campo visualizado en un artículo. La opción *Visualización automática* es responsable de la posición del campo y tu plantilla es responsable del diseño del campo.

La salida es un solo elemento o una lista separada por comas.

![visualización del campo de la lista del sitio](../../../en/images/fields/fields-list-site.png)

*Traducido por openai.com*

