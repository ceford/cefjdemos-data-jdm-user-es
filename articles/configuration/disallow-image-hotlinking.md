<!-- Filename: How_do_you_block_direct_hot_linking_to_image_files_using_htaccess%3F / Display title: Prohibir el Hotlinking de Imágenes  -->

## Definición

El "hotlinking" es la práctica de enlazar una imagen en un sitio web desde un artículo en otro sitio web. Puede ser una práctica muy útil. Este sitio web utiliza muchas imágenes que en realidad se encuentran en el sitio web docs.joomla.org. Esto ahorra tiempo y esfuerzo necesarios para crear capturas de pantalla y en el ancho de banda de este sitio. Sin embargo, puede haber problemas de derechos de autor y es posible que desees evitar que tus imágenes se utilicen de esta manera.

El método descrito aquí utiliza un archivo *.htaccess*, que es una característica del servidor Apache. Otros servidores web pueden ofrecer otros métodos para prevenir el hotlinking.

## Instrucciones

Coloque el siguiente código en el archivo *.htaccess* de su directorio raíz.
```
<IfModule mod_rewrite.c>
    RewriteEngine on
    RewriteCond %{HTTP_REFERER} !^$
    RewriteCond %{HTTP_REFERER} !^http(s)?://(www\.)?yourdomain.com [NC]
    RewriteCond %{HTTP_REFERER} !^http(s)?://(www\.)?google.com [NC]
    RewriteRule \.(jpg|jpeg|png|gif|webp|svg)$ - [NC,F,L]
</IfModule>
```

### Explicación

* La primera RewriteCond permite solicitudes directas usando una URL, sin referer.
* La segunda RewriteCond permite solicitudes desde su propio dominio. La bandera *\[NC\]* 
  significa *No Case*, es decir, coincidir con caracteres en mayúsculas y minúsculas.
* La tercera RewriteCond permite solicitudes desde Google, para que sus imágenes 
  puedan seguir apareciendo en los resultados de búsqueda. Puede agregar líneas similares 
  para cualquier otro sitio que desee permitir.
* La RewriteRule bloquea solicitudes para archivos de imagen desde todos los dominios que no 
  se han permitido previamente. La bandera F le dice al navegador que devuelva un encabezado 
  Prohibido (403). L significa última regla.

### Bloquear Hot Linking desde Dominios Específicos

Para detener el hotlinking desde dominios específicos solamente, como *myspace.com*, 
*blogspot.com* y *livejournal.com*, mientras permite que otros sitios web enlacen a sus 
imágenes, use el siguiente código:

```
<IfModule mod_rewrite.c>
    RewriteEngine On
    RewriteCond %{HTTP_REFERER} ^http(s)?://(.+\.)?myspace\.com/ [NC,OR]
    RewriteCond %{HTTP_REFERER} ^http(s)?://(.+\.)?blogspot\.com/ [NC,OR]
    RewriteCond %{HTTP_REFERER} ^http(s)?://(.+\.)?livejournal\.com/ [NC]
    RewriteRule \.(jpg|jpeg|png|gif|webp|svg)$ - [NC,F,L]
</IfModule>
```

Puede agregar tantos dominios diferentes como desee. Cada línea *RewriteCond* excepto la 
última debe terminar con las banderas *\[NC,OR\]*. *NC* significa ignorar mayúsculas y 
minúsculas. *OR* significa "O Siguiente", es decir, coincide con esta línea **o** la siguiente línea. 
La última *RewriteCond* omite la bandera *OR* para detener la coincidencia después de la 
última *RewriteCond*.

