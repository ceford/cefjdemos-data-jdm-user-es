<!-- Filename: Smart_Search_on_large_sites / Display title: Búsqueda Inteligente en Sitios Grandes  -->

## Indexación del Sitio

La Búsqueda Inteligente funciona creando y manteniendo un índice independiente de términos de búsqueda en varias tablas de bases de datos. El problema para los sitios grandes es que el proceso de indexación puede ser bastante intenso en el uso de CPU, memoria y disco. Incluso después de la construcción inicial del índice, las actualizaciones incrementales también pueden ser pesadas. La buena noticia es que consultar el índice es una operación relativamente rápida y liviana.

La Búsqueda Inteligente es adecuada para la mayoría de los sitios Joomla. Sin embargo, la búsqueda presenta desafíos particulares para los sitios grandes. Hay que recordar que la Búsqueda Inteligente es una implementación pura de PHP de un motor de búsqueda y los sitios particularmente grandes pueden beneficiarse más usando un motor de búsqueda independiente como Solr.

Para usar la Búsqueda Inteligente en un sitio grande, probablemente necesitarás ajustar algunas de las configuraciones. Lo que sigue es un consejo general sobre qué tener en cuenta y qué intentar ajustar. Hay varios problemas pendientes conocidos en cuanto al funcionamiento de la Búsqueda Inteligente en sitios grandes, los cuales se espera que sean abordados en versiones futuras y también se describen aquí.

## Siempre Use el Indexador de CLI

Debido a que el proceso inicial de indexación puede llevar mucho tiempo, es mejor ejecutar el indexador desde la línea de comandos para evitar cualquier problema debido a que las sesiones del navegador expiren. El indexador de CLI no se agotará sin importar cuánto tiempo tarde en completarse y se puede abortar fácilmente si se encuentran problemas. Además, los mensajes de error son visibles con el indexador de CLI, mientras que están ocultos cuando se ejecuta desde el Administrador.

Para usar el CLI, abra una terminal, cambie al directorio cli en la raíz de su sitio y ejecute el siguiente comando:

```
php joomla.php finder:index
```

## Agrupación

El indexador divide el trabajo de indexación en grupos de elementos de contenido. Por defecto, el tamaño del grupo está configurado en 30, lo que significa que se indexarán hasta 30 elementos de contenido por grupo. Aumentar el tamaño del grupo podría hacer que el proceso de indexación sea más rápido, pero usará más memoria y posiblemente más espacio temporal en disco.

## Problemas de Falta de Memoria

Si el indexador se está quedando sin memoria, intenta hacer los siguientes ajustes uno a la vez hasta que se resuelva el problema.

1. Disminuye el tamaño del lote. Si tienes elementos de contenido particularmente grandes, el indexador puede quedarse sin memoria incluso con un único elemento de contenido, así que intenta reducirlo a 5 inicialmente y si todavía te quedas sin memoria, bájalo a 1.
2. Si puedes asignar más memoria al indexador, hazlo. Puedes aumentar la memoria asignada al indexador de línea de comandos utilizando un parámetro extra en la línea de comandos. Por ejemplo, para aumentar el límite de memoria a 256 Mb utiliza el siguiente comando, reemplazando el *256M* con tanta memoria como puedas asignar de manera segura a un proceso en tu sistema.<br>
   *php -d memory_limit=256M finder_indexer.php*
3. Reduce el límite de la tabla de memoria. El valor predeterminado es de 30000 términos, lo que significa que tan pronto como la tabla temporal en memoria *#__finder_tokens* alcance este número de filas, el indexador cambiará a usar una tabla en disco en lugar de una tabla en memoria. Puede ser que no tengas suficiente memoria para manejar una tabla en memoria completa o casi completa, así que reducir el límite indicará al indexador que cambie al disco antes y por lo tanto use menos memoria. Intenta con 10000 o incluso números mucho más pequeños.
4. Cambia el motor de base de datos utilizado para las tablas *__finder_tokens* y *#__finder_tokens_aggregate* de MEMORY a InnoDB. Esto podría impactar seriamente el rendimiento ya que más del proceso de indexación usará el disco en lugar de la memoria, pero podría permitir que el indexador termine sin quedarse sin memoria. Espera que el proceso de indexación tarde mucho más. Sin embargo, esto no afectará el rendimiento de búsqueda.
5. Trata de identificar qué elementos de contenido están haciendo que el indexador se quede sin memoria. Si no es obvio, podrías intentar deshabilitar todos los plugins de Búsqueda Inteligente excepto uno. Ejecutar el indexador con solo un plugin habilitado a la vez debería revelar qué tipo(s) de contenido están causando el problema. Como último recurso, considera dividir algunos elementos de contenido excepcionalmente grandes en elementos separados. Si el problema es con un tipo de contenido personalizado, revisa el código del plugin y considera indexar menos del contenido disponible por elemento.

## Problemas de Espacio en Disco

¡Las tablas del índice de Búsqueda Inteligente pueden crecer rápidamente! Las tablas *#__finder_links_termsX* (donde *X* es un solo carácter hexadecimal) contienen una fila por término/frase por elemento de contenido, y un solo artículo de Joomla que contenga 1000 palabras típicamente resultará en aproximadamente 3000 filas adicionales en estas tablas. Un segundo artículo de tamaño similar añadirá un número similar de filas, incluso si ambos artículos contienen las mismas palabras. Es probable que un sitio con decenas de miles de artículos, algunos de los cuales pueden contener miles de palabras, termine teniendo estas tablas de mapeo con millones de filas. No es inusual que las tablas de índice ocupen varios gigabytes de espacio en disco en tales circunstancias.

Con la versión actual de Búsqueda Inteligente no hay mucho que puedas hacer al respecto. Sin embargo, se espera que en la próxima versión puedas ajustar el número de palabras por frase que se indexa. Actualmente, esto está fijado en 3, lo que significa que cada palabra que se indexa también se indexa como parte de un par de palabras adyacentes y como parte de un trío de palabras adyacentes. Esto es útil para la función de autocompletado y generalmente mejora la calidad de los resultados de búsqueda. En sitios donde el espacio en disco es un problema, sería bueno reducir esto a 2 o incluso 1, de modo que las tablas de mapeo sean proporcionalmente más pequeñas.

## Notas

1. Actualmente no hay un bloqueo de concurrencia para evitar que más de un proceso ejecute el indexador al mismo tiempo. Esto casi con certeza resultará en un índice corrupto. Incluso alguien guardando cambios en un elemento de contenido mientras se realiza un índice completo podría potencialmente dañar el índice.

*Traducido por openai.com*

