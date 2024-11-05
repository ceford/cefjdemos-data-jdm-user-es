<!-- Filename: J4.x:Article_Headings / Display title: Artículo: Editar - Encabezados   -->

## Semántica de Encabezados

Los encabezados definen una estructura semántica para una página. Pueden ser usados para crear una tabla de contenidos automática y como ayudas de navegación para usuarios con discapacidades. Los niveles de los encabezados van desde h1 hasta h6. Una página sólo debe contener un encabezado h1 que usualmente es el título de la página. Un encabezado h1 no debe ser usado en un artículo. Dentro de un artículo, los encabezados deben estar anidados para crear una estructura en la que cada nivel de encabezado introduce una sección bien definida. Por ejemplo, donde el título de la página es Animales:

```
    ... texto sobre animales en general ...
    <h2>Anfibios</h2>
    ... texto sobre anfibios en general ...
    <h3>Ranas</h3>
    ... texto sobre ranas ...
    <h3>Tritones</h3>
    ... texto sobre tritones ...
    <h2>Reptiles</h2>
    ... texto sobre reptiles en general ...
    <h3>Cocodrilos</h3>
    ... texto sobre cocodrilos ...
    <h3>Tortugas</h3>
    ... texto sobre tortugas ...
```
Los encabezados ayudan a facilitar la lectura. ¡Largas secciones de texto en las páginas web son desalentadoras! Resérvalas para las novelas.

Los encabezados deben ser cortos, cuanto más cortos, mejor. Una sola palabra es suficiente. ¡Las oraciones completas no son adecuadas para los encabezados! Los encabezados no deben terminar con un punto.

Los encabezados semánticos no deben omitir niveles, por ejemplo, incluyendo un h4 en un bloque h2 sólo para lograr una apariencia.

## Insertar un Título de Artículo

Abre el artículo que deseas editar. Observa que el contenedor de texto predeterminado es un párrafo, marcado por una letra `P` en una barra de información debajo del área de texto, en la parte inferior de la ventana de edición. El contenedor predeterminado se puede cambiar en las Opciones del Editor, pero eso se cubre en otra parte. Cuando escribes una nueva línea seguida de algún texto, ese texto se contiene en un párrafo. Para crear un título:

- Posiciona el cursor al inicio de un párrafo existente o en la parte inferior del texto si estás creando una nueva sección.
- Escribe el título seguido de una nueva línea.
- Selecciona la línea que se convertirá en título.
- Desde los botones de formato del editor, donde *Párrafo* se muestra seleccionado:
  - Selecciona **Títulos → Título X** donde X es el valor apropiado para tu jerarquía.
- El párrafo seleccionado se convertirá en un título y aparecerá en texto negrita.
- En la parte inferior de la pantalla, el indicador de contenedor mostrará HX.
- Puedes hacer doble clic en cualquier texto seleccionado para realizar un cambio rápido, por ejemplo, de P a H2 (alternar) o de H2 a H3 usando una barra emergente como en la captura de pantalla a continuación:

![formulario de edición de artículos con h3 seleccionado](../../../en/images/articles/articles-edit-headings.png)

Nota: por convención, todas las etiquetas HTML utilizan letras minúsculas. Si seleccionas el botón *Editor de Alternancia* para ver el código fuente, verás los párrafos y títulos establecidos en etiquetas con letras minúsculas.

## Consejos

- Haz doble clic en cualquier selección de texto para ver un menú emergente con una lista de opciones de formato. Las selecciones de *Encabezado* y *Cita en bloque* se aplican a todo el párrafo. *Negrita*, *Cursiva* y *Subrayado* se aplican a los caracteres seleccionados.
*Traducido por openai.com*

