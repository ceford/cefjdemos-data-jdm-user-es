<!-- Filename: J4.x:Guest_Access / Display title: Acceso de Invitados  -->

## Niveles de Acceso

Los visitantes del sitio pueden ver elementos como artículos, módulos y elementos de menú porque esos elementos están asignados al nivel de acceso Público de manera predeterminada. Este nivel de acceso también permite a los usuarios registrados ver los mismos elementos de contenido. Sin embargo, hay ocasiones en las que no es apropiado que un usuario registrado vea un elemento de contenido. Por ejemplo, un elemento de menú de Inicio de sesión debería ser visto por usuarios que no han iniciado sesión, pero no por usuarios que sí han iniciado sesión. Para eso está el nivel de acceso Invitado. Los usuarios registrados deberían ver un elemento de menú de Cerrar sesión en su lugar. Tales elementos deben asignarse al nivel de acceso Registrado.

En algunos casos, también es apropiado restringir el acceso a un artículo o a un módulo a usuarios que no han iniciado sesión o que están registrados.

## Acceso de Invitado

El uso del nivel de acceso de Invitado puede ilustrarse con un elemento de menú de inicio de sesión:

- Seleccione **Menús → Menú Principal → +** desde el menú del Administrador.
  Use el menú que prefiera para los nuevos elementos.
- En el formulario **Menús: Nuevo Elemento**, ingrese un título adecuado en el
  campo **Título**, por ejemplo **Iniciar Sesión**.
- En el campo **Tipo de Elemento de Menú**, use el botón **Seleccionar** para abrir el
  cuadro de diálogo emergente de Tipo de Elemento de Menú.
- En la lista **Tipo de Elemento de Menú**, seleccione la sección Usuarios y elija el
  elemento **Formulario de Inicio de Sesión**.
- De vuelta en el formulario **Menús: Nuevo Elemento**, configure el campo **Acceso** a
  **Invitado**.
- Guardar
- Opcionalmente, seleccione la lista de Orden y elija el elemento **después**
  del cual le gustaría que apareciera el elemento de Iniciar Sesión.

![formulario de menú de inicio de sesión restringido al acceso de invitado](../../../en/images/users/guest-access-menu-login.png)

- Guardar y Cerrar.
- Vea el sitio. Verifique que el elemento del menú de inicio de sesión funcione. Verifique
  que desaparezca después de iniciar sesión.

## Acceso Registrado

El uso del nivel de acceso Registrado se puede ilustrar con un elemento de menú de cierre de sesión:

- Selecciona **Menús → Menú Principal → +** desde el menú del Administrador. 
  Utiliza el menú que prefieras para los nuevos elementos.
- En el formulario **Menús: Nuevo Elemento**, ingresa un título adecuado en el campo **Título**, por ejemplo, **Cerrar sesión**.
- En el campo **Tipo de Elemento de Menú** usa el botón **Seleccionar** para abrir el cuadro de diálogo emergente Tipo de Elemento de Menú.
- En la lista **Tipo de Elemento de Menú** selecciona la sección Usuarios y selecciona el elemento **Cerrar sesión**.
- De vuelta en el formulario **Menús: Nuevo Elemento**, ajusta el campo **Acceso** a **Registrado**.
- Guardar.
- Opcionalmente, selecciona el desplegable de Orden y elige el elemento **después** del cual te gustaría que aparezca el elemento de Iniciar sesión.

![formulario de menú de cierre de sesión restringido a acceso registrado](../../../en/images/users/guest-access-menu-logout.png)

- Guardar y Cerrar.
- Ve al sitio. Verifica que el elemento de menú de cierre de sesión funciona. Asegúrate de que desaparece después de cerrar sesión.

