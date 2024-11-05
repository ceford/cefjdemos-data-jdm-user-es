<!-- Filename: J4.x:Module_and_Menu_Styles / Display title: Estilos de Módulo y Menú  -->

## Acerca de las Hojas de Estilo en Cascada

La salida de una página web a través de Joomla! consiste en etiquetas HTML con atributos de estilo en forma de declaraciones de clase. Por ejemplo, un encabezado dentro de un artículo podría ser `<h3 class="special-warning">¡Cuidado!</h3>`. Este encabezado podría presentarse con una fuente más grande, diferentes colores para el texto y el fondo, y tal vez un borde y un ícono de advertencia. Los estilos de clase se definirían en el archivo user.css de la plantilla, de esta manera:
```css
    h3.special-warning {
      color: #900;
      background-color: #fee;
      border: 1px solid #900;
      padding: 1rem;
      font-size: 2rem;
    }
```
Esto funciona porque la hoja de estilo user.css se carga al final y cualquier estilo que contenga tiene prioridad sobre los mismos estilos en los archivos css cargados previamente. El estilo `special-warning` no se aplica a otras etiquetas `<h3>`, solo a aquellas con esta clase específica. Funciona dentro de un artículo porque ahí introduces tú mismo el nombre de la clase.

¿Pero qué pasa si quieres estilizar un módulo o toda una página? Por ejemplo, podrías aplicar diferentes colores de fondo a diferentes módulos o páginas. O podrías estilizar el encabezado de tu página principal para que difiera de los encabezados en otras páginas. Todo esto se puede lograr agregando nombres de clase en el formulario de edición del módulo o en el formulario de edición del elemento del menú. Las clases de estilo se ingresan luego en el archivo user.css.

## Estilos del Módulo

Este sencillo ejemplo aplica estilos personalizados al módulo de inicio de sesión y a su título. La siguiente captura de pantalla muestra los nombres de estilo ingresados en la pestaña Avanzado del formulario de edición de Módulos: Inicio de sesión. La Clase del Módulo se ha establecido como `make-me-light-green` y la Clase del Encabezado se ha establecido como `make-me-dark-green`. Ten en cuenta que puedes incluir guiones o subrayados en los nombres de clase, pero los espacios separan diferentes nombres de clase.

![formulario de edición del módulo de inicio de sesión pestaña avanzada mostrando clase personalizada](../../../en/images/templates/templates-edit-module-style.png)

Las siguientes declaraciones de estilo se utilizan en el archivo user.css:
```css
    .make-me-light-green {
      background-color: #efe;
      border-color: darkgreen;
    }
    .make-me-dark-green {
      color: darkgreen;
      border-color: #264f71;
    }
```
Presta atención al punto (.) que se utiliza en CSS para definir una clase con ese nombre. El punto no debe usarse en el formulario de entrada de datos del módulo. El resultado en este ejemplo es el siguiente:

![apariencia del sitio del módulo personalizado con herramientas de desarrollo](../../../en/images/templates/templates-edit-module-style-result.png)

La parte inferior de la imagen muestra el panel de Herramientas de Desarrollo del navegador con la etiqueta `<div>` que encierra el módulo de inicio de sesión seleccionada. Puedes ver que el estilo de Clase de Módulo personalizada se ha agregado a los estilos ya definidos en la plantilla del módulo. La siguiente línea muestra la etiqueta `<h3>` también con la Clase de Encabezado personalizada agregada a los estilos ya definidos.

¡Puede que te guste o no el estilo de este módulo! Pero esto es solo una lección sobre cómo hacerlo, ¡no sobre lo que hace un buen esquema de colores!

## Estilos de Página

Hay varias formas de personalizar la apariencia general de una página. 
Todas funcionan a través del formulario de Editar Elemento en los Menús:

- La pestaña Detalles tiene una opción de Estilo de Plantilla desde la cual puedes seleccionar una plantilla específica para usar.
- La pestaña Diseño del Blog tiene campos de Clase de Artículo Principal y Clase de Artículo donde puedes escribir un nombre de clase.
- La pestaña Opciones tiene un campo de Elige un Diseño desde el cual puedes elegir entre los diseños disponibles para todos los elementos.
- La pestaña Tipo de Enlace tiene campos para una Clase de Enlace, una Clase de Ícono de Enlace y una Clase de Imagen.
- La pestaña Visualización de Página tiene campos para una Clase de Página.

Es el último en esta lista que se cubre en este artículo. ¿Qué sucede con `make-me-aliceblue` ingresado en este campo? Y lo siguiente se ingresa en user.css:
```css
    .make-me-aliceblue {
      background-color: aliceblue;
    }
```
La clase se añade a la etiqueta body de la página:

![apariencia del sitio de la página personalizada con herramientas de desarrollador](../../../en/images/templates/templates-edit-page-class-result.png)

¡QED!

*Traducido por openai.com*

