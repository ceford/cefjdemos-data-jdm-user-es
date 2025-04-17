<!-- Filename: Smart_Search_quickstart_guide / Display title: Guía Rápida de Búsqueda Inteligente  -->

## Antecedentes

La búsqueda ha sido una característica de Joomla! desde sus primeros días. Permitía
a los usuarios buscar en la base de datos palabras o frases y devolver resultados en el orden
en que se encontraban. Esa forma de búsqueda ha sido eliminada y reemplazada por Búsqueda Inteligente,
que pre-indexa palabras significativas y utiliza algoritmos de puntuación y filtrado
para ayudar a devolver los mejores resultados. La Búsqueda Inteligente está habilitada por defecto en Joomla 4
y 5.

### Tenga en cuenta

Si tiene elementos de contenido que no están disponibles para vista pública,
la función de autocompletado aún mostrará términos contenidos en esos elementos de contenido.
Los elementos de contenido en sí no pueden ser vistos y no se listarán en los resultados de búsqueda, pero si le preocupa revelar la presencia de una palabra o frase en un elemento de contenido restringido, entonces debería desactivar el autocompletado. Para desactivar el autocompletado, use el siguiente procedimiento:

1. Inicie sesión en el administrador.
2. Seleccione **Componentes → Búsqueda Inteligente**.
3. Seleccione el botón de la barra de herramientas **Opciones**.
4. Cambie *Sugerencias de Búsqueda* de **Mostrar** a **Ocultar**.
5. Seleccione **Guardar y cerrar**.

## Preparación de plugins de Búsqueda Inteligente

Para que el contenido se muestre en los resultados de búsqueda, primero debe ser indexado por uno de los plugins de Búsqueda Inteligente. Antes de iniciar el índice, se recomienda que revises los plugins disponibles y desactives aquellos que no serán necesarios para tu sitio. Para revisar los plugins de Búsqueda Inteligente disponibles, sigue el siguiente procedimiento:

1. Inicia sesión en el Administrador.
2. Selecciona **Plugins** desde el *Panel de Inicio*.
3. Filtra los plugins usando el elemento **finder** de la lista **- Seleccionar Tipo -**.
4. Revisa la lista de plugins y desactiva los que no serán necesarios para tu sitio seleccionando el icono de tick verde en la columna Estado para el plugin. Esto debería cambiar a una cruz/círculo gris para indicar que el plugin está desactivado.

## Ejecutar el indexador

Después de revisar los complementos de búsqueda, es hora de iniciar el indexador de Búsqueda Inteligente. Esto escaneará el contenido de tu sitio web y construirá un índice que permitirá a los visitantes de tu sitio realizar búsquedas rápidas e inteligentes. Hay dos formas de ejecutar el indexador:

* Desde el menú **Administrador / Búsqueda Inteligente / Índice**. Esto es adecuado para sitios más pequeños.
* Desde la Línea de Comandos. Esto es adecuado para sitios más grandes y no debería causar errores de tiempo de espera. Sin embargo, los sitios muy grandes podrían realmente necesitar un servicio de búsqueda externo.

### Indexar desde la interfaz del Administrador

1. Inicia sesión en el Administrador.
2. Selecciona los elementos del menú **Componentes → Búsqueda Inteligente → Índice**.
3. Selecciona el botón **Índice** en la barra de herramientas para iniciar el indexador. Esto
   hará que se cargue una ventana modal con información sobre el estado del indexador y una barra de progreso.

Dependiendo del tamaño de tu sitio, la indexación puede llevar desde unos pocos minutos hasta unas pocas horas en completarse. El indexador utiliza solicitudes AJAX para completar el proceso general en pequeños fragmentos para evitar tiempos de espera y problemas de memoria. La indexación se completa cuando desaparece la barra de progreso y se cierra la ventana modal.

### Indexar desde la CLI

1. Abre una ventana de terminal.
2. Usa el comando `cd` para cambiar al directorio cli en la raíz de tu sitio.
3. Utiliza el siguiente comando:<br>
    php joomla.php finder:index
4. Cuando el indexador haya terminado, ve a la página de Contenido Indexado de Búsqueda Inteligente del Administrador.

## Contenido Indexado

La página de Contenido Indexado muestra todo el contenido indexado. Si prefieres que ciertos elementos no se muestren en los resultados de búsqueda, puedes despublicarlos de la base de datos de Búsqueda Inteligente seleccionando la casilla de verificación junto al título del elemento y luego presionando el botón Despublicar.

**NOTA IMPORTANTE**: Si tu sitio tiene una gran cantidad de contenido, o elementos de contenido particularmente grandes, o tiene espacio en disco restringido, deberías leer sobre [Búsqueda Inteligente en sitios grandes](jdocmanual?article=user/smart-search/smart-search-on-large-sites).

## Exponiendo la Búsqueda Inteligente a los Usuarios del Sitio

Ahora que el índice de Búsqueda Inteligente está preparado y listo, necesitas exponer la Búsqueda Inteligente a los usuarios de tu sitio web. Búsqueda Inteligente ofrece dos maneras de hacer esto:

### La Interfaz del Módulo

Búsqueda Inteligente incluye un módulo que se puede habilitar para mostrar un formulario de búsqueda sencillo en cualquier página y prácticamente en cualquier posición. Para habilitar el módulo de Búsqueda Inteligente utiliza el siguiente procedimiento:

1. Inicia sesión en el Administrador.
2. Selecciona el elemento del menú Extensiones → Gestor de Módulos.
3. Haz clic en el botón Nuevo en la barra de herramientas del Gestor de Módulos.
4. Selecciona "Módulo de Búsqueda Inteligente" de la lista de tipos de módulos mostrada.
5. Configura el módulo al menos ingresando un título, seleccionando la posición del módulo y ajustando las páginas en las que se mostrará si así lo deseas. Opciones adicionales de configuración del módulo se describen en la pantalla de ayuda del módulo de Búsqueda Inteligente.
6. Selecciona el botón Guardar en la barra de herramientas para publicar el módulo.

### La Interfaz del Elemento de Menú

Búsqueda Inteligente también se puede vincular a través de un elemento de menú de Joomla para que los usuarios puedan navegar directamente al formulario de búsqueda principal. Para crear un enlace de elemento de menú a Búsqueda Inteligente utiliza el siguiente procedimiento:

1. Inicia sesión en el Administrador.
2. Selecciona el elemento del menú Extensiones → Gestor de Módulos.
3. Presiona el botón Nuevo en la barra de herramientas del Gestor de Menús.
4. Haz clic en el botón Seleccionar al lado del campo Tipo de Elemento de Menú.
5. Selecciona "Buscar" bajo la entrada "Búsqueda Inteligente" en la lista de tipos de elementos de menú mostrada.
6. Configura el elemento de menú al menos ingresando un Título de Menú y ajustando el elemento padre si así lo deseas.
7. Selecciona el botón Guardar en la barra de herramientas para publicar el elemento de menú.

## Pruebas, Pruebas, Pruebas

Para probar la Búsqueda Inteligente, navega a uno de los elementos del menú que creaste e ingresa una consulta en el formulario de búsqueda, o ingresa una consulta en una de las instancias del módulo de Búsqueda Inteligente. Deberías ser llevado a una lista de resultados de búsqueda si se encuentra alguno para la palabra o frase que ingresaste. Si no se encuentra ningún resultado, se mostrará un mensaje indicando que no se encontraron resultados. Si no se encontró ningún resultado y el sistema tiene una sugerencia de búsqueda basada en tu término, la frase de búsqueda sugerida se mostrará encima del mensaje que indica que no se encontraron resultados.

*Traducido por openai.com*

