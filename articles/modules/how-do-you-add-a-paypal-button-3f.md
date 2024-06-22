<!-- Filename: How_do_you_add_a_PayPal_button%3F / Display title: ¿Cómo agregar un botón de PayPal? -->

Joomla!  3.x Joomla!  2.5

PayPal, Google Checkout y otros sitios de comercio electrónico a menudo
proporcionan un código HTML que puedes utilizar para insertar enlaces
tales como los botones de "Añadir al carrito de compras" y "Comprar
Ahora" en tu sitio Web.

Generalmente es preferible crear un módulo de HTML Personalizado en
lugar de simplemente pegar el código en un artículo. De esta manera
puedes poner el enlace en una posición de módulo en las páginas que
quieras. También puedes poner el módulo dentro de un artículo mediante
el comando  {loadposition
myposition}.

## Documentación técnica de PayPal

Las especificaciones y ejemplos de código HTML se encuentran en la <a
href="https://cms.paypal.com/cms_content/US/en_US/files/developer/PP_WebsitePaymentsStandard_IntegrationGuide.pdf"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">Guía de integración estándar de pagos
con PayPal en sitios web</a> (en formato PDF).

## Problemas con el editor de HTML

Puedes insertar este tipo de código HTML, incluyendo formularios, en un
artículo o en un módulo personalizado HTML, sin embargo, el editor
TinyMCE normalmente eliminará el código HTML. Si intentas pegar algún
tipo de HTML con este editor, no funcionará, pues el código será
eliminado cuando salves el artículo o módulo.

### Solución para el editor TinyMCE

Para evitar este problema al usar el editor TinyMCE:

1.  Ir al Gestor de usuarios y cambiar el Editor de usuario a "Sin
    editor".
2.  Ir al artículo o módulo HTML personalizado y pegar el código HTML
    deseado.
3.  Regresar al Gestor de usuarios y cambiar el Editor de usuario de
    nuevo a TinyMCE.

Deberás repetir este proceso cada vez que desees editar el código (a
menos que uses la solución alternativa a continuación).

### Solución para el Editor JCE

1.  Instalar el editor JCE que se encuentra en: <a
    href="http://extensions.joomla.org/component/option,com_mtree/task,viewlink/link_id,88/Itemid,35/"
    class="external free" target="_blank"
    rel="noreferrer noopener">http://extensions.joomla.org/component/option,com_mtree/task,viewlink/link_id,88/Itemid,35/</a>
1.  Cambiar el editor predeterminado (Configuración global \> Sitio \>
    Editor WYSIWYG) a JCE. Puede que necesites cambiar también el editor
    predeterminado para otros usuarios.
2.  Ir al artículo o módulo HTML personalizado y hacer clic en el botón
    "Mostrar/ocultar", el cual cambiará el cuadro de edición y así se
    podrá escribir código HTML en vez de texto WYSIWYG.
3.  Pegar el código HTML en el editor.

Cuando vayas al artículo o módulo en el administrador, este ya estará
configurado para recibir HTML y no habrá problemas con el código. Esto
es más fácil que cambiar la configuración del usuario cada vez que
deseas editar el código mientras se están probando varios ajustes del
botón.

## Problemas al ocultar direcciones de correo electrónico

El código de PayPal incluye una dirección de correo para su sitio web.
Joomla! tiene un plugin llamado "Contenido - Enmascarar correo" el cual
intenta disfrazar los correos electrónicos en los artículos. Si deseas
pegar el código de PayPal directamente en un artículo, deberás
desactivar este plugin: Ve a Extensiones \> plugins, encuentra el plugin
"Contenido - Enmascarar correo" y haz clic en la casilla de verificación
verde en la columna Habilitado para desactivarlo.

Los plugins no son procesados en módulos, así que debes usar un módulo
personalizado HTML y puedes mantener el enmascaramiento de correo
activado.

### Activar/desactivar enmascarar correo en un artículo específico

Puedes desactivar el enmascaramiento de correos electrónicos en un
artículo, escribiendo "{emailcloak=off}" en cualquier parte del artículo
antes de la dirección de correo electrónico, de esta forma no necesitas
desactivar el enmascaramiento global de correos electrónicos.

### ID seguro de la cuenta de vendedor en lugar del correo electrónico

PayPal ofrece un ID seguro de la cuenta de vendedor (una cadena
alfanumérica usada en lugar de la dirección de correo electrónico del
vendedor) sin ningún costo. Está disponible para clientes estándar de
pagos web, así como en los planes con costos adicionales. El
enmascaramiento de correos electrónicos no afecta el ID seguro de la
cuenta de vendedor.

## Función de botón paypal llamada por un elemento de menú de Joomla

Puedes usar un elemento de menú para que funcione como un botón de
PayPal, por ejemplo, el botón de Ver carrito de PayPal simplemente envía
una cadena de consulta como parte de una URL, usando un formulario HTML.
Puedes crear un elemento de menú Joomla que cumpla la misma función.

En el Gestor de elementos de menú, crea un nuevo elemento de enlace
externo. En la sección de detalles del elemento, ve al campo de enlace e
ingresa en URL del formulario:

    https://www.paypal.com/us/cgi-bin/webscr&business=myusername@mysite.com&cmd=_cart&display=1

Reemplaza "miusuario@misitio.com" en la URL de ejemplo que aparece
arriba con el nombre de usuario de **tu** cuenta de PayPal.

Para probar la transacción en el Sandbox de PayPal, simplemente modifica
la URL para que aparezca "www.sandbox.paypal.com" en vez de
"www.paypal.com"

    https://www.sandbox.paypal.com/us/cgi-bin/webscr&business=myusername@mysite.com&cmd=_cart&display=1
