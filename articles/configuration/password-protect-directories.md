<!-- Filename: How_do_you_password_protect_directories_using_htaccess%3F / Display title: Proteger Directorios con Contraseña -->

## Introducción

Puede que desee proteger un directorio o todo un sitio del acceso público. Una razón para esto es denegar el acceso público a un sitio en desarrollo. Solo aquellos que conozcan el nombre de usuario y la contraseña podrán obtener acceso. Otra razón es la paranoia, por ejemplo, la protección de la carpeta del administrador para que los usuarios tengan que ingresar un nombre de usuario y una contraseña solo para acceder al formulario de inicio de sesión del administrador de Joomla.

El método descrito aquí es para servidores Apache utilizando un archivo *.htaccess*.

### Advertencia de Apache.org

La autenticación básica no debe considerarse segura bajo ninguna definición rigurosa de seguridad. Aunque la contraseña se almacena en el servidor en formato cifrado, puede pasar del cliente al servidor en texto plano a través de la red. Cualquiera que escuche con cualquier variedad de analizador de paquetes podrá leer el nombre de usuario y la contraseña a medida que se transmiten.

El nombre de usuario y la contraseña se envían con cada solicitud, no solo cuando el usuario los ingresa por primera vez. Por lo tanto, el analizador de paquetes no necesita estar escuchando en un momento particularmente estratégico, sino solo el tiempo suficiente para ver alguna solicitud única a través del cable.

Además de eso, el contenido en sí también se transmite a través de la red de forma clara, por lo que si el sitio web contiene información sensible, el mismo analizador de paquetes tendría acceso a esa información, incluso si el nombre de usuario y la contraseña no se utilizaran para obtener acceso directo al sitio web.

No use la autenticación básica para nada que requiera seguridad real. Es un obstáculo para la mayoría de los usuarios, ya que muy pocas personas se tomarán la molestia o tendrán el software o equipo necesario para descubrir contraseñas. Sin embargo, si alguien quisiera entrar, le resultaría muy sencillo hacerlo.

La autenticación básica a través de una conexión SSL, sin embargo, será segura, ya que todo estará cifrado, incluido el nombre de usuario y la contraseña.

## Usando cPanel

Si estás utilizando un servicio de alojamiento, deberías usar su método para la protección de directorios. Por ejemplo, cPanel tiene una opción llamada Privacidad de Directorio. Al seleccionarla, puedes navegar a cualquier directorio y asignarle un nombre. Luego tendrás la oportunidad de crear un Nombre de Usuario y una Contraseña para el directorio nombrado. ¿Simple?

Si ahora miras en el directorio que protegiste, encontrarás un nuevo archivo .htaccess que contiene algo similar a la siguiente configuración para proteger la carpeta api de Joomla:

```
#----------------------------------------------------------------cp:ppd
# Sección gestionada por cPanel: Directorios Protegidos por Contraseña -cp:ppd
# - ¡No edites esta sección del archivo htaccess!                       -cp:ppd
#----------------------------------------------------------------cp:ppd
AuthType Basic
AuthName "API"
AuthUserFile "/home/username/.htpasswds/public_html/[jroot]/api/passwd"
Require valid-user
#----------------------------------------------------------------cp:ppd
# Fin de la sección gestionada por cPanel: Directorios Protegidos por Contraseña -cp:ppd
#----------------------------------------------------------------cp:ppd
```
Es importante tener en cuenta que la protección de directorios de cPanel puede usar el mismo archivo .htaccess que Joomla emplea para otros propósitos.

Si miras en el archivo passwd citado, verás el Nombre de Usuario que proporcionaste y la versión encriptada de la contraseña.

La protección se puede eliminar repitiendo el proceso y desmarcando la casilla `Proteger con contraseña este directorio.` Eso elimina la sección de autenticación del archivo .htaccess. ¡No elimina el archivo .htaccess!

## Reglas de .htaccess

Puedes realizar todos los pasos necesarios manualmente. Esta herramienta puede ayudarte:

<a href="https://www.htaccessredirect.net/" rel="nofollow noreferrer noopener"><em>Generador de .htaccess</em></a>

Crea los archivos necesarios para ti. Necesitas especificar el nombre de usuario, la contraseña y la ruta.

Completa las dos secciones: **Proteger Archivo con Contraseña** y **Generador de htpasswd** y luego selecciona el botón `Generar Código`. Obtendrás el texto para el archivo .htaccess y el texto para el archivo .htpasswd en cuadros separados. Ejemplos:
```
// Proteger archivo con contraseña
<Files /admin>
AuthName "Prompt"
AuthType Basic
AuthUserFile /home/user/.htpasswd
Require valid-user
</Files>
```

```
John:$apr1$a3dbt6j7$KJQr137CY9QuN6tYl6M4Z1
```

*Traducido por openai.com*

