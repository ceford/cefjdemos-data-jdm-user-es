<!-- Filename: J4.x:Adding_a_New_Article / Display title: Añadir un Artículo Nuevo -->

Joomla!  4.0 <span id="main-portal-heading">**Tutorial**
Añadir un Artículo Nuevo</span>

## Introducción

Este tutorial es parte de una serie que tratan cómo trabajar con
Artículos en Joomla!

Abarca los métodos para añadir un artículo nuevo después de iniciar
sesión en el Panel de Administración, y está basado en una instalación
estándar de Joomla, utilizando el editor de contenido predeterminado.

Para más información sobre los diferentes editores disponibles en
Joomla, lea:  Creadores de
Contenido.

Antes de comenzar, además del contenido, si lo usa, necesitará saber qué
categoría y qué etiquetas asignará al artículo.

- Acceda al Inicio del Panel de Administración. Más sobre esto aquí:
   Logging in or out of the Administrator
  Dashboard.

## Comenzando

### Directamente desde el Panel de Inicio

<img
src="https://docs.joomla.org/images/e/e4/J4x_add_article_at_home_dashboard-es.png"
class="thumbborder" decoding="async" data-file-width="800"
data-file-height="224" width="800" height="224"
alt="J4x add article at home dashboard-es.png" />

Dependiendo de si su Panel de Inicio ha sido personalizado después de la
instalación, tendrá una o dos opciones para generar un nuevo artículo:

1.  En el Menú Lateral haga clic en el enlace **Contenido**. Luego, en
    el menú desplegable haga clic en el **símbolo más (+)** situado a la
    derecha del enlace Artículos.
2.  Si se muestra, en el Panel Sitio del Panel de Inicio, haga clic en
    el **símbolo más (+)** situado a la derecha del icono Artículos.

### A través del Gestor de Artículos

<img
src="https://docs.joomla.org/images/thumb/2/24/J4x_home_dashboard_add_article_en.png/800px-J4x_home_dashboard_add_article_en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/2/24/J4x_home_dashboard_add_article_en.png 1.5x"
data-file-width="1000" data-file-height="147" width="800" height="118"
alt="J4x home dashboard add article en.png" />

Cualquiera de estas opciones abrirá una página: **Artículos: Nuevo**
quedando listo para la entrada.

## Preparando el Artículo

<img
src="https://docs.joomla.org/images/f/f5/J4x_add_article_basic_es.png"
class="thumbborder" decoding="async" data-file-width="800"
data-file-height="286" width="800" height="286"
alt="J4x add article basic es.png" />

Cuando se genera un nuevo artículo, se abre un panel con una serie de
pestañas, y la pestaña **Contenido** seleccionada. Es posible guardar un
nuevo artículo con solo dos piezas de información requerida:

1.  Introduzca un título en el campo *Título*. Esto se ha de realizar
    cada vez que se muestre el título del artículo. El campo *Alias*
    (**Obligatorio**) al lado del campo del título no es un campo
    obligatorio, ya que si se deja en blanco Joomla creará el alias
    cuando se guarde el artículo. El alias se utiliza para hacer
    referencia al artículo y es importante para las [URLs Amigables a
    los
    Buscadores](https://docs.joomla.org/Search_Engine_Friendly_URLs "Special:MyLanguage/Search Engine Friendly URLs").
    El alias también puede ser utilizado para otras funciones del sitio,
    como plugins y módulos, para encontrar el artículo.
2.  Elija una **Categoría**. Consulte Configuración del Artículo a
    continuación para obtener más información.
3.  Si bien no es estrictamente necesario para añadir y guardar un
    artículo, introduzca su contenido utilizando el editor.

### Parámetros del Artículo

Las otras pestañas sobre el editor de contenido incluyen varias opciones
o parámetros para el artículo. **Es posible que no vea todas las
siguientes pestañas**, ya que un administrador del sitio puede ocultar
algunas para ayudar a mantener la coherencia del diseño del artículo en
todo el sitio web. También puede que vea una pestaña adicional para
*Campos personalizados* si se han configurado.

1.  *Imágenes y enlaces* le permite establecer una imagen de
    introducción y otra para mostrar al completo dentro del artículo,
    y/o enlaces para que estas imaégenes aparezcan en posiciones
    predefinidas. Esto resulta muy útil si su artículo se mostrará
    dentro de una categoría de tipo blog.
2.  *Opciones* le permite especificar el diseño del artículo y la
    información asociada, como el título, la categoría, las etiquetas,
    los detalles de publicación, etc. Esto normalmente se establece de
    forma global, pero puede configurarse de forma específica para un
    artículo a través de estas opciones.
3.  *Publicación* le permite establecer las fechas y tiempos de
    publicación para programar la publicación de un artículo. De forma
    predeterminada, cuando se guarda un artículo, se publicará de
    inmediato. También puede configurar los metadatos para el artículo.
4.  *Opciones de la pantalla de edición* le permite mostrar u ocultar
    parámetros para el artículo.
5.  *Permisos* muestra los permisos para cada grupo de usuarios que
    controlan lo que se puede o no se puede hacer.

### Opciones de Artículos

Además del contenido, un artículo tiene configuraciones para administrar
la publicación, cómo/dónde se mostrará y quién puede verlo cuando se
publique. En muchos casos, algunos de ellos se quedarán en su
configuración por defecto:

<img
src="https://docs.joomla.org/images/6/69/J4x_add_article_info_right_es.png"
class="thumbborder" decoding="async" data-file-width="300"
data-file-height="525" width="300" height="525"
alt="J4x add article info right es.png" />

1.  Seleccione el **Estado**: Publicado, Despublicado, Archivado o
    Movido a la papelera - el valor predeterminado es *Publicado*.
2.  Seleccione una **Categoría** usando el menú desplegable - este es un
    campo **Obligatorio**. Tenga en cuenta que, aunque es obligatorio,
    si no lo configura, el artículo se guardará, pero se configurará en
    la categoría predeterminada de Joomla "Sin Categoría". Puede agregar
    una nueva categoría en este campo escribiéndola y **presionando
    enter**.
3.  Active o no la opción **Destacado**, si desea que se muestre o no el
    artículo en la página de inicio.
4.  Seleccione el nivel de **Acceso** para el artículo: Public,
    Registered, Super Users, etc.
5.  Seleccione una o más **Etiquetas** para su artículo. Empiece a
    escribir para buscar y seleccionar etiquetas predefinidas o puede
    agregar una nueva escribiéndola y **presionando enter**.
6.  Puede agregar una **Nota** que será visible desde el Gestor de
    Artículos.
7.  También puede agregar una **Nota de Versión** que se mostrará en el
    historial de versiones del artículo.

## Saving the Article

Una vez que haya agregado la información y el contenido requerido, puede
guardar el artículo.

Hay varias formas de hacer esto dependiendo de lo que desee hacer a
continuación en Joomla.

Para guardar el artículo, puede elegir *Guardar*, *Guardar y cerrar*,
*Guardar en el menú* o *Guardar y nuevo* de la siguiente manera:

<img
src="https://docs.joomla.org/images/a/a5/J4x_add_article_saving_es.png"
class="thumbborder" decoding="async" data-file-width="300"
data-file-height="127" width="300" height="127"
alt="J4x add article saving es.png" />

1.  Haga clic en el botón de la barra de herramientas **Guardar** para
    guardar los cambios. Esto mantendrá el artículo abierto. Es una
    buena práctica guardar regularmente su trabajo en artículos más
    largos.
2.  Haga clic en el botón de la barra de herramientas **Guardar y
    cerrar** para guardar el artículo y acceder a la Lista de Artículos.
    El botón Guardar y cerrar tiene otras dos opciones en el
    desplegable:
    1.  Haga clic en el botón de la barra de herramientas **Guardar en
        el menú** para agregar el artículo a un menú abriendo una página
        de **Menús: Nuevo Elemento**.
    2.  Haga clic en el botón de la barra de herramientas **Guardar y
        nuevo** para guardar el artículo y posteriormente abrir una
        página de **Artículos: Nuevo**. Esta opción ahorra tiempo a la
        hora de agregar varios artículos.

Un mensaje del sistema indicará que el artículo se ha guardado
correctamente.

#### Errores al intentar guardar:

- Si no ha completado los campos obligatorios, aparecerá un mensaje de
  error en rojo indicando la información que falta y que debe agregar.
- Verá un mensaje de error si el artículo tiene un alias que ya existe.
  Puede solucionar este problema modificando el campo de alias.

## Consejos Rápidos

- Si no es el Super User o el Administrator, tómese un tiempo para
  comprender cómo está configurado el sitio web. El hecho de que haya
  guardado un artículo no significa que esté visible en el sitio web. Si
  se utilizan páginas de blogs de categorías, al asignar la categoría
  correcta se mostrará el artículo. De lo contrario, es necesario
  asignar un artículo a un elemento del menú. Puede hacerlo desde el
  artículo o a través de **Menús** y luego **Gestionar**.
- Trate de que los títulos de los artículos sean breves y específicos.
- Si bien se puede hacer, cuando haya varios usuarios agregando
  artículos al sitio web, evite crear nuevas categorías y etiquetas en
  los artículos. Los errores ortográficos y las diferencias pueden
  impedir con facilidad que los artículos se muestren donde estaban
  destinados. La creación de categorías y etiquetas en sus respectivas
  páginas de lista garantiza la coherencia en todo el sitio web.
- Si es necesario, utilice las notas del artículo. Pueden ser muy
  útiles, especialmente cuando varias personas agregan artículos.
- Dondequiera que se encuentre en Joomla, puede agregar un artículo sin
  tener que ir al Panel de Inicio - use el menú de la barra lateral de
  Joomla.
