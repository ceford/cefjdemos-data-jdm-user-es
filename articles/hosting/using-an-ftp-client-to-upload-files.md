<!-- Filename: Using_an_FTP_client_to_upload_files / Display title: El uso de un cliente FTP para subir archivos -->

Dado que muchas empresas de hosting no permiten a sus usuarios el acceso
shell/local a sus archivos, los usuarios que deseen enviar (upload) los
nuevos archivos a su espacio de alojamiento deben hacer uso de un
Programa de Transferencia de Archivos. Clientes
<a href="http://es.wikipedia.org/wiki/File_Transfer_Protocol"
class="extiw" title="es.wp:File Transfer Protocol">FTP</a> permiten a
los usuarios subir archivos que se han editado localmente a un servidor.
Hay una gran variedad de clientes
<a href="http://es.wikipedia.org/wiki/File_Transfer_Protocol"
class="extiw" title="es.wp:File Transfer Protocol">FTP</a> disponibles y
<a href="https://en.wikipedia.org/wiki/Comparison_of_FTP_clients"
class="extiw" title="wikipedia:Comparison of FTP clients">este
gráfico</a> detalla muy bien los puntos fuertes de numerosos programas
populares, muchos de los cuales son de código abierto y/o libre para
descargar.

Si estás usando Firefox, podemos sugerirte
<a href="http://fireftp.mozdev.org/" class="external text"
target="_blank" rel="nofollow noreferrer noopener">FireFTP</a> como un
útil complemento. FireFTP será utilizado para este tutorial.

Puede que desees habilitar la visualización de archivos ocultos, de modo
que no pierdas tu .htaccess (en un cuadro de linux) al cargar.

## Utilizando el Explorador de Windows

Si tienes un Sistema Operativo Windows instalado, puedes utilizar el
Explorador de Windows para conectarse a FTP.

### Lanzando el Explorador de Windows

Las imágenes que siguen están tomados de Windows Vista, pero el proceso
sigue siendo idéntico.

Hay muchas maneras de iniciar el Explorador de Windows. Simplemente
puedes abrir una carpeta o desde Mi Equipo, o puedes presionar la
**Tecla de Windows** y pulsar **R**. Escribe **explorer.exe** y has clic
en "Ejecutar"'.

<img src="https://docs.joomla.org/images/f/f2/Runexplorer-en.png"
decoding="async" data-file-width="427" data-file-height="233"
width="427" height="233" alt="Runexplorer-en.png" />

### La conexión a FTP

Para conectarse a Tu servidor FTP, se requiere la información de inicio
de sesión proporcionadA por el host o el administrador. En la barra de
direcciones, escribe **`ftp://USERNAME:PASSWORD@example.com`** sustituir
el nombre de usuario, contraseña y example.com con tus propias
credenciales. Si estás ejecutando Windows Vista, te puede ser requerido
que hagas doble clic en la barra de direcciones para habilitar al
usuario para introducir el texto. Presiona el botón **enter** en tu
teclado una vez que haya rellenado los datos correctamente y el
Explorador de Windows se conectara a tu servidor FTP.

Si introdujiste las credenciales de forma incorrecta, recibirás un error
similar a este:

<img src="https://docs.joomla.org/images/2/2a/Errorwindowsftp-en.png"
decoding="async" data-file-width="496" data-file-height="345"
width="496" height="345" alt="Errorwindowsftp-en.png" />

Si este es el caso, vuelve a introducir tus datos de usuario en los
campos correspondientes y prueba de nuevo.

Deberías ver una página con la lista de todas las carpetas/archivos en
el servidor similar a la siguiente imagen:

<img
src="https://docs.joomla.org/images/a/ab/Connectedwindowsftp-en.png"
decoding="async" data-file-width="680" data-file-height="411"
width="680" height="411" alt="Connectedwindowsftp-en.png" />

*Por razones de seguridad se han eliminado `los archivos/carpetas` en la
captura de pantalla de ejemplo*

### Transferencia de archivos

La ventaja de utilizar el Explorador de Windows como tu aplicación FTP
es que lo más probable es que esté familiarizado con la forma de
transferir los archivos de trabajo. La interfaz es la misma que si
fueras a copiar/mover a otra carpeta en tu computadora.

El truco es trabajar fuera de la carpeta donde vas a subir los archivos.
En la mayoría de los casos, tendrás que cargarlos en una carpeta llamada
**"public_html"**, **"htdocs"** o **"www"**. Tendrás que ver esto con tu
host o el administrador.

Para cargar un archivo, basta con arrastrar el archivo desde la carpeta
original en la ventana que está conectado a tu servidor FTP. He aquí un
ejemplo:

<img src="https://docs.joomla.org/images/0/07/Transferftpwin-en.png"
decoding="async" data-file-width="1069" data-file-height="566"
width="1069" height="566" alt="Transferftpwin-en.png" />

### Cerrar tu conexión FTP

Para cerrar la conexión FTP, simplemente cierra la ventana del
Explorador de Windows. Para ello, pulsa la **X** roja en la esquina
superior derecha de la ventana, como en la siguiente captura de
pantalla.

<img src="https://docs.joomla.org/images/8/86/Closewin-en.png"
decoding="async" data-file-width="380" data-file-height="201"
width="380" height="201" alt="Closewin-en.png" />

## El Uso de FireFTP

<a href="http://fireftp.mozdev.org/" class="external text"
target="_blank" rel="nofollow noreferrer noopener">FireFTP</a> es una
gran herramienta para la transferencia FTP si utilizas Mozilla FireFox.

### El lanzamiento de FireFTP

Para comenzar la transferencia de un archivo, abre FireFox, a
continuación, has clic en **Herramientas \>\> FireFTP**. FireFTP se
abrirá en una nueva pestaña.

<img src="https://docs.joomla.org/images/8/8d/Fireftpmenu-en.png"
decoding="async" data-file-width="226" data-file-height="280"
width="226" height="280" alt="Fireftpmenu-en.png" />

### Configurar tus detalles de FTP

Si esta es la primera vez que te conectas a un servidor FTP, tendrás que
configurar FireFTP para conectarte al servidor apropiado. Necesitas
obtener los detalles de tu host o administrador.
