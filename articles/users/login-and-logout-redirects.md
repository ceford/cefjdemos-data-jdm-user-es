<!-- Filename: J4.x:Login_and_Logout_Redirects / Display title: Redirecciones de Inicio y Cierre de Sesión -->

## Predeterminados

El inicio y cierre de sesión tienen opciones para seleccionar una página a la que redirigir al tener éxito. Hay valores predeterminados, pero pueden no ser adecuados para tu sitio. Por ejemplo, el formulario de inicio de sesión conduce a la página de perfil de usuario por defecto. Eso se vuelve tedioso si no hay una buena razón para ver la página de perfil en cada inicio de sesión.

Este artículo cubre las opciones de redirección disponibles después de un inicio de sesión o cierre de sesión exitoso.

## Módulo de Inicio de Sesión

El comportamiento predeterminado de un módulo de inicio de sesión es permanecer en la misma página después de iniciar y cerrar sesión. El único inconveniente de este comportamiento es que un usuario que cierra sesión desde una página restringida será solicitado para iniciar sesión nuevamente. Si esto resulta problemático, una solución sencilla es seleccionar la página de inicio a la que redirigir en el campo Configuraciones del Módulo de Redirección tras Cerrar Sesión.

![formulario de menú de cierre de sesión restringido al acceso registrado](../../../en/images/users/login-redirects-login-form.png)

Consejo: Podrías usar dos módulos de inicio de sesión. Uno con acceso **Invitado** titulado **Iniciar Sesión**. El segundo con acceso **Registrado** titulado **Cerrar Sesión**.

## Elemento de Menú de Inicio de Sesión

El tipo de elemento de menú de inicio de sesión puede utilizarse para iniciar y cerrar sesión. Si se utiliza para ambos propósitos, debería tener un título como Iniciar/Cerrar Sesión. Si te parece poco elegante, puedes usar elementos de menú separados para Iniciar Sesión y Cerrar Sesión.

El tipo de elemento de menú de Inicio de Sesión permite elegir el Tipo de Redirección de Inicio de Sesión: por Elemento de Menú o por URL Interna. Por defecto, se selecciona Elemento de Menú, pero no se configura y el inicio de sesión lleva a la página de Perfil de Usuario. Puedes seleccionar un elemento de menú o proporcionar la URL de una página. Por ejemplo, podrías tener una página de Estado del Sistema con un mensaje elaborado del día.

![formulario del menú de cerrar sesión restringido a acceso registrado](../../../en/images/users/login-redirects-login-menu-options.png)

El comportamiento predeterminado al Cerrar Sesión es redirigir a la página de inicio del sitio. Podrías redirigir a algo diferente, como un mensaje de Despedida enlazado por un elemento de menú o una URL interna.  

## Elemento del Menú de Cierre de Sesión

El elemento del menú de cierre de sesión es sencillo. El valor predeterminado es permanecer en la misma página después del cierre de sesión. Si eso resulta inconveniente, selecciona la página de inicio del sitio.

![formulario del menú de cierre de sesión restringido a acceso registrado](../../../en/images/users/login-redirects-logout-menu-options.png)

*Traducido por openai.com*  

