<!-- Filename: Enabling_Search_Engine_Friendly_(SEF)_URLs_on_Apache / Display title: URLs SEF en Apache  -->

## Verificar que .htaccess está habilitado

Compruebe que su archivo de configuración de Apache permita las anulaciones mediante .htaccess. Debe asegurarse de que las anulaciones estén habilitadas o el archivo .htaccess en el directorio raíz de su Joomla! será ignorado o causará un error. En la sección de su archivo de configuración de host virtual o en el archivo de configuración principal (`httpd.conf`), debe tener algo similar al siguiente ejemplo que habilite las anulaciones:

```bash
<Directory "/home/user/public_html">
  AllowOverride All
</Directory>

<Directory "/path/to/htdocs">
  AllowOverride All Options=[una opción],[una opción],...
</Directory>
```

Existen otras formas de comprobar si `.htaccess` está habilitado si no tienes acceso a los archivos de configuración de tu sitio. Consulte el <a href="http://httpd.apache.org/docs/current/howto/htaccess.html"
rel="nofollow noreferrer noopener">tutorial de .htaccess</a> que se encuentra en el sitio web de
<a href="http://www.apache.org/"
rel="nofollow noreferrer noopener">The Apache Software Foundation</a> para obtener información adicional.

## Paso a paso

Estas son instrucciones paso a paso. Por favor, síguelas en el orden en que se presentan aquí. Si un paso falla, **no** continúes hasta que hayas resuelto el problema.

1. Renombra el archivo `"htaccess.txt"` en la carpeta base de tu Joomla! a `".htaccess"`.
2. *Este paso puede no ser necesario.* Abre `.htaccess` en un editor de texto. Descomenta `RewriteBase /` (elimina el primer carácter, \#). Si Joomla está instalado en su propia carpeta, ingresa el nombre de la carpeta de Joomla después de la barra inclinada. por ejemplo, `RewriteBase /tucarpetaedjoomla`.
3. Inicia sesión en tu panel de administración y abre la Configuración Global.
4. Activa la opción **Usar reescritura URL/mod_rewrite de Apache** y *Guarda*. Esta opción utiliza la función *mod_rewrite* de Apache para eliminar la parte "index.php" de la URL.

    Verifica si tu sitio funciona correctamente. Tus URLs ahora deberían verse así:

        http://www.example.com/the-­news/1­-latest-­news/1-­welcome-­to­-joomla

    Si esta opción causa errores, por favor consulta [Cómo verificar si mod_rewrite está habilitado en tu servidor](https://docs.joomla.org/How_to_check_if_mod_rewrite_is_enabled_on_your_server).

    - Si no está habilitado y tienes acceso al archivo `apache/conf/httpd.conf`, abre ese archivo y verifica si la línea `LoadModule rewrite_module modules/mod_rewrite.so` está descomentada. Si es necesario, descomenta la línea y reinicia el servidor web Apache.
    - Si *mod_rewrite* no puede ser habilitado, deja esta opción desactivada. No importa si dejas el archivo `.htaccess` renombrado.
5. *Si crees que esto es necesario*, activa **Agregar sufijo a las URLs** y *Guarda*. Esta opción añade `.html` al final de las URLs. Hay diferentes opiniones sobre si esto es necesario o incluso útil. Los motores de búsqueda no parecen preocuparse si tus URLs terminan en `.html` o no.
6. Abre el Administrador de Plugins y activa el plugin **Sistema - SEF**. Este plugin añade soporte SEF a los enlaces en tus artículos de Joomla. Opera directamente sobre el HTML y no requiere una etiqueta especial.
