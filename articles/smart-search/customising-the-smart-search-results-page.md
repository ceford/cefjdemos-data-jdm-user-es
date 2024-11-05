<!-- Filename: Customising_the_Smart_Search_results_page / Display title: Reemplazos de Diseño de Búsqueda Inteligente  -->

## Páginas de Resultados

El componente de Búsqueda Inteligente tiene cinco archivos de diseño que puedes sobrescribir para crear un diseño a tu gusto. Para iniciar el proceso desde el menú del Administrador:

* Selecciona **Sistema / Plantillas del Sitio / Detalles y Archivos de Cassiopeia**.
* Selecciona la pestaña **Crear Sobreescrituras**.
* Desde el panel de Componentes, selecciona **com_finder**.
* Selecciona el elemento **Búsqueda**.
* Desde el panel del Editor, selecciona **html / com_finder / search** para ver la lista de archivos de sobreescritura creados.

Estos archivos no se verán afectados por las actualizaciones de Joomla, pero es posible que se te recuerde que los revises si las fuentes originales se actualizan.

## La Vista de Búsqueda (Diseño Predeterminado)

La vista de búsqueda en diseño predeterminado está dividida en varias partes: el diseño predeterminado, el diseño del formulario, el diseño de los resultados y el diseño de ordenamiento.

### El diseño predeterminado (default.php)

Este diseño es muy simple. Solo define la estructura en la cual se muestran el formulario de búsqueda y los resultados de búsqueda. Este diseño también es responsable de cargar la hoja de estilos CSS predeterminada para Búsqueda Inteligente que se encuentra en `media/com_finder/css/finder.css`, por lo que podrías querer modificar esto para cargar tus propias reglas CSS para Búsqueda Inteligente.

### El diseño del formulario (default_form.php)

Este diseño define el código necesario para que el formulario de búsqueda funcione correctamente. El diseño utiliza código JavaScript, por lo que debes tener cuidado de preservar los selectores que no deben ser alterados a menos que sepas lo que estás haciendo.

El método de vista `getFields` incluye una serie de campos ocultos que son necesarios para realizar búsquedas de forma fiable. El término de búsqueda está definido por el campo de entrada con el nombre "q".

### El diseño de los resultados (default_results.php)

Este diseño produce la lista de resultados coincidentes para el término de búsqueda. También maneja la paginación y carga un diseño para cada resultado de búsqueda individual.

### El diseño del resultado (default_result.php)

Este es el diseño que se carga para mostrar un solo resultado.

### El diseño de ordenamiento (default_sorting.php)

Este elemento solo está presente si Mostrar Campos de Ordenación está configurado en Sí y uno o más Campos de Ordenación Adicionales están seleccionados en la pestaña Avanzado del Ítem de Menú.

*Traducido por openai.com*

