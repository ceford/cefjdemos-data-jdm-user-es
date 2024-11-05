<!-- Filename: J4.x:How_to_Show_a_Calendar_Month_List_of_Archived_Articles_Using_a_Module / Display title: Artículos Archivados -->

## Introducción

La archivación de artículos es una de las maneras en que Joomla! ayuda a gestionar los artículos de un sitio web, ya que contribuye a reducir el desorden en el backend. Pero, ¿quiénes deberían poder acceder a los artículos archivados?

Una forma de lograr esto es mostrar una lista mensual de artículos archivados utilizando uno de los Módulos básicos de Joomla. En este ejemplo, se configurará un **Módulo de Artículos Archivados** para que se muestre en la barra lateral del sitio web.

## Crear el Módulo *Artículos - Archivado*

Utilice uno de los siguientes métodos:
* Seleccione el elemento **Módulos** desde el Panel de Inicio. O...
* Seleccione **Contenido / Módulos del Sitio** desde el menú del Administrador.
* Seleccione el elemento **Artículos Archivados** de la lista de Módulos (Sitio).

Esto creará el nuevo módulo y lo abrirá para su configuración.

## Configuración del Módulo

Para el uso estándar del módulo, solo hay algunas configuraciones:

- **Título** Ingrese un nombre para el módulo.
- **\# de Meses** Establece el número de meses que deseas mostrar. Estos aparecerán como enlaces en el frontend. Configura usando las flechas hacia arriba/abajo o introduce directamente un número en el campo.
- **Mostrar/Ocultar Título** Elige si deseas mostrar el título activando *Mostrar* o *Ocultar*.
- **Posición** Establece una posición donde deseas mostrar el módulo en el frontend. Las posiciones están dictadas por tu plantilla. Este ejemplo usa la posición *Sidebar Right* de la plantilla Cassiopeia de Joomla.
- **Estado** Por defecto, el estado del módulo es **Publicado**. Otras opciones son **No publicado** y **En la papelera**.
- **Inicio de Publicación** Puedes programar el inicio de la publicación del módulo.
- **Final de Publicación** Puedes programar cuándo detener la publicación del módulo.
- **Acceso** Si deseas controlar quién puede ver el módulo en el frontend, puedes elegir un nivel de acceso.
- **Orden** Se utiliza para controlar dónde se muestra el módulo dentro de la posición que has seleccionado. Por ejemplo, es posible que tengas varios módulos en la barra lateral y quieras que este esté en la parte superior o inferior, o en algún lugar entre otros en la barra lateral. Puede ser un poco confuso al principio, ya que el campo muestra una posición numerada y el nombre de un módulo. El nombre puede ser de un módulo que no está publicado. Lo importante es recordar que el número más bajo estará en la parte superior y el número más alto, en la parte inferior.
- **Nota** Puede ser útil usar el campo de notas si, por ejemplo, estás usando el mismo tipo de módulo en varios lugares.

### Pestaña de Asignación de Menú

Por defecto, el módulo se publicará **En todas las páginas**.

Alternativamente, puedes elegir a través de una lista desplegable **Ninguna página**, **Solo en las páginas seleccionadas** o **En todas las páginas excepto las seleccionadas**. Las dos últimas opciones te proporcionan un árbol de menúes del sitio web donde puedes seleccionar/deseleccionar páginas.

### Otros Ajustes

La pestaña **Avanzado** tiene configuraciones relacionadas con el diseño del módulo cuando se muestra.

La pestaña **Permisos** te permite controlar qué grupos de usuarios pueden hacer con el módulo.

## Publicar el Módulo

Cuando estés listo, selecciona el botón **Guardar y Cerrar**.

El módulo se publicará en la barra lateral del sitio web y mostrará una
lista de enlaces según el número de meses a mostrar establecido en el módulo.

![Ejemplo de Módulo de Artículos Archivados](../../../en/images/modules/modules-archived-articles.png "Ejemplo de Módulo de Artículos Archivados")

## Consejos

Cuantos más artículos archivados tengas, mayor será el número de enlaces que
muestre el módulo. Puede ser más apropiado limitar el número
de enlaces utilizando categorías o puedes usar múltiples Módulos de Artículos
Archivados nombrados en consecuencia.

*Traducido por openai.com*

