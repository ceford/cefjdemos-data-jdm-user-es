<!-- Filename: J4.x:Logging_in_to_Joomla / Display title: Iniciar Sesión en Joomla -->

<span id="main-portal-heading">**Tutorial**  
Iniciar y cerrar sesión en Joomla!</span> Joomla!  4.0

## Introducción

Una de las mejores cosas de Joomla! es que ofrece la flexibilidad de
realizar tareas a través del Panel de Administración (a menudo
denominado backend) y, si está habilitado, para llevar a cabo tareas
directamente desde la parte frontal (denominado frontend) del sitio web.

El acceso frontend es una forma fácil y eficiente de permitir que los
editores de contenido agreguen o editen artículos rápidamente, sin la
necesidad de acceder al Panel de Administración.

Su inicio de sesión en Joomla está configurado para controlar lo que
puede o no ver y hacer, utilizando el Gestor de Usuarios de Joomla y los
potentes niveles de control de acceso (ACL). Esto significa que un sitio
web Joomla puede tener usuarios que solo puedan usar el backend, algunos
que solo estén habilitados para el frontend, y otros que pueden utilicen
ambos.

A continuación se explica cómo iniciar y cerrar sesión, tanto desde el
backend, como desde el frontend, de su sitio web Joomla.

**Nota:** Su Administrador Joomla puede haber deshabilitado su acceso
desde el frontend, requiriendo que todas las tareas se lleven a cabo
usando el Panel de Administración del backend.

Los pasos establecidos en este tutorial se basan en una instalación
estándar de Joomla!

## Iniciar y cerrar sesión en el backend del Panel Administración

### Iniciar sesión

Navegue a la página de inicio de sesión de administración. Esta es la
dirección web de su sitio web añadiendo /administrator, por ejemplo,
mi-sitio-joomla.com/administrator.

Esto le llevará al inicio de sesión de la administración de Joomla:

<img
src="https://docs.joomla.org/images/thumb/0/07/J4x_administrator_login_es.png/800px-J4x_administrator_login_es.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/thumb/0/07/J4x_administrator_login_es.png/1200px-J4x_administrator_login_es.png 1.5x, https://docs.joomla.org/images/thumb/0/07/J4x_administrator_login_es.png/1600px-J4x_administrator_login_es.png 2x"
data-file-width="1670" data-file-height="944" width="800" height="452"
alt="J4x administrator login es.png" />

1.  Introduzca su **Usuario**.
2.  Introduzca su **Contraseña**.

Haga clic en el botón **Conectar** y será llevado al Panel de Inicio de
Joomla!.

**Nota:**

1.  Joomla le brinda la opción de configurar y usar la autenticación
    web - esto no está dentro del alcance de este tutorial.
2.  Si el sitio web tiene otros idiomas instalados, podrá seleccionar el
    idioma correspondiente de una lista desplegable antes de iniciar
    sesión.

### Cerrar Sesión

Para cerrar la sesión, haga clic en el **Menú de usuario** y luego en
**Desconectar**.

<img
src="https://docs.joomla.org/images/thumb/0/03/J4x_administrator_logout_es.png/800px-J4x_administrator_logout_es.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/thumb/0/03/J4x_administrator_logout_es.png/1200px-J4x_administrator_logout_es.png 1.5x, https://docs.joomla.org/images/thumb/0/03/J4x_administrator_logout_es.png/1600px-J4x_administrator_logout_es.png 2x"
data-file-width="3308" data-file-height="582" width="800" height="141"
alt="J4x administrator logout es.png" />

## Iniciar y cerrar sesión desde el frontend del sitio web

### Iniciar Sesión

Si el acceso desde el frontend está habilitado, se habrá agregado un
formulario de inicio de sesión al sitio web. Joomla permite varias
formas de hacer esto. Una instalación estándar incluye un formulario de
inicio de sesión en la barra lateral del sitio web, pero es posible que
se haya agregado un enlace al menú del sitio web, o quizás en el pie de
página. En algunos casos, puede existir un enlace "Crear página". El
diseño del sitio web dictará dónde acceder al formulario de inicio de
sesión.

En este ejemplo, utilizamos un formulario de inicio de sesión en el
sitio web que se encuentra en la barra lateral.

<img
src="https://docs.joomla.org/images/thumb/2/27/J4x_front_end_login_es.png/800px-J4x_front_end_login_es.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/thumb/2/27/J4x_front_end_login_es.png/1200px-J4x_front_end_login_es.png 1.5x, https://docs.joomla.org/images/thumb/2/27/J4x_front_end_login_es.png/1600px-J4x_front_end_login_es.png 2x"
data-file-width="3036" data-file-height="1362" width="800" height="359"
alt="J4x front end login es.png" />

  
En el **Formulario Acceso**:

1.  Introduzca su **Usuario**.
2.  Introduzca su **Contraseña**.

Haga clic en el botón **Identificarse**.

Al iniciar sesión desde el frontend del sitio web, se le mantendrá en la
misma página en la que inició sesión. Notará que el formulario de inicio
de sesión también será reemplazado por un botón **Cerrar sesión**.

### Cerrar Sesión

<img
src="https://docs.joomla.org/images/thumb/6/6e/J4x_front_end_logout_es.png/800px-J4x_front_end_logout_es.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/thumb/6/6e/J4x_front_end_logout_es.png/1200px-J4x_front_end_logout_es.png 1.5x, https://docs.joomla.org/images/thumb/6/6e/J4x_front_end_logout_es.png/1600px-J4x_front_end_logout_es.png 2x"
data-file-width="3022" data-file-height="904" width="800" height="239"
alt="J4x front end logout es.png" />

Para cerrar sesión, vaya a la posición en la que inició sesión y luego
haga clic en el botón **Desconectar**.

## Consejos Rápidos

- Algunos administradores de sitios web de Joomla instalan extensiones
  que ocultan o restringen el acceso al panel del administrador del
  backend. Es posible que deba realizar pasos adicionales o visitar una
  URL de inicio de sesión alternativa.
- Si está realizando ediciones utilizando el inicio de sesión del
  frontend, ahorre tiempo iniciando sesión en la página que desea
  editar.
