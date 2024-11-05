<!-- Filename: J6.x:_Article_Options / Display title: Artículo: Editar - Opciones   -->

## Introducción

La palabra *Opciones* es ambigua en Joomla! A veces se utiliza de manera intercambiable con *Parámetros* y la mayoría de las vistas de lista de componentes tienen un botón de *Opciones* en la barra de herramientas. Eso lleva a una página de Opciones donde se configuran los parámetros para el componente en su totalidad. Además, muchos formularios de edición de ítems de componentes tienen una pestaña etiquetada como *Opciones* utilizada para establecer parámetros para ese ítem individual.

Este artículo trata sobre la pestaña *Opciones* en el formulario *Artículo: Editar*. Es donde se configuran los parámetros que afectan la apariencia general del artículo que se está editando. Las opciones para los artículos en su conjunto se tratan en un artículo separado.

## Captura de pantalla

La pestaña *Opciones* del formulario *Artículo: Editar* contiene una serie de paneles, la mayoría con opciones de *Usar global (Ocultar o Mostrar)*, *Ocultar* o *Mostrar*. La siguiente captura de pantalla parcial muestra el diseño general.

![Pestaña de opciones de edición de artículo](../../../en/images/articles/articles-edit-options-tab.png)

## Panel de diseño

Un artículo, o parte de él, puede aparecer como una sola página o en un diseño de blog de categoría controlado por un elemento de menú. En un elemento de menú de blog, la mayoría de los campos de diseño tienen opciones de *Usar Global*, *Sí/No* o *Mostrar/Ocultar* y *Usar Configuración del Artículo*. Las opciones en este panel no tienen efecto en los diseños de blog a menos que se seleccione la opción de *Usar Configuración del Artículo* en el elemento del menú.

De lo contrario, estas opciones afectan la apariencia del artículo individual que se está editando.

- **Diseño** En una instalación predeterminada se ofrecen las dos primeras opciones:
  - **---De Opciones Globales--- / Usar Global** Esto se refiere a la configuración de *Artículos: Opciones* disponible desde el botón *Opciones* en la barra de herramientas de la vista de lista de *Artículos*. Su valor de *Elegir un Diseño* está configurado como *Predeterminado*.
  - **---Del Componente--- / Predeterminado** Esto se refiere a la configuración en las opciones de *Artículos: Opciones*. En una instalación predeterminada, es efectivamente igual a la opción de *Usar Global*. Pero si existe una sustitución que se llama default.php, entonces esa sustitución se usa para el diseño.
  - **---Del Plantilla Cassiopeia--- / nombredelapersonalización** Si se ha creado una personalización de plantilla con un nombre diferente de *predeterminado*, aparecerá aquí y se puede seleccionar como un diseño alternativo.
- **Título** Es normal mostrar el título de un artículo, pero puede haber circunstancias en las que no sea apropiado. Seleccione *Ocultar* para omitir el título del artículo en la visualización de la página.
- **Títulos Enlazados** El comportamiento predeterminado es hacer del título del artículo un enlace al artículo donde aparece en los diseños de blog o lista. Esta configuración está controlada por el elemento de menú. Puede estar configurado para *Usar Global (Sí)*, *Usar Configuración del Artículo*, *No* o *Sí*. Si el elemento de menú está configurado para *Usar Configuración del Artículo*, entonces se utilizará el valor de *Títulos Enlazados* en el artículo. De lo contrario, esta configuración no tiene efecto. Si el título no está enlazado, podría usar un enlace de *Leer más* para acceder al artículo desde un diseño de blog o lista.
- **Etiquetas** Mostrar u ocultar etiquetas en la página del artículo individual.
- **Texto de Introducción** Mostrar u ocultar el texto de introducción en la página del artículo individual. Hay ciertas circunstancias en las que puede desear tener un texto de introducción completamente diferente para los diseños de blog que se omiten en el texto completo del artículo.
- **Posición de la Información del Artículo** Esto se refiere al bloque de información sobre un artículo encabezado con *Detalles* y que contiene la información de *Autor*, *Categoría*, *Publicado* y *Visitas*. El valor predeterminado es tener esto por encima del texto del artículo. Ajuste a Abajo para moverlo debajo del texto del artículo en una vista de artículo único. Si se configura como *Dividir*, el elemento *Visitas* se mueve debajo del texto del artículo.
- **Título de la Información del Artículo** Mostrar u ocultar la palabra *Detalles* sobre la lista de información del artículo en la vista de artículo único.

## Panel de categoría

El campo en este panel funciona como podrías esperar. En las vistas de blog, la configuración del elemento del menú tiene prioridad a menos que se establezca en *Usar configuración del artículo*.

- **Categoría** Mostrar u ocultar el nombre de la categoría.
- **Vincular categoría** Vincula (Sí o No) el nombre de la categoría. Si se establece en *Sí*, el nombre de la categoría está vinculado a su blog de categoría.
- **Categoría padre** Si se establece en Sí, la categoría padre aparece como un elemento separado sobre la categoría en *Detalles* de la información del artículo en el diseño de un solo artículo.
- **Vincular categoría padre** Si se establece en Sí, el nombre de la categoría padre se vincula a su página de blog de categoría.

## Panel de asociaciones

Este panel solo está presente en sitios multilingües.

- **Asociaciones** Si se configura para mostrar, se coloca un elemento adicional en la información del artículo comenzando con *También disponible en:* seguido de banderas para representar las versiones de este artículo disponibles en otros idiomas.
- **Usar banderas de imagen** Este elemento aparece si *Asociaciones* está configurado para *Mostrar*. El valor predeterminado *Sí* muestra los botones como banderas de idiomas. La alternativa *No* muestra los botones como códigos de idioma, por ejemplo, *en-GB*.

## Panel del autor

- **Autor** Mostrar u ocultar el nombre del autor de este artículo en la vista de artículo individual. La línea en la información del artículo dice *Escrito por: Nombre del autor*
- **Enlace a la página de contacto del autor** Sí o no para enlazar el Nombre del autor a la página de contacto del autor, si la hay.  

## Panel de Fecha

Los artículos de Joomla almacenan varias fechas. Si se muestran, cada una de las siguientes aparece como líneas separadas en la información de un solo artículo. Recuerda, los diseños de blog utilizan la configuración del elemento de menú a menos que esté configurado en *Usar Configuración del Artículo*. El formato de la fecha es 03 de noviembre de 2024, pero eso puede ser modificado ...[Por Hacer]

- **Fecha de Creación** Oculta por defecto.
- **Fecha de Modificación** Oculta por defecto.
- **Fecha de Publicación** Mostrada por defecto.

## Panel de opciones

- **Navegación** Para un artículo que es uno de varios artículos en una
  categoría, hay botones de *Anterior* y *Siguiente* debajo del texto del artículo para
  navegar a las páginas anteriores o siguientes. Si se establece en *Ocultar*, los botones de navegación
  no se muestran en las páginas de un solo artículo.
- **Visitas** El número total de veces que se ha mostrado el artículo como
  un solo artículo, se muestra en la lista de información del artículo.
- **Enlaces no autorizados** Esto afecta a los diseños de blog, por lo que el elemento de menú del blog de la categoría
  relevante debe tener su valor de *Opciones: Enlaces no autorizados* establecido en
  *Sí* o *Usar configuración del artículo*. Luego, si el *Acceso* de este artículo se establece en
  *Registrado* y la configuración en el artículo no es *No*, el *Texto de introducción*
  para el artículo se mostrará en el diseño del blog pero la etiqueta del botón Leer más
  será *Registrarse para leer más...*. Hacer clic en el enlace Leer más requerirá
  iniciar sesión para ver el contenido completo del artículo.
- **Posición de los enlaces** Esto se refiere a la posición de los enlaces en la
  pestaña de Imágenes y Enlaces, Enlaces A, B y C. La posición predeterminada es encima del
  texto del artículo. Esta opción permite que los enlaces se coloquen debajo del texto del 
  artículo o no se muestren en absoluto.
- **Texto de Leer más** El texto normal, *Leer más:* seguido por el título del
  artículo, se toma de los valores clave/cadena del idioma. Se puede ingresar aquí una anulación 
  personalizada solo para este artículo, por ejemplo, *Ver artículo completo:* seguido
  por el título del artículo.
- **Título de la página en el navegador** El título de la página suele ser el título del artículo. Si
  eso es inconveniente, se puede ingresar un título de página alternativo aquí para usar en la
  página de un solo artículo. Aparece en la pestaña del navegador y en el área
  `<head>...</head>` de la página. Será utilizado por los motores de búsqueda.
*Traducido por openai.com*

