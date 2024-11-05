<!-- Filename: J4.x:Setup_a_Multilingual_Site / Display title: Configurar un sitio multilingüe  -->

## Datos de Muestra

Joomla viene con dos conjuntos de datos de muestra: Blog y Multilingüe. Hay un tercer conjunto de Pruebas, pero solo para usuarios que trabajan con la versión de Desarrollo de Joomla. Si tienes un sitio existente con artículos, menús y módulos, será similar en principio a un sitio con los datos de muestra del Blog instalados.

En el Panel de Control Principal, los datos de muestra Multilingües dicen: **Antes de lanzar, asegúrate de tener al menos 2 idiomas instalados con sus Idiomas de Contenido y que no se haya instalado ningún dato de muestra**. Eso probablemente te llevará a crear un sitio multilingüe ejecutando manualmente los pasos requeridos uno por uno. Ese es un procedimiento propenso a errores en el cual es probable que cometas un error, especialmente si estás utilizando varios idiomas. Los errores se pueden corregir, pero todo el proceso es un poco tedioso y puede ser confuso.

Puedes ignorar ese consejo y usar los Datos de Muestra Multilingües para configurar un sitio multilingüe si comprendes cómo realizar algunas correcciones en los menús y módulos originales más adelante.

## Sitio Inicial

Un sitio de Joomla recién instalado tiene un **Menú Principal** en la barra lateral derecha. Contiene un único elemento de menú llamado **Inicio** del tipo de Artículos Destacados. También hay un **Formulario de Inicio de Sesión** en la barra lateral derecha.

Inicialmente, no hay artículos destacados, por lo que la parte principal de la página está vacía.

## Datos de Muestra del Blog

Si has creado el contenido de tu propio sitio, **no** deberías instalar los
Datos de Muestra del Blog. Sin embargo, te recomendamos leer esta sección para ver cómo
se compara. De lo contrario:

- Selecciona **Instalar** en la sección de Datos de Muestra Multilingües del
  Panel de Inicio. Las etapas de instalación aparecerán brevemente y luego
  desaparecerán.
- Deberías notar que se instalan varios menús nuevos (recarga la
  página del administrador y expande el menú Menús):
  - Menú Principal del Blog.
  - Menú Inferior, que contiene los elementos de menú de Iniciar/Cerrar sesión.
  - Menú Especial, visible después de iniciar sesión.
- Selecciona el icono **Abrir frontend** en la barra de estado superior o recarga
  el sitio si ya está abierto en una pestaña separada.

Deberías esperar ver un diseño lleno de información de Artículos Destacados:

- En la parte superior está el nuevo menú **Menú Principal del Blog** para varios diseños de blog
  y artículos.
- En la barra lateral derecha hay módulos para un Formulario de Inicio de Sesión, un Menú Principal y un
  feed RSS de Mi Blog.
- Después de iniciar sesión, la barra lateral derecha tiene un Menú Especial solo para acciones de Administrador.
- El elemento **Inicio** del Menú Principal lleva al diseño de Artículos Destacados.
- El elemento de menú superior **Blog** lleva a un diseño de Blog de Categoría algo
  diferente del diseño de Artículos Destacados.

Tómate unos minutos para explorar los elementos del menú y los tipos de
información a los que conducen.

## Instalar y Publicar Idiomas de Contenido

Primero instala todos los idiomas que deseas utilizar. Si más tarde necesitas instalar un idioma adicional, deberás completar los pasos de configuración para ese idioma manualmente uno por uno. Eso se cubrirá en otra parte. Para este tutorial, se agregaron francés, alemán y galés al inglés predeterminado del sitio durante la instalación de Joomla. Para agregar idiomas después de la instalación:

- Selecciona **Sistema** → **Instalar Idiomas** en el menú del Administrador.
- Selecciona el botón **Instalar** para cada idioma que propongas usar.

Los idiomas instalados deben ser **Publicados** para que estén disponibles. Desde el menú del Administrador:

* Selecciona **Sistema / Panel de Gestión / Idiomas de Contenido**
* En la columna Estado, **Publica** cada uno de los idiomas que deseas utilizar.

## Datos de Muestra Multilingües

La instalación de los Datos de Muestra Multilingües tiene efectos con los que tendrás que lidiar más adelante:

- Los menús en la barra lateral derecha se despublicarán. Eso significa que el módulo del Menú Principal se despublicará y no habrá enlace al diseño de Artículos Destacados. Si tenías otros enlaces en el Menú Principal, también estarán no disponibles.
- El Menú Especial se despublicará. Este proporcionaba un enlace para crear una nueva publicación.

Los Datos de Muestra Multilingües ofrecen las siguientes características adicionales:

- Una categoría de artículos para cada idioma.
- Un artículo configurado para cada idioma, aunque en texto pseudo de Lorem ipsum.
- Un menú separado para cada idioma. Verás esto en la lista de **Administrador** → **Menús**.
- Un módulo de menú **Main Menu xx-YY** en la barra lateral derecha del Sitio, donde xx-YY es un código de idioma como en-GB.
- El elemento de menú **Main** ahora conduce a un diseño de Blog de Categoría para artículos en el idioma seleccionado. Contiene solo un artículo.
- Hay un módulo **Language Switcher** en la barra lateral derecha. No tiene título para evitar la necesidad de un módulo separado para cada idioma con títulos traducidos. La selección se hace por bandera de idioma. Pruébalo.

Algo a tener en cuenta: las palabras que proporciona Joomla se traducirán, por ejemplo, en las Migas de Pan y el Formulario de Inicio de Sesión. Las palabras que son ingresadas por los usuarios necesitan ser traducidas manualmente, por ejemplo, Formulario de Inicio de Sesión y Menú Principal. Más sobre eso más adelante.

## Solucionando Problemas Iniciales

### Orden de Idiomas

Puede notar que el selector de idiomas tiene los idiomas en orden
alfabético inverso. Para cambiar el orden:

- Seleccione **Sistema → Idiomas de Contenido** en el menú de Administrador.
- Use los íconos de elipsis vertical para arrastrar los idiomas al orden deseado.
- Recargue el Sitio y verá que el selector de idiomas ahora tiene los idiomas en su orden preferido.

### Orden de Módulos de la Barra Lateral Derecha

El orden de los módulos en la barra lateral derecha es una cuestión de preferencia personal. Para cambiar el orden:

- Seleccione **Contenido → Módulos del Sitio** en el menú de Administrador.
- Filtre por **Posición → barra-lateral-derecha**.
- Seleccione el ícono de la columna de orden para revelar los controles de arrastrar el orden
  (íconos de elipsis vertical). El ícono del encabezado de la columna debe ser un chevron
  apuntando hacia arriba.
- Arrastre los elementos para ordenar:
  - Selector de Idiomas
  - Menú Principal (todas las variantes - el orden no importa).
  - Menú Especial
  - Formulario de Inicio de Sesión
  - Artículos Archivados
  - Sindicación

### Artículos Destacados

El Menú Principal original está sin publicar, pero el elemento de menú Inicio que contiene
se puede reproducir en otro lugar. El lugar más conveniente es el menú superior.

- Seleccione **Menús → Menú Principal Blog** en el menú de Administrador.
- Seleccione el botón **Nuevo** en la Barra de Herramientas.
- Ingrese un **Título** en el formulario **Menús: Nuevo Ítem**, por ejemplo
  **Destacados**.
- Use el botón **Seleccionar** en el campo **Tipo de Ítem de Menú**.
- Seleccione **Artículos → Artículos Destacados** de la lista de **Tipo de Ítem de Menú**.
- Seleccione **Guardar** en la Barra de Herramientas.
- En el campo **Orden** seleccione **- Primero -**.
- En la pestaña **Diseño del Blog** establezca **Artículos Intro** en 3.
- Seleccione **Guardar & Cerrar** en la Barra de Herramientas.

### Asignación de Módulos del Sitio

El diseño original de la página de Inicio para Artículos Destacados se produjo asignando módulos seleccionados para aparecer solo en esa página. La nueva página de Destacados necesita ser añadida para cada uno de esos módulos.

- Seleccione **Contenido → Módulos del Sitio** en el menú de Administrador.
- Encuentre y seleccione el elemento **Imagen**.
- En la pestaña **Asignación de Menú**, busque y marque el elemento **Destacados** en
  la sección **Menú Principal Blog**.
- Seleccione **Guardar & Cerrar** en la Barra de Herramientas.
- Encuentre y seleccione el elemento **Últimas Publicaciones**.
- En la pestaña **Asignación de Menú**, busque y marque el elemento **Destacados** en
  la sección **Menú Principal Blog**.
- Seleccione **Guardar & Cerrar** en la Barra de Herramientas.

## Recargar Sitio

Cuando recargues el sitio, el primer elemento en el menú superior será el enlace Destacado, que lleva al diseño de Artículos Destacados. El elemento Blog adyacente es un diseño más compacto de Blog de Categoría. Prueba el selector de idiomas. El texto proporcionado por Joomla en las migas de pan y el Formulario de Inicio de Sesión cambia en consecuencia. Además, los artículos destacados ahora incluyen un artículo de los Datos de Muestra Multilingües, que está en el idioma seleccionado. Puede estar en la última página.

### Sitio Híbrido o Puramente Multilingüe 

En esta etapa tienes un sitio híbrido: algunos contenidos están disponibles en todos los idiomas y otros contenidos están disponibles en un idioma específico. Si deseas un sitio puramente multilingüe, necesitarás despublicar el módulo del Blog del Menú Principal superior y quizás otros. En algunos casos, puede que desees crear módulos específicos para cada idioma, por ejemplo, el Formulario de Inicio de Sesión podría tener versiones con los títulos Formulaire de connexion, Login Formular y Ffurflen Mewngofnodi.

¡Lo que hagas después depende de ti!

## Menú Principal Original

Tu módulo de Menú Principal original, que ahora no está publicado, puede haber 
contenido elementos de menú adicionales. Podrías publicarlo. El problema es que 
el elemento de Inicio enlaza con la misma ubicación que cada una de las páginas 
de inicio de los menús específicos de idioma, pero solo en inglés. Puedes solucionar 
eso de la siguiente manera:

- Selecciona **Menús** → **Menú Principal** desde el menú del Administrador.
- Selecciona el elemento de menú **Inicio**.
- Selecciona la pestaña **Tipo de Enlace**.
- Establece **Mostrar en Menú** en **No**.
- Selecciona **Guardar & Cerrar** en la Barra de herramientas.
- Selecciona **Contenido** → **Módulos del Sitio** desde el menú del Administrador.
- Encuentra el **Menú Principal** y publícalo, cambiando la cruz gris por una 
  marca verde.

Los elementos visibles en el Menú Principal original ahora deberían funcionar normalmente. 
Si el Menú Principal no tiene elementos visibles, no se mostrará.

## Añadiendo un Idioma Extra

Después de la configuración inicial de un sitio multilingüe, si deseas agregar otro idioma tendrás que seguir los pasos manualmente uno por uno:

### Paso 1: Instalar el Idioma

- Selecciona **Sistema**→**Instalar**→**Idiomas** desde el menú del Administrador.
- Encuentra el idioma requerido en la lista de **Extensiones: Idiomas**.
- Selecciona el botón **Instalar**.
- Habrá un mensaje: **La instalación del paquete de idioma fue exitosa.**

En esta secuencia de ejemplo, el idioma extra es el español.

### Paso 2: Publicar y Ordenar

- Selecciona **Sistema**→**Gestionar**→**Idiomas de Contenido** desde el menú del Administrador.
- Habilita el idioma recién instalado: selecciona el botón de Estado para convertir la cruz gris en una marca verde.
- Usa los iconos de puntos suspensivos verticales para arrastrar los idiomas al orden deseado.

### Paso 3: Crear un Menú

- Selecciona **Menús**→**Gestionar** desde el menú del Administrador.
- Selecciona el botón **Nuevo** desde la Barra de herramientas.
- Ingresa un título de menú adecuado y un nombre único, ejemplos: Menú Principal (es-ES) y menuprincipal-es-es.
- Ingresa una Descripción, ejemplo: El menú principal para el sitio en idioma español (es-ES).

### Paso 4: Agregar un Módulo de Menú

- Selecciona **Menús**→**Gestionar** desde el menú del Administrador.
- Selecciona el botón **Agregar un módulo para este menú** para el menú recién creado.
- Ingresa un título adecuado, ejemplo: Menú Principal es-ES.
- Selecciona una Posición: Sidebar-right.
- Selecciona un Idioma: Español (es-ES).
- Selecciona **Guardar**.
- Ordena el módulo: desde la lista de Orden selecciona el elemento después del cual debería aparecer este nuevo elemento.
- Selecciona **Guardar y Cerrar**.

### Paso 5: Agregar una Categoría

- Selecciona **Contenido**→**Categorías** desde el menú del Administrador.
- Selecciona el botón **Nuevo** en la Barra de herramientas.
- Ingresa un título adecuado, ejemplo: Categoría (es-es).
- Selecciona el idioma correcto: Español (es-ES).
- Selecciona la pestaña **Asociaciones**.
- Para cada idioma, selecciona una Categoría. Solo hay una elección en cada caso.
- Selecciona **Guardar y Cerrar**.

### Paso 6: Agregar un Ítem de Menú

- Selecciona **Menús**→**Menú Principal (es-ES)**, el menú recién creado.
- Selecciona el botón **Nuevo** en la Barra de herramientas.
- Ingresa un título adecuado, ejemplo: Página de inicio.
- Usa el botón Seleccionar al final del campo **Tipo de Ítem de Menú** para seleccionar un tipo de ítem.
- De la lista emergente selecciona **Artículos**→**Blog de Categoría**.
- En el campo Elegir una Categoría usa el botón Seleccionar.
- Desde la lista emergente de Categorías selecciona la categoría Categoría (es-es).
- Establece el campo **Página Predeterminada** en **Sí**.
- En la lista desplegable de **Idioma** selecciona **Español (es-ES)**.
- **Guardar y Cerrar**

### Paso 7: Agregar un Artículo

La forma fácil de agregar un artículo para el nuevo idioma es copiar un artículo existente.

- Selecciona **Contenido**→**Artículos** desde el menú del Administrador.
- Selecciona el artículo para copiar, en este ejemplo **Artículo (en-GB)**.
- En el formulario **Artículos: Editar** cambia el título a **Artículo (es-ES)**.
- Cambia la **Categoría** a **Categoria (es-es) (es-ES)**.
- Cambia el **Idioma** a **Español (es-ES)**.
- Selecciona **Guardar como Copia** desde la lista desplegable **Guardar y Cerrar** en la Barra de herramientas. **¡Cuidado!**
- Selecciona la pestaña **Asociaciones**.
- Para cada idioma selecciona un artículo para ser asociado - el artículo equivalente en cada idioma.
- Selecciona **Guardar y Cerrar** desde la Barra de herramientas.

## Añadiendo un Artículo Multilingüe

Supongamos que deseas crear un artículo en cada uno de tus idiomas seleccionados.

- Selecciona **Contenido** → **Artículos** → **+** desde el menú del Administrador o el botón **Nuevo** desde la Barra de herramientas en la lista de Artículos.
- Ingresa un título para el artículo, por ejemplo, **William Shakespeare**.
- Configura el campo **Categoría** a **Categoría (en-gb) (en-GB)**.
- Establece el campo **Idioma** a **Inglés (en-GB)**.
- Ingresa el **Texto del Artículo**, por ejemplo, de Wikipedia:

“William Shakespeare (baut. 26 de abril de 1564 – 23 de abril de 1616) fue un dramaturgo, poeta y actor inglés. Es ampliamente considerado como el mayor escritor en lengua inglesa y el dramaturgo más destacado del mundo. A menudo se le llama el poeta nacional de Inglaterra y el "Bardo de Avon" (o simplemente "el Bardo"). Sus obras existentes, incluidas las colaboraciones, consisten en unas 39 obras de teatro, 154 sonetos, tres largos poemas narrativos y algunos otros versos, algunos de autoría incierta. Sus obras han sido traducidas a todos los principales idiomas vivos y se representan con más frecuencia que las de cualquier otro dramaturgo. Sigue siendo indiscutiblemente el escritor más influyente en lengua inglesa, y sus obras continúan siendo estudiadas e interpretadas.”

- Selecciona **Guardar** desde la Barra de herramientas.
- Selecciona la pestaña **Asociaciones**.
- Para cada idioma:
  - Selecciona el botón **Crear**.
  - En el formulario emergente **Nuevo Artículo**, ingresa un título traducido, **William Shakespeare**.
  - Configura la Categoría para el idioma que seleccionaste.
  - Ingresa el texto traducido en el campo **Texto del Artículo** (puedes probar <a href="https://translate.google.com/" rel="nofollow noreferrer noopener">https://translate.google.com/</a>).
  - Selecciona **Guardar y Cerrar**.
- Después de que un nuevo artículo para cada idioma haya sido creado, selecciona **Guardar y Cerrar**.

## Menú Principal

Si tienes un enlace a un artículo para Todos los Idiomas en el Menú Principal y luego usas ese artículo como base para artículos asociados en otros idiomas, necesitarás cambiar el enlace del Menú Principal. De lo contrario, cambiar de idioma con ese artículo seleccionado llevará a un error de Página No Encontrada en el idioma seleccionado.

- Selecciona **Menús** → **Menú Principal** desde el menú del Administrador.
- Selecciona el elemento del menú que necesitas cambiar, por ejemplo **William Shakespeare**.
- Cambia el campo **Idioma** a **Inglés (en-GB)**.
- Selecciona **Guardar & Cerrar** desde la Barra de Herramientas.

Si hay solo ese único elemento en el Menú Principal, ese módulo desaparecerá al cambiar a otros idiomas.

*Traducido por openai.com*

