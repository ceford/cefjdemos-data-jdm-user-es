<!-- Filename: Nginx / Display title: Nginx  -->

<a href="http://nginx.org/"
rel="nofollow noreferrer noopener">Nginx</a> es un servidor web ligero
que impulsa
<a href="https://es.wikipedia.org/wiki/Nginx"
rel="nofollow noreferrer noopener">alrededor del 33%</a> de los
servidores web en todos los dominios. A menos que tengas requisitos específicos que
exijan un servidor web pesado como Apache, es mucho mejor usar
Nginx.

A continuación se presentan las instrucciones sobre cómo poner en
marcha Joomla! con el <a
href="https://www.nginx.com/resources/wiki/start/topics/examples/phpfcgi/"
rel="nofollow noreferrer noopener">ejemplo de PHP FastCGI</a>.
## Instalar Nginx

Para Ubuntu, ejecuta *aptitude install Nginx*. Para otras distribuciones, ejecuta el gestor de paquetes correspondiente o consulta la <a href="https://www.nginx.com/resources/wiki/start/topics/tutorials/install/" rel="nofollow noreferrer noopener">página de instalación de Nginx</a>.

## Instalar PHP FastCGI

Para Ubuntu, lee el <a href="https://www.nginx.com/resources/wiki/start/topics/examples/phpfcgi/" rel="nofollow noreferrer noopener">Ejemplo de PHP FastCGI</a>.

Para Gentoo, PHP se ejecutará como un servicio FastCGI (FPM), por lo que el servidor Nginx ejecutará PHP como un proceso separado:

    # echo "dev-lang/php gd gd2 curl simplexml tokenizer dom tidy sqlite xml fpm cgi" >> /etc/portage/package.use
    # emerge php

La configuración predeterminada de PHP-FPM es adecuada para la mayoría de los servidores. Para configuraciones especiales, visita el
<a href="http://php.net/manual/en/install.fpm.php" rel="nofollow noreferrer noopener">sitio de PHP FPM</a>.

## Configurar Nginx

Los archivos de configuración de Nginx se encuentran en:

- `/etc/nginx/sites-available/` en Ubuntu (para los sitios que se ejecutan
  en esa instancia de Nginx)
- `/etc/nginx/nginx.conf` en Gentoo y Raspbian (Debian optimizado para
  Raspberry Pi)

Aquí hay un archivo de configuración de Nginx de ejemplo, *joomla.conf*, que puedes reutilizar en todos tus sitios habilitados para Nginx.

    server {
      listen 80;
        server_name TU_DOMINIO;
        server_name_in_redirect off;

        access_log /var/log/nginx/localhost.access_log;
        error_log /var/log/nginx/localhost.error_log info;

        root RUTA_EN_SERVIDOR;
        index index.php index.html index.htm default.html default.htm;
        # Soporte para URLs Limpias (también conocidas como Amigables para Motores de Búsqueda)
        location / {
            try_files $uri $uri/ /index.php?$args;
        }

        # agregar encabezado global x-content-type-options
        add_header X-Content-Type-Options nosniff;

        # denegar la ejecución de scripts dentro de directorios escribibles
        location ~* /(images|cache|media|logs|tmp)/.*\.(php|pl|py|jsp|asp|sh|cgi)$ {
            return 403;
            error_page 403 /403_error.html;
        }

        location ~ \.php$ {
          fastcgi_pass  127.0.0.1:9000;
          fastcgi_index index.php;
          include fastcgi_params;
          fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
          include /etc/nginx/fastcgi.conf;
        }

        # caché de archivos
        location ~* \.(ico|pdf|flv)$ {
            expires 1y;
        }

        location ~* \.(js|css|png|jpg|jpeg|gif|swf|xml|txt)$ {
            expires 14d;
        }

    }

Presta atención a algunas cosas:

1.  El parámetro *fastcgi_pass* está configurado en *127.0.0.1:9000*,
    correspondiente al puerto en el que FPM está configurado para escuchar.
    Esto significa que puedes ejecutar los procesos PHP en servidores
    separados. En Gentoo, puedes encontrar esta configuración en el archivo
    */etc/php/fpm-php5.3/php-fpm.conf/*.
2.  No olvides reemplazar TU_DOMINIO y RUTA_EN_SERVIDOR según tu dominio y la
    ruta de Joomla en tu servidor.

## Soporte para GZip

Si necesitas soporte para la compresión GZip, añade la siguiente sección a la
sección *http* del archivo de configuración principal de Nginx:

    gzip on;
    gzip_http_version 1.1;
    gzip_comp_level 6;
    gzip_min_length 1100;
    gzip_buffers 4 8k;
    gzip_types text/plain application/xhtml+xml text/css application/xml application/xml+rss text/javascript application/javascript application/x-javascript
    gzip_proxied any;
    gzip_disable "MSIE [1-6]\.";

## Fuentes

- <a href="https://wiki.gentoo.org/wiki/Nginx"
rel="nofollow noreferrer noopener">Nginx en Gentoo</a>
- <a href="https://kevinworthington.com/nginx-for-windows/"
  rel="nofollow noreferrer noopener">Nginx para Windows</a>
- <a
  href="https://ubuntu.com/tutorials/install-and-configure-nginx#1-overview"
  rel="nofollow noreferrer noopener">Nginx en Ubuntu</a>
- <a
  href="https://www.debianadmin.com/howto-install-nginx-webserver-in-debian.html"
  rel="nofollow noreferrer noopener">Nginx en Debian</a>
- <a href="https://www.php.net/manual/en/install.fpm.php"
  rel="nofollow noreferrer noopener">Instalación y
  configuración de PHP-FPM</a>
- <a
  href="https://docs.nginx.com/nginx/admin-guide/web-server/compression/"
  rel="nofollow noreferrer noopener">Compresión y Descompresión</a>
- <a href="https://www.nginx.com/blog/creating-nginx-rewrite-rules/"
  rel="nofollow noreferrer noopener">Creación de Reglas de Reescritura de NGINX</a>
- <a href="http://nginx.org/en/docs/http/request_processing.html"
  rel="nofollow noreferrer noopener">Cómo procesa una solicitud Nginx</a>

*Traducido por openai.com*

