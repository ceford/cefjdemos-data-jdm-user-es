<!-- Filename: J3.x:Adding_custom_fields/List_Field / Display title: Lista de Campo -->

## Propósito

El tipo de campo de lista proporciona un menú desplegable o un cuadro de lista con entradas definidas por el usuario. Si el campo tiene un valor guardado, este se selecciona cuando se carga la página por primera vez. Si no, se selecciona el valor predeterminado (si existe).

## Creación de Campo

Las opciones especiales dentro de este campo son:

- **Múltiple** Permitir seleccionar múltiples valores. Si se configura en *No*, se muestra un solo ítem en la lista. Si se configura en *Sí*, se muestran tres ítems. La lista se desplaza para permitir la selección de uno o más ítems.
- **Valores de la lista** Agregar ítems según sea necesario y usar el ícono de arrastre para cambiar su orden. Comienza la lista con Texto configurado en *- Seleccionar -* y Valor vacío. Esto proporciona un valor predeterminado vacío, lo que resulta en que esta lista esté ausente del Artículo.
- **Clase de Campo** Configurar en *w-auto* para hacer que la lista tenga solo el ancho necesario para sus etiquetas.

![Creación de campo de lista](../../../en/images/fields/fields-list.png "Creación de Campo de Lista")

## Ingreso de Datos

Sencillo: solo selecciona un elemento de la lista o más elementos si *Múltiple* es *Sí*.

## Visualización de Datos

La siguiente captura de pantalla del sitio muestra el campo que se visualiza en un artículo. La opción *Visualización automática* es responsable de la posición del campo y tu plantilla es responsable del diseño del campo.

La salida es un solo elemento o una lista separada por comas.

Busca el elemento **Origen**.

![Visualización de todos los campos](../../../en/images/fields/fields-display.png "Visualización de campos")

*Traducido por openai.com*

