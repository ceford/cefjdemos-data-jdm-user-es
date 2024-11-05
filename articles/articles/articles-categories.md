<!-- Filename: J4.x:Create_and_Manage_Article_Categories / Display title: Artículos: Categorías  -->

## Introducción

Imagina una biblioteca sin un sistema de clasificación: los libros simplemente se colocan en los estantes en el orden en que son recibidos. Eso no es muy útil si la biblioteca tiene millones de libros y estás buscando algo sobre Historia, Jardinería o Ciencia. El mismo tipo de argumento se aplica a los Artículos. Si tienes docenas, cientos o miles de artículos, realmente necesitas un método para clasificarlos y así poder encontrar fácilmente lo que necesitas. Para eso están las Categorías.

Una categoría de Joomla! puede contener tanto artículos como subcategorías en una estructura tipo árbol anidada a cualquier profundidad, aunque es poco probable que desees ir más allá de una profundidad de tres o cuatro. Por ejemplo, si tus artículos son sobre Naturaleza, podrías clasificarlos de la siguiente manera:

- Animales
  - Aves
    - Halcones
    - Pinzones
    - Gaviotas
  - Mamíferos
    - Simios
    - Monos
    - Roedores
- Plantas
  - Flores
    - Margaritas
    - Rosas
  - Árboles
    - Robles
    - Olmos

En este ejemplo, la categoría *Animales* podría contener artículos sobre animales en general, así como subcategorías para artículos sobre diferentes tipos de animales.

Joomla proporciona una categoría predeterminada denominada No categorizado. Cualquier artículo que no se asigne a una categoría específica que hayas creado se convierte en miembro de la categoría No categorizado. Creas categorías según sea necesario para adaptarse a la naturaleza de tus artículos.

Un artículo solo puede estar en una categoría. En algunas circunstancias eso no es del todo suficiente. Supongamos, por ejemplo, que deseas buscar libros de todo tipo escritos en un idioma particular, o todas las plantas que son venenosas o todos los animales que son peligrosos. Ahí es donde los Tags resultan útiles. Se abordan en otra parte.

### Uso de Categorías

En la página de *Artículos* del administrador, el formulario *Opciones de Filtro* tiene una lista desplegable **- Seleccionar Categoría -** que muestra un árbol de categorías que te permite filtrar los artículos en una Categoría seleccionada. También puedes crear tipos de elementos de menú *Blog de Categoría* y *Lista de Categoría* para mostrar artículos de una categoría seleccionada a los visitantes del sitio.

## Agregar Categorías y Subcategorías

Existen varias rutas para llegar a la página *Artículos: Nueva Categoría*:

- A través del **Tablero de Inicio** Seleccione el **símbolo más (+)** a la derecha del enlace *Categorías de Artículos*. Este último lleva a la página de lista *Artículos: Categorías*.
- A través del **Menú de Administrador** Seleccione el elemento *Contenido* para expandir la lista y luego seleccione el **símbolo más (+)** a la derecha del enlace *Categorías*.
- A través del **Tablero de Contenido** Seleccione el icono del Tablero a la derecha del enlace *Contenido* en el menú del Administrador y luego, en el panel de *Contenido* del tablero, seleccione el **símbolo más (+)** a la derecha del enlace *Categorías*.
- A través de **Artículos: Categorías** Siga cualquiera de las rutas a la página de lista y seleccione el botón **Nuevo** en la Barra de Herramientas.

La siguiente captura de pantalla muestra el enlace *Categorías de Artículos* en el Tablero de Inicio a la lista de categorías y el *Símbolo Más* adyacente que lleva al formulario *Artículos: Nueva Categoría*.

![El ícono agregar categoría resaltado en el tablero de inicio](../../../en/images/articles/category-add-via-home-dashboard.png)

## Los artículos: Formulario de nueva categoría

![El formulario de edición de nueva categoría de artículos](../../../en/images/getting-started/article-category-edit.png)

La captura de pantalla de arriba muestra el formulario completado. Solo hay dos campos que necesitan contenido. Todo lo demás tiene valores predeterminados o nulos que puedes dejar por ahora y completar más tarde según sea necesario.

- **Título** Este es el único campo obligatorio. Debe ser corto pero descriptivo de la categoría.

### La pestaña Categoría

- **Descripción** Aunque no es obligatorio, este campo puede mostrarse en las páginas de lista de categorías del sitio controladas por elementos de menú. Puede ser necesario volver y actualizar la Descripción más tarde.
- **Padre** Si está configurado en *- Sin padre -* este nuevo elemento es una categoría potencialmente padre para otras categorías. Si otra categoría se selecciona como padre, este nuevo elemento es una subcategoría.
- **Estado** Por defecto, una nueva categoría se establece como *Publicado*. Puedes cambiar el estado de una categoría a *Publicado*, *No publicado*, *Archivado* o *En la papelera*. [Tarea pendiente] Explicar qué sucede cuando una Categoría no está publicada...
- **Acceso** Por defecto el acceso está configurado en *Público*. Otras opciones para restringir el acceso son *Invitado*, *Registrado*, *Especial* y *Super Usuarios*. [Tarea pendiente] Explicar cómo podría usarse el Acceso a una Categoría...
- **Idioma** En sitios multilingües, configurarlo en *Todos* hará que la nueva categoría sea independiente del idioma del sitio. Si está configurado en un idioma específico, solo estará disponible en las páginas que usen ese idioma.
- **Etiquetas** Si las utilizas, puedes añadir una o más etiquetas a la categoría. Configurar etiquetas a nivel de categoría es una buena manera de mantener la consistencia. Para este tutorial se creó una etiqueta *Naturaleza* y se usó para filtrar listas y mostrar solo los elementos relacionados con los tutoriales.
- **Nota** y **Nota de versión** Usa estos campos para añadir notas relevantes si es necesario.

### La pestaña Opciones

Las configuraciones en esta pestaña afectan la apariencia de esta Categoría en las páginas del sitio.

- **Diseño** Se refiere a la colocación de contenido en la página. Puede haber una elección de diseños dependiendo del componente y la plantilla en uso. [Tarea pendiente] Ejemplos...
- **Imagen** Es posible que desees usar una imagen para que actúe como un ícono y que esta categoría pueda ser reconocida instantáneamente en una lista de categorías. Si se utiliza para tal propósito, no se necesita una *Descripción de la imagen (texto Alt)* pero debe estar marcada la casilla de *Sin descripción*.

### Guardar y Cerrar

- **Guardar y Cerrar** Para terminar de editar esta categoría. O en la lista desplegable...
  - **Guardar y Nuevo** Guarda esta categoría y abre un nuevo formulario de edición para una nueva categoría. Por ejemplo, es posible que desees comenzar a construir un árbol de categorías añadiendo una categoría de *Simios* con *Mamíferos* como su padre.
  - **Guardar en Menú como Lista** ...
  - **Guardar en Menú como Blog** ...
  - **Guardar como Copia** ...

Cerrar el formulario de edición conduce a la página de lista de **Artículos: Categorías**.

![Una lista de categorías filtrada por la etiqueta Naturaleza](../../../en/images/articles/categories-list.png)

### Guardar en Menú como Lista

La selección de este elemento del menú desplegable *Guardar y Cerrar* guardará y cerrará el formulario de edición de la categoría y abrirá un nuevo formulario de elemento de menú con todos los datos necesarios para crear una *Lista de Categorías* para esta categoría. Es posible que desees cambiar el *Título*. Por ejemplo, podría ser *Lista de Artículos de Mamíferos* para dejar claro que es probable que sea una lista de artículos.

En la pestaña *Visualización de la Página* intenta configurar el campo *Mostrar encabezado de página* en *Mostrar*. Eso mostrará *Lista de Artículos de Mamíferos* como un encabezado en negrita en la parte superior de la página, dándole un aspecto más completo en general.

### Guardar en Menú como Blog

La selección de este elemento del menú desplegable *Guardar y Cerrar* guardará y cerrará el formulario de edición de la categoría y abrirá un nuevo formulario de elemento de menú con todos los datos necesarios para crear un *Blog de Categorías* para esta categoría. Es posible que desees cambiar el *Título*. Por ejemplo, podría ser *Blog de Artículos de Mamíferos* para que los últimos artículos sobre mamíferos se destaquen.

En la pestaña *Visualización de la Página* intenta configurar el campo *Mostrar encabezado de página* en *Mostrar*. Eso mostrará *Blog de Artículos de Mamíferos* como un encabezado en negrita en la parte superior de la página, dándole un aspecto más completo en general.

La siguiente captura de pantalla muestra la vista del sitio de una página de blog de categoría en desarrollo.

![Página de blog de la categoría Mamíferos](../../../en/images/articles/article-mammals-articles-blog-site-view.png)

## Consejos

- También puedes crear categorías de artículos desde dentro de un artículo.
- Recuerda que solo puedes asignar un artículo a una categoría.
- Como tanto las categorías principales como las subcategorías pueden tener más subcategorías, planifica y organiza las categorías cuidadosamente. Una jerarquía de categorías complicada puede volverse un desafío para gestionar.
- Otro método para agrupar contenido en Joomla es el uso del Componente de **Etiquetas**, que te permite agregar múltiples etiquetas a tus artículos. Usar categorías y etiquetas puede ayudar a minimizar el número de subcategorías y proporciona una manera eficiente de estructurar el contenido del sitio web y ofrecer a los visitantes más características para navegar por el contenido del sitio web.

*Traducido por openai.com*

