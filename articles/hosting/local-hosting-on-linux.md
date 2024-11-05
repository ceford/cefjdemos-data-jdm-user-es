<!-- Filename: No_original_yet / Display title: Alojamiento Local en Linux -->

Este artículo cubre el alojamiento de Joomla en una computadora personal con Linux para propósitos de prueba y desarrollo. Las versiones de Linux cubiertas pertenecen a la familia Debian-Ubuntu, y específicamente a Linux Mint. Otras distribuciones son similares pero tienen diferente sintaxis de comandos y ubicaciones de archivos.

Necesitas instalar un conjunto de paquetes de software conocido comúnmente como pila LAMP. Las letras se refieren a Linux, Apache, MySQL y PHP. Puedes instalar el software usando la Interfaz Gráfica de Usuario (GUI) o la línea de comandos en una ventana del Terminal. Son diferentes maneras de utilizar el Gestor de Paquetes Synaptic.
## Instalar Apache con la interfaz gráfica

Desde el Menú del sistema, marcado con el logotipo de LM, selecciona Administración / Gestor de paquetes Synaptic. Se te pedirá tu contraseña. Ingresa tu contraseña de inicio de sesión para abrir la interfaz gráfica. En la parte superior derecha hay un botón de `Buscar`. Selecciónalo, introduce **apache** y selecciona `Buscar`. Marca la casilla de `apache2` y en la etiqueta emergente selecciona `Marcar para instalar`. Otro cuadro emergente mostrará una lista de paquetes adicionales necesarios para soportar apache. Selecciona `Marcar`:

![gestor de paquetes synaptic](../../../en/images/hosting/synaptic-package-manager-gui.png "Interfaz gráfica del Gestor de paquetes Synaptic")

Selecciona el botón `Aplicar` en la barra de herramientas superior y el botón `Aplicar` en el diálogo de Resumen. Apache será instalado y configurado, y el proceso terminará con un **diálogo de Cambios Aplicados**. Selecciona `Cerrar`.

Puedes confirmar que Apache está instalado y funcionando abriendo tu navegador, Firefox por defecto en una nueva instalación de Linux Mint, e ingresando **localhost** en la barra de direcciones. Deberías ver la Página predeterminada de Ubuntu Apache2:

![página predeterminada de apache](../../../en/images/hosting/apache-default-page.png "Página predeterminada de Apache")

La página contiene información útil sobre las ubicaciones de archivos que puede no estar tan fácilmente disponible más adelante, por lo que podrías querer imprimir esta página en papel o en un archivo pdf.

## Instalar PHP con la CLI

Probablemente sea mejor instalar PHP usando la línea de comandos. Una razón para esto es que, en el momento de escribir, el Gestor de Paquetes Synaptic solo ofrece PHP8.1, aunque PHP8.2 ha estado disponible por algún tiempo y puede instalarse desde un repositorio de terceros. Hay una buena descripción del procedimiento en este tutorial con secciones de Inicio rápido y Detallado. 

Primero cierra la interfaz gráfica del Gestor de Paquetes Synaptic y luego abre una ventana de Terminal e ingresa los siguientes comandos uno por uno:

```bash
sudo add-apt-repository ppa:ondrej/php
sudo apt update
sudo apt install php8.2 php8.2-cli php8.2-{bz2,curl,mbstring,intl}
sudo apt install php8.2-fpm
sudo a2enconf php8.2-fpm
sudo systemctl reload apache2
```
En tu navegador, verifica que la página predeterminada de localhost siga funcionando.

## Instalar MySQL o MariaDB

Puedes buscar en la web información sobre cada uno de estos paquetes de bases de datos. MySQL es la elección tradicional, pero fue adquirido por Oracle y ahora es menos popular. MariaDB es un reemplazo de código abierto con características adicionales. Ambos funcionan con Joomla! 5, pero no es fácil cambiar de uno a otro. Las tablas deben ser exportadas e importadas. Joomla! 5 requiere versiones mínimas específicas que Linux Mint ofrece a través del Synaptic Package Manager.

Abre la interfaz gráfica de Synaptic Package Manager y busca mysql-server o mariadb-server. Selecciona la casilla de verificación del elemento que termina en -server. Selecciona `Marcar para instalar` y luego `Aplicar` en la barra de herramientas superior. Puedes abrir el panel de Detalles para ver qué está sucediendo durante la instalación. Selecciona `Cerrar` cuando hayas terminado.

Puedes probar si tu base de datos está funcionando introduciendo `mysql` en la línea de comandos. Esto es igual para tanto MySQL como MariaDB. Deberías ver un mensaje de error de `Access denied`, lo cual está bien ya que indica que tu instalación de la base de datos está funcionando realmente.
```

## Instalar phpMyAdmin

phpMyAdmin es una herramienta de gestión de bases de datos con interfaz gráfica que necesitarás para crear y administrar tus bases de datos. En la interfaz de Synaptic Package Manager busca **phpmyadmin**. Selecciona su casilla y `Marcar para instalación`. Después de la descarga, aparece un mensaje para seleccionar el `Servidor web a reconfigurar automáticamente`. Marca la casilla de `apache2` y luego el botón de `Siguiente`. En la siguiente pantalla de configuración, deja seleccionada la casilla `Configurar base de datos...` y selecciona `Siguiente`.

Selecciona una contraseña de aplicación para el usuario phpmyadmin. Prueba: en tu navegador ingresa localhost/phpmyadmin en la barra de URL. Deberías ver la pantalla de inicio de sesión de phpMyAdmin. Con el nombre de usuario phpmyadmin y la contraseña que ingresaste durante la instalación podrás iniciar sesión. ¡Pero no podrás crear ninguna base de datos! Para resolver el problema necesitas editar el archivo de configuración como root en la ventana del Terminal:

```bash
sudo nano /etc/phpmyadmin/config.inc.php
```
Encuentra las dos líneas que contienen // $cfg['Servers'][$i]['AllowNoPassword'] = TRUE; y elimina las barras diagonales iniciales para descomentarlas. ¡Ambas!

Luego inicia sesión en mysql desde la línea de comandos y crea un nuevo usuario y concede a ese usuario todos los privilegios:
```bash
sudo mysql
CREATE USER 'admin'@'localhost' IDENTIFIED BY '';
GRANT ALL PRIVILEGES ON *.* TO 'admin'@'localhost' WITH GRANT OPTION;
exit
```
Luego regresa a phpMyAdmin e intenta iniciar sesión con el nombre de usuario **admin** y sin contraseña. Deberías ver todas las bases de datos y poder crear nuevas bases de datos.

## Prioridad del Archivo Índice

La ubicación predeterminada para las páginas web en Ubuntu/Linux Mint es /var/www/html. Si listamos el contenido de ese directorio, veremos que contiene un archivo index.html con el contenido de la página predeterminada de Apache2 en Ubuntu. Crea un archivo llamado index.php en ese directorio con el siguiente contenido:

```php
<?php echo phpinfo();
```
Recarga localhost. ¡No hay cambio! Ingresa **localhost/index.php** en la barra de URL y verás una página que contiene información de la versión de PHP. Este comportamiento está controlado por la configuración predeterminada de Apache, la cual se puede cambiar habilitando el módulo `dir` de Apache y editando su configuración:

```bash
sudo a2enmod dir
sudo nano /etc/apache2/mods-enabled/dir.conf
```

Mueve index.php al frente de la lista. Luego reinicia Apache:

```bash
sudo systemctl restart apache2
```

Esta vez, usando solo **localhost** en la barra de URL, deberías ver el contenido del archivo index.php, que es una página de información de PHP.

## Hosts Virtuales

En una instalación predeterminada de Linux, los archivos del sistema están en la carpeta raíz (/), y los archivos de datos de usuario están en la carpeta home (/home/miusuario). Esto puede ser un problema porque el usuario predeterminado de Apache, www-data, puede no tener los permisos apropiados para crear archivos en el espacio de archivos del usuario. La mejor solución es crear Hosts Virtuales.

Primero, se necesita un módulo que permita a Apache cambiar su usuario y grupo para adaptarse a cada usuario:

```bash
sudo apt-get install libapache2-mpm-itk
sudo a2enmod mpm_itk
```

A continuación, haz una copia del archivo de configuración del sitio predeterminado y edítalo:

```bash
cd /etc/apache2/sites-available
sudo cp 000-default.conf nombreusuario.localhost.conf
sudo nano nombreusuario.localhost.conf
```

El archivo de configuración del sitio predeterminado contiene comentarios para explicar su contenido. No se incluyen en la ilustración a continuación. Descomenta la línea ServerName y cambia todas las instancias de `nombreusuario` por tu propio nombre de usuario.

```xml
<VirtualHost *:80>
        ServerName nombreusuario.localhost
        ServerAdmin webmaster@localhost
        DocumentRoot /home/nombreusuario/public_html
        <IfModule mpm_itk_module>
                AssignUserId nombreusuario nombreusuario
        </IfModule>
        <Directory /home/nombreusuario/public_html/ >
                Options Indexes FollowSymLinks
                AllowOverride None
                Require all granted
        </Directory>
        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

Activa el nuevo sitio y reinicia Apache:

```bash
sudo a2ensite nombreusuario.localhost
sudo systemctl reload apache
```

Haz una entrada en el archivo /etc/hosts para agregar una entrada para el nuevo host virtual. De lo contrario, tu navegador lo buscará en internet.

```bash
sudo nano /etc/hosts
```
Al finalizar, se verá algo como esto:

```bash
127.0.0.1       localhost
127.0.0.1       nombreusuario.localhost
127.0.1.1       nombrehost

# Las siguientes líneas son deseables para hosts compatibles con IPv6
::1     ip6-localhost ip6-loopback
fe00::0 ip6-localnet
ff00::0 ip6-mcastprefix
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters
```
**NombreHost:** Este es el nombre que diste a tu computadora cuando instalaste Linux. Lo necesitarás en breve. Puedes cambiarlo si lo deseas, pero es mejor informarse sobre eso y hacerlo primero.

Si todo va bien, con una URL del tipo nombreusuario.localhost verás un listado de directorio de tu directorio public_html. La exhibición pública de listados de directorios se considera una mala práctica, un riesgo de seguridad, y usualmente está deshabilitada por otra configuración de Apache. Sin embargo, para un sitio personal en una computadora personal utilizada para desarrollo y pruebas, es muy útil. Se pueden configurar muchos sitios diferentes en diferentes subdirectorios. Por ejemplo, sitios de Joomla 4 y Joomla 5, tablones de anuncios, wikis, y así sucesivamente. Cuando tienes muchos sitios de prueba, es difícil recordar todos los nombres de los subdirectorios.

## Acceso a la Red Doméstica

Si tienes otra computadora en tu red doméstica, probablemente querrás acceder a tu sitio Linux desde allí también. Para que eso funcione, necesitas otro host virtual. Copia y edita el que acabas de hacer:

```bash
cd /etc/apache2/sites-available
sudo cp username.localhost.conf username.conf
sudo nano username.conf
```
Cambia el ServerName de username.localhost a username.hostname y luego habilita el nuevo sitio virtual y reinicia Apache.

```bash
sudo a2ensite username
sudo apachectl restart
```
Ve a tu otra computadora en la red doméstica y edita su archivo de hosts personal. Por ejemplo, en una Mac edita /private/etc/hosts y añade la siguiente línea al final:

```bash
192.168.178.20 username.hostname www.username.hostname
```
Donde 192.168.178.20 es la dirección IP de tu computadora Linux.

Ahora, en tu segunda computadora deberías poder acceder al servidor web en tu computadora Linux ingresando username.hostname en la barra de URL de tu navegador.

## Notas de Partición

El software instalado mediante el Gestor de Paquetes Synaptic normalmente se encuentra en el directorio raíz de Linux (/). Los datos del usuario se ubican en el directorio de inicio (/home). En una instalación simple, estos directorios están en la misma partición de disco físico.

En una instalación más compleja, tal vez con la opción de iniciar diferentes sistemas operativos (Windows o Linux) o diferentes versiones del mismo sistema operativo, la raíz y los datos del usuario suelen estar en particiones separadas. Esto permite el acceso a los mismos datos del usuario desde cada sistema operativo.

Hay un inconveniente: un sitio Joomla ubicado en un directorio /home/username necesita datos de la base de datos que generalmente se encuentran en el directorio raíz, específicamente en /var/lib/mysql. Puedes mover el directorio de datos de MySQL/MariaDB a una ubicación accesible para ambos sistemas operativos, ya sea en la partición /home o en una partición separada. Este tutorial describe cómo cambiar el directorio de datos de MySQL en Ubuntu y Debian Linux. Esto necesita hacerse para cada sistema operativo, pero no se cubre aquí.

*Traducido por openai.com*

