<!-- Filename: Setting_up_Apache,_PHP_and_MySQL_manually / Display title: Configuración manual de Apache, PHP y MySQL -->

## Resumen

Aquí tienes un breve resumen de los pasos para configurar Apache, PHP y MySQL en un entorno Windows, y también referenciar varias herramientas relacionadas para mantener y trabajar con la mayoría de las tareas relacionadas con Joomla!.

Para que las instrucciones sean claras y concisas, asumiremos que, donde no se indique ninguna instrucción explícita, dejarás que se apliquen las rutas de instalación predeterminadas sin modificación.

### Advertencia

Si ya tienes instalados en tu máquina alguno de los paquetes AMP preempaquetados:

- Será difícil volver a tu pila AMP. Las diversas instalaciones que realizaremos a continuación sobrescribirán los valores del registro y realizarán cambios generales en el entorno. (Esto se aplica al menos al entorno de PC/Windows).
- Si necesitas mantener alguna configuración (Apache, MySQL o PHP) o datos (tus sitios web existentes y las bases de datos relacionadas), antes de intentar seguir esta instrucción, realiza copias de seguridad adecuadas.

(necesita ser ampliado con consejos específicos sobre cómo lograr lo anterior...)

## Configuración de MySQL

1.  Descarga el <a href="https://dev.mysql.com/downloads/mysql/" rel="nofollow noreferrer noopener">instalador de MySQL</a> apropiado para tu plataforma.
2.  Inicia la instalación y elige la ruta de instalación personalizada.
3.  Haz clic en todo el proceso de instalación y haz clic en Finalizar.
4.  Ahora se te presentará el *Asistente de Configuración de Instancia del Servidor MySQL*.
    1.  Asegúrate de que la *Configuración Estándar* esté seleccionada y haz clic en Siguiente.
    2.  Si ya tienes MySQL instalado, puede que recibas el mensaje *Un servicio de Windows con el nombre MySQL ya existe. Por favor, desinstala este servicio correctamente o elige un nombre diferente para el nuevo servicio.* Si es así, elige un nombre de servicio alternativo.
    3.  En la ventana siguiente, marca *Incluir el Directorio Binario en la Ruta de Windows*. Al hacer esto, podrás acceder a las diversas utilidades de MySQL desde la línea de comandos.
    4.  En la ventana siguiente podrás crear una contraseña para tu usuario root de MySQL, el usuario con el nivel de acceso más alto en tu servidor.
    5.  En la ventana final, todos los cambios que hayas configurado hasta ahora se guardarán cuando presiones el botón *Ejecutar* y se iniciará el servicio de Windows para esta instancia.

### Notas

1.  Para que la instrucción sea lo más accesible posible, omitimos una serie de escenarios de configuración de tu instancia de MySQL, como la posibilidad de ubicar tus archivos de base de datos.
2.  MySQL se instala por defecto con un modo ESTRICTO, lo que podría provocar algunos errores al usar extensiones o aplicaciones que no hayan tenido esto en cuenta.

### Recursos de MySQL

- <a href="https://www.heidisql.com/" class="external text" rel="nofollow noreferrer noopener">HeidiSQL</a> Un reemplazo de cliente completo y extensible de phpMyAdmin en constante desarrollo.
- <a href="https://dev.mysql.com/downloads/workbench/" class="external text" rel="nofollow noreferrer noopener">MySQL Workbench</a> Varias herramientas entre las cuales apreciarás el Administrador, que te ayuda a configurar tu instancia de MySQL. Requiere el <a href="https://dotnet.microsoft.com/en-us/" class="external text" rel="nofollow noreferrer noopener">marco de trabajo .Net</a>.
- <a href="https://www.phpmyadmin.net/" class="external text" rel="nofollow noreferrer noopener">phpMyAdmin</a> Un poderoso cliente web basado para administrar cualquier cosa relacionada con MySQL.
- <a href="https://dev.mysql.com/doc/" class="external text" rel="nofollow noreferrer noopener">Documentación de MySQL</a>

## Configuración de Apache

1.  <a href="https://httpd.apache.org/download.cgi" class="external text" rel="nofollow noreferrer noopener">Descarga el instalador</a> de tu preferencia.
2.  Ejecuta el asistente de instalación y haz clic en cada paso hasta llegar a la ventana de Información del Servidor. Indica las opciones a continuación en el orden dado en cada uno de los campos, a menos que tengas requisitos específicos sobre cómo se configura tu servidor web:
    1.  localhost,
    2.  localhost y
    3.  admin@localhost
3.  Haz clic a través del asistente, que instalará e iniciará el servidor web Apache como un servicio de Windows.
4.  En la barra de estado de Windows, ahora verás una pluma de color rosa con un botón de reproducción verde que indica que Apache está en funcionamiento. Apunta tu navegador a <a href="http://localhost/" rel="nofollow noreferrer noopener">http://localhost/</a> y deberías obtener una página indicando que está funcionando.
5.  Ahora vamos a la ubicación donde Apache está instalado, que comúnmente está en *C:\Program Files\Apache Software Foundation\Apache2.2*, y revisa los diversos directorios:
    1.  *bin* - contiene varios archivos binarios, algunos de los cuales se listan a continuación. Para acceder a estas aplicaciones, la mayoría de las cuales son basadas en comandos, necesitamos agregar la ruta al directorio *bin* en nuestra variable de sistema PATH. Para hacer eso, haz clic derecho en Mi PC \> Propiedades \> Avanzado \> Variables de Entorno y en la lista de Variables del Sistema localiza y selecciona la Variable PATH y haz clic en Editar. Agrega un punto y coma al final si no está ya, seguido de la ruta absoluta a tu directorio bin. Acepta para salir del diálogo Propiedades del Sistema.
        1.  *httpd.exe* que es el servidor web Apache en sí, que se genera en varios procesos hijos mientras sirve tantas solicitudes entrantes simultáneas como lo requiera la directiva MaxClients;
        2.  *ab.exe* es una herramienta de medición comparativa que viene con Apache, permitiéndote ver qué tan bien puede rendir tu aplicación por unidad de tiempo.
    2.  *conf* - carpeta donde se ubican varios archivos de configuración, de los cuales los siguientes son de mayor interés en nuestro caso:
        1.  *httpd.conf* - la mayoría de las directivas del servidor se encuentran en este archivo y para fácil acceso deberías asociar el tipo de archivo *.conf* con un editor de texto más amigable, es decir, algo que no sea el Notepad por defecto.
        2.  *extra\httpd-vhosts.conf* - contiene directivas que te permitirán usar tu servidor local como un host virtual, es decir, capaz de ejecutar varios servidores en tu PC. Un escenario de uso es que durante una fase de desarrollo, si deseas mapear el dominio real para el que estás trabajando a tu copia local, podrás hacerlo realizando pequeños ajustes en este archivo. Discutiremos esto en más detalle a continuación.
    3.  *htdocs* - la raíz del servidor web por defecto, aquí es donde se mapea <a href="http://localhost/" rel="nofollow noreferrer noopener">http://localhost/</a>, es decir, si no la reconfiguras en *httpd.conf* arriba.
    4.  *logs* - registros de acceso y de errores, útiles cuando se intenta abordar varios problemas relacionados con tu servidor o incluso tu aplicación.

### Recursos de Apache

- La <a href="https://httpd.apache.org/docs/current/" class="external text" rel="nofollow noreferrer noopener">documentación de referencia de Apache</a>

## Configuración de PHP

1.  <a href="https://windows.php.net/download/" class="external text" rel="nofollow noreferrer noopener">Descargar PHP</a> y elegir comúnmente VC6 x86 Thread Safe en formato Zip. Las diversas opciones tienen que ver con cómo se compiló la base de código de PHP a binario y probablemente no es algo de lo que debas preocuparte por ahora.
2.  Crea una carpeta en tu C:\Archivos de Programa\\ (o donde se encuentre tu directorio de programas) una carpeta llamada PHP.
3.  Localiza tu archivo Zip descargado, muévelo a la carpeta recién creada y descomprímelo directamente en la carpeta.
4.  Ahora agreguemos la ruta de PHP a nuestra variable de PATH global siguiendo las instrucciones anteriores.

### Configuración de PHP

La configuración consiste en editar el archivo *php.ini*. Un archivo de ejemplo para diferentes escenarios ya está en tu carpeta PHP. Renombremos *php.ini-development* a *php.ini* y ábrelo en tu editor de texto favorito. Los valores comunes para ajustar son los siguientes y todas estas variables están bien documentadas en el archivo *php.ini*. (Ten en cuenta que esta es una configuración a nivel de servidor que se aplica a todos tus proyectos):

- *max_execution_time* - cuando tienes scripts que se ejecutan demasiado tiempo y el servidor devuelve varios resultados inesperados que piensas que se deben a no poder completar todo el proceso
- *memory_limit*
- *error_reporting*
- *display_errors*
- *log_errors* - una variable que necesitarás tener en cuenta en escenarios de producción
- *upload_tmp_dir*
- *upload_max_filesize*
- *extension_dir* - para evitar complicaciones señalaremos el directorio donde se encuentran las siguientes extensiones descomentando esta variable y asignando la ubicación absoluta de la carpeta. La línea completa debería leerse de la siguiente manera:
  extension_dir = "C:\Archivos de Programa\PHP\ext"

- La sección de extensiones dinámicas contiene varios módulos adicionales que deseas cargar, y los comentados son aquellos que vienen preempaquetados con PHP y se pueden encontrar en el directorio *ext* ubicado en tu carpeta PHP. Si deseas activar alguno, simplemente elimina el comentario tal como deberías hacer con las siguientes extensiones:
  - php_curl.dll
  - php_gd2.dll
  - php_mbstring.dll
  - php_mysql.dll
  - php_mysqli.dll
  - php_pdo.dll
  - php_pdo_mysql.dll
  - php_xsl.dll
- session.save_path

### Configuración de Apache para funcionar con PHP

Ahora que hemos configurado PHP para que funcione como queremos, vamos a Apache y hagamos lo mismo.

- Abre *httpd.conf* y en la sección "Soporte de Dynamic Shared Object (DSO)" añade las siguientes directivas. (Si has ubicado tu carpeta PHP de manera diferente, realiza el cambio correspondiente para php5apache2_2.dll a continuación.):
  LoadModule php5_module "C:/Archivos de Programa/PHP/php5apache2_2.dll"
  AddType application/x-httpd-php .php

- En el DirectoryIndex agrega *index.php* e *index.htm* como posibles archivos a servir cuando se solicite un directorio de la siguiente manera:
  DirectoryIndex index.html index.htm index.php

- Al final del archivo añade la siguiente línea que indicará dónde se encuentra el archivo *php.ini*:
  PHPIniDir "C:/Archivos de Programa/PHP"

### Reiniciar y Probar PHP

Tan pronto como realices cualquier cambio en *php.ini*, *httpd.conf* o cualquier otro archivo de configuración, debes reiniciar Apache para ver el efecto de los cambios. Así que ahora reiniciemos Apache usando la herramienta Monitor de Apache que puedes encontrar en la barra de estado de Windows. Esperemos que no se te presenten diálogos y que el Monitor de Apache continúe funcionando en verde.

Ahora probaremos que PHP está funcionando. Dirígete al directorio raíz del documento de tu servidor web (en el caso predeterminado *C:\Archivos de Programa\Apache Software Foundation\Apache2.2\htdocs*) y agrega un archivo llamado *phpinfo.php* con el siguiente contenido:

```php
<?php
phpinfo();
?>
```

Esto mostrará una página que contiene información sobre tu configuración de PHP y acerca de los varios módulos/extensiones que están cargados actualmente. Dirige tu navegador a <a href="http://localhost/phpinfo.php" rel="nofollow noreferrer noopener">http://localhost/phpinfo.php</a>.

### Instalación y Configuración de *xdebug*

1.  Dirige tu navegador a <a href="https://xdebug.org/wizard" class="external text" rel="nofollow noreferrer noopener">Asistente de Instalación de Xdebug</a>. Esta página te ayudará a encontrar una versión adecuada de Xdebug.
2.  Copia toda la página del *phpinfo* que ejecutamos anteriormente y pégala en el área de texto y sigue las instrucciones proporcionadas para instalar.

### Recursos de XDebug

- El <a href="https://www.php.net/docs.php" class="external text" rel="nofollow noreferrer noopener">Manual de PHP</a> proporciona documentación excelente y actualizada con valiosos comentarios adicionales de los usuarios. Hay versiones descargables disponibles.
- La <a href="https://xdebug.org/docs/" class="external text" rel="nofollow noreferrer noopener">Documentación de Xdebug 3</a>

