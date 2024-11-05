<!-- Filename: Installing_Joomla!_using_BitNami_Joomla!_stack / Display title: Instalación de Bitnami  -->

## Prefacio

**NOTA:** La pila BitNami Joomla! ya no existe como instalador independiente. En su lugar, se ofrece como: 1) Una instancia basada en la nube, 2) En un contenedor, ya sea Kubernetes o Docker o 3) Una máquina virtual. La máquina virtual se ejecutará en tu sistema operativo en un hipervisor como Virtual Box o VMware Player. Aún viene con todas las dependencias necesarias, tal como el instalador independiente.

La Opción 1 a continuación ya no aplica. Además, en la Opción 2, BitNami Lamp Stack más abajo, se ofrece en la nube o máquina virtual. En cualquier caso, Bitnami hace que tener una instalación local de Joomla! que funcione sea fácil y completa.

Puedes descargar la última versión del paquete Bitnami para Joomla! para Windows, Linux y Mac en <a href="http://bitnami.org/stack/joomla" rel="nofollow noreferrer noopener">http://bitnami.org/stack/joomla</a>.

**¡Se necesita revisión!**

BitNami Joomla! Stack es un instalador todo-en-uno que hace que sea fácil instalar Joomla en tu computadora. Es gratuito, fácil de usar y autónomo. Esto significa que agrupa y configura automáticamente cada pieza de software (dependencia) necesaria para ejecutar Joomla con fines de desarrollo o producción, incluyendo Apache HTTP Server, MySQL y PHP.

## Opción 1: Stack de Joomla! (Recomendado)

Este método asume que ya tienes un entorno **AMP** (Apache HTTP Server, MySQL y PHP) instalado en (**W**indows/**L**inux/**M**ac).

### Instalación del Stack de Joomla!

Independientemente del sistema operativo que estés utilizando (Windows / Linux / Mac), el proceso de instalación es el mismo.

Descarga la última versión de Joomla! Stack desde el <a href="http://bitnami.org/stack/joomla" rel="nofollow noreferrer noopener">sitio web de BitNami</a>.

Encuentra el instalador que acabas de descargar (el nombre del archivo será similar a bitnami-joomla-VERSION-linux-installer.run. Haz doble clic en el ícono para iniciar el instalador.

Si utilizas Linux, primero tendrás que otorgar permisos de ejecución al archivo, usando este comando:

chmod +x /ruta/al/bitnami-joomla-VERSION-linux-installer.run

<img src="https://docs.joomla.org/images/a/a0/Joomla_welcome2.png" decoding="async" data-file-width="614" data-file-height="538" width="614" height="538" alt="Configuración de Joomla Bitnami lampstack" />

Haz clic en "Next" (Siguiente).

<img src="https://docs.joomla.org/images/5/5f/Joomla_components2.png" decoding="async" data-file-width="614" data-file-height="538" width="614" height="538" alt="Componentes de Joomla Bitnami lampstack" />

Selecciona los componentes que deseas instalar. Si no estás seguro, deja los componentes predeterminados marcados. Haz clic en "Next" (Siguiente) cuando termines.

<img src="https://docs.joomla.org/images/0/0a/Joomla_directory2.png" decoding="async" data-file-width="614" data-file-height="538" width="614" height="538" alt="Directorio de instalación de Joomla Bitnami lampstack" />

Ahora te preguntará dónde deseas instalar el programa. Proporciona la ubicación donde deseas instalar el stack de BitNami Joomla! y haz clic en "Next" (Siguiente) cuando termines.

<img src="https://docs.joomla.org/images/3/3c/Joomla_userdata2.png" decoding="async" data-file-width="614" data-file-height="538" width="614" height="538" alt="Cuenta de administrador de Joomla Bitnami lampstack" />

El usuario y la contraseña que proporciones aquí se utilizarán para crear la cuenta de administrador en Joomla! Haz clic en "Next" (Siguiente) cuando termines.

<img src="https://docs.joomla.org/images/8/8b/Joomla_sitename2.png" decoding="async" data-file-width="614" data-file-height="538" width="614" height="538" alt="Nombre del sitio de Joomla Bitnami lampstack" />

Escribe el nombre que deseas usar para tu sitio de Joomla y haz clic en "Next" (Siguiente).

<img src="https://docs.joomla.org/images/d/dd/JoomlaReadytoinstall2.png" decoding="async" data-file-width="614" data-file-height="538" width="614" height="538" alt="Listo para instalar Joomla Bitnami lampstack" />

El instalador te permite configurar una cuenta de correo electrónico para que Joomla! pueda enviar notificaciones por correo electrónico. Haz clic en "Next" (Siguiente).

<img src="https://docs.joomla.org/images/9/9d/JoomlaCopyingfiles2.png" decoding="async" data-file-width="614" data-file-height="538" width="614" height="538" alt="Copiando archivos de Joomla Bitnami lampstack" />

Espera un momento mientras el instalador copia los archivos y configura tu instalación de Joomla!.

<img src="https://docs.joomla.org/images/e/ea/Joomlafinalscreen2.png" decoding="async" data-file-width="614" data-file-height="538" width="614" height="538" alt="Pantalla final de Joomla Bitnami lampstack" />

¡Joomla! está ahora configurado y listo para ser usado. Haz clic en "Finish" (Finalizar) para iniciar la aplicación.

<img src="https://docs.joomla.org/images/8/8d/JoomlaManager.png" decoding="async" data-file-width="784" data-file-height="586" width="784" height="586" alt="Administrar servidores de Joomla Bitnami lampstack" />

Usar la herramienta de administración es fácil para iniciar/detener los servidores Apache y MySQL.

<img src="https://docs.joomla.org/images/7/73/Joomlaapplicationscreen2.png" decoding="async" data-file-width="982" data-file-height="729" width="982" height="729" alt="Pantalla de aplicación de Joomla" />

Puedes administrar la base de datos de Joomla! fácilmente con phpMyAdmin.

<img src="https://docs.joomla.org/images/f/f3/JoomlaphpMyAdmin.png" decoding="async" data-file-width="982" data-file-height="751" width="982" height="751" alt="Pantalla phpMyAdmin" />

## Opción 2: BitNami LAMPStack y Joomla!

### ¿Qué es BitNami LAMPStack?

BitNami LAMPStack es un paquete gratuito y fácil de instalar que incluye cada pieza de software (dependencia) necesaria para configurar un entorno LAMP (Apache, MySQL y PHP para Linux) en funcionamiento para propósitos de desarrollo o producción. Es autónomo, no realiza modificaciones en tu sistema y se puede desinstalar fácilmente. Puedes descargar la última versión de BitNami LAMPStack para Linux en <a href="http://bitnami.org/stack/lampstack" rel="nofollow noreferrer noopener">http://bitnami.org/stack/lampstack</a>. También está disponible una <a href="http://bitnami.org/stack/wampstack" rel="nofollow noreferrer noopener">versión para Windows</a> y una <a href="http://bitnami.org/stack/mampstack" rel="nofollow noreferrer noopener">versión para OS X</a>.

Independientemente del sistema operativo que estés utilizando (Windows / Linux / Mac), el proceso de instalación es el mismo.

### Instalando BitNami LAMPStack

Busca el instalador que acabas de descargar del sitio web de BitNami (el nombre del archivo será similar a bitnami-lampstack-VERSION-linux-installer.run). Haz doble clic en el icono para iniciar el instalador.

<img src="https://docs.joomla.org/images/1/14/Lampstack_welcome.png" decoding="async" data-file-width="516" data-file-height="391" width="516" height="391" alt="Bienvenida a Bitnami lampstack" />

Haz clic en "Adelante".

<img src="https://docs.joomla.org/images/7/78/Lampstack_directory.png" decoding="async" data-file-width="516" data-file-height="391" width="516" height="391" alt="Directorio de Bitnami lampstack" />

Ahora te preguntará dónde quieres instalar el programa. Selecciona la ubicación en tu máquina y haz clic en "Adelante" cuando termines.

<img src="https://docs.joomla.org/images/2/22/Lampstack_passwd.png" decoding="async" data-file-width="516" data-file-height="391" width="516" height="391" alt="Contraseña de Bitnami lampstack" />

Escribe tu contraseña de MySQL root. Esta será la contraseña para el usuario "root" de la base de datos.

<img src="https://docs.joomla.org/images/7/72/LampstackReadytoinstall.png" decoding="async" data-file-width="516" data-file-height="391" width="516" height="391" alt="Bitnami lampstack listo para instalar" />

El instalador está ahora listo para comenzar el proceso de instalación. Haz clic en "Adelante".

<img src="https://docs.joomla.org/images/1/19/LampstackCopyingfiles.png" decoding="async" data-file-width="516" data-file-height="391" width="516" height="391" alt="Copiando archivos de Bitnami lampstack" />

Espera un momento mientras el instalador copia los archivos y configura tu instalación de LAMPStack.

<img src="https://docs.joomla.org/images/b/bc/Lampstackfinalscreen.png" decoding="async" data-file-width="516" data-file-height="391" width="516" height="391" alt="Pantalla final de Bitnami lampstack" />

BitNami LAMPStack está ahora configurado y listo para usarse. Haz clic en "Finalizar" para iniciar la aplicación.

### Instalación manual de Joomla!

Sigue las instrucciones descritas en el artículo Instalando Joomla.

