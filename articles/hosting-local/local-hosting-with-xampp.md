<!-- Filename: / Display title: Hospedaje Local con XAMPP -->

## Introducción

XAMPP es un paquete fácil de instalar que incluye el servidor web Apache, PHP, XDEBUG y la base de datos MySQL. Esto te permite crear el entorno necesario para ejecutar Joomla! en tu máquina local. La última versión de XAMPP está disponible en el sitio web de [Apache Friends](https://www.apachefriends.org/index.html). Las descargas están disponibles para Linux, Windows y Mac OS X. Descarga el paquete para tu plataforma.

*Nota importante sobre XAMPP y Skype:* Apache y Skype utilizan ambos el puerto 80 como alternativa para las conexiones entrantes. Si usas Skype, ve al panel Herramientas-Opciones-Avanzado-Conexión y deselecciona la opción *Usar 80 y 443 como alternativas para las conexiones entrantes*. Si Apache inicia como un servicio, tomará el puerto 80 antes de que Skype inicie y no verás un problema. Pero, para estar seguro, desactiva la opción en Skype.  

## Instalación

La instalación en cualquier plataforma es muy simple: utiliza el instalador. No hay un manual o guía real para XAMPP. La documentación está en forma de FAQs vinculadas desde la página de descargas.

### Instalación en Windows

Para Windows, se recomienda instalar XAMPP en "c:\xampp" (no en "c:\program files"). Si haces esto, tus carpetas de sitios web locales como Joomla! irán en la carpeta "c:\xampp\htdocs". (Por convención, todo el contenido web va bajo la carpeta "htdocs").

Si tienes múltiples servidores http (como IIS), puedes cambiar el puerto de escucha de xampp. En \apache\conf\httpd.conf, modifica la línea Listen 80 a Listen \[número de puerto\] (ej: "Listen 8080").

<div class="alert alert-info">
<h4>Tutorial de la Joomla Community Magazine<h4>
<p>Puedes encontrar un tutorial detallado sobre la instalación de XAMPP en Windows, junto con la Joomla 4 Beta, el Joomla Patch Tester y Git en este <a href="https://magazine.joomla.org/all-issues/june-2020/github-installing-git" rel="noreferrer noopener">artículo de la Joomla Community Magazine</a>.</p></div>

Para instalar XDebug: [Configuración de XAMPP - XDebug para PHP 8](https://odan.github.io/2020/12/03/xampp-xdebug-setup-php8.html)

### Instalación en Linux

#### Instalar XAMPP

La página de descargas descarga un instalador xampp-linux-x64-8.2.12-0-installer.run donde 8.2.12 es la última versión. Ejecuta el archivo instalador para instalar Apache2, MySQL y PHP.

Después de la instalación utiliza los siguientes comandos para iniciar y detener los servicios:
```sh
    sudo /opt/lampp/lampp start
    sudo /opt/lampp/lampp stop
```

#### Prueba tu servidor localhost XAMPP

Abre tu navegador y apunta a

    http://localhost

El index.php redirigirá a

    http://localhost/xampp

Ahí encontrarás instrucciones sobre cómo cambiar los nombres de usuario/contraseñas predeterminados. En una PC que no sirve archivos a Internet o LAN, cambiar los valores predeterminados es una decisión personal.

#### Obtener Joomla

* Descarga el último zip de instalación de Joomla
* Descomprímelo en tu disco duro
* Conéctate a localhost con un cliente FTP predeterminado
* Crea una carpeta para tu Joomla en el servidor localhost
* Sube por FTP los archivos de instalación descomprimidos de Joomla a la carpeta Joomla recién creada.

##### Importante:

- La instalación de xampp establece la propiedad correcta de los archivos y permisos.
- Usar el **comando CHOWN** **causará problemas de propiedad con xampp**.
- Usar **nautilus** para manipular carpetas/archivos en localhost **causará problemas de propiedad con xampp**.

#### Información de la base de datos

- Host: localhost
- Nombre predeterminado de la base de datos: test
- Usuario predeterminado de la base de datos: root
- Contraseña predeterminada: No hay **contraseña** predeterminada.
- Contraseña de administrador: tu elección.

Se recomienda instalar los datos de muestra para el usuario novato.

Después de la instalación, elimina el directorio de instalación y apunta tu navegador a: `http://localhost/tuNuevaCarpetaJoomla` o `http://localhost/tuNuevaCarpetaJoomla/administrator`.

#### Creación de un enlace en el menú de Ubuntu

##### Para crear una GUI para xampp conectada a tu menú de Ubuntu

Abre el Terminal y escribe

    sudo nano /usr/share/applications/xampp-control-panel.desktop

Luego copia lo siguiente en el editor nano y guarda.

    [Desktop Entry]
    Encoding=UTF-8
    Name=XAMPP Control Panel
    Comment=Start and Stop XAMPP
    Exec=gksudo "python /opt/lampp/share/xampp-control-panel/xampp-control-panel.py"
    Icon=/usr/share/icons/Tango/scalable/devices/network-wired.svg
    Terminal=false
    Type=Application
    Categories=GNOME;Application;Network;
    StartupNotify=true

Si el panel de control no se inicia, intenta ejecutar el comando Exec directamente en el terminal:

    gksudo "python /opt/lampp/share/xampp-control-panel/xampp-control-panel.py"

Si recibes el error:

    Error importing pygtk2 and pygtk2-libglade

Instala las bibliotecas faltantes:

    sudo apt-get install python-glade2

#### Depurador PHP XDebug

El paquete XAMPP para Linux no incluye el depurador PHP XDebug. Para instalar XDebug en Debian o Ubuntu:

- Instala el paquete *build-essential*:

    sudo apt-get update
    sudo apt-get install build-essential
    sudo apt-get install autoconf

- Descarga el [paquete de desarrollo](http://www.apachefriends.org/en/xampp-linux.html) para tu versión de XAMPP y extráelo sobre tu instalación existente:

    sudo tar xvfz xampp-linux-devel-1.7.7.tar.gz -C /opt

- Construye XDebug:

    wget http://xdebug.org/files/xdebug-2.1.3.tgz
    tar xzf xdebug-2.1.3.tgz
    cd xdebug-2.1.3/
    /opt/lampp/bin/phpize

Después de esto, tendrás el siguiente resultado en tu consola…

    Configuring for:
    PHP Api Version:         20090626
    Zend Module Api No:      20090626
    Zend Extension Api No:   20090626

    ./configure --with-php-config=/opt/lampp/bin/php-config
    make
    sudo make install

Luego el resultado será este... por favor monitorea el directorio especificado.

    Installing shared extensions:     /opt/lampp/lib/php/extensions/no-debug-non-zts-20090626/

Crea una carpeta en tu carpeta temporal que contendrá el archivo de datos generado por XDebug:

    sudo mkdir /opt/lampp/tmp/xdebug
    sudo chmod a+rwx -R /opt/lampp/tmp/xdebug

Instalaciones alternativas:

Instala utilizando la biblioteca comunitaria de extensiones PHP (PECL) incluida con xampp:

    sudo /opt/lampp/bin/pecl install xdebug

En Ubuntu/Debian puedes instalar usando:

    apt-get install php5-xdebug

(advertencia: esto también instalará Apache y PHP desde los repositorios apt).

##### Advertencia para usuarios de 64bit

Al compilar XDebug o instalar via apt-get, recibirás un error al (re)iniciar xampp:

    /opt/lampp/lib/php/extensions/no-debug-non-zts-20090626/xdebug.so: wrong ELF class: ELFCLASS64

Esto se debe a que xampp se ejecuta en 32bit pero XDebug es 64bit. Para superar este problema, haz xdebug.so en una máquina de 32bit o descárgalo de:

    http://code.activestate.com/komodo/remotedebugging/

Descarga el archivo: "PHP Remote Debugging Client" para "Linux (x86)". Extrae el contenido del archivo en tu computadora. Este archivo comprimido contiene varias carpetas con números de versión como: 4.4, 5.0, 5.1 ... 5.3 y así sucesivamente, entra en la carpeta con el número de versión más alto o la que funcione para ti, luego copia manualmente el archivo "xdebug.so" a la siguiente ubicación, sobrescribe si es necesario:

    /opt/lampp/lib/php/extensions/no-debug-non-zts-20090626/

Recuerda que esta ubicación podría ser diferente en tu computadora.

### Instalación en Mac OS X

Mac OS X en realidad incluye un servidor Apache de serie, pero la mayoría de los desarrolladores preferirán usar las herramientas integradas y la configurabilidad proporcionadas por XAMPP.

Como con la mayoría de los programas en Mac, la instalación es sencilla. Visita el sitio web de [Apache Friends](https://www.apachefriends.org/) y descarga el instalador (xampp-osx-8.2.4-0-installer.dmg). Haz doble clic en el instalador descargado para iniciar el proceso de instalación.

Para iniciar el servidor, abre "XAMPP Control.app" y presiona el botón de inicio junto a Apache.

#### Un poco de solución de problemas

Muchos usuarios de Mac tienen un poco de dificultad en esta etapa cuando intentan configurar otra instancia de Apache en su máquina. Si no puedes iniciar el Apache de XAMPP, tienes dos opciones:
**Puedes cambiar el puerto de escucha de XAMPP.** En \Applications\XAMPP\xamppfiles\etc\httpd.conf, modifica la línea que dice, "Listen 80" a Listen \[número de puerto\]. Por ejemplo:

    Listen 8080

**Puedes cambiar el puerto de escucha del servidor Apache preinstalado.** En Finder, ve a "/etc" (CMD+SHIFT+G); desde aquí podrás navegar por los archivos normalmente ocultos de Apache. Encuentra la carpeta etiquetada Apache2 y edita el archivo "http.conf". Modifica la línea que dice, "Listen 80" a Listen \[número de puerto\]. Por ejemplo:

    Listen 8080

*Nota: Si eliges cambiar el puerto del servidor Apache preinstalado, es posible que necesites reiniciar tu computadora para que los cambios surtan efecto. También tendrás que autenticarte como administrador para cambiar estos archivos.*

### Prueba de Instalación de XAMPP

Una vez que XAMPP está instalado y has iniciado el servicio Apache con la herramienta del Panel de Control de XAMPP, puedes probarlo abriendo tu navegador y navegando a `http://localhost`. Deberías ver la pantalla de bienvenida de XAMPP similar a la que se muestra a continuación.

![La página de inicio de XAMPP](../../../en/images/hosting/local-hosting-xampp.png)

Selecciona el enlace llamado `phpinfo()` en el menú superior. Esto mostrará una pantalla larga con información sobre la configuración de PHP, como se muestra a continuación.

![La página de información de la versión de PHP de XAMPP](../../../en/images/hosting/local-hosting-xampp-php.png)

En este punto, XAMPP está instalado con éxito. Nota el *Archivo de Configuración Cargado*. Editaremos este archivo en la siguiente sección para configurar XDebug.

*Traducido por openai.com*

