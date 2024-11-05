<!-- Filename: J4.x:Logging_in_to_Joomla / Display title: Iniciar sesión en Joomla -->

## Introducción

Una de las grandes cosas de Joomla! es que ofrece la flexibilidad de realizar tareas a través del Panel de Administración (a menudo llamado backend) y, si está habilitado, realizar tareas directamente desde el frontend (la parte pública) del sitio web.

El acceso al frontend es una manera fácil y eficiente de permitir a los redactores de contenido agregar o editar artículos rápidamente sin la necesidad de ir al Panel de Administración.

El inicio de sesión en Joomla está configurado para controlar lo que los usuarios pueden ver y hacer (o no pueden) utilizando el componente de usuario de Joomla y los niveles de control de acceso (ACL) potentes. Esto significa que un sitio web Joomla puede tener usuarios que solo usan el backend, algunos que solo usan el frontend y otros que usan ambos.

Lo siguiente cubre cómo iniciar y cerrar sesión tanto en el backend como en el frontend de un sitio web Joomla.

**Nota:** Un Administrador de Joomla puede haber deshabilitado el acceso al frontend, requiriendo que todas las tareas se realicen utilizando el Panel de Administración del backend.

### Inicio de Sesión del Administrador

Navega a la página de inicio de sesión del Administrador. Esta es la dirección web del sitio, seguida de /administrator, por ejemplo, my-joomla-website.com/administrator que invoca la página de inicio de sesión del Administrador de Joomla:

![Formulario de inicio de sesión del administrador](../../../en/images/getting-started/logging-in-to-joomla-administrator-login-form.png)

1. Añade tu **Nombre de Usuario**
2. Añade tu **Contraseña**

Selecciona el botón **Iniciar sesión** para ser llevado al Panel de Control principal de Joomla!

**Nota:**

1. Joomla proporciona una opción para configurar y usar la Autenticación Web. Esto no está dentro del alcance de este tutorial.
2. Si un sitio web tiene varios idiomas instalados, podrás seleccionar un idioma para usar desde una lista desplegable antes de iniciar sesión.

### Cierre de Sesión del Administrador

Para cerrar sesión, selecciona el **Menú de Usuario** y luego **Cerrar sesión**.

![Enlace de cierre de sesión del administrador](../../../en/images/getting-started/logging-in-to-joomla-logout-link.png)

### Inicio de Sesión del Sitio

Si el acceso al frontend está habilitado, se habrá añadido un formulario de inicio de sesión al sitio web. Joomla permite varias formas de hacer esto. Una instalación estándar incluye un formulario de inicio de sesión en la barra lateral del sitio web, pero puedes encontrar un enlace añadido al menú del sitio web, o quizás en el pie de página. En algunos casos puede existir un enlace de *Crear Página*. El diseño del sitio web dictará dónde accedes al formulario de inicio de sesión.

Este ejemplo utiliza un formulario de inicio de sesión ubicado en la barra lateral derecha.

![Módulo de formulario de inicio de sesión del sitio](../../../en/images/getting-started/logging-in-to-joomla-site-login-form.png)

En el **Formulario de Inicio de Sesión**

1. Añade tu **Nombre de Usuario**
2. Añade tu **Contraseña**

Selecciona el botón **Iniciar sesión**.

Al iniciar sesión desde el frontend del sitio web, puedes permanecer en la misma página desde la que iniciaste sesión o puedes ser llevado a tu página de Perfil. Notarás que el formulario de inicio de sesión también contendrá un botón **Cerrar sesión**.

### Cierre de Sesión del Sitio

![Módulo de formulario de cierre de sesión del sitio](../../../en/images/getting-started/logging-in-to-joomla-site-logout-form.png)

Para cerrar sesión, ve al formulario de inicio de sesión y selecciona el botón **Cerrar sesión**.  

## Consejos

- Algunos administradores de sitios web de Joomla instalan extensiones que ocultan o restringen el acceso al Panel de Administración del backend. Es posible que tengas que tomar medidas adicionales o visitar una URL de inicio de sesión alternativa.
- Si estás realizando ediciones utilizando el inicio de sesión en el frontend, ahorra tiempo iniciando sesión en la página que deseas editar.

*Traducido por openai.com*  

