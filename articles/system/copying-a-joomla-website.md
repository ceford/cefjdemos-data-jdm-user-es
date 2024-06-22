<!-- Filename: Copying_a_Joomla_website / Display title: Copiar un sitio web Joomla! -->

<span id="main-portal-heading">Tutorial  
Copiando un sitio web Joomla!</span>

  
Copiar un sitio web Joomla! es un proceso de dos partes: debes copiar
los archivos y la base de datos (que es donde se almacena el contenido).
La copia de los archivos y de la base de datos son operaciones
independientes. Cual se lleva a cabo primero dependerá de tus
circunstancias particulares, pero en la mayoría de los casos realmente
no importa. Si tu sitio web se actualiza con frecuencia y que necesita
para poner a tu sitio web fuera de línea, mientras la copia se lleva a
cabo, a continuación, probablemente, por último, desearas realizar la
copia de base de datos a fin de minimizar el tiempo de inactividad.

## Copiar un sitio web (método común)

#### Akeeba

- Akeeba Backup produce un archivo .jpa
- La archivo .jpa contiene todos los archivos/carpetas y archivos de
  base de datos.
- La archivo .jpa también contiene un instalador
- Kickstart.php (de Akeeba) descomprime el archivo .jpa
- A continuación, ejecutar el instalador e instalar tu sitio como si
  instalaras Joomla!
- El instalador de cambia la configuración para restaurar a una
  ubicación diferente y solicita los nuevos datos de base de datos.

Después de crear la Base de Datos para tu sitio Joomla, descarga e
instala Akeeba, se puede descargar desde <a
href="https://extensions.joomla.org/extensions/extension/access-a-security/site-security/akeeba-backup/"
class="external text" target="_blank"
rel="noreferrer noopener">Directorio de extensiones de Joomla!</a>. Hay
un enlace para obtener instrucciones completas.

### Copiar los archivos con FTP

Un método para copiar los archivos de una instalación de un sitio
Joomla! a otro, es utilizar un software FTP estándar de escritorio para
descargar todos los archivos que componen tu sitio Web desde su
ubicación en el servidor Web, y luego cargar estos archivos a la
ubicación de la nueva instalación de Joomla!. Dependiendo de dónde
desees colocar la copia de tu sitio Joomla!, la nueva ubicación podría
ser un directorio diferente en el mismo servidor Web, o podría ser una
nueva ubicación en un servidor Web completamente diferente. Al copiar
una instalación de Joomla en el mismo servidor (es decir, con fines de
prueba), es recomendable utilizar un subdominio en lugar de un
subdirectorio. Esto evitará errores y posibles problemas al ejecutar
ambas instalaciones al unísono.

Es importante mantener la misma estructura de directorios para todas las
carpetas y archivos a medida que se copian de un lugar a otro.
Afortunadamente, el software FTP de escritorio se hará cargo de esto
automáticamente a medida que se carga y descarga el conjunto de archivos
y carpetas. (Tu software FTP debe contener la documentación de Ayuda que
explica FTP y cómo utilizar la interfaz del software FTP). Ten en cuenta
que después de copiar los archivos de una ubicación a otra, todavía
puede necesitar el archivo de configuración de Joomla! para lograr que
tu copia de Joomla! trabaje en la nueva ubicación; también puede que
necesites cambiar aspectos de la configuración de tu servidor Web para
lograr que la copia de tu sitio Joomla! trabaje.

En casos raros, un archivo puede dañarse durante una transferencia FTP,
donde sólo una parte del archivo se transmite correctamente. Si te
encuentras con errores extraños o inesperados con la instalación del
nuevo Joomla! después de copiar los archivos, puede que desees intentar
volver a cargar tus archivos en caso de corrupción durante la
transferencia.

#### Descargar archivos desde el servidor a tu equipo

1.  Utiliza software FTP (por ejemplo FileZilla) para conectarte con el
    servidor
2.  Selecciona el directorio del que deseas descargar (en su mayoría
    /public_html/ o /htdocs/)
3.  Has clic derecho + selecciona archivos/carpeta a descargar, o
    arrastre + coloca la carpeta que ves en el "Sitio remoto" a la que
    ves en el "Sitio local"
4.  La descarga remota de los archivos se iniciará
5.  Después de que hayas descargado los archivos, consulta los "Errores
    de transferencia" para ver si no hay errores

#### Cargar archivos desde tu equipo a un servidor

1.  Asegúrate que *configuration.php* tiene derecho de configuración
    para el servidor (especialmente: localhost, base de datos, usuario
    de la base de datos, contraseña de base de datos, ruta a la carpeta
    log, ruta a la carpeta tmp)
2.  Utilice el software FTP (por ejemplo FileZilla) para conectarte con
    el servidor
3.  Seleccione el directorio en el que desea cargar, y a donde (en su
    mayoría /public_html/ o /htdocs/)
4.  Has clic derecho + selecciona los archivos/carpeta a cargar, o
    arrastrar + de colocar la carpeta que ves en el "Sitio local" la que
    ves en el "Sitio remoto"
5.  La carga de los archivos locales en el servidor remoto comenzará
6.  Después de subir los archivos, consults los "Errores de
    transferencia" para ver si no hay errores

### Copiar la base de datos con phpMyAdmin

La herramienta phpMyAdmin se puede utilizar para exportar e importar una
base de datos, proporcionando una forma sencilla de duplicar una copia
de una base de datos utilizando un nombre diferente en nuestros
servidores.

#### Exportar una copia de la base de datos a tu equipo

1.  Inicia sesión para la base de datos que desea duplicar usando
    phpMyAdmin
2.  Has clic en el nombre de base de datos en el lado izquierdo de la
    página
3.  Selecciona la pestaña Exportar
4.  Selecciona la opción Guardar como archivo
5.  Haga Clic en Continuar

Entonces se te pedirá que guardes el archivo de base de datos en tu
equipo personal.

#### Importar la copia a una nueva base de datos

Primero debes crear la nueva base de datos vacía en el servidor mediante
el panel de control de cuentas. Debe ser UTF8 (utf8_general_ci). Después
que la nueva base de datos se ha creado:

1.  Inicia sesión para la nueva base de datos usando phpMyAdmin
2.  Has clic en el nombre de base de datos en el lado izquierdo de la
    página
3.  Selecciona la pestaña Importar
4.  Has clic en el botón Examinar en "Archivo a importar", a
    continuación, selecciona el archivo de base de datos desde tu equipo
5.  Has clic en Continuar para importar la base de datos

**Hint:** Si ves un mensaje de error "No hay base de datos
seleccionada", es probablemente porque te olvidaste hacer clic primero
en el nombre de base de datos en la columna de la izquierda.

### Cambiar configuration.php

Con el fin de lograr que Joomla! trabaje en el nuevo servidor, debes
hacer los cambios necesarios en el archivo *configuration.php* para
reflejar la nueva configuración del servidor. Debes revisar/editar lo
siguiente:

       var $host = 'localhost'; // usually "localhost". If it's different for your server then your hosting provider should be able to tell you that.
        var $user = 'the_db_username';
        var $db = 'the_databasename';
        var $password = 'the_db_password';
            var $live_site = ''; // is usually empty.
            var $cookie_domain = ''; // Should be empty.

Joomla funciona, incluso si *\$log_path* y *\$tmp_path* están mal, pero
no seráx capaz de instalar extensiones. Inicia sesión en el Lado
Servidor de tu nuevo sitio Joomla.

Ir a: Sistema \> Información del Sistema \> Permisos de Carpetas.  
Mira las últimas 4 filas:

    cache (Cache Directory) Writable
    administrator/cache (Cache Directory)  Writable
    /var/www/some/other/folder/example.com/logs/ (Log directory) Unwritable
    /var/www/some/other/folder/example.com/tmp (Temp directory)  Unwritable

Si el `$og_path` y `$tmp_path` son "No escribible", entonces necesitarás
cambiar los valores en `configuration.php`.

Usa los valores del "Directorio de Caché" sin la parte "/cache/" y de
cambia `$puesta` y `$tmp_path` a

       var $log_path = '/var/www/example.com/logs';
       var $tmp_path = '/var/www/example.com/tmp';

Si los Permisos de Carpetas muestran que `$puesta` y `$tmp_path` son
"Escribible", entonces deberías ser capaz de instalar extensiones.

## Copia de un sitio web mediante la línea de comando SSH (método para usuarios experimentados)

### Copiar los archivos mediante el método de un archivo comprimido

Copiar una gran cantidad de archivos a través de FTP a veces puede ser
poco fiable. Si tienes acceso a la línea de comandos de los sidtemas de
origen y destino, entonces, puedes crear un archivo comprimido que
contenga todos los archivos del sistema de origen, luego, transferir ese
archivo único al sistema de destino, donde puede ser descomprimido.

#### Crear un archivo de almacenamiento

En los sistemas Unix (por ej. Linux) se puede utilizar el programa
**gzip** para crear .los archivos comprimidos, o el programa **tar**
para crear archivos *.tar.gz* o *.tar.bz2*. Para obtener instrucciones
detalladas escribe **man gzip** o **man tar** en la línea de comandos de
la consola de linux. Por ejemplo,

    tar cvfz joomlabackup.tar.gz /path-to-joomla

Creará un archivo comprimido gzip, llamado *joomlabackup.tar.gz*,
conteniendo todos los archivos en tu Instalación Joomla!.

**Nota importante!** Necesitas asegurarte que NO están en la carpeta
donde estás tratando la copia de seguridad al ejecutar el comando tar o
va a crear un bucle sin fin.

#### Extraer un archivo de almacenamiento

Luego de copiar el archivo en el sistema de destino, es necesario
descomprimirlo. Utiliza un comando equivalente al usado para crear el
archivo de almacenamiento. Por ejemplo, para desempaquetar el archivo
creado en el ejemplo anterior, escribe

    cd /path-to-joomla
    tar xvfz joomlabackup.tar.gz

Si el usuario o el Id del grupo no son los mismos entre los sistemas de
origen y destino, entonces tendrás que modificar la propiedad de los
archivos que acabas de extraer. Por ejemplo, en un sistema Apache,
necesitarás introducir el comando

    cd /path-to-joomla
    chown -R www-user:www-group *

para que Apache tenga la propiedad de los archivos de Joomla!.

*Por favor, pregunta a tu proveedor de alojamiento web el grupo y nombre
de usuario correcto `www-group` y `www-user`, en tu sistema.*

### Copiando la base de datos con un método línea de comando de MySQL

Generalmente se ejecuta `mysqldump` para crear una copia de base de
datos:

    $ mysqldump -u user -p db-name > db-name.out

Copia el archivo `db-name.out`, usando sftp/ssh, al servidor MySQL
remoto:

    $ scp db-name.out user@remote.box.com:/backup

Restaurar la base de datos en el servidor remoto (inicio de sesión a
través de ssh):

    $ mysql -u user -p db-name < db-name.out
