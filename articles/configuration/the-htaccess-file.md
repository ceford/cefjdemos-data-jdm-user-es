<!-- Filename: Preconfigured_htaccess / Display title: El archivo htaccess.txt  -->

## Introducción

Un servidor web Apache utiliza un archivo .htaccess para la configuración específica del sitio.
Se entrega con Joomla un archivo htaccess preconfigurado (`htaccess.txt`). Se encuentra ubicado en el directorio raíz de Joomla y contiene instrucciones para evitar ataques comunes de hackers e implementar URLs SEF. Si Joomla está instalado en un subdirectorio, puede haber un archivo `.htaccess` adicional en el directorio superior. Apache procesa cada uno de ellos por turno.

La práctica normal es renombrar el `htaccess.txt` suministrado por Joomla a
`.htaccess` junto con la selección de configuraciones de SEO en el panel de
Configuración Global. Tu servicio de hosting puede añadir configuraciones
adicionales a .htaccess, por lo que puede ser mejor combinar tu archivo
.htaccess con cualquier archivo .htaccess del sistema que ya exista.

### Configuración de la plataforma

El archivo activo se establece en uno de los archivos httpd.conf con:
```
    AccessFileName .htaccess
```
Por defecto, es .htaccess (lo que lo hace oculto en sistemas de archivos tipo Unix). No hay necesidad de cambiarlo.

En la plataforma Windows podrías cambiarlo a:

    AccessFileName htaccess.ini

para poder editarlo más fácilmente.

No realices cambios en `htaccess.txt` porque podría ser sobrescrito por una
actualización de Joomla y se perderían los cambios.

## Actualizaciones de Joomla

El archivo htaccess.txt puede cambiar de una versión de Joomla a otra. Si tienes dudas, o si ocurren problemas extraños después de la actualización, asegúrate de que tu archivo .htaccess esté actualizado. Este es el contenido del archivo `htaccess.txt` incluido con Joomla 5.1:

```bash
##
# @package    Joomla
# @copyright  (C) 2005 Open Source Matters, Inc. <https://www.joomla.org>
# @license    Licencia Pública General de GNU versión 2 o posterior; ver LICENSE.txt
##

##
# ¡LEE ESTO COMPLETAMENTE SI ELIGES UTILIZAR ESTE ARCHIVO!
#
# La línea 'Options +FollowSymLinks' puede causar problemas con algunas configuraciones de servidor.
# Es necesaria para el uso de Apache mod_rewrite, pero es posible que ya haya sido establecida por
# el administrador de tu servidor de una manera que impide cambiarla en este archivo .htaccess.
# Si al usarlo tu sitio produce un error, coméntalo (agrega # al inicio de la línea), recarga tu sitio
# en el navegador y prueba tus URLs amigables. Si funcionan, entonces ha sido establecido por el
# administrador de tu servidor y no necesitas establecerlo aquí.
##

## ERRORES DE CSS O JAVASCRIPT FALTANTES

# Si tu sitio se ve extraño después de habilitar este archivo, entonces probablemente tu servidor ya
# está comprimiendo los archivos css y js, y deberías comentar la sección GZIP de este archivo.
##

## OPENLITESPEED
#
# Si estás utilizando un servidor web OpenLiteSpeed, cualquier cambio realizado en este archivo
# no tendrá efecto hasta que reinicies el servidor web.
##

## Puede ser comentado si causa errores, ver notas arriba.
Options +FollowSymlinks
Options -Indexes

## Sin listados de directorio
<IfModule mod_autoindex.c>
    IndexIgnore *
</IfModule>

## Suprimir la detección de tipo MIME en navegadores para tipos desconocidos
<IfModule mod_headers.c>
    Header always set X-Content-Type-Options "nosniff"
</IfModule>

## Protégete contra ciertas solicitudes de origen cruzado. Se puede encontrar más información aquí:

## https://developer.mozilla.org/es/docs/Web/HTTP/Política_de_Recursos_de_Origen_Cruzado_(CORP)

## https://web.dev/why-coop-coep/
#<IfModule mod_headers.c>
#    Header always set Cross-Origin-Resource-Policy "same-origin"
#    Header always set Cross-Origin-Embedder-Policy "require-corp"
#</IfModule>

## Desactivar JavaScript en línea al abrir archivos SVG directamente o al incrustarlos con la etiqueta object
<FilesMatch "\.svg$">
  <IfModule mod_headers.c>
    Header always set Content-Security-Policy "script-src 'none'"
  </IfModule>
</FilesMatch>

## Estas directivas solo están habilitadas si el módulo mod_rewrite de Apache está habilitado
<IfModule mod_rewrite.c>
    RewriteEngine On

    ## Inicio - Reglas de reescritura para bloquear algunos exploits comunes.
    # Si experimentas problemas en tu sitio, comenta las operaciones listadas
    # abajo añadiendo un # al inicio de la línea.
    # Esto intenta bloquear el tipo más común de intentos de exploit en Joomla!
    #
    # Bloquear cualquier script que intente base64_encode datos dentro de la URL.
    RewriteCond %{QUERY_STRING} base64_encode[^(]*\([^)]*\) [OR]
    # Bloquear cualquier script que incluya una etiqueta <script> en la URL.
    RewriteCond %{QUERY_STRING} (<|%3C)([^s]*s)+cript.*(>|%3E) [NC,OR]
    # Bloquear cualquier script que intente establecer una variable PHP GLOBALS vía URL.
    RewriteCond %{QUERY_STRING} GLOBALS(=|\[|\%[0-9A-Z]{0,2}) [OR]
    # Bloquear cualquier script que intente modificar una variable _REQUEST vía URL.
    RewriteCond %{QUERY_STRING} _REQUEST(=|\[|\%[0-9A-Z]{0,2})
    # Devolver encabezado 403 Forbidden y mostrar el contenido de la página de inicio raíz
    RewriteRule .* index.php [F]
    #
    ## Fin - Reglas de reescritura para bloquear algunos exploits comunes.

    ## Inicio - Redirecciones personalizadas
    #
    # Si necesitas redirigir algunas páginas, o establecer una redirección canónica no-www a
    # www (o viceversa), coloca ese código aquí. Asegúrate de que esas
    # redirecciones usen la sintaxis correcta de RewriteRule y las banderas [R=301,L].
    #
    ## Fin - Redirecciones personalizadas

    ##
    # Descomenta la siguiente línea si la URL de tu servidor web
    # no está directamente relacionada con rutas de archivos físicas.
    # Actualiza tu directorio de Joomla! (solo / para la raíz).
    ##

    # RewriteBase /

    ## Inicio - Sección SEO básica de Joomla!.
    #
    # Solución PHP FastCGI para la Autorización HTTP, requerida para la aplicación API
    RewriteRule .* - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]
    # -- URLs SEO para la aplicación API
    # Si la ruta solicitada comienza con /api, el archivo no es /api/index.php
    # y la solicitud no se ha reescrito internamente ya al
    # script api/index.php
    RewriteCond %{REQUEST_URI} ^/api/
    RewriteCond %{REQUEST_URI} !^/api/index\.php
    # y la ruta y archivo solicitados no coinciden directamente con un archivo físico
    RewriteCond %{REQUEST_FILENAME} !-f
    # y la ruta y archivo solicitados no coinciden directamente con una carpeta física
    RewriteCond %{REQUEST_FILENAME} !-d
    # reescribir internamente la solicitud al script /api/index.php
    RewriteRule .* api/index.php [L]
    # -- URLs SEO para la aplicación de frontend pública
    # Si la ruta y archivo solicitados no son /index.php y la solicitud
    # no se ha reescrito internamente ya al script index.php
    RewriteCond %{REQUEST_URI} !^/index\.php
    # y la ruta y archivo solicitados no coinciden directamente con un archivo físico
    RewriteCond %{REQUEST_FILENAME} !-f
    # y la ruta y archivo solicitados no coinciden directamente con una carpeta física
    RewriteCond %{REQUEST_FILENAME} !-d
    # reescribir internamente la solicitud al script index.php
    RewriteRule .* index.php [L]
    #
    ## Fin - Sección SEO básica de Joomla!.
</IfModule>

## Estas directivas solo están habilitadas si el módulo mod_rewrite de Apache está deshabilitado
<IfModule !mod_rewrite.c>
    <IfModule mod_alias.c>
        # Cuando el módulo mod_rewrite de Apache no está disponible, indicamos una redirección temporal
        # de la página de inicio al controlador frontal explícitamente para que el sitio web
        # y los enlaces generados todavía puedan utilizarse.
        RedirectMatch 302 ^/$ /index.php/
        # RedirectTemp no puede ser usado en su lugar
    </IfModule>
</IfModule>

## GZIP & BROTLI
## Estas directivas solo están habilitadas si el módulo mod_headers de Apache está habilitado.
## Esta sección verificará si existe un archivo .gz y, de ser así, lo transmitirá
## directamente o de forma alternativa comprimir cualquier recurso al vuelo
## Si tu sitio comienza a verse extraño después de habilitar este archivo, y ves
## ERR_CONTENT_DECODING_FAILED en la pestaña de red de la consola de tu navegador,
## entonces tu servidor ya está comprimiendo los archivos css y js, y no necesitas esto
## Bloque habilitado en tu .htaccess
<IfModule mod_headers.c>
    # Servir archivos CSS comprimidos con gzip si existen
    # y el cliente acepta gzip.
    RewriteCond "%{HTTP:Accept-encoding}" "gzip"
    RewriteCond "%{REQUEST_FILENAME}\.gz" -s
    RewriteRule "^(.*)\.css" "$1\.css\.gz" [QSA]

    # Servir archivos JS comprimidos con gzip si existen
    # y el cliente acepta gzip.
    RewriteCond "%{HTTP:Accept-encoding}" "gzip"
    RewriteCond "%{REQUEST_FILENAME}\.gz" -s
    RewriteRule "^(.*)\.js" "$1\.js\.gz" [QSA]

    # Servir tipos de contenido correctos y prevenir doble compresión con mod_deflate.
    RewriteRule "\.css\.gz$" "-" [T=text/css,E=no-gzip:1,E=no-brotli:1]
    RewriteRule "\.js\.gz$" "-" [T=text/javascript,E=no-gzip:1,E=no-brotli:1]

    <FilesMatch "(\.js\.gz|\.css\.gz)$">
        # Servir tipo de codificación correcto.
        Header set Content-Encoding gzip

        # Obligar a los proxies a cachear archivos css/js
        # comprimidos y no comprimidos por separado.
        Header append Vary Accept-Encoding
    </FilesMatch>
</IfModule>
```

*Traducido por openai.com*
