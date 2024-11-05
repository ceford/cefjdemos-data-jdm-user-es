<!-- Filename: Adding_www_to_a_url / Display title: Agregar www a una URL  -->

## Expresiones Regulares de Apache .htaccess

Para una solución sencilla, añade lo siguiente a tu archivo `.htaccess`:

```bash
    RewriteEngine On
    RewriteCond %{HTTP_HOST} !^(www\.example\.com)?$ [NC]
    RewriteRule (.*) https://www.example.com/$1 [R=301,L]
```

En este caso, una URL de la forma `https://example.com/index.php?item=1` será redirigida a `https://www.example.com/index.php?item=1`.

En el ejemplo anterior:

* `RewriteCond` define una condición de prueba.
* `%{HTTP_HOST}` utiliza la variable de host de la solicitud (example.com).
* `!` significa NO y `^` significa INICIO - por lo tanto, no comienza con www.example.com
* `(` y `)` capturan lo que esté entre paréntesis para uso de referencia posterior.
* `\` convierte el siguiente carácter de un carácter de control a un carácter real.
* `.` generalmente significa cualquier carácter, pero precedido por \ significa un punto.
* `?` hace que la coincidencia sea opcional.
* `$` significa FIN (de la coincidencia opcional).
* `[NC]` significa sin mayúsculas, es decir, insensible a mayúsculas y minúsculas.
* `RewriteRule` es válido si la URL no comienza con www.
* `(.*)` es un patrón, en este caso un solo carácter repetido 0 o más veces, lo que significa la parte de la ruta de la URL. Se captura como $1.
* `https://www.example.com/` es el reemplazo para la parte de host de la URL.
* `$1` es la ruta capturada.
* `[]` contiene banderas - instrucciones sobre qué hacer.
* `R=301` es una instrucción para enviar un encabezado de Movido Permanentemente.
* `L` significa Último en el conjunto - dado que se ha encontrado una coincidencia ignora cualquier regla subsiguiente.

Una solución más completa que soluciona varios otros problemas de canonización al mismo tiempo:

    RewriteEngine On
    #
    RewriteCond %{THE_REQUEST} ^[A-Z]{3,9}\ /([^/]+/)*index\.html?\ HTTP/
    RewriteRule ^(([^/]+/)*)index\.html?$ http://www.example.com/$1 [R=301,L]
    #
    RewriteCond %{THE_REQUEST} !^POST
    RewriteCond %{THE_REQUEST} ^[A-Z]{3,9}\ /([^/]+/)*index\.php\ HTTP/
    RewriteCond %{SERVER_PORT}>s ^(443>(s)|[0-9]+>s)$
    RewriteRule ^(([^/]+/)*)index\.php$ http%2://www.example.com/$1 [R=301,L]
    #
    RewriteCond %{HTTP_HOST} !^(www\.example\.com)?$
    RewriteRule (.*) http://www.example.com/$1 [R=301,L]

Si deseas entender qué significa todo esto, puedes leer estos artículos:

* [Introducción a Apache mod_rewrite](https://httpd.apache.org/docs/2.4/rewrite/intro.html)
* [Introducción a Redirecciones .htaccess](https://www.danielmorell.com/guides/htaccess-seo/redirects/introduction-to-redirects)

*Traducido por openai.com*

