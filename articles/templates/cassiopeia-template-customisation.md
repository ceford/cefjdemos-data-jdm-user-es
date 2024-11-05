<!-- Filename: J4.x:Cassiopeia_Template_Customisation / Display title: Personalización de Cassiopeia -->

## Introducción

Cassiopeia es la plantilla del sitio proporcionada con Joomla 4. Es una plantilla **accesible** y **responsive** de propósito general excelente. Se puede personalizar a través de las opciones de la plantilla y el archivo *user.css* por usuarios con un poco de conocimiento de HTML y CSS.

La siguiente ilustración muestra la apariencia de un sitio Joomla 4 con un artículo y algunos elementos de menú creados.

![Vista de artículo único de Cassiopeia](../../../en/images/templates/cassiopeia-customisation-article-view.png)

## Plantillas: Editar Estilo

Puedes experimentar con la apariencia del sitio abriendo el formulario Editar Estilo. Ve a **Sistema → Plantillas → Estilos de Plantillas del Sitio** y selecciona el título de la plantilla en la columna de Estilo, Cassiopeia - Predeterminado. La pestaña Avanzado contiene configuraciones que puedes ajustar:

![Pestaña avanzada de edición de estilo de Cassiopeia](../../../en/images/templates/cassiopeia-customisation-edit-style.png)

Para probar las opciones, abre una pestaña o ventana del navegador con la interfaz de Administrador y una segunda pestaña o ventana con la interfaz del Sitio y alterna entre ellas después de cada cambio guardado.

### Marca

- **Sí** el predeterminado. La barra de logo de Cassiopeia que contiene un Logo o Nombre de Marca se muestra con un fondo oscuro, azul por defecto.
- **No** La barra de logo no se muestra. Las opciones para seleccionar un Logo, Título y Lema desaparecen.

La imagen de marca predeterminada es la palabra Cassiopeia como una imagen en un archivo SVG. Eso es lo que se muestra en la primera ilustración arriba.

Puedes configurar la Marca en No si deseas proporcionar branding en un módulo HTML personalizado.

### Logo

- **Ninguno** Se usará el logo de imagen predeterminado de Cassiopeia a menos que se defina un Título.
- **Imagen del Logo** El Logo seleccionado aparecerá en lugar del logo de Cassiopeia incluso si se define un Título.

### Título (alternativa al logo)

- **Mi Nombre de Marca** Si está presente y no has seleccionado una imagen de Logo, las palabras en el campo de Título aparecerán pero subrayadas en la barra superior azul.

### Lema

- **Siempre a tu servicio** Si está presente, las palabras en el campo de lema aparecerán en un tamaño de fuente pequeño debajo de la imagen del logo o nombre de la Marca.

![Marca de Cassiopeia con lema](../../../en/images/templates/cassiopeia-customisation-brand-with-tagline.png)

### Esquema de Fuentes

- **Ninguno** el predeterminado. Se usa la familia de fuentes especificada en la hoja de estilo de la plantilla, lo que generalmente significa que el sitio usará las fuentes con las que estás familiarizado disponibles en tu propia computadora.
- **Otros** Se usará una familia de fuentes ubicada en la jerarquía del directorio de plantillas o descargada de la web. Puedes ver la apariencia cambiada del texto en una página cuando recargas el sitio después de cambiar esta opción.

### Tema de Colores

- **Estándar** Un color de fondo azul oscuro para la barra de Marca y otras características como el botón de Inicio de Sesión.
- **Alternativo** Un color de fondo marrón en lugar de azul oscuro.

![Esquema de color alternativo de Cassiopeia](../../../en/images/templates/cassiopeia-customisation-alt-color-scheme.png)

### Diseño

- **Estático** el predeterminado. El ancho máximo se establece en 1320px. En pantallas más anchas, el margen solo se amplía.
- **Fluido** No hay un ancho máximo.

La vista en un dispositivo móvil de pantalla estrecha:

![Vista móvil de Cassiopeia](../../../en/images/templates/cassiopeia-customisation-mobile-view.png)

### Encabezado Fijo

- **No** el predeterminado. Los elementos del encabezado y contenido se desplazan hacia arriba fuera de la vista.
- **Sí** Excepto en pantallas estrechas, los elementos del encabezado permanecen fijos en la parte superior de la vista mientras los elementos de contenido se desplazan hacia arriba. Eso solo es evidente cuando el contenido de la página es más alto que la vista.

### Enlace Volver al inicio

- **No** el predeterminado. No hay un enlace Volver al inicio.
- **Sí** Donde el contenido es más alto que la vista, en la parte inferior derecha de la página hay un botón marcado con un chevrón hacia arriba. Selecciónalo para desplazarte de nuevo a la parte superior de la página.

![Volver al inicio de Cassiopeia](../../../en/images/templates/cassiopeia-customisation-back-to-top.png)

## Posiciones de Plantilla de Cassiopeia

A medida que construyes un sitio con Cassiopeia, se vuelve realmente útil conocer las ubicaciones de las posiciones que puedes usar para los módulos. Algunas son descriptivas, como *menu* y *bottom-a*, pero no es tan obvio dónde están hasta que las usas. Esta ilustración debería ayudar:

![Posiciones de plantilla de Cassiopeia](../../../en/images/templates/cassiopeia-template-positions.png)

Prueba lo siguiente:

### Mover el Módulo de Menú a la Posición *menu*

Un sitio recién instalado con Joomla 4 tiene un menú en la posición *sidebar-right*, como se ve en la primera ilustración arriba. Para este tutorial se han añadido algunos elementos al menú, uno de los cuales es un elemento principal con dos elementos secundarios. Para mover este menú a la posición del menú, ve a **Contenido** → **Módulos del Sitio** en el menú del Administrador. En la lista hay tres módulos, incluido el Menú Principal. Selecciónalo para abrir el formulario de edición de Módulos: Menú.

En la pestaña del Módulo, cambia el campo de Posición a Menú \[menu\]. Guarda y observa el resultado en la vista del Sitio. El menú se ve bien, pero los elementos secundarios no están allí.

En el formulario de edición del menú, selecciona la pestaña Avanzado y desplázate hacia abajo hasta el campo de Distribución. Es una lista desplegable con cuatro opciones. --Desde Módulo-- / Por defecto está seleccionado por defecto. Prueba las otras opciones y observa el resultado. (Recuerda *Guardar* en el formulario de edición y recargar en la vista del Sitio). Ninguna de las opciones --Desde Módulo-- muestran los elementos secundarios del menú, pero ambas opciones --Desde Plantilla Cassiopeia-- sí lo hacen.

![Posiciones del menú de Cassiopeia](../../../en/images/templates/cassiopeia-customisation-menu-position.png)

Entonces, ¿qué diferencia hace **Colapsible**?

- Menú Desplegable Colapsible: En dispositivos móviles con pantallas estrechas, el menú se colapsa a un icono de Hamburguesa hasta que se selecciona. Al seleccionarlo, se expande para mostrar una lista vertical.
- Desplegable: El menú siempre aparece como una lista vertical.

### Mover el Módulo de Menú a la Posición *topbar*

En el formulario de edición, en la pestaña del Módulo, configura la Posición a Barra Superior \[topbar\] y observa el resultado. Hay un inconveniente: el menú está posicionado más a la izquierda que cuando estaba en la posición del menú. Eso se debe a que la posición del menú y la ubicación del logo tienen una clase CSS de *grid-child*, pero la barra superior no. Eso se puede solucionar con una entrada en el archivo *user.css*, que se detallará más adelante.

## Personalizar Cassiopeia

¿Qué pasa si no te gusta el color de fondo azul oscuro del encabezado? Supongamos que prefieres un tema verde oscuro. Para solucionarlo, necesitas un poco de conocimiento de CSS. Ve a **Sistema** → **Plantillas del Sitio** → **Detalles y Archivos de Cassiopeia** para abrir el formulario de la plantilla: Personalizar (Cassiopeia).

La ilustración a continuación muestra dos grupos de carpetas. El primer grupo consta de las carpetas y archivos de la plantilla que no deberías cambiar, pero a los que puedes añadir archivos. En particular, puedes agregar archivos HTML de sobreescritura de plantilla a la carpeta *html*. El segundo grupo contiene los archivos de medios de la plantilla que no deberías cambiar. Sin embargo, puedes añadir un archivo *user.css* a la carpeta *css* y/o un archivo *user.js* a la carpeta *js*. Harías esto si quisieras hacer algunos cambios simples en la apariencia del sitio.

![Editar archivos de Cassiopeia](../../../en/images/templates/cassiopeia-customisation-edit-files.png)

Nota que no hay un archivo *user.css* presente en la carpeta *css*. Ese es uno que crearás tú mismo para poder sobrescribir estilos definidos anteriormente. Si no está presente, créalo ahora seleccionando la carpeta *css* y luego el botón *Nuevo*. En el diálogo modal de Nuevo Archivo selecciona la carpeta *css*, de lo contrario, el nuevo archivo aparecerá en el lugar equivocado. Introduce user (minúsculas y sin *.css*) en el campo Nombre de Archivo y selecciona *.css* en el campo Tipo de Archivo. Selecciona el botón Crear para crear el archivo. Si *user.css* ya está presente, selecciónalo para abrir el formulario de edición.

### Encabezados

Como un inicio simple, cambia el color de los encabezados a verde oscuro. Los encabezados son etiquetas en el rango de *h1, h2, h3, h4, h5* y *h6*. En el archivo *user.css* ingresa la definición de estilo:
```css
h1, h2, h3, h4, h5, h6 {
  color: darkgreen;
}
```
Guarda y recarga el sitio para ver el resultado. El título de la página o artículo debería ser verde oscuro. Si no, verifica lo que has escrito. El lenguaje formal para la documentación de Joomla es el inglés británico, así que "colour" en lugar de "color" como en el inglés americano. Pero en CSS debe ser "color". ¿Está la puntuación correcta?

No es tan obvio que algunas etiquetas distintas a los encabezados pueden estar estilizadas para parecerse a los encabezados. Así que añade esto:
```css
.h1, .h2, .h3, .h4, .h5, .h6 {
  color: darkgreen;
}
```
Nota aquí que el punto inicial (.) es un selector de clase, por ejemplo, Dummy H1, por lo que hay un punto en el archivo CSS pero no en el nombre de la clase.

### Fondo del Encabezado

En la pestaña del navegador que contiene el Sitio, abre las herramientas de desarrollador de tu navegador, Firefox en este ejemplo, y selecciona la etiqueta del encabezado.

![Herramientas de desarrollador de Cassiopeia](../../../en/images/templates/cassiopeia-customisation-developer-tools.png)

Eso muestra los estilos utilizados. El estilo container-header es donde se establecen el fondo-color y el fondo-imagen. Necesitan ser sobrescritos en el archivo *user.css*. Intenta esto:
```css
.container-header {
  background-color: darkgreen;
  background-image: none;
}
```
### Estilo *topbar*

¿Recuerdas ese comentario sobre el menú estando demasiado a la izquierda en la barra superior? Eso es porque no tiene un ancho máximo y márgenes apropiados establecidos. Pon esto en el archivo *user.css* para corregir eso:
```css
.container-topbar {
  max-width: 1320px;
  margin-left: auto;
  margin-right: auto;
}
```
Este es el tema verde funcionando:

![Tema verde de Cassiopeia](../../../en/images/templates/cassiopeia-customisation-green-theme.png)

### Accesibilidad

Nota que debe haber un contraste suficiente entre los colores de fondo y primer plano para cumplir con los estándares de accesibilidad web. Puedes verificar tu contraste en el WebAIM Contrast Checker. El verde oscuro es \#006400.

## Sobrescrituras

La pestaña "Plantillas: Personalizar (Cassiopeia) en el formulario Crear Sobrescrituras" muestra la lista de extensiones para las que puedes crear una sobrescritura. Nota los diferentes símbolos: selecciona un símbolo de carpeta para mostrar una lista de las carpetas y archivos que contiene; selecciona un símbolo de múltiples archivos para crear inmediatamente una sobrescritura para esa extensión; el elemento creado desaparece de la lista - selecciona la pestaña Editor y localiza la sobrescritura creada en la carpeta *html*. Puede que se creen más de un archivo - los archivos creados se copian de la extensión original listos para que los edites. ¡Para eso necesitas conocer algo de HTML y PHP!

Esta es la pestaña Crear Sobrescrituras:

![Cassiopeia crear sobrescrituras](../../../en/images/templates/cassiopeia-customisation-create-overrides.png)

Si solo estás experimentando y realmente no quieres una sobrescritura, puedes *Cerrar* el formulario de edición, seleccionar el botón Gestionar Carpetas en la Barra de herramientas y seleccionar el botón Eliminar en la parte inferior del formulario modal Gestionar Carpetas.

Las sobrescrituras realmente tratan sobre personalizar extensiones antes que la plantilla Cassiopeia, y esa es otra historia.

## Plantillas Hijas

Si deseas realizar cambios más significativos en la apariencia del sitio, puedes crear una plantilla hija. Esto copia solo una pequeña selección de carpetas y archivos para que puedas cambiar o agregar, pero de lo contrario sigue utilizando las carpetas y archivos de la plantilla principal. Al usar plantillas hijas, podrías tener algunas páginas con un color de tema y otras páginas con un segundo color de tema. Las plantillas hijas se abordan en otra parte. Esta es una ilustración de la estructura de archivos en un hijo de Cassiopeia:

![Archivos de plantilla hija de Cassiopeia](../../../en/images/templates/cassiopeia-customisation-child-template-files.png)

*Traducido por openai.com*

