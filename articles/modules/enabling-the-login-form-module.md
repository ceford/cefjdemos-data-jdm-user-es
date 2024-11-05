<!-- Filename: Enabling_the_Login_Form_module / Display title: Formulario de Inicio de Sesión  -->

## Métodos de Inicio de Sesión del Sitio

Hay dos formas de permitir que los usuarios registrados inicien sesión en el frontend de un sitio web. Hay un elemento de menú **Formulario de Inicio de Sesión** que se encuentra en el grupo de elementos de menú de Usuarios. Necesita que sus permisos de *Acceso* estén configurados en *Invitado*. Se necesita un segundo elemento de menú de *Cerrar Sesión* con sus permisos de *Acceso* configurados en *Registrado*.

La alternativa es el módulo **Formulario de Inicio de Sesión**. Está instalado por defecto en la posición *sidebar-right* en una nueva instalación de Joomla. Este módulo puede ser movido a otra posición, despublicado, enviado a la papelera y eliminado. Las últimas acciones se aplican a una instancia del módulo y no al código del módulo. Así que puedes crear un nuevo módulo de *Formulario de Inicio de Sesión* o hacer un duplicado, quizás para usar en diferentes plantillas. El módulo de Formulario de Inicio de Sesión cambia su visualización después del inicio de sesión para presentar un botón de *Cerrar Sesión*.

## El Módulo de Formulario de Inicio de Sesión

Para publicar un Formulario de Inicio de Sesión no publicado:

* Selecciona **Contenido → Módulos del Sitio** desde el menú de Administrador.
* Localiza el módulo **Formulario de Inicio de Sesión**.
* Si el icono de **Estado** es una marca verde dentro de un círculo, ya está habilitado. Si el icono de Estado es una cruz gris, está actualmente deshabilitado. Selecciona el icono para habilitar el módulo.
* Si el módulo *Formulario de Inicio de Sesión* no está presente en la lista, ajusta las Opciones de Filtro, en el campo *- Seleccionar Estado -* a *Todos* o *Papelera* para ver si ha sido movido a la papelera. Si es así, puede publicarse seleccionando su icono de papelera.
* Si falta el módulo del Formulario de Inicio de Sesión, crea uno nuevo.

Para crear un nuevo Formulario de Inicio de Sesión o un segundo Formulario de Inicio de Sesión:

* Selecciona **Contenido → Módulos del Sitio** desde el menú de Administrador.
* Selecciona el botón **Nuevo** desde la Barra de Herramientas.
* Desde la lista de Módulos, selecciona el elemento **Inicio de Sesión**.
* Rellena el formulario de entrada de datos *Módulos: Inicio de Sesión*.
  - Ingresa un Título único.
  - Selecciona una posición de plantilla o crea una posición con nombre para usar en un artículo.
  - Rellena otros campos según corresponda.
* **Guardar y Cerrar**
* Prueba que el módulo aparezca correctamente en el frontend del sitio.

## Para asignar el módulo de formulario de inicio de sesión a páginas web seleccionadas

Puede hacer que el módulo de formulario de inicio de sesión aparezca en una o más páginas asignándolo a elementos del menú seleccionados. Esto se realiza utilizando los campos en el grupo de Asignación de Menú en la pantalla de edición del módulo:

- Seleccione la pestaña **Asignación de Menú**.
- La lista **Asignación de Módulo** tiene cuatro opciones:
  - **En todas las páginas**: El módulo de formulario de inicio de sesión aparecerá en todas las páginas.
  - **En ninguna página**: El módulo de formulario de inicio de sesión no aparecerá en ninguna página.
  - **Solo en las páginas seleccionadas**: Aparecerá una lista de todos los menús y elementos del menú de su
    sitio. El módulo de formulario de inicio de sesión aparecerá en aquellas páginas seleccionadas
    en esta lista.
  - **En todas las páginas excepto en las seleccionadas**: El formulario de inicio de sesión aparecerá en todas
    las páginas no seleccionadas.
- **Selección de Menú**: Muestra una lista de todos los menús y elementos del menú de los que
  se pueden seleccionar uno o más. Este campo solo se usa si el
  campo **Menús** está configurado para **Seleccionar elemento(s) del menú de la lista**.

  ![asignación de menú de módulo](../../../en/images/modules/modules-login-menu-assignment.png)

## Para personalizar el módulo de formulario de inicio de sesión

Si deseas cambiar la apariencia del módulo de inicio de sesión, puedes agregar estilos, ya sean estilos de Bootstrap o tus propios estilos definidos en el archivo user.css de tu plantilla. Agrega los estilos en la pestaña **Avanzado** del formulario de edición del módulo de inicio de sesión.

Si deseas cambiar la información que se muestra en el formulario de inicio de sesión, puedes crear una anulación de plantilla. Consulta la sección sobre [Anulaciones de Plantilla](jdocmanual?article=user/templates/template-overrides) para más detalles.

*Traducido por openai.com*

