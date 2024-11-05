<!-- Filename: J4.x:Article_Tables / Display title: Artículo: Editar - Tablas  -->

## Acerca de las Tablas

En HTML, las tablas consisten en filas y columnas de celdas. Por ejemplo, una tabla simple puede consistir de 4 filas y 4 columnas, dando un total de 16 celdas. Sin embargo, las celdas pueden combinarse horizontal o verticalmente para crear estructuras de tabla bastante intrincadas. Las tablas también tienen características no tan obvias como encabezado, cuerpo, pie de página y subtítulos. ¡Las tablas pueden anidarse!

Por defecto, las celdas de las tablas se expanden para acomodar su contenido. El único estilo proviene del marcado de la tabla: por defecto, las celdas de encabezado (`<th>`) tienen texto en negrita y centrado, mientras que las celdas de datos (`<td>`) tienen texto normal y alineado a la izquierda.

El uso de tablas debe reservarse para datos estrictamente tabulares, como un horario o un calendario, donde es importante mantener la estructura de filas y columnas. Las tablas no deben usarse para diseño, como la colocación de imágenes o texto uno al lado del otro.

Hay más información en los siguientes artículos:

- [Conceptos Básicos de Tablas](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics)
- [Características Avanzadas y Accesibilidad](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Advanced)
- [Estilización de Tablas](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Styling_tables)

¡Las tablas son un dilema! Si insertas una tabla usando las herramientas de tablas de TinyMCE, la tabla se verá bien en la pantalla de edición y en el sitio, pero el diseño se logra con estilos CSS en línea que pueden ser voluminosos y difíciles de editar. Si la tabla se inserta como HTML puro, el resultado no se ve bien en el editor de texto TinyMCE, pero puede aprovechar las clases de Bootstrap y verse mucho mejor en el sitio. Ambos métodos se cubren a continuación.

## Insertar una Tabla con Herramientas de TinyMCE

Para comenzar con una tabla:

- Abre el artículo que deseas editar.
- Coloca el cursor en una línea en blanco donde deseas que aparezca la tabla.
- Selecciona el botón *Tabla* en la primera fila de herramientas de TinyMCE.
- En el menú desplegable, selecciona Tabla y luego mueve el cursor para definir el 
  número de filas y columnas. Las flechas del teclado también funcionan para esto.
- Selecciona la última celda en la matriz de 4x4.
- Llena las celdas de la tabla.

Opciones de edición:

- Puedes insertar una fila por encima o por debajo de una celda seleccionada.
- Puedes insertar una columna antes o después de una celda seleccionada.
- Puedes eliminar una fila o columna.
- Puedes arrastrar los bordes de columna para cambiar los anchos o alturas de las columnas.
- Puedes fusionar celdas: arrastra sobre las celdas para seleccionarlas y luego
  usa Tabla -> Celda -> Fusionar celdas.
- Puedes seleccionar Propiedades de Tabla, incluyendo ancho del borde, estilo y color, y
  color de fondo.

Si utilizas el botón de Alternar Editor, verás que el diseño se logra con
declaraciones de estilo en línea en cada fila y cada celda. Aquí tienes un breve ejemplo:

```html
<table style="border-collapse: collapse; width: 100%; height: 96px;" border="1"><colgroup><col style="width: 24.9735%;"><col style="width: 24.9735%;"><col style="width: 24.9735%;"><col style="width: 24.9735%;"></colgroup>
<tbody>
<tr style="height: 24px;">
<td style="height: 24px;">Día</td>
<td style="height: 24px;">Mañana</td>
<td style="height: 24px;">Tarde</td>
<td style="height: 24px;">Noche</td>
</tr>
<tr style="height: 24px;">
<td style="height: 24px;">Martes</td>
<td style="height: 24px;">Bienvenida</td>
<td style="height: 24px;">Presentaciones</td>
<td style="height: 24px;">BBQ</td>
</tr>
...
</tbody>
</table>
```

## Insertar una Tabla como HTML

Si lo prefieres, puedes prescindir de los estilos en línea y usar clases de Bootstrap. Tendrías que modificar la tabla creada por las herramientas de tabla de TinyMCE o escribirla tú mismo. Se vería así:

```html
<div class="table-responsive">
<table class="table table-striped table-bordered table-group-divider">
<thead>
<tr>
<th>Día</th>
<th>Mañana</th>
<th>Tarde</th>
<th>Noche</th>
</tr>
</thead>
<tbody class="table-group-divider">
<tr>
<th>Martes</th>
<td>Bienvenida</td>
<td>Presentaciones</td>
<td>Parrillada</td>
</tr>
...
</tbody>
</table>
</div>
```

Aquí, las clases de Bootstrap tienen los siguientes efectos:

- `table` - aplica varios estilos para dar un buen diseño estándar de tabla.
- `table-striped` - las filas alternas son oscuras y claras.
- `table-bordered` - aplica bordes a las celdas.
- `table-group-divider` - aplica una línea gruesa sobre un elemento.
- `table-responsive` - permite que una tabla ancha se desplace de derecha a izquierda.

La siguiente captura de pantalla del sitio muestra una tabla para un programa de conferencias con los estilos en línea predeterminados de TinyMCE y una tabla similar con estilos de Bootstrap:

![Ejemplo de tablas](../../../en/images/articles/articles-site-tables.png)

Consulta la documentación de Bootstrap sobre [Tablas](https://getbootstrap.com/docs/5.3/content/tables/) para más opciones.

## Reflexión

Podrías colocar el HTML de una tabla en un módulo personalizado e incluir ese módulo en el artículo. En el artículo, eso aparece como `{loadmoduleid xx}` donde xx es el Id del módulo.

*Traducido por openai.com*

