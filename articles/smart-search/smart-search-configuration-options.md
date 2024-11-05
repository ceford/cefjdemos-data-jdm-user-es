<!-- Filename: Smart_Search_configuration_options / Display title: Opciones de Búsqueda Inteligente  -->

## Acerca de las Opciones

Las opciones te permiten gestionar la configuración global de Búsqueda Inteligente. La configuración de Opciones es heredada por las vistas, pero la configuración en un Elemento del Menú anulará la configuración Global.

El panel de Opciones está dividido en dos partes. Cuando termines de hacer ajustes, selecciona el botón Guardar; de lo contrario, selecciona el botón Cancelar para descartar cualquier cambio.

## Opciones de Búsqueda

Las opciones de búsqueda controlan el comportamiento de los formularios de búsqueda y los resultados de búsqueda para el front-end de Finder.

- **Descripción del Resultado** - Esta opción controla si los resultados de búsqueda deben mostrarse con descripciones. El valor predeterminado es Mostrar.
- **Longitud de la Descripción** - Esta opción controla la longitud máxima de caracteres de las descripciones de los resultados de búsqueda. Las descripciones se truncan a la longitud máxima, pero la truncación siempre se realiza en el último espacio de manera que no se corte una palabra por la mitad. Solo es efectivo cuando la opción de Descripción del Resultado está configurada para Mostrar. El valor predeterminado es 255 caracteres.
- **URL del Resultado** - Esta opción controla si los resultados de búsqueda deben mostrarse con URLs debajo de la descripción (si está habilitado). El valor predeterminado es Mostrar.
- **Búsqueda Avanzada** - Esta opción controla si se deben mostrar las opciones de búsqueda avanzada. El valor predeterminado es Mostrar.
- **Expandir Búsqueda Avanzada** - Las opciones de búsqueda avanzada están contenidas en un contenedor colapsable. Esta opción controla si el contenedor de las opciones de búsqueda avanzada debería estar expandido por defecto. El valor predeterminado es No.
- **Filtros de Fecha** - Esta opción controla si los filtros de fecha deben mostrarse en las opciones de búsqueda avanzada. El valor predeterminado es Ocultar.
- **Etiquetas de Resultados** - Esta opción controla si los resultados de búsqueda deben mostrarse con Etiquetas. Requiere que las Etiquetas JXtended estén instaladas. El valor predeterminado es Mostrar.
- **Resaltar Términos de Búsqueda** - Esta opción controla si los términos de búsqueda deben ser resaltados en los resultados de búsqueda. El valor predeterminado es Sí.

## Opciones de Índice

Las opciones de índice controlan el comportamiento del indexador utilizado para procesar y analizar contenido para la búsqueda. La mayoría de los ajustes como el multiplicador de peso y las opciones de stemmer no producirán cambios inmediatos ya que se utilizan durante la indexación y los efectos de cambiar esos ajustes solo se verán después de que el índice haya sido purgado y ejecutado de nuevo.

- **Tamaño de Lote del Indexador** - Esta opción controla el tamaño de lote del indexador. El indexador de Búsqueda Inteligente divide el proceso total de indexación en varios lotes para reducir la carga del servidor y evitar los límites de memoria y tiempo de ejecución de PHP. Si los elementos de contenido que se están indexando son particularmente cortos y/o el servidor es particularmente rápido, el indexador puede procesar más elementos por lote. Sin embargo, si los elementos de contenido que se están indexando son particularmente largos y/o el servidor es particularmente lento, el indexador tiene que procesar menos elementos por lote. El valor predeterminado es 50.
- **Límite de Tabla de Memoria** - Esta opción controla el límite de la tabla de memoria. El indexador de Búsqueda Inteligente utiliza tablas de memoria MySQL para almacenar temporalmente datos de contenido en lugar de almacenarlos en los buffers de memoria de PHP porque los elementos de contenido grandes agotarán rápidamente los ajustes de límite de memoria predeterminados de PHP. Sin embargo, las tablas de memoria de MySQL también tienen límites de tamaño ajustables y reajustarlas no es confiable. Se proporciona esta configuración para lidiar con tablas de memoria con límites de tamaño menores al usual y solo debe ajustarse al encontrar errores de Tabla Llena durante la indexación. El valor predeterminado es 30,000. Si encuentras errores de "tabla llena", intenta **reducir** este parámetro. El valor óptimo debería resultar en tablas de memoria que sean un poco más pequeñas que el parámetro <a href="http://dev.mysql.com/doc/refman/5.1/en/server-system-variables.html#sysvar_max_heap_table_size" rel="nofollow noreferrer noopener"><em>max_heap_table_size</em></a> en MySQL, que por defecto es de 16 megabytes.
- **Multiplicador de Peso del Texto del Título** - Esta opción controla cuánto influye el texto del título en la puntuación de relevancia general de un resultado de búsqueda. El valor predeterminado es 1.7.
- **Multiplicador de Peso del Texto del Cuerpo** - Esta opción controla cuánto influye el texto del cuerpo en la puntuación de relevancia general de un resultado de búsqueda. El valor predeterminado es 0.7.
- **Multiplicador de Peso de Meta-datos** - Esta opción controla cuánto influye el texto de meta-datos en la puntuación de relevancia general de un resultado de búsqueda. El valor predeterminado es 1.2.
- **Multiplicador de Peso del Texto de la Ruta/URL** - Esta opción controla cuánto influye el texto de la ruta/URL en la puntuación de relevancia general de un resultado de búsqueda. El valor predeterminado es 2.0.
- **Multiplicador de Peso del Texto Misceláneo** - Esta opción controla cuánto influye el texto misceláneo en la puntuación de relevancia general de un resultado de búsqueda. El valor predeterminado es 0.3.
- **Stemmer** - Esta opción controla qué stemmer de idioma debe usarse durante la indexación. El stemmer Solo Inglés es una implementación en PHP puro que no tiene dependencias. El stemmer Snowball requiere la extensión PHP de Stem pero ofrece soporte para 14 idiomas, incluidos danés, alemán, inglés, español, finlandés, francés, húngaro, italiano, noruego, neerlandés, portugués, rumano, ruso y turco. El valor predeterminado es Solo Inglés.
- **Habilitar Registro** - crea un archivo de registro durante el proceso de indexación. El valor predeterminado es no.

*Traducido por openai.com*

