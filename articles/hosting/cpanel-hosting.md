<!-- Filename: J4.x:Hosting_Setup / Display title: Alojamiento cPanel  -->

## Introducción

## Hosting cPanel

Al iniciar sesión en tu servicio de hosting cPanel, esto es lo que deberías esperar ver:

![panel de control de hosting cPanel](../../../en/images/hosting/cpanel-hosting.png)

### Configuración de la Base de Datos

El panel de Bases de Datos se utiliza para crear una base de datos y un usuario de base de datos para Joomla.

Selecciona la opción de Bases de Datos MySQL e introduce un nombre para la base de datos en el formulario. La primera parte del formulario está predefinida; el resto depende de ti. Debe ser corto y quizás no obvio - *jblog* por ejemplo.

En el mismo formulario, desplázate hacia abajo a la sección *Añadir Nuevo Usuario*. Introduce un nombre de usuario. Puede ser cualquier cosa que desees. Se usará en tu archivo de configuración de Joomla, así que no es algo que necesites recordar. Usa el generador de contraseñas para crear una contraseña no memorable y cópiala en un editor de texto; la necesitarás durante la instalación de Joomla.

En el mismo formulario, deslízate hasta *Añadir Usuario a la Base de Datos*. Selecciona el usuario que creaste y la base de datos que creaste de las listas desplegables y luego haz clic en el botón Añadir. Se abre un formulario para Administrar Privilegios. Marca la casilla de *Todos los Privilegios* y luego haz clic en el botón *Realizar Cambios*.

Eso es todo, ya tienes una base de datos lista para una instalación de Joomla.

### Subir el Código Fuente de Joomla

En algún momento habrás descargado el archivo zip del código fuente de Joomla en tu propio portátil o computadora de escritorio. Ahora tienes que decidir cómo estructurar tu sitio. La raíz de documentos para tu sitio es la carpeta *public_html*. Podrías colocar Joomla allí. Sin embargo, eso te impide usar otra aplicación en el mismo sitio. Por ejemplo, podrías tener dos instalaciones de Joomla completamente separadas, una para producción (visión pública) y otra para pruebas (visión privada). Así que podrías crear una carpeta dentro de *public_html*, llamada *j4* por ejemplo, y subir Joomla allí. Podrías tener otra carpeta llamada *j4pruebas* y poner otra copia de Joomla allí. La ilustración a continuación muestra tal configuración con dos sitios web Joomla.

![gestor de archivos de hosting cPanel](../../../en/images/hosting/cpanel-file-manager.png)

Cuando hayas decidido la estructura, selecciona la carpeta de Joomla elegida en el Administrador de Archivos y haz clic en el botón Subir. En el formulario de carga, selecciona el archivo zip del código fuente de Joomla en tu ordenador local para subirlo a la carpeta seleccionada. Después de subirlo, vuelve al Administrador de Archivos, selecciona el archivo *zip* y haz clic en el botón Extraer. Después de la extracción, puedes seleccionar y eliminar el archivo *zip*.

¡Eso es todo! Estás listo para instalar Joomla.

