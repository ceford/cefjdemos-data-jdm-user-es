<!-- Filename: Smart_Search_Frequently_Asked_Questions / Display title: Preguntas Frecuentes sobre Búsqueda Inteligente   -->

## ¿Por qué debería usar la búsqueda inteligente?

La tecnología de búsqueda ha mejorado considerablemente a lo largo de los años desde que Joomla fue lanzado por primera vez; sin embargo, el componente estándar y básico de búsqueda no ha cambiado mucho durante ese tiempo. Sigue siendo muy rudimentario y carece del tipo de características de búsqueda que los usuarios web han llegado a esperar, especialmente dada la prevalencia de motores de búsqueda avanzados como Google. La búsqueda inteligente te permite incorporar algunas de esas características de búsqueda más avanzadas en tu sitio web.

## ¿Por qué Crear un Plugin de Búsqueda Inteligente?

Generalmente, si tienes un tipo de contenido que no es manejado por los componentes principales de Joomla y quieres dar a los visitantes de tu sitio la oportunidad de buscar ese contenido, necesitarás escribir un Plugin de Búsqueda Inteligente para soportarlo. Por ejemplo, supongamos que tienes un componente que almacena información sobre diferentes especies de animales. El componente mantiene una tabla de base de datos que contiene campos como nombre científico, nombre vernáculo, clasificación y una descripción. Entonces necesitarás crear un Plugin que indique al indexador de Búsqueda Inteligente cómo indexar los datos en esa tabla. Además de indexar palabras y frases individuales, puedes hacer que el Plugin agregue cada registro a un mapa de contenido, que en este caso podría incluir las <a href="https://es.wikipedia.org/wiki/Taxonom%C3%ADa_(biolog%C3%ADa)" rel="nofollow noreferrer noopener">clasificaciones biológicas de reino, filo, clase, orden y familia</a>. Los mapas de contenido luego pueden utilizarse para filtrar los resultados de búsqueda.

## ¿Se pueden seleccionar múltiples nodos desde los menús desplegables de filtro?

Sí, esto es totalmente compatible con la propia Búsqueda Inteligente. De hecho, puedes usar cualquier interfaz de usuario que desees diseñar para los filtros. Solo echa un vistazo al código proporcionado en el módulo y componente estándar del Frontend y verás cómo necesitas hacerlo.

## Tengo un sitio grande. ¿Puedo usar Búsqueda Inteligente?

Los sitios grandes pueden beneficiarse más de un motor de búsqueda independiente y dedicado, como Solr, en lugar de la implementación pura de PHP utilizada en Búsqueda Inteligente. En esta primera iteración de búsqueda avanzada en Joomla, es probable que se revelen problemas relacionados con la escalabilidad y el rendimiento. También existe el potencial de que ocurran condiciones de carrera al actualizar el índice con cambios frecuentes de contenido. Se espera que estos problemas se aborden de manera más completa en una versión futura de Joomla.

## ¿Por qué Smart Search tiene tantas tablas?

Smart Search añade bastantes tablas nuevas a una instalación de Joomla, incluyendo 16 "tablas de mapeo". Estas tablas de mapeo resuelven la relación de muchos a muchos entre los términos de búsqueda y los elementos de contenido que los contienen. En teoría, esas 16 tablas podrían fusionarse en una sola tabla y hacerlo tendría un impacto insignificante en sitios pequeños. Sin embargo, en sitios más grandes habría un impacto sustancial en el rendimiento, porque la tabla de mapeo tendría un gran número de entradas y actualizar una tabla tan grande puede consumir mucho tiempo.

## ¿Por qué la Búsqueda Inteligente usa tanto espacio en disco?

Mantener un índice de términos de búsqueda requiere una cantidad considerable de espacio en disco, que aumenta cuanto más términos contienen los elementos de contenido. Dado que las frases también se indexan, cuanto más largas sean, más espacio en disco se necesitará. Para la Búsqueda Inteligente en Joomla 2.5, la longitud máxima de una frase se ha fijado en 3 términos como un compromiso razonable entre la usabilidad de búsqueda y el uso de espacio en disco. Es probable que esto sea un parámetro que se pueda ajustar en una versión futura de Búsqueda Inteligente.

## ¿Por qué las entradas en las tablas de mapeo no están distribuidas uniformemente?

Quizás resulte sorprendente que el número de entradas en cada una de las tablas de mapeo no sea ni siquiera aproximadamente el mismo. ¿Seguramente el rendimiento mejoraría con una distribución uniforme? En realidad no, existe un equilibrio entre el rendimiento de inserción y el rendimiento de búsqueda, siendo la distribución uniforme buena para el primero pero mala para el segundo. Esta es un área de investigación continua, con el número de tablas y el algoritmo de distribución sujetos a cambios a la luz de la experiencia.

## ¿Por qué hay un complemento de contenido de búsqueda inteligente separado?

Esto es solo una conveniencia que facilita habilitar o deshabilitar todos los complementos de búsqueda inteligente con una única operación. Esto se consideró deseable porque la Búsqueda Inteligente no está habilitada por defecto en Joomla 2.5.

## ¿Por qué los complementos de búsqueda inteligente utilizan eventos separados como *onFinderContentAfterSave*?

La Búsqueda Inteligente utiliza sus propios eventos, como onFinderContentAfterSave, en lugar de los equivalentes genéricos como onContentAfterSave, simplemente por conveniencia para facilitar la habilitación o deshabilitación de la indexación de Búsqueda Inteligente activando/desactivando un solo complemento.

## ¿Por qué la Búsqueda Inteligente no está habilitada por defecto en Joomla 2.5 y Joomla 3.x?

Porque Joomla 2.5 es la última en la serie 1.x/2.x, debe mantener un alto grado de compatibilidad hacia atrás con la versión anterior de la serie. Dado que la Búsqueda Inteligente es algo completamente nuevo y no se parece en nada al componente de búsqueda regular de esta o versiones anteriores, se consideró importante que los usuarios que actualizaran desde esas versiones anteriores no se vieran obligados a cambiar la forma en que funciona la búsqueda en sus sitios. De hecho, la activación de la Búsqueda Inteligente es algo que debe hacerse de una manera cuidadosamente considerada.

## ¿Por qué no hay una API de búsqueda?

El enfoque de la versión actual de Smart Search fue trasladar el código del antiguo componente JXtended Finder a la última versión de Joomla. Como ese código ya se consideraba estable y solo había una ventana de tiempo limitada para trasladarlo, se consideró que una gran renovación de Finder estaba fuera del alcance para el lanzamiento de Joomla 2.5. En consecuencia, el código utiliza Plugins para evitar cualquier cambio en el código central del CMS, en lugar de desarrollar una API de búsqueda adecuada. Estamos considerando crear tal API para una futura iteración de Joomla.

## ¿Puede la Búsqueda Inteligente Realizar una Búsqueda Facetada?

Sí. La búsqueda avanzada disponible en la página de resultados de búsqueda y el módulo de búsqueda inteligente proporcionan un ejemplo de cómo puedes filtrar los resultados de búsqueda para producir una búsqueda facetada. Nada te impide crear tus propias variaciones sobre estas ideas básicas. Por ejemplo, podrías cambiar los menús desplegables simples para aceptar múltiples selecciones, o podrías reemplazar los menús desplegables con una serie de casillas de verificación.

## ¿Por qué no se permiten las búsquedas con comodines?

La antigua búsqueda de Joomla utilizaba un método muy primitivo que dependía de la búsqueda FULLTEXT proporcionada por la base de datos. Esto era muy ineficiente, pero proporcionaba un medio simple para manejar consultas de búsqueda con comodines. Smart Search ofrece una función de autocompletar que, de hecho, es una búsqueda con comodines de términos en el índice, pero no se admite la búsqueda completa con comodines debido al potencial de sobrecargar el servidor si se abusara de la función. En la mayoría de los casos, las búsquedas con comodines se utilizan para cubrir variaciones en un término de búsqueda. Por ejemplo, buscar *juggl\** para incluir referencias a *juggling* así como *juggler*. Smart Search intenta evitar la necesidad de búsquedas con comodines al admitir el descomposición de palabras, donde palabras que tienen la misma raíz se consideran equivalentes, de modo que buscar *juggler* también recuperará instancias de *juggling* sin necesidad de usar comodines.

## ¿Se puede utilizar la Búsqueda Inteligente en sitios multilingües?

Sí, pero todavía hay algunos problemas por resolver, especialmente en cuanto al soporte para idiomas asiáticos.

- Para ser indexado correctamente, debes asegurarte de que todo el contenido sea UTF-8 válido.
- La función *¿Quiso decir?* utiliza la función Soundex para encontrar frases de búsqueda fonéticamente similares. Sin embargo, Soundex no funciona bien para idiomas no ingleses y para muchos idiomas no funciona en absoluto. Actualmente estamos investigando métodos alternativos para ofrecer esta función.

Si utilizas la Búsqueda Inteligente en un sitio multilingüe y encuentras algún problema, por favor infórmalo en el rastreador para que podamos entender mejor los problemas que necesitan ser resueltos.

## ¿Funcionarán los plugins de Finder de *jXTended* con la Búsqueda Inteligente?

No. Deberás actualizar los plugins de Finder para que funcionen con la Búsqueda Inteligente. Sin embargo, los cambios no deberían ser difíciles de implementar y, en la mayoría de los casos, resultarán en un código significativamente menor. Si echas un vistazo a los plugins actuales de Búsqueda Inteligente, deberías ver que actualizar un plugin de Finder es bastante sencillo.

*Traducido por openai.com*

