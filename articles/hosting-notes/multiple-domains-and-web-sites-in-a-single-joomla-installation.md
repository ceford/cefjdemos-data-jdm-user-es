<!-- Filename: Multiple_Domains_and_Web_Sites_in_a_single_Joomla!_installation / Display title: Múltiples Dominios y Sitios Web en una sola instalación de Joomla!  -->

**Nota:** ¡Este artículo fue actualizado por última vez en 2012!

Aunque es una mejor práctica darle a cada sitio web su propio dominio, instalación de Joomla! y base de datos, puede haber condiciones especiales en las que se justifique una solución de múltiples sitios bajo una sola instalación de Joomla.

## Un Ejemplo de Aplicación

Una pequeña empresa, 'Johnson Candies', tiene dos marcas separadas pero relacionadas: *Red Candy* y *Yellow Candy*. Requieren un único sitio web basado en Joomla! donde ambos tipos de caramelos sean visibles, cada uno con su propia página de inicio en el sitio de Joomla! que corresponde a los dominios `www.redjohnsoncandy.com` y `www.yellowjohnsoncandy.com`.

Además, cada marca y sitio **requiere su propio diseño**: una plantilla amarilla para uno; una plantilla roja, para el otro.

## Beneficios

Al incluir ambas marcas en una sola instalación web de Joomla!, Johnson Candies puede ahorrar tiempo de edición (solo un inicio de sesión), compartir artículos y datos entre ambas marcas (o sitios) y utilizar una única función, como un formulario de Contacto, para ambas marcas.

## Procedimiento de Implementación

### Prepara Tus Dominios

Utiliza un único dominio para tu cuenta de hosting, como lo harías normalmente. Crea los dominios adicionales requeridos en el panel de control de tu cuenta de hosting. Para los propósitos de este tutorial, usaremos `www.redjohnsoncandy.com` además del dominio base `www.yellowjohnsoncandy.com`.

### Instala y Configura Joomla!

Instala y configura Joomla! de manera normal. Luego desarrolla artículos, menús y módulos para cada sitio.

### Crea Plantillas

Luego, desarrolla e instala las plantillas necesarias: una para cada sitio que deseas tener. En el ejemplo anterior, crearías una plantilla para *red candy* llamada *Red Template* y una plantilla para *yellow candy* llamada *Yellow Template*. Una vez que las plantillas estén instaladas, asígnalas a los elementos de menú pertinentes, utilizando el administrador de plantillas de Joomla! en el área de administración de Joomla!

### Añadir un Redireccionamiento

#### Opción #1: Crear un redireccionamiento .htaccess (Apache)

**Nota** *Habilita las URLs SEF en Joomla! Primero*

Una opción es utilizar .htaccess (Apache) para redirigir consultas a un dominio dado a una página específica de Joomla!.

Nuestro objetivo es redirigir cualquier consulta al nombre de dominio de Red Candy a una página específica en el sitio de Joomla!. En este ejemplo, redirigimos cualquier consulta a `www.redjohnsoncandy.com` a una página de blog de categoría. Habrías asignado previamente la plantilla 'red candy' a este elemento de menú, para crear la ilusión de un sitio separado.
```
#La siguiente regla funciona, pero cambia qué nombre de dominio se muestra.
RewriteCond %{HTTP_HOST} ^(www\.)?redjohnsoncandy\.com$
RewriteRule (.*) http://www.yellowjohnsoncandy.com/index.php?option=com_content&view=category&layout=blog&id=3&Itemid=12 [R=301,L]
```
Bueno, eso funciona, pero puedes ver la desventaja de inmediato. Aunque el usuario está viendo con éxito el sitio de Red Candy, seguirá viendo el nombre de dominio de Yellow Candy. Desafortunadamente, si estás usando tanto .htaccess como estacionamiento de dominio (técnicamente un redireccionamiento), esto es necesario para evitar crear un BUCLE.

#### Opción #2: Crear un Redireccionamiento de Encabezado PHP

Esta solución tiene el beneficio de mantener la ilusión de dominios/sitios web separados aparente para el visitante. En lugar de usar .htaccess (Apache) para nuestro redireccionamiento, usamos una de las plantillas en el sitio.

En este ejemplo, el dominio base es `www.redjohnsoncandy.com`. Has creado una plantilla para esa área llamada *Red Template*. El truco es abrir el archivo index.php de 'Red Template' y agregar lo siguiente **como las primeras líneas** del index.php principal del instalador.

```php
<?php
$domain = $_SERVER["HTTP_HOST"];
$uri = $_SERVER["REQUEST_URI"];
$url = $domain . $uri;

if (($url == "redjohnsoncandy.com/") ||
   ($url == "www.redjohnsoncandy.com/")) {
   header("Status: 301 Moved Permanently");
   header("Location: http://www.redjohnsoncandy.com/index.php?option=com_content&view=category&layout=blog&id=3&Itemid=12");
}
?>
```

Aquí está el beneficio: el visitante ahora será redirigido a la página apropiada de *Red Site*, que tiene asignada la *Red Template* **solo** en el caso de que haya llegado al nombre de dominio del 'red site'. De lo contrario, la regla condicional de PHP es ignorada, y se carga el Yellow Site.

Es importante recordar solicitar también el URI (la URL que sigue al dominio puro) para que puedas hacer redireccionamientos al mismo dominio. Cuando el URI es invisible en la URL, la variable se convierte en un signo "/". Por eso tienes que comparar tu URL pura con un "/" al final. De esta manera, podrás hacer redireccionamientos 301 en el mismo dominio. De lo contrario, crearás un bucle infinito en el proceso de redirección.

#### Opción #3: Crear un Redireccionamiento de Encabezado PHP, para múltiples dominios con redirecciones específicas de dominio para plantillas personalizadas

Solución para un único espacio web, con diferentes dominios, una instalación de Joomla y dependiendo del dominio al que arrive el usuario, redirecciona a una página predeterminada diferente. Pega el siguiente código PHP **como la primera cosa** en el archivo index.php principal del instalador. Para asignar otro dominio, simplemente copia/pega la función "if" y edítala con los valores del otro dominio de la misma manera. Además, para configurar las vistas de la plantilla, tendrás que asignar diferentes alias de elementos de módulo/enlace y configurar las vistas de las plantillas dentro del administrador de plantillas de Joomla!. La configuración del alias es necesaria cuando usas configuraciones SEF.
```php
<?php
$domain = $_SERVER["SERVER_NAME"];
$requri = $_SERVER['REQUEST_URI'];
if (($domain == "www.example.de" && $requri == "/" ||
   $domain == "example.de"))  {
   header("Status: 301 Moved Permanently");
   header("Location: http://www.example.de/index.php?option=com_content&view=article&id=6");
}
?>
```
*Traducido por openai.com*

