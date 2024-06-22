<!-- Filename: Moving_the_site_among_directories/sub-directories / Display title: Mover el sitio entre directorios/subdirectorios -->

Muchas veces instalas Joomla! en un subdirectorio y luego deseas moverlo
a un directorio superior. A continuación te mostramos como hacerlo.

Supongamos que tienes instalado Joomla! en la siguiente carpeta:
public_html/tryjoomla. Ahora que estás contento con tu sitio web, deseas
moverlo a public_html.

1\. Mueve todos los archivos del subdirectorio (por ejemplo:
public_html/tryjoomla) al nivel superior (ejemplo: public_html). Puedes
usar tu cliente favorito FTP o el panel de control que te ofreca la
empresa de hosting.

2\. Descarga y abre el archivo configuration.php en un editor de texto.

3\. Borra el nombre de la carpeta de la ruta. Busca las siguientes
líneas en el archivo:

    var $live_site = '';
    var $log_path = '/home/username/public_html/tryjoomla/administrator/logs';
    var $tmp_path = '/home/username/public_html/tryjoomla/tmp';
    var $ftp_root = 'public_html/tryjoomla';

Cambiar a:

    var $live_site = '';
    var $log_path = '/home/username/public_html/administrator/logs';
    var $tmp_path = '/home/username/public_html/tmp';
    var $ftp_root = 'public_html';

Ten en cuenta que la variable \$live_site en muy pocas ocasiones debe
tener un valor, sin embargo, si durante la instalación se le asignó un
valor, debes modificar dicha ruta también.

    var $live_site = 'http://www.example.com/tryjoomla';

Cambiar a:

    var $live_site = 'http://www.example.com';

4\. Revisa el archivo .htaccess de tu sitio web. El subdirectorio debe
eliminarse de dicho archivo también. La directiva RewriteBase debe ser
comentada. Busca una línea de RewriteRule que contenga el antiguo
subdirectorio.

5\. Verifica que ninguna redirección que apunte al antiguo subdirectorio
exista en el panel de control de tu hosting.

Si tienes la caché activa, ingresa al administrador de Joomla! (el cual
estará ahora en
<a href="http://www.example.com/administrator" class="external free"
target="_blank"
rel="nofollow noreferrer noopener">http://www.example.com/administrator</a>
y no en <a href="http://www.example.com/tryjoomla/administrator"
class="external free" target="_blank"
rel="nofollow noreferrer noopener">http://www.example.com/tryjoomla/administrator</a>).
Ve a Herramientas -\> Limpiar Caché y borra todos los archivos de caché.
