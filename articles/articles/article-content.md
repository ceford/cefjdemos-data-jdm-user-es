<!-- Filename: J4.x:Adding_a_New_Article / Display title: # Artículo: Editar - Contenido -->

## Introducción

*Agregar un artículo* se trató en un artículo de *Introducción*. Este es el primero de una serie de artículos que proporcionan más detalles sobre el formulario de *Artículo: Editar*. Cubre la pestaña *Contenido* y algunos aspectos del editor TinyMCE, que es el editor predeterminado proporcionado con Joomla.

La siguiente captura de pantalla muestra el formulario de edición con un artículo que ya ha sido guardado.

![El formulario de edición de contenido](../../../en/images/articles/articles-edit-content.png)

## Entrada de Datos

El formulario de edición de artículos tiene paneles con pestañas. Un artículo nuevo tiene la pestaña de **Contenido** seleccionada por defecto. De lo contrario, la última pestaña abierta es la que se selecciona.

### El campo de Título

El campo **Título** es *Requerido* y se utiliza donde quiera que se muestre el título del artículo. Este es el único campo que debe contener algún texto para poder guardar un formulario de edición.

Los títulos deben ser breves pero descriptivos del contenido del artículo, ya que aparecen en listas y elementos de menú donde el espacio es limitado.

Los títulos no tienen que ser únicos, aunque lo ideal es que lo sean. Por ejemplo, si seleccionas *Guardar como Copia* desde la lista desplegable de *Guardar y Cerrar*, el proceso de guardado almacenará el artículo actual y generará uno nuevo con un número añadido al Título y Alias. Puedes eliminar el número del Título, pero no del Alias, y *Guardar* la copia. Esto da como resultado dos artículos con el mismo título mostrado.

### El campo del Alias

El campo de *Alias* generalmente se deja en blanco. Cuando se guarda el artículo, el Alias se genera a partir del título convirtiéndolo todo a minúsculas y reemplazando los caracteres no alfanuméricos con guiones.

Si cambias el título del artículo, puedes eliminar el Alias y se generará uno nuevo. Si el Alias ha sido utilizado para referirse al artículo en enlaces internos y externos, esto romperá los enlaces. Por lo tanto, es mejor no cambiar el Alias de un artículo antiguo.

### La pestaña de Contenido - Texto del Artículo

La captura de pantalla anterior muestra el texto del artículo en un editor WYSIWYG que se parece bastante a un procesador de texto. Sin embargo, debes tener en cuenta que el texto del artículo se almacena como HTML y el campo de entrada de datos es realmente un área de texto que contiene ese HTML. Puedes verlo por ti mismo seleccionando el botón de *Alternar Editor* debajo del área de edición. El Editor es, de hecho, una aplicación de JavaScript que vuelve a mostrar el HTML para facilitar su lectura y manipulación.

#### Etiquetas y Atributos HTML No Permitidos

Tanto Joomla como el editor TinyMCE tienen configuraciones que no permiten determinadas etiquetas y atributos HTML. Por ejemplo, la lista prohibida por defecto de Joomla incluye *iframe*, por lo que si intentas incluir esa etiqueta en un artículo, se eliminará silenciosamente al guardar. Los filtros de texto se establecen en *Configuración Global*. El complemento TinyMCE tiene una opción para *Usar Filtro de Texto de Joomla*. Si está configurado en *Off*, lista *script, applet, iframe* como *Elementos Prohibidos*.

#### Barras de Herramientas del Editor

Encima del área de texto hay filas de barras de herramientas. Hay dos que se muestran por defecto. Las otras se pueden alternar seleccionando el símbolo de puntos suspensivos (...) al final de la segunda barra de herramientas. Las barras de herramientas se pueden configurar para mostrar diferentes barras y contenidos de barra a diferentes grupos de usuarios.

Hay demasiadas herramientas para describir cada una aquí. Eso crearía una aguja en un pajar para que busques. ¡Simplemente explora!

Sin embargo, hay algunas funciones que merecen una explicación adicional.

#### Contenido del CMS

Este botón revela una lista desplegable que permite la inclusión de elementos en un artículo obtenidos de otro lugar en el CMS.

- **Artículo** Este enlace revela una lista emergente de artículos. Selecciona un artículo para incluir un enlace a ese artículo en el artículo actual.
- **Contacto** Incluye un enlace a un Contacto en el artículo actual.
- **Campo** Incluye un campo en el artículo. Se muestra como `{field 1}`.
- **Media** Incluye una imagen o archivo desde un componente emergente de Media.
- **Menú** Incluye un enlace a un elemento de Menú desde una lista emergente de Menú.
- **Salto de Página** Hay un aviso para un *Título de Página* y Alias de *Tabla de Contenidos*. Esta función se utiliza para dividir documentos largos en varias páginas.
- **Leer más** Se inserta un separador de *Leer más...* en la posición del cursor. Elige un punto de ruptura entre párrafos antes de la selección.

#### Enlaces externos

El elemento **Insertar** en la primera barra de herramientas tiene opciones para insertar un *Enlace...*, *Imagen...* o *Media...*. Estos son para elementos externos, así que ten lista la URL del elemento que se va a utilizar.

### La pestaña de Contenido - Configuración

La pestaña **Contenido** está mayormente ocupada por el editor TinyMCE.

Junto al contenido, hay campos para gestionar la publicación, cómo y dónde se mostrará el artículo y quién puede verlo una vez publicado. En la mayoría de los casos, estas configuraciones pueden dejarse en sus valores por defecto.

1.  **Estado** *Publicado*, *No Publicado*, *Archivado* o *Basura* - el valor por defecto es *Publicado*.
2.  **Categoría** Este es un campo *Requerido*, pero por defecto estará en *Sin Categorizar*. Puedes seleccionar una categoría de la lista o escribir algunos caracteres de un nombre de categoría para acortar la lista de categorías para elegir.
3.  **Destacado** Alternar entre *No* y *Sí* para mostrar el artículo en la página principal si esta usa un diseño de *Artículos Destacados*.
4.  **Acceso** El nivel de acceso se puede cambiar para restringir el artículo a Grupos de Usuarios asignados a niveles de *Acceso* específicos: *Público*, *Invitado*, *Registrado*, *Especial* o *Super Usuarios*.
5.  **Etiquetas** Comienza a escribir para encontrar y seleccionar etiquetas predefinidas, o puedes agregar una nueva escribiéndola y **presionando enter**.
6.  **Nota** Cualquier comentario sobre este artículo que será visible bajo el Título en la página de lista de Artículos.
7.  **Nota de Versión** Agregar comentarios para indicar qué cambió en esta versión. Esto se muestra en el cuadro de diálogo modal *Versiones* y el campo vuelve a vaciarse después de guardar.

### Otras Pestañas

**Puede que no veas todas las siguientes pestañas** ya que un Administrador del Sitio puede ocultar algunas para ayudar a mantener la consistencia del diseño del artículo en todo el sitio web. También puedes ver pestañas adicionales para *Campos Personalizados* si han sido configurados.

1.  **Imágenes y Enlaces** te permite configurar una imagen introductoria y destacada y/o enlaces para aparecer en posiciones predefinidas. Esto puede usarse si tu artículo se mostrará dentro de un blog de categoría.
2.  **Opciones** te permite especificar el diseño del artículo y la información asociada como título, categoría, etiquetas, detalles de publicación, etc. Esto normalmente se configura de forma global, pero puede ser específico del artículo a través de estas opciones.
3.  **Esquema** es un método para agregar metadatos a un artículo. Es usado por robots pero no es visto por humanos.
4.  **Publicación** te permite establecer fechas y horas de publicación para programar la publicación de un artículo. Por defecto, cuando un artículo se guarda, se publicará de inmediato. También puedes establecer los Metadatos para el artículo.
5.  **Configurar Pantalla de Edición** te permite mostrar u ocultar parámetros para el artículo.
6.  **Permisos** muestra los permisos para cada grupo de usuarios que controlan lo que se puede o no hacer.

Hay artículos separados para cada una de estas pestañas.

## Guardar el Artículo

Una vez que hayas agregado la información y el contenido requerido, puedes guardar el artículo. Hay varias maneras de hacerlo dependiendo de lo que desees hacer a continuación en Joomla.

Para guardar el artículo, puedes elegir entre *Guardar* o *Guardar y Cerrar*. Este último tiene opciones desplegables como *Guardar y Nuevo*, *Guardar en Menú* y *Guardar como Copia*.

- **Guardar** Guarda el artículo y lo mantiene abierto para más ediciones. 
  Es buena práctica guardar regularmente tu trabajo en artículos más largos.
- **Guardar y Cerrar** Guarda el artículo y ve a la lista de Artículos. El botón Guardar y Cerrar tiene más opciones desplegables:
    - **Guardar y Nuevo** Guarda el artículo y luego abre una página de **Artículos: Nuevo**. 
      Esta opción ahorra tiempo al agregar múltiples artículos.
    - **Guardar en Menú** Guarda el artículo y abre una página de **Menús: Nuevo Ítem**.
    - **Guardar como Copia** Guarda el artículo y luego abre una página de **Artículos: Editar** 
      con un número entre paréntesis añadido al título y el mismo número 
      seguido de un guion, -2 por ejemplo, en el campo alias. Puedes cambiar 
      el título y cambiar o eliminar el alias del nuevo artículo que ya ha 
      sido creado.

Un mensaje del sistema indicará que el artículo se ha guardado con éxito.

### Errores al intentar guardar:

- Si no has completado los campos requeridos, aparecerá un mensaje de error rojo 
  indicando la información faltante que debes agregar.
- Verás un mensaje de error si el artículo tiene un alias que ya existe. Puedes solucionar esto modificando el campo alias.

## Consejos

- Si no eres el Super Usuario o Administrador, tómate el tiempo para
  entender cómo está configurado el sitio web. Que hayas guardado un
  artículo no significa que sea visible en el sitio web. Si se están utilizando páginas de Categoría Blog, asignar la categoría correcta mostrará el artículo. De lo contrario, un artículo necesita ser asignado a un elemento de menú. Puedes hacer esto en el artículo o a través del menú **Menús** del Administrador.
- Trata de mantener los títulos de los artículos cortos y específicos.
- Aunque se puede hacer, si hay varios usuarios añadiendo artículos al
  sitio web, evita crear nuevas categorías y etiquetas en los artículos.
  Los errores ortográficos y las diferencias pueden fácilmente impedir que los artículos se muestren donde se pretendía. Crear categorías y etiquetas en su página de lista respectiva asegura la consistencia en todo el sitio web.
- Si hay una necesidad, usa las notas de los artículos. Pueden ser muy
  útiles, especialmente cuando varias personas añaden artículos.
- Dondequiera que estés en Joomla, puedes añadir un artículo sin ir al
  Panel de Control principal; utiliza el Menú de Administrador de Joomla.

