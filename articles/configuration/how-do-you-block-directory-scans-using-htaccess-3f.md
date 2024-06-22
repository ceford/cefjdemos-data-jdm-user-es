<!-- Filename: How_do_you_block_directory_scans_using_htaccess%3F / Display title: Cómo bloquear análisis del directorio usando htaccess? -->

**Las instrucciones**

Agrega reglas de reescritura de Apache tu archivo `.htaccess`. Por
ejemplo, el siguiente va a redirigir todos los intentos de acceso a
archivos con nombres que comienzan con "phpMyAdmin" a `index.php`.

  
**Ejemplo de la Regla de Reescritura de Apache**

    RewriteRule ^/phpMyAdmin.*$ /index.php

  
**Algunos Consejos de Expresiones Regulares**

    ^ Significa inicio de nombre del archivo
    . Significa cualquier carácter que no sea el de nueva línea
    * Significa uno o más de los caracteres anteriores
    $ Significa final de línea
