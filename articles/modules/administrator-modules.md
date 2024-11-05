<!-- Filename: J4.x:Administrator_Modules / Display title: Módulos de Administrador  -->

## Introducción

La plantilla del Administrador de Atum se proporciona con un conjunto completo de módulos de Administrador instalados y configurados para el uso diario. La siguiente ilustración muestra las posiciones del Panel de Control Inicio para indicar dónde se encuentran los módulos.

![posiciones del panel de control inicio de atum](../../../en/images/modules/atum-template-positions.png)

En la ilustración anterior, los paneles son instancias del módulo de Icono Rápido vinculados a plugins quickicon.

### Notas sobre algunas posiciones de Módulo

- **Custom Top** está por encima del banner y es útil si deseas publicar un menú personalizado o un módulo personalizado que contenga un mensaje importante. Por ejemplo, para advertir a los Administradores que el sitio cerrará pronto para mantenimiento del sistema.
- **Status** es para los iconos que se muestran alineados a la derecha en el Banner.
- **Menu** está en la barra lateral izquierda de la pantalla de Atum.
- **Toolbar** está por encima del área de contenido principal en las pantallas de lista y edición, pero no está presente en las pantallas del panel de control.
- **Top** está debajo de la Toolbar, pero por encima de cualquier Mensaje del Sistema y contenido de componente.
- **Bottom** está debajo del contenido del componente.
- **Debug** está abajo de todo.

Posiciones de la plantilla Atum por nombre

```xml
  <positions>
    <!-- utilizado directamente en la plantilla -->
    <position>bottom</position>
    <position>cpanel</position>
    <position>customtop</position>
    <position>debug</position>
    <position>icon</position>
    <position>login</position>
    <position>menu</position>
    <position>sidebar</position>
    <position>status</position>
    <position>title</position>
    <position>toolbar</position>
    <position>top</position>
  </positions>
```

## Añadir un Módulo Personalizado

Es posible que desees agregar un módulo personalizado para advertir a los administradores sobre algún problema del sistema. Selecciona **Contenido → Módulos de Administrador** desde el menú del Administrador. La lista de módulos instalados es bastante larga:

![Lista de módulos de administrador de atum](../../../en/images/modules/atum-admin-modules-list.png)

Selecciona el botón Nuevo y luego el módulo Personalizado. En el formulario de edición de Módulos: Personalizado, ingresa un Título, un mensaje Personalizado y selecciona una Posición para el módulo. En el siguiente ejemplo, se ha seleccionado la posición Superior. Además, en la pestaña Avanzado, en el campo Clase del Módulo se han ingresado algunos estilos para centrar el texto y proporcionar algo de relleno: **alert alert-warning text-center**. Guarda para ver el resultado. Cierra para ver el resultado en la página de la lista de Módulos.

![mensaje del sistema del módulo personalizado de atum](../../../en/images/modules/atum-admin-module-system-message.png)

Cuando hayas terminado con el mensaje, simplemente puedes seleccionar el botón de Estado en la lista de módulos para Despublicar el módulo.  

## Lista de Módulos del Administrador

- **Registros de acciones - Últimos** Este módulo muestra una lista de las acciones más recientes.
- **Menú del Panel de Control del Administrador** Este módulo muestra un submenú del administrador.
- **Menú del Administrador** Este módulo muestra un módulo de menú de administrador.
- **Artículos - Últimos** Este módulo muestra una lista de los artículos creados más recientemente.
- **Personalizado** Este módulo te permite crear tu propio módulo usando un editor WYSIWYG.
- **Visualización de Feed** Este módulo permite la visualización de un feed sindicado.
- **Enlace al Frontend** Este módulo muestra un enlace al frontend y está destinado a mostrarse en la posición 'estado'.
- **Información de la Versión de Joomla!** Este módulo muestra la versión de Joomla! y está destinado a mostrarse en la posición 'estado'.
- **Usuarios Conectados** Este módulo muestra una lista de los usuarios conectados.
- **Formulario de Inicio de Sesión** Este módulo muestra un formulario de inicio de sesión con nombre de usuario y contraseña. No debe despublicarse.
- **Información de Soporte de Inicio de Sesión** Este módulo muestra algunos enlaces útiles a sitios de soporte de Joomla en la pantalla de inicio de sesión.
- **Mensajes** Este módulo muestra el conteo de mensajes privados y está destinado a mostrarse en la posición 'estado'. Solo se muestra cuando hay mensajes para leer.
- **Estado Multilingüe** Este módulo muestra el estado de los parámetros multilingües y está destinado a mostrarse en la posición 'estado'.
- **Artículos Populares** Este módulo muestra una lista de los artículos publicados más populares que siguen vigentes. Algunos que se muestran pueden haber expirado aunque sean los más recientes.
- **Mensajes Post-Instalación** Este módulo muestra un contador y un enlace a los últimos mensajes post-instalación. Solo se muestra cuando hay mensajes para leer.
- **Panel de Privacidad** El Módulo de Panel de Privacidad muestra información sobre solicitudes de privacidad.
- **Verificación de Estado de Privacidad** El Módulo de Verificación de Estado de Privacidad muestra información sobre el estado de privacidad de tu sitio.
- **Iconos Rápidos** Este módulo muestra Iconos Rápidos que son visibles en el Tablero de Inicio (página principal del área de administrador).
- **Datos de Muestra** Este módulo te permite instalar datos de muestra.
- **Estadísticas** El Módulo de Estadísticas muestra información sobre la instalación de tu servidor junto con estadísticas sobre los usuarios del sitio web y la cantidad de artículos en tu base de datos.
- **Título** Este módulo muestra el Título del Componente de la Barra de Herramientas.
- **Barra de Herramientas** Este módulo muestra los iconos de la barra de herramientas utilizados para controlar acciones en toda el área de administrador.
- **Menú de Usuario** Este módulo muestra el Menú de Usuario y está destinado a mostrarse en la posición 'estado'.

*Traducido por openai.com*

