<!-- Filename: Enabling_HTTPS_on_your_site / Display title: Habilitando HTTPS en tu sitio web -->

<a
href="https://docs.joomla.org/index.php?title=Security_Checklist/TOC/es&amp;action=edit&amp;redlink=1"
class="new"
title="Security Checklist/TOC/es (page does not exist)">Security
Checklist/TOC/es</a>

## ¿Qué es SSL/TLS?

Seguridad de la Capa de Transporte (TLS, del inglés Transport Layer
Security) es el sucesor de Capa de Puertos Seguros (SSL, del inglés
Secure Sockets Layer), aunque la mayoría todavía le denomina SSL. Habrás
visto el símbolo de candado que aparece junto a la barra de navegación
de la mayoría de navegadores. Significa que los datos que envías al
sitio web están siendo cifrados así que, si alguien entra en tu red (o
similares) y puede interceptar tus peticiones, no es capaz de ver los
datos, solo las URLs a las que accedes.

## ¿Por qué usar TLS?

Google (y la mayoría de buscadores) ahora tratan a los sitios con https
con preferencia<sup>[\[1\]](#cite_note-1)</sup>. Además los navegadores
alertan de peligro en sitios con formularios (como el de inicio de
sesión o de contacto) que no estén usando
https<sup>[\[2\]](#cite_note-2)</sup>

## ¿Cómo configuro TLS?

Para configurar un certificado, la manera más sencilla es solicitarlo al
proveedor de alojamiento web.

El certificado correcto a comprar depende de los requerimientos de
protección de seguridad en tu sitio. Si no sabes probablemente la formas
más barata y fácil sea usando
<a href="https://letsencrypt.org/" class="external text" target="_blank"
rel="nofollow noreferrer noopener">Let's Encrypt</a> - es gratuito y
dependiendo de tu servidor se puede configurar directamente desde el
panel de control.

Si has adquirido un dirección IP dedicada y un certificado SSL,
simplemente solicita ayuda a tu proveedor y lo firmará e instalará en la
ubicación correcta por ti.

## Cómo enviar todo el tráfico a https

### En Joomla

La manera más sencilla es configurarlo en Joomla. En la Configuración
Global hay una opción "Forzar https" que permite establecer HTTPS solo
en el área de administración o en todo el sitio. Esta última opción es
la ideal.

<img
src="https://docs.joomla.org/images/thumb/6/6d/Enable_HTTPS_In_Global_Config-en.png/800px-Enable_HTTPS_In_Global_Config-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/6/6d/Enable_HTTPS_In_Global_Config-en.png/1200px-Enable_HTTPS_In_Global_Config-en.png 1.5x, https://docs.joomla.org/images/6/6d/Enable_HTTPS_In_Global_Config-en.png 2x"
data-file-width="1512" data-file-height="1012" width="800" height="535"
alt="Image Showing the Force HTTPS option in the Joomla 3.x default backend template" />

### En .htaccess

    RewriteEngine on
    RewriteCond %{SERVER_PORT} !^443$
    RewriteRule .* https://%{HTTP_HOST}%{REQUEST_URI} [QSA,R=301,L]

    Redirect permanent / https://www.yourdomainname.com

#### Ejemplos más complejos de .htaccess

Como por ejemplo, para cambiar de HTTP a HTTPS en páginas que tengan
'abc/def' o 'ghi' en la URL, se añade algo como lo siguiente:

Código:

    RewriteCond %{HTTPS} off
    RewriteRule ^(abc/def|ghi)(.*)/?$ https://%{HTTP_HOST}%{REQUEST_URI} [R=301,NC,L]

... y para cambiar de HTTPS de vuelta a HTTP en cualquier página que
tiene 'home' o 'help' en la URL, hay que utilizar:

Código:

    RewriteCond %{HTTPS} on
    RewriteRule ^(home|help)(.*)/?$ http://%{HTTP_HOST}%{REQUEST_URI} [R=301,NC,L]

Si se quiere forzar SSL para un directorio específico se puede insertar
el siguiente código en el archivo .htaccess del directorio específico:

Código:

    RewriteEngine On 
    RewriteCond %{REQUEST_URI} folder 
    RewriteRule ^(.*)$ https://www.example.com/folder/$1 [R,L]

En la segunda línea se debe establecer el nombre del directorio. También
hay que asegurarse reemplazar www.example.com/folder por el dominio y el
nombre de directorio adecuados en los que se quiere forzar SSL.

1.  <span id="cite_note-1">[↑](#cite_ref-1) <a
    href="https://webmasters.googleblog.com/2014/08/https-as-ranking-signal.html"
    class="external free" target="_blank"
    rel="nofollow noreferrer noopener">https://webmasters.googleblog.com/2014/08/https-as-ranking-signal.html</a></span>
2.  <span id="cite_note-2">[↑](#cite_ref-2) <a
    href="https://www.blog.google/products/chrome/milestone-chrome-security-marking-http-not-secure/"
    class="external free" target="_blank"
    rel="nofollow noreferrer noopener">https://www.blog.google/products/chrome/milestone-chrome-security-marking-http-not-secure/</a></span>
