<!-- Filename: Search_Engine_Friendly_URLs / Display title: URLs Amigables a los Buscadores (Search Engine Friendly URLs) -->

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

Un buen ejemplo de enrutamiento es la dirección URL del artículo
"Welcome to Joomla!", de los datos de ejemplos.

- Sin las URLs SEF activadas, la dirección URL sería
  `http://www.example.com/index.php?option=com_content&view=article&id=1:welcome-to-joomla&catid=1:latest-news&Itemid=50`
- Con las URLs SEF y mod_rewrite, desactivado
  `http://www.example.com/index.php/the-­news/1-­latest­-news/1­-welcome­-to­-joomla`
- Tanto con SEF URLs y mod_rewrite, activado
  `http://www.example.com/the-­news/1­-latest-­news/1-­welcome-­to­-joomla`

Las URLs amigables a los buscadores, pueden obtenerse mediante la
activación de la opción "'URLs amigables"' en la "Configuración Global"
del sitio. Esta opción está activada por defecto desde Joomla! 1.6. Para
más información véase  Habilitar las URLs Amigables a Buscadores (URLs
SEF).

## Preguntas frecuentes

### ¿Qué significan los números en la URL?

    Si comparamos la URL antigua y la nueva, podemos ver en la URL antigua los números,

    http://www.example.com/index.php?option=com_content&view=article&id=1:welcome-to-joomla&catid=1:latest-news&Itemid=50

también, en la URL nueva veremos lo siguiente:

    http://www.example.com/the-­news/1­-latest-­news/1-welcome-­to­-joomla

Estos números son los parámetros que Joomla! necesita para obtener la
dirección URL interna y mostrar la página que desea ver. (En este caso,
el primer número 1 es la ID de la categoría, el segundo número 1 es el
ID del artículo).

### Ya no hay `index.php` en la URL. ¿Puedo borrar ahora el archivo?

¡No! La URL no contiene más `index.php`, pero internamente el
mod_rewrite se redirigirá a la ruta original sin mostrarlo.

### Alias? y ¿cómo se crea?

El Alias aparece debajo, o al lado, del campo Título, en los Artículos,
Categorías y Elementos de Menú. En Joomla! se puede crear un alias
automáticamente. Para este automatismo del alias utiliza el propio
título. Todas las letras mayúsculas cambian a minúsculas. Los espacios y
caracteres especiales no permitidos en una dirección URL, se cambian por
guiones.

### Quiero poner un valor propio para el Alias.

Si no le gusta el alias proporcionado por Joomla!, puede introducir, en
ese campo, un valor a su elección. Muchas personas opinan que usar bien
las palabras clave en la URL, ayuda a la optimización para los
buscadores. Puede hacerse mediante la inclusión de las palabras claves
en el título, permitiendo que Joomla! genere el alias por si solo, o
creando el alias por usted mismo.

### How is Alias used in a URL?

For a menu item, Joomla! uses the alias as the URL slug. Assume that you
use the first two SEF URL options and you create a menu item called
Products. Your URL would be example.com/products.

Joomla! también utiliza los valores del ID de los datos dentro de la URL
para ayudar al enrutador a navegar a la página correcta. Continuando con
el ejemplo anterior, si el elemento de menú productos era un
"Artículo/Categoría Blog", en el enlace del título y/o en el "Leer más",
el vínculo al artículo tendría tres partes:

- La dirección URL del elemento de menú sería example.com/productos;
- Más, el ID de la categoría y el alias de la categoría - "'32-frutas"';
- Más,el ID del artículo y el alias del artículo - "'1-manzana"';

La dirección URL completa es:
`http://example.com/productos/32-frutas/1-manzana`

### ¿Cómo puedo deshacerme de los números de las URLs SEF?

Los números de la URL SEF son necesarios para que el enrutador de
Joomla! sepa cómo dirigir el tráfico en el sitio. Una vez que la lógica
del enrutador se estabiliza, se pueden desarrollar plugins de terceros
para aumentar las capacidades del enrutador permitiendo más opciones al
sistema. En ese momento, probablemente, se eliminarán los números de la
URL.

## Formatos de Ruta y el Mecanismo de Enrutamiento

*Esta sección describe el mecanismo de enrutamiento del núcleo de
Joomla!. Las extensiones de enrutamiento pueden cambiar la forma en que
se crean las rutas en el sistema*.

### Formatos de Ruta

Para describir el mecanismo de enrutamiento de Joomla! con más detalle,
primero necesitamos definir lo que denominamos "ruta". Supongamos que
Joomla! se ha instalado en `http://example.com/sitios/primero/`. La ruta
de instalación es generalmente conocida como **base URL**. Un posible
ejemplo sería la dirección URL
`http://example.com/sitios/primero/productos/32-fruta/1-manzana`. La
primera parte de esta URL es la dirección "base URL" antes mencionada y
ni Joomla! o cualquier componente enrutador puede crear direcciones URL
con esta primera parte distinta. La segunda parte,
`productos/32-fruta/1-manzana`, es una **ruta**, que consta de tres
**segmentos**.

El primer segmento de una ruta es, para las URL normales, el alias de un
elemento de menú. La URL SEF se dice que **enruta a través de** ese
elemento de menú. Los otros segmentos se determinan en su totalidad por
el enrutador del componente que proporciona el tipo de elemento de menú.
Por ejemplo, el tipo de elemento de menú "Categoría - Blog", es
proporcionado por el componente
Content,
y por lo tanto el enrutador de ese componente es el responsable de la
construcción y análisis de los segmentos restantes.

También es posible (para extensiones) pedir al sistema, crear una ruta
sin necesidad de suministrar un elemento de menú. En ese caso, el
sistema suele decidir crear una ruta especial que tiene la palabra
`component` como primer segmento. Estas rutas se crean utilizando un
formato fijo: el nombre del componente (sin el encabezamiento `com_`) se
selecciona como el segundo segmento, y cualquier otro parámetro, para el
resto de los segmentos.

### Limitaciones

Es importante tener en cuenta que la creación de un elemento de menú es
la "única" forma en que un usuario de Joomla! define la ruta que conduce
a un componente específico. Es posible, sin embargo, crear una ruta sin
necesidad de mostrarla en el sitio (es decir, en un menú). Un método
frecuentemente aplicado es, crear un elemento de menú en un menú que no
se muestra en ninguna parte. Dicho menú se suele llamar un,  menú
oculto.

El párrafo anterior implica que no es posible hacer una componente
responsable de el manejo de todas las rutas. Por ejemplo, no es posible
especificar que la dirección URL `http://ejemplo.com/elalias` debe
mostrar el contenido del artículo con el alias `elalias`, donde
`elalias` puede ser cualquier palabra. Si necesita hacerse esto para
unos cuantos artículos, los elementos de menú pueden crearse manualmente
para estos. De todas formas, se necesita una extensión de enrutamiento.

Por lo tanto, este mecanismo de enrutamiento no es tan flexible como a
veces requieren los usuarios. En cambio, tiene una gran ventaja: se
reduce la posibilidad de rutas ambiguas (rutas que podrían conducir a
dos páginas diferentes). Ya que el primer segmento de una ruta es
siempre un alias de elemento de menú, el sistema sabe inmediatamente el
enrutador de qué componente tiene que utilizar para analizarlo.

## Detalles de la Implementación

### Manipulación de Rutas

"En esta sección se describe la implementación del enrutamiento. Si es
un desarrollador de componentes, vea  Soporte URL SEF en su
componente."

Las rutas de Joomla se crean y se resuelven mediante <a
href="https://docs.joomla.org/index.php?title=JRouter&amp;action=edit&amp;redlink=1"
class="new" title="JRouter (page does not exist)">the JRouter class</a>.
Esta clase mira en la raíz del componente actualmente activo
(especificado en el parámetro `option` en la cadena de la consulta) e
incluye el archivo `router.php` en el directorio raíz de dicho
componente. A continuación, llama a una de las dos funciones: una para
crear la URL SEF y otra para interpretar la URL SEF.

La clase JRouter se sobrescribe por el CMS en /includes/router.php. En
este fichero, las funciones "build" y "parse" son sobrescritas, para
construir e interpretar las direcciones URL correctamente para el CMS de
Joomla.

El archivo `router.php`, de cada componente (por ejemplo,
`/components/com_content/router.php`) debe contener las dos funciones
siguientes:

- ContentBuildRoute - esto construye la URL SEF
  - Parámetros
    - \$query - este es el nombre de un array que contiene las cadenas
      de los segmentos
  - Devuelve: Un array de segmentos, en los que cada segmento está
    separado por un '/' utilizado más tarde para crear la dirección URL
    real (los elementos del array no deben contener caracteres '/')
- ContentParseRoute - este interpreta la URL SEF
  - Parámetros
    - \$segments - se trata de un array que contiene los segmentos de la
      dirección URL solicitada.
  - Devuelve: un array del tipo mapa de valores de las cadenas de los
    segmentos que necesitan los enlaces

### El Plugin SEF

El plugin "Sistema - SEF *de Joomla - hereda de `JPlugin` y ejecuta la
función `onAfterRender()`. En esta función, el cuerpo de la respuesta
que se envía al navegador se recupera mediante `JResponse::getBody()`.
El cuerpo de la respuesta entonces busca los enlaces que contengan
`/index.php...`, y los reemplaza por una dirección URL SEF correcta,
llamando a `JRoute::_("url")`.*

JRoute construye las URLs SEF creando una instancia al objeto `JRouter`
y solicitando que se construya el enlace correcto de la URL pasada.

### Manipulación de las URLs SEF

    Por defecto las URLs SEF se manipulan por el objeto JRouterSite (en /includes/router.php) y se llama por una llamada a JApplication::route() en el index.php. Esta llamada se realiza en la variable $app que en realidad es una instancia de JSite (en /includes/application.php).

`JApplication::route()` tiene un resultado no destructivo sobre el array
\$\_GET. Es decir, JApplication::route() establece variables en `$_GET`
llamando a `JRequest::set()` con el indicador de sobrescribir
establecido en false. Así, si un nombre de una variable se devuelve
desde `JApplication::route()`, el cual ya está en `$_GET`, no va a poner
ese valor en `$_GET`. Esto permite el enrutamiento personalizado.

### Enrutamiento Personalizado

Joomla le permite crear su propio mecanismo de enrutamiento. Con el fin
de crear este mecanismo debe tener un plugin que reemplace la función
`JPlugin::onAfterInitialise()`. Esta función analiza la URL y crea las
variables necesarias en `$_GET` antes de que el enrutamiento estándar de
Joomla se realice.

*Ver  Crear un plugin de sistema para argumentar el
JRouter
como ejemplo.*
