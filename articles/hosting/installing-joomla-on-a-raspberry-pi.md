<!-- Filename: Installing_Joomla_on_a_Raspberry_Pi / Display title: Instalación de Raspberry Pi -->

## Prefacio

**Nota: Este documento aún no está completo ni plenamente probado.**

El <a href="https://www.raspberrypi.org/" rel="nofollow noreferrer noopener">Raspberry Pi</a> es una pequeña computadora de placa única que fue desarrollada originalmente para promover la enseñanza de la informática básica en escuelas y países en desarrollo. Debido a su versatilidad, se ha vuelto muy popular y se utiliza como reproductor multimedia, pequeño servidor independiente, etc. Puedes usarlo como servidor web e instalar Joomla! en él. Esta página te muestra cómo hacer que tu sitio web Joomla! funcione en el Raspberry Pi.

## Hardware

- **Raspberry Pi versión 3 Modelo B** - Hay varios modelos de Raspberry Pi. Puedes usar la mayoría de los modelos que tienen un puerto Ethernet (los tipos Modelo B). Sin embargo, para el rendimiento usaremos la última versión con más memoria RAM.
- **Tarjeta micro SD** - Para el sistema operativo + servidor web + Joomla. (La versión RPi 3 modelo B usa micro SD, otras versiones podrían usar tarjetas SD normales).
- **Adaptador de 5 Voltios (1 Amperio)** - Para alimentar la Raspberry Pi, necesitarás convertir la corriente alterna (230V o 110V) a 5 Voltios. La Raspberry Pi necesita aproximadamente 1 Amperio, y tal vez más si conectas dispositivos USB a ella.
- **Cable Ethernet estándar** - Para conectar la RPi a tu red de área local / router / internet.

## Instalación del Sistema Operativo

El sistema operativo Raspbian es una versión de Debian Linux especialmente compilada para la Raspberry Pi. Hay dos versiones de <a href="https://www.raspberrypi.com/software/" rel="nofollow noreferrer noopener">Raspbian</a> disponibles: **Raspbian Jessie con Pixel Lite** (versión con escritorio PIXEL basado en Debian Jessie) y **Raspbian Jessie Lite** (versión mínima basada en Debian Jessie). Como usamos la Raspberry Pi como un servidor web para Joomla, no necesitaremos la interfaz gráfica de usuario.

**Descarga** <a href="https://www.raspberrypi.org/downloads/raspbian/" rel="nofollow noreferrer noopener">Raspbian Jessie Lite</a> y descomprime el archivo descargado, por ejemplo **2016-09-23-raspbian-jessie-lite.zip** (306 MB) a **2016-09-23-raspbian-jessie-lite.img** (1.4 GB).

Ahora necesitamos copiar el archivo .img a la tarjeta SD (micro). Puedes usar una herramienta con interfaz gráfica como <a href="https://unetbootin.github.io/" rel="nofollow noreferrer noopener">UNetbootin</a> (para Windows, Mac OS X y Linux) o hacerlo en la línea de comandos).

**Ten cuidado** al escribir la imagen de disco *.img* en otro disco. Si especificas el disco de destino incorrecto, sobrescribirás ese disco con el *.img*, lo que lo hará inutilizable, resultando en pérdida de datos.

### Windows

En una terminal (CMD) verifica qué dispositivo corresponde con la tarjeta SD y haz algo parecido a:

```
    dd bs=1M if=c:\temp\2016-09-23-raspbian-jessie-lite.img od=[el dispositivo de tu tarjeta SD]
```

Ver también <a href="https://www.raspberrypi.org/documentation/installation/installing-images/windows.md" rel="nofollow noreferrer noopener">Instalación de Imágenes del Sistema Operativo usando Windows</a>

### Apple OSX

Verifica qué dispositivo se usa para tu tarjeta SD. En nuestro caso es *disk1s1* y haremos en Terminal:

```
    sudo dd bs=1M if=~/Downloads/2016-09-23-raspbian-jessie-lite.img of=/dev/disk1s1
```

Ver también: <a href="https://www.raspberrypi.org/documentation/installation/installing-images/mac.md" rel="nofollow noreferrer noopener">Instalación de Imágenes del Sistema Operativo en MacOS</a>

### Linux

Conectamos un lector de tarjetas SD con la tarjeta SD (micro) a una computadora. Con *dmesg* podemos encontrar el nombre del dispositivo de la tarjeta SD. En nuestro caso, dmesg muestra algo como `[xxxxxx.xxxxxxx]  sdd: sdd1 sdd2`, lo que significa que tenemos una tarjeta SD con 2 particiones. No escribas la imagen de Raspbian en una partición sino en todo el disco **sdd**.

Usaremos *dd* ("Disk Dump") para escribir un archivo de entrada (*if*) a un archivo de salida (*of*) usando un tamaño de bloque especificado (*bs*).

**Ten cuidado**: *dd* escribirá en un dispositivo sin ninguna advertencia. ¡Verifica dos veces que escribas en el dispositivo correcto! Si escribes en el disco incorrecto, siempre recordarás el comando *dd* como "Destructor de Discos".

```bash
    sudo dd if=~/Downloads/2016-09-23-raspbian-jessie-lite.img of=/dev/sdd bs=4M
```

Ver también <a href="https://www.raspberrypi.org/documentation/installation/installing-images/linux.md" rel="nofollow noreferrer noopener">Instalación de Imágenes del Sistema Operativo en Linux</a>

**ADVERTENCIA para la versión Raspbian Stretch**: para tener un servidor SSH funcionando desde el arranque necesitas crear un archivo vacío *ssh* en la partición raíz.

## Conexión del Raspberry Pi a la LAN

Cuando hayamos instalado el Sistema Operativo Raspbian en la tarjeta SD, haremos lo siguiente:

- Insertar la tarjeta micro SD en la ranura del Raspberry Pi.
- Conectar un cable Ethernet al Raspberry Pi y a la Red de Área Local (conectarlo a nuestro router).
- Conectar la fuente de alimentación de 5V al Raspberry Pi.

El arranque del Raspberry Pi tarda aproximadamente 30 segundos. Tenemos que encontrar la dirección IP para conectarnos a él usando SSH. Podemos utilizar diferentes enfoques para ello:

- Iniciar sesión en la interfaz web de tu router y buscar los dispositivos conectados;
- Usar un teléfono móvil conectado al router wi-fi utilizando una aplicación de escaneo de red llamada **Fing Overlook**;
- Usar un comando como **nmap**. Suponiendo que nuestro PC tiene la dirección IP **192.168.0**.25, podemos encontrar todos los demás dispositivos en el mismo rango de red haciendo lo siguiente:
```
    sudo nmap -sP 192.168.0/24
```
Lo que podría mostrar los siguientes detalles:

    Starting Nmap 6.47 ( http://nmap.org ) at 2016-10-22 17:42 CEST
    Nmap scan report for 192.168.0.35
    Host is up (0.00042s latency).
    MAC Address: 42:42:42:42:42:42 (Raspberry Pi Foundation)

Para iniciar sesión en nuestro Raspberry Pi, utilizaremos el comando **ssh**.

```
    ssh pi@192.168.0.35
```

La primera vez que te conectes, mostrará algo como:

    The authenticity of host '192.168.0.35 (192.168.0.35)' can't be established.
    ECDSA key fingerprint is 42:42:42:42:42:42:42:42:42:42:42:42:42:42:42:42.
    Are you sure you want to continue connecting (yes/no)?

Elegiremos **Yes**

    Warning: Permanently added 192.168.0.35 (ECDSA) to the list of known hosts.
    pi@192.168.0.35's password:

y usaremos la *contraseña predeterminada*: *raspberry* que al iniciar sesión con éxito mostrará:

    The programs included with the Debian GNU/Linux system are free software;
    the exact distribution terms for each program are described in the
    individual files in /usr/share/doc/*/copyright.

    Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
    permitted by applicable law.
    pi@raspberrypi:~ $

Podemos configurar el Raspberry Pi utilizando una interfaz de texto a través de:

    sudo raspi-config

### Herramienta de Configuración de Software de Raspberry Pi (raspi-config)

Con esta herramienta de configuración solo cambiaremos las siguientes configuraciones.

#### 1 Expandir Sistema de Archivos

Por defecto, el espacio de disco en la tarjeta SD es del mismo tamaño que el archivo .img de 1.4GB que usaste para crear la tarjeta SD para tu Raspberry Pi. Puedes usar esta opción para obtener el resto del espacio en disco.

#### 2 Cambiar Contraseña de Usuario

Por razones de seguridad, es mejor **cambiar la contraseña predeterminada** "raspberry" lo antes posible.

#### 3 Opciones de Arranque

Nos gustaría que el Raspberry Pi inicie la consola de texto

##### B2 Autologin de Consola de Texto, iniciando sesión automáticamente como usuario 'pi'

#### 9 Opciones Avanzadas

##### A3 División de Memoria

Como utilizaremos el Raspberry Pi como un servidor sin monitor, podemos reducir la memoria usada por la GPU de 64 a **16**

#### 5 Opciones de Internacionalización

##### I2 Cambiar Zona Horaria

Cambiaremos la Zona Horaria a nuestra propia zona horaria (por ejemplo, Europa/Ámsterdam)

Después de todos los cambios, reiniciaremos el Raspberry Pi y volveremos a iniciar sesión con nuestra nueva contraseña.

    ssh pi@192.168.0.35

Ahora es el momento de instalar todo lo demás.

## Actualizar software

Antes de instalar cualquier otra cosa, haremos lo siguiente:

- **actualizar** la lista de versiones de software de todos los
  repositorios externos
    sudo apt-get update

- **mejorar** todo el software instalado
    sudo apt-get upgrade

**Actualizar la lista de versiones y mejorar todo el software es algo que
debería hacerse regularmente.**

## Servidor web Nginx

Una alternativa rápida y ligera al servidor web Apache es el servidor web **Nginx**, que cada vez se está volviendo más popular.

### Instalación de Nginx

Instalaremos nginx y todas sus dependencias (entiéndase: software que nginx necesita para funcionar) con

    sudo apt-get install nginx

Recibiremos un mensaje como:

    Reading package lists... Done
    Building dependency tree
    Reading state information... Done
    The following extra packages will be installed:
     fontconfig-config fonts-dejavu-core libfontconfig1 libgd3 libjbig0 libtiff5 libvpx1 libxpm4 libxslt1.1 nginx-common nginx-full
    Suggested packages:
     libgd-tools fcgiwrap nginx-doc ssl-cert
    The following NEW packages will be installed:
     fontconfig-config fonts-dejavu-core libfontconfig1 libgd3 libjbig0 libtiff5 libvpx1 libxpm4 libxslt1.1 nginx nginx-common nginx-full
    0 upgraded, 12 newly installed, 0 to remove and 0 not upgraded.
    Need to get 3,550 kB of archives.
    After this operation, 8,666 kB of additional disk space will be used.
    Do you want to continue? [Y/n] y

Al elegir "y", se instalarán nginx y todos los paquetes necesarios.

Puedes verificar la instalación con un navegador. Ve a la dirección IP de tu Raspberry Pi, en nuestro caso 
<a href="http://192.168.0.35/" rel="nofollow noreferrer noopener">http://192.168.0.35/</a> Deberíamos ver un mensaje como:

    ¡Bienvenido a nginx en Debian!
    Si ves esta página, el servidor web nginx se ha instalado correctamente y está funcionando en Debian. Se requiere más configuración.
    Para documentación y soporte en línea, por favor, consulta nginx.org
    Usa la herramienta reportbug para reportar errores en el paquete nginx con Debian.
    Sin embargo, revisa los informes de errores existentes antes de reportar un nuevo error.
    Gracias por usar debian y nginx.

#### Iniciar y detener Nginx

Después de la instalación, Nginx se iniciará automáticamente. Puedes:

- Detener Nginx: sudo service nginx stop
- Iniciar Nginx: sudo service nginx start
- Reiniciar Nginx: sudo service nginx restart

### Configurar Nginx

#### Configuración global de Nginx

En la configuración global de Nginx podemos configurar el caché por defecto, etc. La Raspberry Pi 3 utiliza un procesador ARM Cortex-A53 **quad-core** de 64 bits a 1.2 GHz. Si tienes una versión anterior con menos núcleos de CPU, entonces deberías usar

    sudo nano /etc/nginx/nginx.conf

para cambiar "worker_processes" para que se ajuste a la cantidad de CPUs de tu dispositivo. Por defecto, está configurado como

    worker_processes 4;

así que para Raspberry Pi 3 no necesitas cambiarlo.

Después de cambiar la configuración de Nginx o la configuración del dominio virtual, debes hacer un

    sudo nginx reload

para que los cambios sean efectivos.

#### Dominios virtuales

Es posible ejecutar múltiples sitios web Joomla en el mismo servidor utilizando dominios virtuales.

Pon cada sitio web en una carpeta separada en la raíz web por defecto /var/www/, por ejemplo:

- /var/www/example.com/
- /var/www/voorbeeld.nl/

    sudo mkdir /var/www/example.com
    sudo mkdir /var/www/voorbeeld.nl

Para cada sitio, crearemos un dominio virtual que básicamente es un archivo de texto con información específica del dominio:

- /etc/nginx/sites-available/example.com

    ```nginx
    server {
    listen 80;
    server_name example.com www.example.com;
    root /var/www/example.com;

    access_log /var/log/nginx/example.com.access_log;
    error_log /var/log/nginx/example.com.error_log info;

    location / {
      index index.php index.html index.htm;
      }
    }
    ```

- /etc/nginx/sites-available/voorbeeld.nl

    ```nginx
    server {
    listen 80;
    server_name voorbeeld.nl www.voorbeeld.nl;
    root /var/www/voorbeeld.nl;

    access_log /var/log/nginx/voorbeeld.nl.access_log;
    error_log /var/log/nginx/voorbeeld.nl.error_log info;

    location / {
      index index.php index.html index.htm;
      }
    }
    ```

Necesitamos habilitar cada sitio creando un enlace desde /etc/nginx/sites-enabled/ al dominio virtual en "sites-available". Creamos un enlace simbólico para cada dominio virtual:

    sudo ln -s /etc/nginx/sites-available/example.com /etc/nginx/sites-enabled/example.com
    sudo ln -s /etc/nginx/sites-available/voorbeeld.nl /etc/nginx/sites-enabled/voorbeeld.nl

Para hacer que esta configuración de dominio virtual sea efectiva, hacemos

    sudo nginx reload

y cuando todo se ha configurado correctamente responderá:

    Reloading nginx configuration: nginx.

## Base de datos

Podemos instalar MariaDB o MySQL; Joomla funcionará con ambos. Vamos a instalar MariaDB con:

    sudo apt-get install mariadb-server

Durante la instalación, debes agregar una contraseña para el usuario **root**. Vamos a crear una **contraseña para la base de datos**, por ejemplo, **correcthorsebatterystaple**.

Finalmente, mejoremos la seguridad de nuestra instalación de MariaDB eliminando las cuentas root que sean accesibles desde fuera del host local, las cuentas de usuario anónimo y la base de datos de prueba. Podemos hacer eso con

    mysql_secure_installation

## PHP

Para PHP, instalaremos **php-fpm** (FastCGI Process Manager), que se ejecuta como un demonio y recibe solicitudes Fast/CGI. Además, instalaremos **php5-mysql**, que es un módulo para conexiones a bases de datos MySQL directamente desde scripts PHP.

La versión más reciente, php7, debería instalarse con:

    sudo apt-get install php-fpm php-mysql

Ahora necesitamos informar a Nginx que debe usar php-fpm para archivos .php.
Agregamos un par de líneas a nuestros dominios virtuales:

    sudo nano /etc/nginx/sites-available/example.com

agrega:

    location ~ \.php$ {
    fastcgi_pass unix:/var/run/php/php7.0-fpm.sock;
    fastcgi_index index.php;
    include fastcgi_params;
    }

Prueba creando el siguiente archivo PHP:

    sudo nano /var/www/example.com/test.php

Usamos un navegador para comprobar si vemos la página de configuración de PHP en
<a href="http://192.168.0.35/example.com/test.php"
rel="nofollow noreferrer noopener">http://192.168.0.35/example.com/test.php</a>

## ¡Joomla!

- por hacer
```
    sudo wget https://github.com/joomla/joomla-cms/releases/download/3.6.3/Joomla_3.6.3-Stable-Full_Package.zip
    sudo unzip -x Joomla_3.6.3-Stable-Full_Package.zip
```

## Conectando Raspberry Pi a Internet

Queremos que las personas en internet puedan visitar nuestro sitio web de Joomla en nuestro Raspberry Pi. Para lograr eso, necesitamos **configurar nuestro router de Internet** para dirigir todo el **tráfico entrante** en el puerto 80 **a nuestro Raspberry Pi**.

Usa tu navegador web para conectarte a la Interfaz Web de tu router. Un router generalmente se encuentra en el primer número de tu rango de IP, en nuestro caso en 192.168.0.1. En nuestro router configuramos el **Reenvío de Puertos**:

- Dirección IP Externa: 0.0.0.0
- Puerto de Inicio Externo: 80
- Puerto de Fin Externo: 80
- Dirección IP Interna: 192.168.0.35 (= nuestro Raspberry Pi)
- Puerto de Inicio Interno: 80
- Puerto de Fin Interno: 80
- Protocolo: TCP

Asegúrate de que esté habilitado.

Si todo está funcionando correctamente, deberías ver tu propio sitio web de Joomla en el Raspberry Pi visitando tu dirección IP externa (Encuentra tu dirección IP externa con una herramienta como <a href="http://www.whatsmyip.org/" rel="nofollow noreferrer noopener">whatsmyip.org</a>).

### Usando un nombre de dominio

Supongamos que nuestra dirección IP externa es 42.42.42.42. También supongamos que hemos registrado un nombre de dominio llamado example.com. Nos gustaría servir nuestro sitio de Joomla en nuestro Raspberry Pi a los visitantes que ingresan a example.com. Si nuestro registrador de nombres de dominio nos da la posibilidad de configurar el servidor de **Sistema de Nombres de Dominio (DNS)**, entonces necesitaremos crear un **registro MX** en el DNS que apunte nuestro **nombre de dominio a** nuestra **dirección IP** 42.42.42.42. Ten en cuenta que puede tomar hasta 24 horas para que todos los proveedores de internet dirijan el tráfico de sus clientes al registro MX configurado.

### Dirección IP estática

La mayoría de los routers seguirán asignando la misma dirección IP interna a tu Raspberry Pi. A veces es mejor configurar tu Raspberry Pi para usar una dirección IP estática:

    sudo nano /etc/network/interfaces

cambia

    iface eth0 inet static

a

    iface eth0 inet static
    address 192.168.0.35
    netmask 255.255.255.0
    gateway 192.168.0.1

El gateway es la dirección IP de tu router. También puedes encontrarla usando

    route

# Enlaces externos

- <a href="https://raspberrypi.org" rel="nofollow noreferrer noopener">Fundación Raspberry Pi</a> (RPF) - sitio web oficial y foros
- <a href="http://elinux.org/RaspberryPiBoard" rel="nofollow noreferrer noopener">Wiki de Raspberry Pi</a>, apoyado por el RPF
- Video de la presentación <a href="https://youtu.be/u2MFQCoexD0" rel="nofollow noreferrer noopener">Joomla en Raspberry Pi (con Nginx)</a> en Joomladay Alemania 2013 en Nuremberg, Alemania

*Traducido por openai.com*

