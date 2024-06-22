<!-- Filename: Using_A_Sitemap / Display title: Usar un Sitemap -->

## Usar un Sitemap (mapa del sitio)

Ya que los motores de búsqueda generalmente pueden encontrar las páginas
por la forma en que están enlazadas desde otros lugares en internet, es
una buena práctica crear un mapa del sitio que de a los 'bots' del motor
de búsqueda una lista de las páginas de tu sitio web - piensa en ello
como un mapa para encontrar todo el contenido en tu sitio.  

Los mapas del sitio son importantes no sólo para los motores de
búsqueda, ya son también muy útiles para las personas con discapacidad
que necesitan de una interfaz sencilla para ver la estructura del sitio
y navegar por el sitio sin necesidad de utilizar menú estructurados.
<a href="http://www.w3.org/TR/WCAG20-TECHS/G63.html"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">Grupo de Trabajo del W3C Nota sobre
mapas del sitio</a>

Un mapa del sitio sirve para varios propósitos:

- Proporciona una lista estructurada para mostrar una visión general de
  todo el contenido de tu sitio web
- Permite a un visitante obtener rápidamente una visión general de la
  estructura de tu sitio
- Proporciona una manera alternativa de navegación por tu sitio web, sin
  necesidad de complejas estructuras de menú
- Proporciona a los motores de búsqueda un medio de búsqueda de
  contenido que puede no estar disponibles a través de las estructuras
  de tu menú (por ejemplo, páginas de inicio)

### Tipos de mapas del sitio

Es posible proporcionar mapas del sitio para tipos específicos de
información, incluyendo:

- Video <a href="https://support.google.com/webmasters/answer/80471"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Ayuda de Google para mapas del sitio
  de vídeos</a>
- Imágenes <a
  href="https://support.google.com/webmasters/answer/answer.py?answer=178636"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Ayuda de Google para mapas del sitio
  de imágenes</a>
- Noticias
  <a href="https://support.google.com/news/publisher/answer/75717"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Ayuda de Google sobre mapas del sitio
  de Noticias</a>
- Internacional <a
  href="https://support.google.com/webmasters/answer/2620865?hl=en&amp;ref_topic=2370587"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Ayuda de Google para mapas del sitio
  internacionales</a>

Estos mapas del sitio específicos permiten proporcionar información
relacionada con un tipo de medio en particular - por ejemplo, con un
mapa del sitio de vídeo puedes proporcionar información sobre el tiempo
de ejecución, categoría y control familiar; con el mapa del sitio para
imágenes puedes especificar el tema de la imagen, su licencia de uso y
el tipo de imagen.

### Crear un mapa del sitio

En un sitio estático, la creación de un mapa del sitio es simplemente
generar manualmente un archivo XML con los estándares apropiados y
guardarlo como un archivo XML. En un sitio dinámico, donde los cambios
de contenido se producen regularmente, esto no es una opción apropiada
-se tendría que actualizar manualmente el archivo del mapa del sitio
cada vez que se agrega un nuevo contenido!

Por esta razón, hay varias extensiones para mapa del sitio disponibles
en el Directorio de Extensiones de Joomla! (<a
href="http://extensions.joomla.org/category/structure-a-navigation/site-map"
class="external text" target="_blank"
rel="noreferrer noopener">Categoría mapa del sitio en el Directorio de
Extensiones de Joomla!</a>) que permiten generar dinámicamente un mapa
del sitio que cumpla con los estándares esperados por los motores de
búsqueda para un archivo de mapa del sitio.
<a href="http://www.sitemaps.org/es" class="external text"
target="_blank" rel="nofollow noreferrer noopener">Protocolo de mapas
del sitio</a>

La mayoría de estas extensiones trabajan por la elección de los
elementos del menú que deseas incluir en un mapa del sitio y especifican
con qué frecuencia cambian (ver Frecuencia de Actualización). También es
posible incluir sub-páginas de aquellos elementos del menú (por ejemplo,
un elemento de menú puede conducir a una página de categoría del blog,
pero tu deseas mostrar todos los artículos que se muestran en esa página
como elementos individuales -otro ejemplo podría ser un elemento del
menú que apunta a una página de categoría de una tienda y en el mapa del
sitio que tu deseas es la lista de la categoría y, a continuación, cada
producto dentro de él como un enlace separado).

### Frecuencia de actualización

Ya que puedes especificar manualmente en tu mapa del sitio con qué
frecuencia las arañas de motor de búsqueda deben visitar tu sitio web,
la mayoría de los motores de búsqueda han incorporado sistemas que se
ajustan automáticamente la frecuencia de visitas que se basas en la
frecuencia con que cambia la página en cuestión.

Así, por ejemplo, si le dices a los bots de los buscadores que visiten
tu página de forma diaria, pero cuando visitas la página no ha cambiado
nada durante una semana, se puede ajustar la frecuencia de revisita en
consecuencia y no volver tan a menudo como has dicho. Puedes solicitar,
a través de los distintos portales de webmasters, para revisar la tasa a
modificar si es necesario.

Esto sugeriría que, por lo tanto, si cambias con regularidad el
contenido de tu sitio web será 'visitado' con más frecuencia -lo que
conduce a que el contenido se indexe más rápido que los sitios web que
no cambian a menudo.

Es generalmente sensible especificar las páginas estáticas para ser
rastreadas con menos frecuencia que las que cambian regularmente. Por
ejemplo, un artículo con texto estático se puede establecer con una
frecuencia de actualización de una vez al mes, mientras que tu blog o
página de noticias se puede establecer con una frecuencia de
actualización de una vez al día o una vez a la semana, dependiendo de la
frecuencia con que se añada nuevo contenido.

### Mapa del sitio HTML

Un mapa del sitio HTML es esencialmente una tabla de contenido para tu
sitio que puedes poner a disposición de los visitantes de tu sitio web.
Esto sirve a dos propósitos:

1.  Proporciona un lugar donde los visitantes pueden conseguir
    fácilmente cualquier contenido de tu sitio, incluso si esto no es
    necesariamente de fácil acceso con otras ayudas a la navegación en
    el sitio
2.  Proporciona un almacén centralizado de enlaces a los contenidos en
    tu sitio web que puede ser fácilmente indexado por los motores de
    búsqueda
3.  Permite a los usuarios con discapacidad ser capaces de navegar
    rápidamente por tu sitio web con una simple lista de enlaces, en
    lugar de complejos menús

Por lo menos, un mapa del sitio debe enlazar a las secciones y páginas
principales dentro de tu sitio, pero si es más detallada puede que sea
mejor.

Hay extensiones disponibles, como se mencionó anteriormente, que crean
mapas del sitio de forma automática basándose en el contenido de
Joomla!.

### Mapa del sitio XML

Los mapa del sitio XML son una manera fácil de los webmasters para
informar a los motores de búsqueda de las páginas existentes en sus
sitios web y que están disponibles para el rastreo. En su forma más
simple, un mapa del sitio es un archivo XML que enumera las Url de un
sitio junto con metadatos adicionales acerca de cada URL (cuando se
realizó la última actualización, la frecuencia con que generalmente
cambian y lo más importante la relación a otras direcciones Url en el
sitio), de modo que los motores de búsqueda hagan un rastreo más
inteligente del sitio.

Utilizar el protocolo de mapa del sitio no garantiza que las páginas web
sean incluidas en los motores de búsqueda, pero proporciona sugerencias
para los rastreadores web para hacer un mejor trabajo de rastreo de tu
sitio.

1.  Un mapa del sitio XML proporciona una lista de enlaces a los
    contenidos en tu sitio web que puede ser fácilmente indexado por los
    motores de búsqueda
2.  Es posible crear mapas del sitio XML específicos para Noticias,
    Móviles, URLs, Imágenes, y Vídeo

Hay extensiones disponibles que crear mapa del sitio XML de forma
automática basándose en el contenido de Joomla!.
<a href="http://sitemaps.org/protocol.php" class="external text"
target="_blank" rel="nofollow noreferrer noopener">Más información sobre
el protocolo de mapas del sitio</a>
