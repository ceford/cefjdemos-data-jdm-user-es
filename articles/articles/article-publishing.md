<!-- Filename: J6.x:_Article_Publishing / Display title: Artículo: Edición - Publicación -->

## Introducción

Una parte clave de un Sistema de Gestión de Contenidos (CMS) es su capacidad para entregar contenido a usuarios seleccionados durante periodos seleccionados. ¡Joomla! lo hace con niveles de acceso y con fechas de inicio y finalización de publicación.

Se pueden establecer fechas de inicio y finalización tanto para artículos *Destacados* como para artículos *No Destacados*. Por ejemplo, un nuevo artículo podría ser destacado durante un período determinado, digamos 30 días, después de los cuales se convertiría en un artículo ordinario no destacado. Desaparecería de los diseños de artículos destacados, pero aún aparecería en otros diseños de Blog o de artículos individuales.

En su mayoría, los artículos se publican el día en que se crean y permanecen así hasta que se despublican, archivan o eliminan.

## Captura de pantalla

![La pestaña de publicación del formulario de edición de artículos](../../../en/images/articles/articles-edit-publishing-tab.png)

El panel de *Metadatos* se explica en un artículo separado. Este artículo cubre el panel de *Publicación*.  

## Panel de publicación

Algunos de los campos del formulario están destinados solo para información y no se pueden cambiar directamente en el formulario. Se muestran con fondos grises. Otros campos se pueden modificar si es necesario.

### Comenzar publicación

Este campo se establece en la fecha y hora actuales cuando el artículo se guarda por primera vez. Si deseas que el artículo esté embargado hasta una fecha y hora futuras, puedes establecer su valor utilizando la herramienta de Calendario o editando directamente los valores del campo.

### Finalizar publicación

Por defecto, este campo está en blanco. Si deseas que el artículo desaparezca después de una fecha y hora específicas, utiliza la herramienta de Calendario o escribe una fecha y hora futuras directamente en el campo. En ese momento, el artículo desaparecerá del sitio. En la lista de artículos se marcará como *Publicado, pero ha caducado*.

### Comenzar en destacados

Si el artículo está marcado como un *Artículo Destacado*, este campo se puede configurar para que aparezca en un diseño de *Artículos Destacados* en la fecha especificada. Ten en cuenta que la fecha no se guardará si el artículo no está marcado como un *Artículo Destacado*.

### Finalizar en destacados

Si el artículo está marcado como un Artículo Destacado, este campo se puede configurar para que desaparezca de un diseño de *Artículos Destacados* en la fecha especificada. El artículo permanece publicado y aún puede aparecer en otros diseños. En la lista de artículos se marcará como *Destacado, pero ha caducado*.

### Fecha de creación

Esta fecha se establece cuando el artículo se guarda por primera vez. Es posible que desees cambiarla si has creado una serie de artículos en orden aleatorio y deseas ordenarlos por fecha de creación.

### Creado por

El ID del Usuario del creador se guarda en el momento de la creación y el Nombre de ese usuario aparece en este campo. Puedes cambiar el Creador seleccionando el ícono de persona para revelar un cuadro de diálogo emergente *Seleccionar Usuario*, desde el cual puedes encontrar y seleccionar un usuario diferente.

### Creado por Alias

Si no deseas que el Nombre de Usuario del creador aparezca en el bloque de información del artículo, puedes insertar un Alias aquí. Ingresa tu alias, guarda el artículo y verifica con el botón de Vista previa en la Barra de herramientas.

## Programar la Publicación de un Artículo

Por defecto, los artículos se establecen como **Publicados** tan pronto como se guardan. Al guardar inicialmente el artículo, se crean las fechas de **Fecha de Creación** y **Inicio de Publicación**.

Programar un artículo implica establecer manualmente una fecha y hora de **Inicio de Publicación** para retrasar la publicación. También puedes establecer fechas y horas para **Finalizar Publicación**.

**Nota:** Para que la programación funcione, el **Estado** del artículo debe estar establecido en **Publicado**.

Antes de la fecha de Inicio de Publicación, los artículos se consideran **Pendientes** y después de la fecha de Finalizar Publicación, se consideran **Expirados**. A pesar de que el artículo en sí está configurado como publicado, Joomla utiliza las configuraciones de inicio y finalización para anular el estado publicado predeterminado.

Los valores de fecha y hora se pueden escribir en los campos de fecha o seleccionar con la herramienta de Calendario, que se abre al seleccionar el ícono del calendario al final de cada campo de fecha.

![Fechas de publicación](../../../en/images/articles-access/article-schedule-publishing.png)

El calendario se mueve entre días, meses y años usando las flechas del teclado hacia adelante, hacia atrás, arriba y abajo. El botón **Hoy** establece la fecha actual. El botón **Borrar** borra la fecha y hora.

* Selecciona la fecha requerida.
* Establece la hora usando las cajas desplegables.
* Selecciona el botón **Cerrar** del Calendario para establecer la fecha y hora seleccionadas.
* Selecciona **Guardar** o **Guardar y Cerrar** desde la Barra de Herramientas para guardar los cambios.

## Iconos de Vista de Lista

En la lista de Artículos, el icono de *Destacado* suele ser un círculo gris o una estrella amarilla. De manera similar, el icono de *Estado* suele ser un tic verde o una cruz gris. Cada uno tiene una Información sobre herramientas y la acción habitual es cambiar el estado.

- Publicado y está Actual: <span class="icon-publish" aria-hidden="true"></span>
- No Publicado: <span class="icon-unpublish" aria-hidden="true"></span>
- Destacado: <span class="icon-featured" aria-hidden="true"></span>
- No Destacado: <span class="icon-unfeatured" aria-hidden="true"></span>

Los iconos para artículos con fechas de inicio y fin programadas son diferentes.

- Publicado pero Pendiente: <span class="icon-pending" aria-hidden="true"></span>
- Publicado pero ha Caducado: <span class="icon-expired" aria-hidden="true"></span>
- Destacado pero Pendiente: <span class="icon-pending" aria-hidden="true"></span>
- Destacado pero ha Caducado: <span class="icon-expired" aria-hidden="true"></span>

En cada caso, una Información sobre herramientas muestra información adicional sobre las fechas programadas.

## Consejos

- También puedes programar la publicación de artículos desde el front end.
- También es posible programar a través del elemento de menú para el artículo.
- La programación también está disponible para Contactos y Módulos.

*Traducido por openai.com*

