<!-- Filename: Enabling_Search_Engine_Friendly_(SEF)_URLs_on_Apache / Display title: Activas URLs optimizadas para motores de búsqueda (SEF) en Apache -->

  
Las URLs **Amigables a los Buscadores (SEF)**,**legibles por humanos** o
\[<a href="http://es.wikipedia:Clean_URL%7CURLs" class="external text"
target="_blank" rel="nofollow noreferrer noopener">semánticas</a>\] son
URLs que tienen sentido para los seres humanos y los buscadores, porque
explican la ruta a la página concreta que apuntan. Desde la versión 1.5,
Joomla! es capaz de crear y procesar URLs en cualquier formato,
incluyendo URLs SEF. Esto no depende de la reescritura de URL ejecutada
por el servidor web, por lo que funciona incluso si Joomla! ejecuta un
servidor distinto de Apache con el módulo **mod_rewrite**. Las URLs SEF
siguen cierto patrón fijo, pero el usuario puede definir un [texto
descriptivo corto
(alias)](https://docs.joomla.org/Alias "Special:MyLanguage/Alias") para
cada segmento de la URL.

Internamente, la parte local de una URL SEF (la parte después del nombre
de dominio) se llama "ruta"'. Por lo tanto, la creación y el
procesamiento de las URLs SEF se conoce como "enrutamiento", y el código
correspondiente es llamado un '"enrutador"'.

Este artículo trata sobre las URLs amigables (SEF) en el servidor web
Apache. La implementación de URLs SEF es posible en los servidores IIS
de Microsoft también. Por favor revisa [Activar URLs optimizadas para
motores de búsqueda (SEF) en
IIS](https://docs.joomla.org/Enabling_Search_Engine_Friendly_(SEF)_URLs_on_IIS "Special:MyLanguage/Enabling Search Engine Friendly (SEF) URLs on IIS").

A partir de Joomla!
<img src="https://docs.joomla.org/images/d/da/Compat_icon_1_6.png"
decoding="async" data-file-width="40" data-file-height="17" width="40"
height="17" alt="Joomla 1.6" />, las urls SEF están activadas por
defecto. En versiones anteriores debes ir a la configuración global para
activarlas. Las siguientes instrucciones también sirven si deseas
utilizar la reescritura de URL con mod_rewrite de Apache.

## Verifica que .htaccess está habilidado

Verifica que la configuración de Apache permite sobreescribir el
.htaccess. Debes asegurarte que las sobreescrituras del .htaccess son
permitidas, de lo contrario el .htaccess ubicado en el directorio raíz
de Joomla! será ignorado o generará un error. En la sección del archivo
de configuración de hosts virtuales o en el archivo de configuración
principal (`httpd.conf`) debes tener algo similar al ejemplo que
mostramos a continuación:

      AllowOverride All



      AllowOverride All Options=[an option],[an option],...

Hay otras formas de probar si `.htaccess` está activo si no tienes
acceso a los archivos de configuración de tu sirio web. Por favor revisa
el <a href="http://httpd.apache.org/docs/current/howto/htaccess.html"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">tutorial de .htaccess</a> que se
encuentra en el sitio web de
<a href="http://www.apache.org/" class="external text" target="_blank"
rel="nofollow noreferrer noopener">Apache</a> para obtener información
adicional.

## Paso a paso

Por favor sigue estas instrucciones paso a paso. Si un paso no funciona,
**no** continúes hasta que hayas resuelto el problema.

1.  Renombra el archivo `"htaccess.txt"` en el directorio raíz de
    Joomla! a `".htaccess"`

2.  "Este paso puede no ser necesario." Abre el archivo `.htaccess` en
    un editor de texto, quita el comentario de la línea `RewriteBase /`
    (quita el primer caracter, \#). Si Joomla! está instalado en su
    propia carpeta, entonces escribe el nombre de dicha carpeta después
    de la barra oblicua. Ejemplo: `RewriteBase /directoriojoomla`.

3.  Ingresa al administrador de Joomla! y entra a configuración global.

4.  Activa la opción **Utilizar reescritura de URL/mod_rewrite de
    Apache** y *Guardar*. Esta opción utiliza la función de apache
    *mod_rewrite* para eliminar la porción de *index.php* de la URL.

    Verifica si tu sitio web funciona correctamente. Las URL deben verse
    ahora así:

        http://www.example.com/the-­news/1­-latest-­news/1-­welcome-­to­-joomla

    Si esta opción genera errores, por favor visita [Como verificar si
    mod_rewrite está activado en tu
    servidor](https://docs.joomla.org/How_to_check_if_mod_rewrite_is_enabled_on_your_server "Special:MyLanguage/How to check if mod rewrite is enabled on your server").

    - Si no está activdao y tienes acceso al archivo
      `apache/conf/httpd.conf`, abre dicho archivo y verifica si la
      línea `LoadModule rewrite_module modules/mod_rewrite.so` está sin
      comentar (o sea, sin el caracter \# al inicio). De ser necesario,
      remueve el comentario de la línea y reinicia el servidor web
      Apache.
    - Si *mod_rewrite* no puede activarse, no actives la opción. No
      importa si dejas el archivo `.htaccess` con ese nombre.

5.  *Si crees que es necesario*, activa **Agregar sufijo a las URL** y
    *Guardar*. Esta opción agrega `.html` al final de las URL.Hay
    diferentes opiniones al respecto sobre si es necesario o útil. Al
    parecer a los motores de búsqueda no les importa si sus URL terminan
    en `.html` o no.

6.  Abrir el administrador de plugins y activar el plugin **Sistema -
    SEF**. Este plugin agrega soporte SEF a los enlaces en los artículos
    de Joomla!. Este opera directamente en el código HTML y no requiere
    una etiqueta especial.
