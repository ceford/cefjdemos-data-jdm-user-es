<!-- Filename: https://magazine.joomla.org/all-issues/may-2022/joomla-new-http-headers-plugin-for-j4 / Display title: Encabezados HTTP -->

## Artículo de Revista

Este artículo se basa en un artículo de la Revista de la Comunidad de Joomla! por Brendan Hedges en la Edición de Mayo de 2022.

Aunque está escrito para Joomla 4, el contenido se aplica igualmente a Joomla 5.  

## Nuevo Plugin de Encabezados HTTP de Joomla para J4

Siguiendo con el artículo del mes pasado sobre seguridad, contraseñas y el plugin WebAuthn de Joomla, este mes vamos a examinar otra característica de seguridad de Joomla que se lanzó con J4. Se trata del plugin de Encabezados HTTP, que ahora está incluido como parte de las funciones principales de Joomla.

Internet está en constante desarrollo, y Joomla nunca se queda atrás. Por eso lo elijo como mi plataforma de desarrollo web preferida. No importa si tu sitio web es pequeño, como una página de una tienda familiar, o una plataforma de comercio electrónico completamente desarrollada con millones en ventas, el framework de Joomla tiene algo para todos y siempre está buscando implementar nuevas tecnologías. Algunas incluso son innovadoras.

> La introducción del plugin de Encabezados HTTP en el núcleo de Joomla 4 es un gran avance para ayudar a asegurar tu sitio web frente a ataques y actividades maliciosas.

Este plugin de seguridad del sistema ayuda a los propietarios de sitios a configurar fácilmente los Encabezados de Seguridad HTTP desde el backend familiar de Joomla, en lugar de tener que hurgar en el archivo htaccess u otros archivos de configuración. O, aún peor, el Cpanel de tu alojamiento web.

¡Mira lo complicado que es configurarlo en Cpanel y dime que no cometerías un error! Y todo esto suponiendo que, una vez instalado el framework en Apache y creados los directorios, sepas el formato correcto para agregar los encabezados HTTP que deseas integrar.

¿Cuántas veces has intentado implementar un comando htaccess solo para recargar tu sitio web y luego enfrentarte a un error http500?

El mayor problema es que si no obtienes el formato perfecto de tu Encabezado HTTP, romperás tu sitio.

Incluso entonces, lo que funciona para un sitio web puede no funcionar para otro. Un buen ejemplo de esto es mi archivo htaccess y la forma en que configuro el navegador para cargar una versión no-www https de mi sitio web:
```
##www a no-www y mezcla de http a https
RewriteCond %{HTTPS} off [OR]
RewriteCond %{HTTP_HOST} ^www\. [NC]
RewriteRule ^ https://misitio.co.uk%{REQUEST_URI} [R=301,L,NE]
##Fin de www a no-www y mezcla de http a https
```

Esto funcionó muy bien para mi anterior empresa de alojamiento. Pero cuando me cambié a otro host, dejó de funcionar. ¡Ve a saber!

El código htaccess que ahora tengo que usar para lograr el mismo resultado es el siguiente:
```
##www a no-www y mezcla de http a https
RewriteCond %{HTTP_HOST} ^www\.(.*)$ [NC]
RewriteRule ^(.*)$ https://%1/$1 [R=301,L]
RewriteCond %{ENV:HTTPS} !on
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [R=301,L]
##Fin de www a no-www y mezcla de http a https
```

¿Confuso, verdad? Y si cometes un solo error en el formato, ¡BAM! ¡Has roto tu sitio web! Bueno, al menos hasta que corrijas tu código.

Por eso, mantener las cosas simples, como parte del núcleo de Joomla, significa menos frustración, menos tiempo perdido buscando en Google tus errores y más tiempo para celebración mientras te recuestas en tu silla y admiras tu nuevo sitio web.

Así que, echemos un vistazo a lo que realmente son los encabezados HTTP, cómo puedes encontrar el plugin y qué puedes hacer con ellos. Vale la pena mencionar aquí que esta función de Joomla es una función avanzada de Joomla, que está más adaptada a sitios web con datos sensibles, en lugar del nuevo sitio web que has creado con tanto cariño sobre tus adorables gatitos. Sin embargo, dicho esto, incluso los sitios web simples deben ser lo más seguros posible para evitar que se ejecute código malicioso después de que hayan hackeado tu sitio web.

## ¿Qué son las cabeceras HTTP?

No se debe confundir las cabeceras HTTP con la sección &lt;head&gt; de tu documento HTML. Son completamente diferentes. Las cabeceras HTTP son el preámbulo entre tu servidor web y el navegador. Un conjunto de instrucciones que le dicen al navegador qué mostrar, o más importante, qué no mostrar al visitante.

Puedes ver las cabeceras HTTP y cómo se relacionan con objetos HTML individuales en las Herramientas de Desarrollo de tu navegador. En Google Chrome, abre las Herramientas de Desarrollo, luego la pestaña Red. Ahora actualiza la página web y haz clic en un elemento HTML en el panel izquierdo. Se mostrará la cabecera HTTP para ese elemento en el panel derecho.

Puedes ver en la imagen a continuación que la imagen resaltada está devolviendo un estatus HTTP de 200, por lo que el navegador la encontró. También hay una serie de otra información vinculada a ese elemento, como el tamaño del archivo y las fechas de edición.

![Cabeceras HTTP de Joomla 1](../../../en/images/security/http-headers-dev-tools-headers.png "")

Si uno de tus elementos HTML no se ha mostrado, también puedes obtener una pista sobre la razón en las cabeceras HTTP. En este ejemplo, la segunda imagen no se ha mostrado y puedes ver en la información mostrada en el panel derecho que no hay información de cabecera HTTP.

Excepto el mensaje críptico:

**Política de Referencia:** 'strict-origin-when-cross-origin'

'Strict-origin-when-cross-origin' simplemente significa que cuando un elemento HTML (una imagen en este caso) se sirve desde una fuente diferente (no tu servidor), entonces se debe seguir la política de cabecera HTTP establecida en ese momento. En este ejemplo, las cabeceras HTTP, como se establecen en el plugin de Joomla, rechazarán todas las imágenes que no provengan de este sitio web o de un sitio web diferente que esté específicamente 'incluido' en los parámetros de cabecera HTTP establecidos en el plugin de cabecera HTTP de Joomla.

Por lo tanto, cuando la imagen se llama desde el documento HTML, el navegador la rechaza y no se carga.

![Cabeceras HTTP de Joomla 2](../../../en/images/security/http-headers-dev-tools-headers-reject.png "")

Esto difiere de no encontrarse y devolver un mensaje de error HTTP 404 no encontrado. En esta situación, la imagen todavía está siendo buscada en el servidor que la aloja, pero el navegador no la ha encontrado.

![Cabeceras HTTP de Joomla 3](../../../en/images/security/http-headers-dev-tools-headers-not-found.png "")

## Lo que hace el plugin Joomla HTTP Headers

Además de indicar al navegador qué mostrar y devolver información general sobre el documento HTML, los encabezados HTTP ayudan a mitigar ataques y vulnerabilidades de seguridad que puedas tener en tu sitio web Joomla. Ahí es donde el plugin Joomla HTTP Headers entra en juego. Lo logra mostrando explícitamente contenido HTML basado en tus configuraciones en el propio plugin Joomla HTTP Headers.

Al agregar encabezados HTTP basados en seguridad extra a tu sitio web Joomla con el plugin HTTP Header, estarás proporcionando una capa adicional de seguridad para tu sitio web Joomla.

Esto es importante porque, por defecto, una página web HTML mostrará todo su contenido a tu visitante, sea bueno o malo. A menos que se le indique explícitamente que no lo haga en los encabezados HTTP de la página web. El plugin hace esto permitiéndote configurar las opciones avanzadas de seguridad disponibles para ti en la Política de Seguridad de Contenidos (Content-Security-Policy) de tu sitio web. El plugin se puede configurar de manera diferente para cada sitio web dependiendo de tus requisitos, por lo que es un arma verdaderamente flexible en tu arsenal contra los hackers.

## ¿Por qué necesito este complemento?

En un mundo ideal, no lo necesitarías. Sin embargo, en el mundo en el que vivimos, hay demasiadas personas sin escrúpulos intentando encontrar maneras de ganar dinero a costa de los inocentes e incautos. En nuestro mundo, nos referimos a estas personas como hackers. Los hackers se esfuerzan en explotar vulnerabilidades en el software para obtener beneficios económicos, a menudo en detrimento del dueño del sitio web.

Al utilizar el complemento HTTP Header de Joomla para controlar qué contenido se sirve a tus visitantes, reduces las posibilidades de que los hackers puedan servir contenido malicioso a tus visitantes a través de plugins desactualizados y vulnerables. Lo cual ayuda a detener las inyecciones de scripts maliciosos en tu sitio web.

**Así que, pensemos en esta situación hipotética por un minuto.**

Tienes un bonito sitio web Joomla 3. Fue creado hace 5 años, y todavía se ve y funciona perfectamente. Todos tus componentes, complementos y módulos están actualizados. Perfecto, ¿verdad?

Bueno, no del todo, porque cuando creaste tu sitio web hace 5 años, instalaste el moderno complemento Foo Bar para imprimir "FOO BAR" en tu página de inicio. Al principio parecía genial, pero después de un tiempo cambiaste de opinión y eliminaste el shortcode del complemento {foo}FOO - BAR{/bar} de tu artículo de la página de inicio.

Pero, aquí está el problema: no despublicaste ni desinstalaste el complemento en sí y su uso se desvaneció de la memoria. **Esto es algo de lo que TODOS somos culpables, estoy seguro.**

Avanzando rápidamente hasta hoy, 5 años después, ese complemento todavía está allí, publicado y activo en tu sitio web, pero no se ha actualizado en 5 años porque hace mucho tiempo que lo olvidaste o el autor dejó de darle soporte. Ahora, algún individuo nefasto ha descubierto que este complemento tiene una vulnerabilidad de seguridad que puede explotarse para iniciar un ataque de **Cross Site Scripting (XSS)** en tu sitio web, y convertir a tus visitantes desprevenidos en víctimas.

Cross-site scripting, también conocido como XSS, es una vulnerabilidad de seguridad en tu sitio web que permite a un atacante comprometer las interacciones que tus usuarios tienen con tu ahora vulnerable sitio web.

El atacante/hacker utiliza XSS para explotar tu sitio web vulnerable y enviar un script malicioso a tu usuario desprevenido. Debido a que el script proviene de tu sitio web, el navegador de tu usuario no sabe ni sospecha que el script no debería ser confiable y lo ejecuta cuando la página web se carga y se abre.

Los scripts maliciosos que se ejecutan de esta manera pueden causar muchos problemas a tu usuario, desde robar contraseñas de inicio de sesión y datos de nombres de usuario guardados en cookies, hasta redirigir a tu usuario a sitios de phishing falsos. Los scripts incluso pueden cambiar la apariencia de la página web que tu sitio está sirviendo y mostrar diferentes anuncios.

Usar el **complemento HTTP Headers de Joomla** ayuda a detener el cross-site scripting asegurando que solo los scripts y contenido que deseas servir a tu visitante sean realmente servidos. Todo lo demás queda bloqueado.

Así que, en el ejemplo anterior, podrías haber configurado el complemento HTTP Headers para servir solo los archivos JavaScript (script) de tu sitio web desde una carpeta especificada, o tal vez un CDN si usas uno, para detener el ataque.

También podrías detener el sitio web de ejecutar JavaScript en línea que está incrustado en el HTML. Pero, ten en cuenta que dependiendo de cómo hayas diseñado el HTML de tu sitio web, esto podría causar problemas más adelante.

Esto ayudaría a detener la ejecución de código JavaScript malicioso en tu sitio web. Incluso si tu vulnerable complemento Foo Bar fuera el culpable de que un hacker pudiera inyectar código malicioso en tu sitio web en primer lugar.

**Nota:**

> Los puntos débiles comunes en los sitios web que son propensos a ataques XSS son formularios de entrada de usuario (páginas de inicio de sesión de usuario, formularios de suscripción a boletines, formularios de contacto, etc.) sin validación y cifrado.

## ¿Dónde está el plugin de HTTP Headers?

Puedes encontrar el plugin de HTTP Headers de Joomla junto con todos los demás plugins de Joomla, y se accede de la misma manera a la que estás acostumbrado.

![Joomla http headers 4](../../../en/images/security/http-headers-plugins.png "")

## Usando el Plugin de Encabezados HTTP

Usar el Plugin HTTP de Joomla es relativamente sencillo, aunque puede ser una buena idea, antes de hacer cambios en la configuración predeterminada, familiarizarse con algunos de los términos especiales relacionados con su uso. Aunque, al decir eso, algunos de ellos ya deberían resultarte familiares.

**Por ejemplo:**

Al tratar con imágenes, verás el término 'img-src', donde 'img' se refiere a imágenes y 'src' a la fuente válida de la imagen. Estos son términos con los que ya estamos familiarizados desde el HTML básico.

Al final de este artículo, hay una lista de sitios web útiles con información adicional para ayudarte a usar este plugin de Joomla.


## Configuración del Plugin de Cabeceras HTTP - PESTAÑA 2

### Strict-Transport-Security (HSTS)

**La pestaña de Política de Seguridad de Transporte Estricto está desactivada por defecto.**

![Joomla http headers 12](../../../en/images/security/http-headers-plugins-headers-strict-transport-security.png "")

Me encanta investigar, porque a veces te encuentras con momentos de asombro auténtico. Este es uno de esos momentos.

Wikipedia dice:

> Netscape Communications creó HTTPS en 1994 para su navegador web Netscape Navigator. Originalmente, HTTPS se usaba con el protocolo SSL. A medida que SSL evolucionó hacia el Protocolo de Seguridad de la Capa de Transporte (TLS), HTTPS fue especificado formalmente por RFC 2818 en mayo de 2000. Google anunció en febrero de 2018 que su navegador Chrome marcaría los sitios HTTP como "No Seguro" después de julio de 2018. Este movimiento fue para alentar a los propietarios de sitios web a implementar HTTPS, como un esfuerzo para hacer el World Wide Web más seguro." …...

¿Quién habría pensado que Netscape inventó los protocolos HTTPS hace tanto tiempo? Lo que es aún más sorprendente es cuánto tiempo tomó implementarlo en el internet que conocemos y amamos hoy en día.

Durante años, nos han instado, intimidando y finalmente amenazado, para implementar HTTPS en todos nuestros sitios web. La mayoría de nosotros capitulamos y la World Wide Web ahora finalmente está segura. ¿O no?

Hay, sin embargo, algunos rezagados, incondicionales o sitios web olvidados que todavía están usando solo HTTP para entregar su contenido, aunque con una advertencia de Google/Firefox, etc. de "Este sitio web no es seguro".

Una búsqueda rápida en Google arrojó varias listas desactualizadas de esos sitios web "solo culpables de HTTP". Aunque desde que se publicaron esas listas, muchos sitios web han actualizado a HTTPS. Sin embargo, hubo algunas exclusiones obvias de organizaciones que uno pensaría deberían saber mejor.

Por ejemplo:

* NGINX (http://nginx.org/)
* GNU (http://www.gnu.org/)
* La Universidad de Washington (http://www.washington.edu/)

Según w3techs.com, alrededor del 20% de todos los sitios web todavía están corriendo solo en HTTP.

**Entonces, ¿por qué es esto un problema?**

Esto es un problema porque cualquier dato siendo enviado desde y recibido por el navegador de un usuario está en riesgo de ser interceptado. Lo conocemos como un **ataque de intermediario en el medio (man-in-the-middle)**. Ahora, esto puede no parecer una consideración importante si su sitio web es solo sobre imágenes de lindos gatitos.

![instantánea de lindos gatitos](../../../en/images/security/http-headers-plugins-headers-kittens.jpg "")

Pero incluso sitios web simples pueden convertirse en víctimas de hackers y atacantes que implementarán **click-jacking** y otros ataques de origen cruzado que dañarán a sus usuarios.

Un sitio web que no intercambia datos de usuario o información de inicio de sesión, **debería usar HTTPS**.

**Bien, volvamos al tema.**

Como ya sabes, el objetivo de HTTPS es introducir una conexión segura entre el navegador del usuario y tu servidor. Una conexión en la que cualquier intercambio de datos ocurre en un entorno seguro que no puede ser interceptado y copiado por un tercero. Un hombre en el medio.

![ataque de hombre en el medio](../../../en/images/security/http-headers-plugins-headers-man-in-middle.png "")

Pero, ¿sabías que a menos que tu **Certificado SSL de HTTPS** use **TLS**, tu conexión 'segura' no es tan segura como esperarías? Las conexiones HTTPS sin TLS siguen siendo **vulnerables a ataques de intermediario en el medio**.

Aunque es una publicación de blog antigua, este artículo explica bien cómo funciona un ataque de hombre en el medio.

Los navegadores han adoptado ampliamente TLS.

Y, TLS 1.3 no es directamente compatible con versiones anteriores a menos que se esté ejecutando en modo de compatibilidad. Lo que podría plantear un problema para algunos.

![información del certificado TLS](../../../en/images/security/http-headers-plugins-headers-tls.png "")

Usar el Plugin de Cabeceras HTTP de Joomla para manejar Strict-Transport-Security (HSTS) ayuda a mitigar ataques de intermediario en el medio al imponer el uso de TLS en el navegador web de tus visitantes. TLS asegura que toda la comunicación web se realice en el lado del cliente usando una capa de transporte segura.

**¿Estás usando una redirección 301 para servir la versión no segura HTTP de tu sitio web a la versión segura HTTPS?**

La mayoría lo hace. Las redirecciones 301 son instrucciones que la mayoría de los propietarios de sitios web configuran en su archivo .htaccess. Le hacen saber a Google que la versión del sitio web que debe usarse es la HTTPS (segura). El problema con esto es que **el 301 es solo una redirección URL**, por lo que tu sitio web todavía realiza algún elemento de la conexión inicial sobre HTTP.

A diferencia de las conexiones entre un usuario y un servidor de sitio web que usan HSTS, donde el servidor automáticamente interactúa con él solo usando HTTPS.

HSTS tiene una debilidad, sin embargo, ya que la primera conexión inicial entre el navegador del usuario y el servidor web todavía ocurre a través de HTTP. Pero todas las conexiones subsiguientes se conectan automáticamente vía HTTPS hasta que se alcanza la fecha de expiración del encabezado HTTP y este encabezado se restablece.

Esto es a diferencia de una redirección estándar 301 donde cada carga de página incluye una solicitud http inicial para iniciar la conexión https.

Hay una solución a esta debilidad en las configuraciones de HSTS de Cabeceras HTTP, activa 'Preload'.

Lo que agregará la etiqueta 'Preload' al encabezado de respuesta.

En la configuración, también hay una lista de precarga de enlaces**. Esta es una lista que está codificada en muchos navegadores modernos. La lista informa al navegador que la conexión a example.com solo debe hacerse a través de HTTPS. Eliminando así la necesidad de incluso hacer la conexión inicial vía HTTP.

![precarga HSTS](../../../en/images/security/http-headers-plugins-headers-enter-domain.png "")

Una vez que HSTS está configurado en el plugin de cabeceras HTTP de Joomla, se añaden todas las etiquetas necesarias al encabezado de respuesta HTTP. Esto le permite a cualquier navegador de usuario que esté tratando de conectarse a tu servidor que todas las conexiones **deben hacerse con HTTPS**, ya sea especificado en tu HTML o no.

En resumen, usar el plugin de cabeceras HTTP de Joomla para integrar HSTS en lugar de depender de redirecciones 301 para servir tu contenido a través de HTTPS es una mejora de seguridad importante. Una mejora que ayuda a detener los **ataques de intermediario en el medio (man-in-the-middle)**, y proporciona a tu usuario un entorno seguro.

HSTS cubre todo el dominio, a diferencia de una redirección 301 que solo cubre una ruta URI específica.

HSTS usa un caché de navegador separado que normalmente está segregado, por lo que no se puede borrar fácilmente o accidentalmente.

HSTS puede precargarse en un navegador. Esto asegura que un usuario solo se conecte a tu servidor con HTTPS, independientemente de si ha visitado el sitio antes o no.

<div style="background-color: #eeffee; border: 1px solid #009900; padding: 1rem; ">
Conclusiones

Activar: HSTS

Establecer max-age: El valor predeterminado es 1 año (31536000) segundos, pero algunos recomiendan establecer esto a 2 años (63072000) segundos.

Activar: Subdominios - Si tienes subdominios, asegúrate de tener un certificado SSL válido para cubrirlos, ya sea individualmente o como un comodín desde tu dominio principal.

Activar: Precarga

Por último, envía tu dominio a la lista de precarga HSTS.
</div>



## Nota final / Conclusión:

Al escribir este artículo, me he dado cuenta de que solo he rascado la superficie de este enorme tema.

Me encanta descubrir temas que anteriormente había ignorado o de los que no sabía nada. ¿A ti te pasa lo mismo?

La conclusión a la que he llegado al investigar el tema de las cabeceras HTTP, y en particular, al usar el nuevo plugin J4 de Joomla para configurarlas, es que todos necesitamos dominar este tema. Hay demasiadas personas (hackers) esperando una oportunidad para aprovecharse de sitios web con seguridad débil. Así que, no ayudes a que tus usuarios se conviertan en víctimas.

Diviértete investigando el plugin de cabeceras HTTP de Joomla y aprende cómo puede ayudar a asegurar tu sitio web.

Sin embargo, te recomiendo que investigues un poco más sobre este tema interesante antes de comenzar. Hay enlaces más abajo para iniciar tu propia investigación. Obtendrás una mejor comprensión de cómo funciona internet y cómo interactúa tu sitio web con él.

### Para referencia

Si necesitas restablecer el plugin, el plugin de cabeceras HTTP se instaló con las siguientes opciones configuradas:

El plugin está habilitado por defecto.

* Las pestañas HSTS y CSP están deshabilitadas por defecto.
* Las opciones X-Frame están habilitadas por defecto.
* La política de referencia está inicialmente configurada en: strict-origin-when-cross-origin.
* La política de apertura de origen cruzado está inicialmente configurada en same-origin.

Si has leído hasta aquí y has pensado "Eso no es justo, ¿qué pasa con J3?", "¿Por qué no podemos tener las mismas características en Joomla 3?". Bueno, la buena noticia es que sí puedes. Aunque tendrás que descargar el plugin desde el [JED.

Cuando hayas configurado tus cabeceras HTTP con el plugin de Joomla 4, puedes probar tus cabeceras HTTP en el sitio web de Security Headers.

¿Cómo saliste?

Ten en cuenta que la activación del plugin de cabeceras HTTP puede tener acciones inesperadas en el front-end.

Finalmente, ¡me gustaría agradecer a Tobias Zulauf y Ced Keiflin por su aporte para terminar este artículo a tiempo!

<!--
### Más lecturas:

Aquí hay algunas de las páginas web que utilicé para investigar este artículo, están llenas de información útil sobre este tema.

* https://docs.joomla.org/J4.x:Http_Header_Management
* https://csp.withgoogle.com/docs/index.html
* https://content-security-policy.com/
* https://scotthelme.co.uk/content-security-policy-an-introduction/
* https://scotthelme.co.uk/csp-cheat-sheet/
* https://support.cpanel.net/hc/en-us/articles/1500001533562-How-to-add-nosniif-CORS-HSTS-Clickjack-and-X-Xss-Protection-headers-on-a-per-domain-basis
* https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy
* https://developer.mozilla.org/en-US/docs/Web/Security/Referer_header:_privacy_and_security_concerns
* https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cross-Origin-Opener-Policy
* https://web.dev/why-coop-coep/
* https://en.wikipedia.org/wiki/Spectre_(security_vulnerability)
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer
* https://developer.mozilla.org/en-US/docs/Web/API/Performance/now
* https://www.troyhunt.com/clickjack-attack-hidden-threat-right-in/
* https://scotthelme.co.uk/hsts-the-missing-link-in-tls/
* https://scotthelme.co.uk/wifi-pineapple-karma-sslstrip/
* https://help.upguard.com/en/articles/4581202-what-s-the-difference-between-using-hsts-and-doing-a-301-redirect
* https://content-security-policy.com/hash/
* https://content-security-policy.com/frame-ancestors/
* https://content-security-policy.com/nonce/

Iconos de computadora creados por Freepik - Flaticon

Iconos de servidor creados por Freepik - Flaticon

Traducción al alemán de este artículo: https://www.jug-zueri.ch/artikel/das-http-headers-plugin-in-joomla-4

Traducción al ruso de este artículo, parte 1: https://habr.com/ru/articles/697214/

Traducción al ruso de este artículo, parte 2: https://habr.com/ru/articles/704778/
-->
*Traducido por openai.com*

