<!-- Filename: J4.x:Adding_a_New_Menu / Display title: Añadir un Nuevo Menú  -->

## Introducción

Para que el contenido sea accesible en su sitio web Joomla!, los elementos deben ser asignados a un Menú. Una instalación estándar de Joomla! crea un **Menú Principal** para usted. En muchos casos, solo usará un menú, pero puede tener más de uno. Esto le permite crear Menús para diferentes tipos de contenido, contenido oculto, contenido específico para roles de usuario y más.

Hay tres pasos en la creación de un menú utilizable:

1. Crear el Menú. Este es un contenedor para los Elementos del Menú.
2. Crear un Módulo de Menú. Esto permite colocar el Menú en una página.
3. Crear Elementos de Menú. Estos son los elementos seleccionables por el usuario que llevan a páginas específicas.

Esta captura de pantalla muestra los menús disponibles en un sitio multilingüe. En una instalación inicial de Joomla, hay un solo *Menú Principal*.

![Lista de menús](../../../en/images/menus/menus-manage.png)

La lista le permite seleccionar cualquiera de los botones verdes o rojos para ir directamente a la lista de elementos del menú en ese menú y estado.

Este tutorial cubre los pasos involucrados en la creación de un Menú en un sitio de Joomla!.  

## Crear un Nuevo Menú

Utilice cualquiera de los siguientes pasos para crear un nuevo menú:

- Desde el menú de Administrador, seleccione el *Icono del Panel de Menús* para ir al panel de Menús, luego seleccione **Gestionar**. O...
- Desde el menú de Administrador, expanda la sección de *Menús* y luego seleccione **Gestionar**.
- Seleccione el botón **+ Nuevo** en la barra de herramientas.
- En el formulario de entrada de datos del Menú, complete los siguientes campos:
  - **Título**: Un título adecuado para el menú. Esto se utiliza para identificar el menú en el Administrador de Menús.
  - **Nombre Único**: Este debe ser un nombre de identificación único utilizado por Joomla! para identificar este menú. No se permiten espacios, pero puede usar el carácter '-' como en recursos-menu.
  - **Descripción**: Aunque no es obligatorio, a menudo es útil en un sitio con muchos menús. Aparece debajo del *Título* en la lista de menús como se ilustra arriba.<br>
    ![Nuevo Menú](../../../en/images/menus/menus-new.png)
- **Guardar y Cerrar**

En la lista de Menús, el menú recién creado tiene un botón etiquetado **Agregar un módulo para este menú**, que es la siguiente etapa en la creación del menú. Podría comenzar a agregar elementos del menú y regresar para crear el módulo de menú más adelante.

## Crear un Módulo para el Menú

En la lista de Menús, la columna de *Módulos Vinculados* permite seleccionar cualquier módulo de menú existente para fines de edición. Puedes echar un vistazo y luego *Cerrar* sin hacer ningún cambio. Para tu nuevo menú, selecciona el botón **Agregar un módulo para este menú** para abrir un marco modal que contiene el formulario de ingreso de datos del módulo del Menú.

![Formulario de ingreso de datos del módulo del Menú](../../../en/images/menus/menus-module.png)

Campos a completar:

* El campo **Título** es obligatorio, así que crea un título descriptivo.
* El botón **Mostrar Título** a la derecha se utiliza para *Mostrar* u *Ocultar* el título del módulo, una característica común a todos los módulos.
* El campo **Seleccionar Menú** debe mostrar el nombre del Menú que acabas de crear.
* El campo **Posición** se utiliza para seleccionar una posición en tu plantilla donde deseas que aparezca tu menú.
* Selecciona **Guardar y Cerrar** una vez que la información esencial haya sido añadida.

Hay muchas opciones para elegir en el formulario de *Editar configuración del módulo*. Se mencionan en la pantalla de Ayuda disponible en el formulario de *Módulo: Editar*. Este es el mismo formulario, pero en una página normal en lugar de un marco modal. Accede a él a través del menú del Administrador, en la ruta Contenido / Módulos del Sitio para llegar a la lista de Módulos del Sitio.

Nota: el lograr que el Menú tenga el aspecto que deseas depende del estilo de tu plantilla.

## Añadir Elementos al Menú

Para crear los enlaces en tu menú necesitas añadir **Elementos del Menú**. Hay muchos *Tipos de Elementos del Menú* en Joomla y los componentes de terceros pueden añadir más tipos. Para este tutorial se añadirá un enlace a un artículo único.

Puedes crear un artículo por adelantado o puedes crearlo durante el proceso de creación del menú. De cualquier manera, el artículo debe existir antes de que se pueda crear un elemento del menú para él. En este ejemplo, el artículo también se llamará *Recursos*. Está destinado a contener una lista de enlaces a archivos PDF.

En la lista de **Menús**, desde la columna de **Elementos del Menú** selecciona el ícono para el menú recién creado, *Recursos* en este ejemplo. Inicialmente, no hay elementos de menú, por lo que la lista simplemente dice *No Matching Results*.

- Selecciona el botón **Nuevo** de la Barra de herramientas para crear un nuevo elemento del menú.
- En el campo **Título** añade el título que deseas que aparezca en el Menú.
- En el campo **Tipo de Elemento del Menú** selecciona el botón **Seleccionar** para abrir un cuadro de diálogo modal que contiene una lista de componentes. Cada uno tiene un menú desplegable que revela una lista de tipos de elementos del menú disponibles.
  - Selecciona **Artículos** y luego **Artículo Único**.
- En el campo **Seleccionar Artículo**: **O bien:**
  - Usa el botón **Seleccionar** para elegir un artículo existente. Se abrirá una lista de artículos de la cual elegir. **O bien:**
  - Usa el botón **Crear** para crear un nuevo artículo. Todo lo que necesitas ingresar es el título del artículo. Probablemente sea mejor dejar el contenido detallado para más tarde.
- Verifica que el campo **Menú** esté configurado en el nuevo Menú.
- El campo **Estado** debería estar configurado en **Publicado**.
- Selecciona **Guardar y Cerrar**.

![Formulario de entrada de datos del elemento del menú](../../../en/images/menus/menus-single-article.png)

Añade más Elementos del Menú al nuevo Menú según sea necesario.

Una vez que se hayan añadido los elementos al Menú, verifica que el Menú se muestre en el sitio web en la posición correcta.

![Visualización del menú](../../../en/images/menus/menus-display.png)

