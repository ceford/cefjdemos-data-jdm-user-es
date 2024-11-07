<!-- Filename: Setting_up_automatic_Smart_Search_indexing / Display title: Indexación de Búsqueda Inteligente  -->

## Indexación Automática

Aunque el índice de Búsqueda Inteligente se mantiene actualizado automáticamente cada vez que se modifican los elementos de contenido, hay algunas circunstancias en las que necesitas volver a ejecutar el indexador. Puedes hacer esto manualmente utilizando el botón de la barra de herramientas Índice en la página de Búsqueda Inteligente: Contenido Indexado. Sin embargo, si necesitas reindexar contenido automáticamente, también es posible ejecutar el indexador desde la línea de comandos. Esto es particularmente conveniente para ejecutar el indexador desde un trabajo *cron*.

Desde el directorio cli, la línea de comando es:

```
php joomla.php finder:index
```

La salida típica del indexador en la línea de comandos se ve así:

    INDEXADOR DE BÚSQUEDA INTELIGENTE
    ============================

    Iniciando el Indexador
    Configurando los plugins de Finder
    Configurados 154 elementos en 0.094 segundos.
     * Lote procesado 1 en 0.213 segundos.
     * Lote procesado 2 en 0.182 segundos.
     * Lote procesado 3 en 0.177 segundos.
     * Lote procesado 4 en 0.009 segundos.
    Tiempo Total de Procesamiento: 0.676 segundos.

## Purga antes de indexar

Normalmente, ejecutar el indexador realizará una actualización incremental del índice. Es decir, solo actualizará el índice para aquellos elementos de contenido que hayan cambiado desde la última actualización del índice. Sin embargo, si necesitas eliminar por completo todas las entradas del índice existentes antes de reconstruir completamente el índice, entonces necesitas realizar una operación de "purgar y luego indexar". Para hacerlo, puedes agregar el argumento `--purge` en la línea de comandos, así:

    php joomla.php finder:index --purge

Ten en cuenta que esto intentará preservar cualquier filtro estático que hayas configurado, mientras que hacer clic en el botón de "Purgar" en la barra de herramientas del Administrador **no** preservará tus filtros estáticos.

## Configuración de un trabajo *cron*

Aunque los detalles específicos están fuera del alcance de este artículo, en general, solo tendrás que ingresar el comando anterior en el administrador de trabajos *cron* y especificar el momento o los momentos en los que se debe ejecutar el trabajo. Probablemente necesites incluir la ruta completa al indexador. Por ejemplo, de esta manera:

    php /var/www/myjoomla/cli/joomla.php finder:index -- purge

Y posiblemente la ruta completa al archivo php, como `/usr/local/opt/php@8.2/bin/php`.

## Problemas de Falta de Memoria

Si tu sitio tiene requisitos de indexación particularmente complejos, es posible que la asignación de memoria estándar no sea suficiente para que el indexador se complete. Puedes aumentar la memoria asignada al indexador de línea de comandos usando un parámetro adicional en la línea de comandos, como este:

    php -d memory_limit=256M joomla.php finder:index

Reemplaza `256M` con lo que sea apropiado para tus circunstancias.

El indexador de línea de comandos utiliza los mismos parámetros que el indexador en la página de Búsqueda Inteligente: Contenido Indexado. Puedes cambiar los parámetros usando el botón de la barra de herramientas de Opciones en esa página. Ten en cuenta que tanto el campo **Tamaño de Lote del Indexador** como el **Límite de Tabla de Memoria** afectan la cantidad de memoria utilizada por el indexador.

*Traducido por openai.com*

