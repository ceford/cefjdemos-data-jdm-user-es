<!-- Filename: Moving_the_site_among_directories/sub-directories / Display title: Mover el Directorio de Instalación -->

Muchas veces instalas Joomla en un subdirectorio y luego quieres moverlo a un directorio de nivel superior. Aquí tienes un breve tutorial sobre cómo hacerlo.

Supongamos que has instalado Joomla en la siguiente carpeta: public_html/tryjoomla. Ahora que estás satisfecho con el sitio, querrás moverlo a public_html.

1. Mueve todos los archivos del subdirectorio (es decir, public_html/tryjoomla) al directorio de nivel superior (es decir, public_html). Puedes usar tu cliente FTP favorito o el panel de control que proporciona tu servicio de alojamiento.
2. Descarga y abre el archivo configuration.php en un editor de texto.
3. Simplemente elimina el nombre de la carpeta tryjoomla de la ruta. Busca las siguientes líneas:
    ```
    var $live_site = '';
    var $log_path = '/home/username/public_html/tryjoomla/administrator/logs';
    var $tmp_path = '/home/username/public_html/tryjoomla/tmp';
    var $ftp_root = 'public_html/tryjoomla';
    ```
    Cambia a:
    ```
    var $live_site = '';
    var $log_path = '/home/username/public_html/administrator/logs';
    var $tmp_path = '/home/username/public_html/tmp';
    var $ftp_root = 'public_html';
    ```
    Nota: La variable \$live_site rara vez necesita un valor. Pero si se le asignó un valor durante la instalación, edita esa ruta también.
    ```
    var $live_site = 'http://www.example.com/tryjoomla';
    ```
    Cambia a:
    ```
    var $live_site = 'http://www.example.com';
    ```
4. Revisa el archivo .htaccess de tu sitio. El subdirectorio también debe ser eliminado allí. La directiva RewriteBase debe estar comentada. Busca una RewriteRule que contenga el antiguo subdirectorio.
5. Verifica que no existan órdenes de redirección al antiguo subdirectorio en el panel de control de tu alojamiento.
6. Si tienes la caché habilitada, inicia sesión en el backend del administrador (que ahora estará en `http://www.example.com/administrator` y no en `http://www.example.com/tryjoomla/administrator`). Ve a Sistema / Caché y elimina todos los archivos de caché.

*Traducido por openai.com*
