<!--
{
    "source": "https://docs.joomla.org/localhost",
    "title": "Campo num\u00e9rico",
    "description": "",
    "author": ""
}
-->

## Propósito

El campo numérico proporciona un método para introducir un número real con la opción de adjuntar una moneda u otro símbolo antes o después del número. El control permite utilizarlo como un campo entero con flechas para incrementar y disminuir, con un rango predeterminado de 1 a 100. Sin embargo, se pueden introducir valores reales, positivos o negativos, en el campo. Ejemplo: `99.99` podría formatearse para aparecer como `£99.99` para el usuario final. O `-273.15` podría aparecer como `-273.15C` para el usuario final.

## Creación del campo

### Pestaña General

![Creación de campo numérico](../../../en/images/fields/adding-custom-fields-number-field/01-fields-number-edit.png
)

- **Tipo** Número, que no se puede cambiar después de seleccionarlo.
- **Nombre** El nombre único del campo.
- **Etiqueta** Una etiqueta traducible para el campo.
- **Descripción** Una descripción opcional y traducible del campo.
- **Obligatorio** ¿Establecer en *Sí* si este campo es obligatorio?
- **Usar solo en subformulario** *Sí o *No*.
- **Valor predeterminado** Un valor predeterminado opcional.
- **Mínimo** El valor mínimo que se puede seleccionar mediante las flechas arriba/abajo; el valor predeterminado es 1. Puede ser un número negativo, por lo que debe establecerse en un valor inferior al número mínimo esperado, **de lo contrario, seleccionar la flecha hacia abajo puede borrar el número existente**.
- **Máximo** El valor máximo que se puede seleccionar mediante las flechas arriba/abajo; el valor predeterminado es 100. Establézcalo en un valor superior al número máximo esperado, **de lo contrario, seleccionar la flecha hacia arriba puede borrar el número existente**.- **Incremento del paso** El tamaño del incremento que se añade o resta al valor actual del campo mediante las flechas arriba/abajo. Puede ser un entero; el valor predeterminado es 1, o un decimal como 0.01. **Establézcalo en la cantidad mínima con la que desea incrementar o disminuir el valor**.
- **Formato como moneda** Si se selecciona, hay campos adicionales:
    - **Símbolo de moneda** Puede ser un símbolo único, como `£` o `$`, o una cadena de caracteres, como `&deg;C`, que aparece como *&deg;C*.
    - **Posición del símbolo** Seleccione *Antes* o *Después* del número.
    - **Número de decimales** Normalmente 2 para las monedas, pero podría ser otro valor en otros contextos.

### Pestaña Opciones

#### Panel de opciones del formulario:

- **Marcador de posición** Texto de marcador de posición que aparecerá dentro del campo como una indicación para el usuario sobre la entrada requerida.
- **Clase del campo** Clase opcional añadida al campo del formulario de entrada de datos.
- **Clase de la etiqueta** Clase opcional añadida a la etiqueta del formulario de entrada de datos.
- **Editable en** Interfaces de edición permitidas: *Sitio*, *Administrador* o *Ambos*.
- **Atributo Showon** Mostrar u ocultar condicionalmente el campo según el valor de otros campos.#### Panel de opciones de visualización:
- **Clase de visualización** La clase del contenedor del campo en la salida.
- **Clase del valor** La clase del valor del campo en la salida.
- **Etiqueta** *Mostrar* u *Ocultar* la etiqueta en la salida. Si se establece en Mostrar:
    - **Clase de la etiqueta (salida)** Una clase para la etiqueta de salida.
- **Visualización automática** Si se debe mostrar el campo y dónde:
    - **Después del título**
    - **Antes del contenido mostrado**
    - **Después del contenido mostrado**
    - **No mostrar automáticamente**
- **Prefijo** Texto que aparecerá antes del valor del campo.
- **Sufijo** Texto que aparecerá después del valor del campo.
- **Diseño** Una lista de diseños disponibles.
- **Mostrar cuando es de solo lectura** Opción entre *Heredar*, *Sí* o *No*.

#### Panel de búsqueda inteligente

- **Índice de búsqueda** Opción de buscar o no y método de búsqueda.

### Pestañas de publicación y permisos

El contenido de estas pestañas es evidente y se trata en otra sección.## Entrada de datos

Entrada de datos: simplemente escriba el valor que desee. Este ejemplo muestra el punto de ebullición del argón:

![Entrada de datos del campo numérico](../../../en/images/fields/adding-custom-fields-number-field/02-fields-number-data-entry.png
)

**Advertencia:** si el número que introduce está fuera del rango mínimo y máximo establecido en las opciones de creación del campo, una etiqueta flotante del navegador se lo indicará, pero la información proporcionada no se aplica de forma obligatoria. Puede introducir un número fuera del rango y se aceptará.

## Visualización de datos

La siguiente imagen muestra la visualización de un elemento con un valor negativo:

![Visualización del campo numérico en el sitio](../../../en/images/fields/adding-custom-fields-number-field/03-fields-number-site.png
)

*Traducido por openai.com*