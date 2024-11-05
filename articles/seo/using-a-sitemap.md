<!-- Filename: Using_A_Sitemap / Display title: Usando un Mapa del Sitio -->

## Uso de un Mapa del Sitio

Aunque los motores de búsqueda generalmente pueden encontrar tus páginas según cómo están vinculadas desde otros lugares en internet, es una buena práctica crear un mapa del sitio que proporcione a los 'bots' de los motores de búsqueda una lista de las páginas en tu sitio web; piensa en ello como un mapa para encontrar todo el contenido en tu sitio. Los mapas del sitio no solo son importantes para los motores de búsqueda, también son muy útiles para personas con discapacidades que pueden necesitar una interfaz sencilla para ver la estructura de tu sitio y navegar sin utilizar tus estructuras de menú. <a href="https://www.w3.org/TR/WCAG20-TECHS/G63.html"
rel="nofollow noreferrer noopener">Nota del Grupo de Trabajo de W3C sobre
Mapas del Sitio</a>

Un mapa del sitio cumple varios propósitos:

- Proporciona una lista estructurada que muestra una visión general de todo el contenido de tu sitio web
- Permite que un visitante obtenga rápidamente una visión general de la estructura de tu sitio
- Ofrece una forma alternativa de navegar por tu sitio web, sin necesidad de estructuras de menú complejas
- Proporciona a los motores de búsqueda un medio para encontrar contenido que podría no estar disponible a través de tus estructuras de menú (por ejemplo, páginas de aterrizaje)

### Tipos de Mapa del Sitio

Es posible proporcionar mapas del sitio para tipos específicos de información, incluyendo:

- Video <a href="https://support.google.com/webmasters/answer/80471"
  rel="nofollow noreferrer noopener">Ayuda de Google sobre mapas del sitio de videos</a>
- Imágenes <a
  href="https://support.google.com/webmasters/answer/answer.py?answer=178636"
  rel="nofollow noreferrer noopener">Ayuda de Google sobre mapas del sitio de imágenes</a>
- Noticias <a href="https://support.google.com/news/publisher/answer/75717"
  rel="nofollow noreferrer noopener">Ayuda de Google sobre mapas del sitio de noticias</a>
- Internacional <a
  href="https://support.google.com/webmasters/answer/2620865?hl=en&amp;ref_topic=2370587"
  rel="nofollow noreferrer noopener">Ayuda de Google sobre mapas del sitio internacionales</a>

Estos mapas del sitio especializados te permiten proporcionar información relacionada con el tipo específico de medio; por ejemplo, con un mapa del sitio de video puedes proporcionar información sobre el tiempo de ejecución, categoría y estado de apto para familias; con mapas del sitio de imágenes puedes especificar el sujeto de la imagen, su licencia de uso y tipo de imagen.

### Creando un mapa del sitio

En un sitio estático, crear un mapa del sitio es simplemente el caso de crear manualmente un archivo XML usando los estándares apropiados, y guardarlo como un archivo XML. En un sitio dinámico, donde el contenido cambia regularmente, esto no es realmente una opción: ¡tendrías que actualizar manualmente el archivo del mapa del sitio cada vez que agregues contenido nuevo!

Por esta razón, hay varias extensiones de mapas del sitio disponibles en el Directorio de Extensiones de Joomla (<a href="https://extensions.joomla.org/category/structure-a-navigation/site-map"
rel="noreferrer noopener">Categoría de Mapa del Sitio en el Directorio de Extensiones de Joomla</a>) que te permiten crear dinámicamente un mapa del sitio que cumpla con los estándares de mapas del sitio esperados por los motores de búsqueda. <a href="https://www.sitemaps.org/"
rel="nofollow noreferrer noopener">Protocolo de Sitemaps</a>

La mayoría de estas extensiones funcionan eligiendo elementos de menú que deseas incluir en un mapa del sitio, y especificando con qué frecuencia cambian (ver Frecuencia de Actualización). También es posible incluir subpáginas de esos elementos de menú (por ejemplo, un elemento de menú podría llevar a una página de blog de categoría, pero deseas mostrar todos los artículos que se muestran en esta página como elementos individuales; otro ejemplo podría ser un elemento de menú que apunte a una página de categoría de tienda, y en el mapa del sitio deseas listar la categoría, y luego cada producto dentro de ella como un enlace separado).

### Frecuencia de Actualización

Aunque puedes especificar manualmente en tu mapa del sitio con qué frecuencia los motores de búsqueda deberían visitar tu sitio web, la mayoría de los motores de búsqueda tienen sistemas internos que ajustan automáticamente la frecuencia de las visitas de retorno basadas en la frecuencia con la que ha cambiado la página en cuestión.

Entonces, por ejemplo, si indicas a los bots de los motores de búsqueda que visiten tu página diariamente, pero cuando visitan la página nada ha cambiado durante una semana, pueden ajustar la frecuencia de las revisitas en consecuencia y no regresar tan a menudo como les dijiste. Puedes solicitar, a través de los diversos portales para webmasters, que la tasa de revisita se modifique si es necesario.

Esto sugeriría, por lo tanto, que si tienes contenido que cambia regularmente, tu sitio será 'explorado' con más frecuencia, lo que lleva a que el contenido sea indexado más rápido que en los sitios web que no cambian a menudo.

Generalmente es sensato especificar que las páginas que son estáticas sean rastreadas con menos frecuencia que aquellas que cambian regularmente. Por ejemplo, un artículo de texto estático podría configurarse con una frecuencia de actualización de una vez al mes, mientras que tu página de blog o de noticias podría configurarse con una frecuencia de actualización de una vez al día o una vez a la semana, dependiendo de con qué frecuencia agregues nuevo contenido.

### Mapas del Sitio HTML

Un mapa del sitio HTML es esencialmente una tabla de contenidos para tu sitio que puedes hacer disponible para los visitantes de tu sitio web. Esto cumple dos propósitos:

1.  Proporciona un lugar donde los visitantes pueden ir para acceder fácilmente a cualquier contenido en tu sitio, incluso si no es necesariamente fácil de acceder mediante otras ayudas de navegación en el sitio
2.  Proporciona un almacén centralizado de enlaces al contenido en tu sitio que puede ser fácilmente indexado por los motores de búsqueda
3.  Permite que los usuarios con discapacidades puedan navegar rápidamente por tu sitio web con una lista simple de enlaces, en lugar de a través de menús complejos

Al menos, un mapa del sitio debería enlazar con las principales secciones y páginas dentro de tu sitio, pero cuanto más detallado lo puedas hacer, mejor.

Existen extensiones disponibles previamente mencionadas que crean mapas del sitio automáticamente basados en contenido de Joomla.

### Mapas del Sitio XML

Los mapas del sitio XML son una manera fácil para que los webmasters informen a los motores de búsqueda sobre nuevas y existentes páginas en sus sitios que están disponibles para rastrear. En su forma más simple, un mapa del sitio es un archivo XML que lista URLs para un sitio junto con metadatos adicionales sobre cada URL (cuándo fue actualizada por última vez, con qué frecuencia suele cambiar, y cuán importante es, en relación con otras URLs en el sitio) para que los motores de búsqueda puedan rastrear el sitio de manera más inteligente.

El uso del protocolo de mapas del sitio no garantiza que las páginas web se incluyan en los motores de búsqueda, pero proporciona indicios para que los rastreadores web hagan un mejor trabajo al rastrear tu sitio.

1.  Un mapa del sitio XML proporciona una lista de enlaces al contenido en tu sitio que puede ser fácilmente indexado por los motores de búsqueda
2.  Es posible crear mapas del sitio XML específicos para Noticias, URLs móviles, Imágenes, y Video

Existen extensiones disponibles que crean mapas del sitio XML automáticamente basados en contenido de Joomla.

*Traducido por openai.com*

