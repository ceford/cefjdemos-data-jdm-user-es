<!-- Filename: Nginx / Display title: Nginx -->

<a href="http://nginx.net/" class="external text" target="_blank"
rel="nofollow noreferrer noopener">nginx</a> es un servidor web ligero
utilizado en alrededor de 13% de todos los servidores web del
mundo<a href="http://en.wikipedia.org/wiki/Nginx#Description"
class="external autonumber" target="_blank"
rel="nofollow noreferrer noopener">[1]</a>. Nginx es una mejor opción
que Apache, a menos que tengas requerimientos específicos que exijan un
servidor web mucho más pesado.

A continuación encontrarás las instrucciones para ejecutar Joomla! con
<a href="http://wiki.nginx.org/PHPFcgiExample" class="external text"
target="_blank" rel="nofollow noreferrer noopener">nginx y PHP via
FastCGI</a>.

## Instalar nginx

En Ubuntu, ejecuta `aptitude install nginx`. En otras distribuciones,
ejecuta el administrador de paquetes correspondiente, o visita
<a href="http://wiki.nginx.org/Install" class="external free"
target="_blank"
rel="nofollow noreferrer noopener">http://wiki.nginx.org/Install</a>.

## Instalar PHP FastCGI

Si usas Ubuntu, lee esta excelente página acerca de como
<a href="http://wiki.nginx.org/PHPFcgiExample" class="external text"
target="_blank" rel="nofollow noreferrer noopener">configurar PHP y
FastCGI para nginx</a>.

En Gentoo, PHP se ejecutará como un servicio FastCGI (fpm), de esa
manera el servidor nginx ejecutará PHP como un proceso separado:

    # echo "dev-lang/php gd gd2 curl simplexml tokenizer dom tidy sqlite xml fpm cgi" >> /etc/portage/package.use
    # emerge php

Los parámetros por defecto de php-fpm funcionan de manera adecuada para
la mayoría de servidores. Si necesitas configuraciones especiales,
visita el
<a href="http://php.net/manual/en/install.fpm.php" class="external text"
target="_blank" rel="nofollow noreferrer noopener">sitio de PHP FPM</a>.

## Configurar Nginx

Los archivos de configuración de nginx se encuentran en:

- `/etc/nginx/sites-available/` en Ubuntu (para sitios ejecutándose en
  esa instancia de nginx)
- `/etc/nginx/nginx.conf` en Gentoo y Raspbian (= Debian optimizado para
  Raspberry Pi)

Este es un ejemplo de archivo de configuración de nginx, joomla.conf, el
cual puedes reutilizar en todos tus sitios que usen nginx.

    server {
      listen 80;
        server_name YOUR_DOMAIN;
        server_name_in_redirect off;

        access_log /var/log/nginx/localhost.access_log;
        error_log /var/log/nginx/localhost.error_log info;

        root PATH_ON_SERVER;
        index index.php index.html index.htm default.html default.htm;
        # Support Clean (aka Search Engine Friendly) URLs
        location / {
            try_files $uri $uri/ /index.php?$args;
        }

        # add global x-content-type-options header
        add_header X-Content-Type-Options nosniff;

        # deny running scripts inside writable directories
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

        # caching of files 
        location ~* \.(ico|pdf|flv)$ {
            expires 1y;
        }

        location ~* \.(js|css|png|jpg|jpeg|gif|swf|xml|txt)$ {
            expires 14d;
        }

    }

Presta atención a algunos detalles:

1.  El parámetro `fastcgi_pass` tiene el valor 127.0.0.1:9000, el cual
    corresponde al puerto asignado a fpm para que 'escuche' o monitoree.
    Esto significa que puedes ejecutar los procesos de PHP en servidores
    separados. En Gentoo, puedes encontrar esta configuración en
    `/etc/php/fpm-php5.3/php-fpm.conf/`
1.  No olvides reemplazar los valores YOUR_DOMAIN & PATH_ON_SERVER por
    tu dominio y la ruta de Joomla en tu servidor.

## Soporte GZip

Si necesitas soporte para compresión GZip, agrega la siguiente sección a
la sección http del archivo de configuración principal de nginx:

    gzip on;
    gzip_http_version 1.1;
    gzip_comp_level 6;
    gzip_min_length 1100;
    gzip_buffers 4 8k;
    gzip_types text/plain application/xhtml+xml text/css application/xml application/xml+rss text/javascript application/javascript application/x-javascript
    gzip_proxied any;
    gzip_disable "MSIE [1-6]\.";

## Fuentes

- <a href="https://wiki.gentoo.org/wiki/Nginx" class="external text"
  target="_blank" rel="nofollow noreferrer noopener">Nginx in Gentoo</a>
- <a href="https://kevinworthington.com/nginx-for-windows/"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Nginx for Windows</a>
- <a
  href="https://ubuntu.com/tutorials/install-and-configure-nginx#1-overview"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Nginx in Ubuntu</a>
- <a
  href="https://www.debianadmin.com/howto-install-nginx-webserver-in-debian.html"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Nginx in Debian</a>
- <a href="https://www.php.net/manual/en/install.fpm.php"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">PHP-FPM installation and
  configuration</a>
- <a
  href="https://docs.nginx.com/nginx/admin-guide/web-server/compression/"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Compression and Decompression</a>
- <a href="https://www.nginx.com/blog/creating-nginx-rewrite-rules/"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Creating NGINX Rewrite Rules</a>
- <a href="http://nginx.org/en/docs/http/request_processing.html"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">How Nginx processes a request</a>
