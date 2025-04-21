<!-- Filename: Smart_Search_on_large_sites / Display title: Búsqueda Inteligente en Sitios Grandes -->

## Indexación del Sitio

Smart Search funciona creando y manteniendo un índice independiente de términos de búsqueda en varias tablas de la base de datos. El problema para los sitios grandes es que el proceso de indexación puede ser bastante pesado en cuanto al uso de CPU, memoria y disco. Incluso después de la construcción inicial del índice, las actualizaciones incrementales también pueden ser pesadas. La buena noticia es que consultar el índice es una operación relativamente rápida y ligera.

Smart Search es adecuado para la mayoría de los sitios Joomla. Sin embargo, la búsqueda presenta desafíos particulares para los sitios grandes. Debe recordarse que Smart Search es una implementación pura en PHP de un motor de búsqueda y los sitios particularmente grandes pueden beneficiarse más al usar un motor de búsqueda independiente como Solr.

Para usar la Búsqueda Inteligente en un sitio grande, probablemente necesitarás ajustar algunas de las configuraciones. A continuación, se ofrece un consejo general sobre qué observar y qué intentar ajustar.

## Siempre usa el Indexador CLI

Debido a que el proceso de indexación inicial puede llevar mucho tiempo, es mejor ejecutar el indexador desde la línea de comandos para evitar cualquier problema relacionado con el tiempo de espera de las sesiones del navegador. El indexador de la CLI no expirará sin importar cuánto tiempo tome completarse y se puede abortar fácilmente si se presentan problemas. Además, los mensajes de error son visibles con el indexador de la CLI, mientras que podrían estar ocultos al ejecutarse desde el Administrador.

Para utilizar la CLI, abre un terminal, cambia al directorio cli en la raíz de tu
sitio y emite el siguiente comando:

```
php joomla.php finder:index
```

## Agrupación

El indexador divide el trabajo de indexación en lotes de elementos de contenido. Por defecto, el tamaño del lote está configurado en 50, lo que significa que se indexarán hasta 50 elementos de contenido por lote. Aumentar el tamaño del lote potencialmente hará que el proceso de indexación sea más rápido, pero utilizará más memoria y posiblemente más espacio temporal en disco.

## Problemas de falta de memoria

Si el indexador se está quedando sin memoria, intente realizar los siguientes ajustes uno a la vez hasta que se resuelva el problema.

1. Disminuye el tamaño del lote. Si tienes elementos de contenido particularmente grandes, el indexador puede quedarse sin memoria incluso con un solo elemento de contenido, así que intenta reducirlo inicialmente a 5 y si aún te quedas sin memoria, baja a 1.
2. Si puedes asignar más memoria al indexador, hazlo. Puedes aumentar la memoria asignada al indexador desde la línea de comandos utilizando un parámetro adicional. Por ejemplo, para aumentar el límite de memoria a 256Mb utiliza el siguiente comando, reemplazando el *256M* con la cantidad de memoria que puedas asignar de manera segura a un proceso en tu sistema.
```php
    php -d memory_limit=256M joomla.php finder:index
```
3. Intenta identificar qué elementos de contenido están haciendo que el indexador se quede sin memoria. Si no es obvio, podrías intentar deshabilitar todos los plugins de Búsqueda Inteligente excepto uno. Ejecutar el indexador con solo un plugin habilitado a la vez debería revelar qué tipo(s) de contenido están causando el problema. Como último recurso, considera dividir algunos elementos de contenido excepcionalmente grandes en elementos separados. Si el problema es con un tipo de contenido personalizado, revisa el código del plugin y considera indexar menos contenido disponible por elemento.

## Problemas de Espacio en Disco

¡Las tablas de índice de Búsqueda Inteligente pueden crecer rápidamente! La tabla *#__finder_links_termsX* contiene una fila por término/frase por ítem de contenido y un solo artículo de Joomla que contiene 1000 palabras típicamente resultará en aproximadamente 3000 filas agregadas a estas tablas. Un segundo artículo de tamaño similar agregará un número similar de filas incluso si ambos artículos contienen las mismas palabras. Un sitio con decenas de miles de artículos, algunos de los cuales pueden contener miles de palabras, probablemente terminará con esta tabla de mapeo conteniendo millones de filas. No es inusual que las tablas de índice ocupen varios gigabytes de espacio en disco en tales circunstancias.

El índice tiene una opción para decidir entre la precisión de búsqueda y el tamaño del índice. Cuando tienes "Buscar por frases" habilitado en las opciones globales del componente, tu índice será más grande, pero también permitirá obtener resultados de búsqueda más precisos. Tenerlo desactivado significará un índice mucho más pequeño, pero también sin la posibilidad de buscar frases completas.

## Notas

1. Actualmente no hay bloqueo de concurrencia para evitar que más de un proceso ejecute el indexador al mismo tiempo. Esto casi seguramente resultará en un índice corrupto. Incluso alguien que guarde cambios en un elemento de contenido mientras se lleva a cabo un índice completo podría potencialmente dañar el índice.

*Traducido por openai.com*

