<!-- Filename: J6.x:Workflow_Scenarios_Example_1 / Display title: Ejemplo de Flujo de Trabajo 1  -->

## Introducción

Un flujo de trabajo consiste en *etapas* y *transiciones* entre esas etapas. Para cualquier artículo, es la etapa actual la que se registra en la base de datos y se utiliza para identificar el flujo de trabajo y las transiciones utilizadas por ese flujo de trabajo.

Un solo sitio puede tener muchos flujos de trabajo. Aquí se utiliza un *Flujo de Trabajo de Boletín* como ejemplo para explicar cómo tres personas con diferentes roles pueden involucrarse en la producción de un artículo de boletín. El ejemplo utiliza los grupos de usuarios predeterminados de Joomla: Autor, Editor y Publicador. Eso tiene un problema: un Autor solo puede ver los artículos Publicados, por lo que no puede volver a editar artículos No Publicados. Un método para evitar ese problema se trata en [Ejemplo 2](jdocmanual?article=user/workflows/workflow-example-2).

![Lista de flujos de trabajo](../../../en/images/workflows/example-1-workflows-list.png)

Nota que el *Flujo de Trabajo Básico* está configurado como el *Predeterminado*. ¡Esto puede tener consecuencias problemáticas que se tratan más adelante en este artículo!

## Los Usuarios

- *Arthur* es un usuario asignado al **Grupo de Autores** de Joomla. Puede crear nuevos
  artículos y editar sus propios artículos, pero no puede editar los artículos escritos por
  otros usuarios ni cambiar el estado de los artículos. Por lo tanto, no puede publicar sus propios
  artículos. Su trabajo es redactar nuevos artículos.
- *Eddie* es un usuario asignado al **Grupo de Editores** de Joomla. Puede editar
  artículos creados por cualquier otro usuario, incluidos Arthur y él mismo. Tampoco
  puede cambiar el estado de un artículo. Su trabajo es revisar los artículos
  enviados por Eddie, verificar su precisión, ortografía y gramática, calidad
  de las imágenes, etc.
- *Pru* es una usuaria asignada al **Grupo de Editores** de Joomla. Ella puede hacer 
  todo lo que Eddie y Arthur pueden hacer. Además, puede cambiar el estado
  de un artículo. Es su trabajo decidir si un artículo es aceptable para
  publicación y publicarlo.

## Las Etapas

Hay cuatro etapas en este Flujo de Trabajo:

![Lista de flujos de trabajo](../../../en/images/workflows/example-1-workflow-stages.png)

- **Borrador** es la etapa creada por Arthur para un nuevo artículo.
- **Revisión** es la etapa donde Eddie se encarga de revisar el contenido.
- **Aprobar** es la etapa donde Pru decide si el artículo es lo suficientemente bueno para publicarse.
- **Publicar** es la etapa cuando el artículo ha sido aprobado y publicado.

Los formularios de entrada de datos de la etapa requieren poca explicación, solo un Nombre y una Descripción.

## Las Transiciones

Se requieren dos transiciones entre cada etapa: una para revertir la etapa si se necesita más trabajo en la etapa anterior; y una segunda para migrar a la siguiente etapa. Se requieren transiciones adicionales para gestionar la finalización de un artículo:

![Lista de flujos de trabajo](../../../en/images/workflows/example-1-workflow-transitions.png)

- **Borrador/Revisión** para mover la etapa de Borrador a Revisión.
- **Revisión/Borrador** para revertir la etapa de Revisión a Borrador.
- **Revisión/Aprobación** para mover la etapa de Aprobación a Revisión.
- **Aprobar/Revisión** para revertir la etapa de Aprobación a Revisión.
- **Revisión/Publicar** para mover la etapa a Publicado y cambiar el estado del artículo a *Publicado*.
- **Publicar** Para establecer el estado del artículo en *Publicado* cuando la transición sea ejecutada por un Autor o Editor.
- **Despublicar** para cambiar el estado del artículo a *No publicado*.
- **Archivar** para cambiar el estado del artículo a *Archivado*.
- **Papelera** para cambiar el estado del artículo a *En la papelera*.

Las últimas tres transiciones permiten a Pru cambiar el estado de un artículo cuando ya no se necesita.

### Editar Transición

El formulario de entrada de datos tiene cuatro pestañas comenzando con la pestaña *Transición*:

![Lista de flujos de trabajo](../../../en/images/workflows/example-1-edit-transition.png)

- **Nombre** Es mejor usar las etapas Actual y Objetivo en el nombre.
- **Etapa Actual** La etapa antes de que ocurra la transición.
- **Etapa Objetivo** La etapa después de que la transición ha tenido lugar.
- **Nota** Cualquier nota explicativa para ayudar a explicar la transición.

#### La pestaña *Acciones de Transición*:

![Lista de flujos de trabajo](../../../en/images/workflows/example-1-edit-transition-actions.png)

- **Estado Destacado** Definir el estado destacado que un artículo debería tener después de ejecutar esta transición. Dejar en *-No seleccionado-* si es probable que el usuario que ejecute esta transición no tenga permiso para destacar artículos.
- **Estado de Publicación** Definir el estado publicado que un artículo debería tener después de ejecutar esta transición. Dejar en *-No seleccionado-* si es probable que el usuario que ejecute esta transición no tenga permiso para cambiar el estado del artículo.

#### La pestaña *Notificaciones*:

![Lista de flujos de trabajo](../../../en/images/workflows/example-1-edit-transition-notification.png)

- **Enviar Notificación** Configurar esto en *Sí* cuando sean necesarias las notificaciones, por ejemplo, cuando Arthur necesite notificar a Eddie que un artículo está listo para revisión.
- **Texto de Mensaje Adicional** Este es un texto adicional genérico para ayudar al receptor.
- **Grupos de Usuarios** Puede optar por enviar la notificación a uno o más grupos de usuarios, o ninguno y enviar la notificación a individuos en su lugar.
- **Usuarios** Seleccionar usuarios individuales de la lista de usuarios.

#### La pestaña *Permisos*:

Tenga en cuenta que *Autor* tiene *Ejecutar Transición* configurado como Permitido (Heredado). No cambie estas configuraciones para otras transiciones que un Autor no deba usar, ya que esto también afectará a Editores y Publicadores.

## La Categoría del Artículo

Cada artículo se asigna a un flujo de trabajo en el primer guardado. Si el artículo se asigna primero a una Categoría que tiene un Flujo de Trabajo seleccionado, se asigna a ese flujo de trabajo. De lo contrario, se asigna al flujo de trabajo predeterminado. Eso puede ser problemático porque el componente de Flujo de Trabajo no proporciona un método para cambiar el flujo de trabajo una vez asignado. Puede ser cambiado por un Super Usuario utilizando la Acción por Lote en la página de lista de Artículos.

### Crear una Categoría de Boletín

Se necesita una nueva categoría de Boletín para mostrar el Boletín como un Blog de Categoría y para asegurar que los artículos del Boletín se asignen al Flujo de Trabajo del Boletín.

![Lista de flujos de trabajo](../../../en/images/workflows/example-1-newsletter-category.png)

## El elemento de menú del boletín

Para que los visitantes del sitio vean el Boletín, este debe ser la página de inicio o estar vinculado con un elemento de menú. Para seguir este ejemplo, crea un nuevo elemento de menú del tipo *Blog de categoría* utilizando la categoría *Boletín*.

Prueba el elemento de menú del sitio. Es probable que sea una página en blanco con este mensaje:

<div class="alert alert-info">
No hay artículos en esta categoría. Si las subcategorías se muestran en esta página, pueden tener artículos.
</div>

## Iniciar sesión como Arthur

¿Recuerdas a Arthur el Autor? Después de iniciar sesión, la página del Boletín debería tener un botón etiquetado como **Nuevo Artículo**. Selecciónalo para redactar un nuevo artículo.

### Redactar un Artículo

Completa el formulario de edición del artículo como lo harías para cualquier artículo. Excepto, antes de la primera guardada, fíjate en la pestaña de *Publicación*.

- **Etapa del Flujo de Trabajo** debe estar configurada en **Ejecutar Transición** *Borrador/Revisión*.
- **Categoría** debe estar configurada en *Boletín*.

Cuando hayas terminado de editar el artículo, selecciona *Guardar* o *Guardar y Cerrar*.

<div class="alert alert-danger">Después de cerrar el artículo, Arthur no podrá editarlo de nuevo porque los usuarios en el grupo de Autor no pueden ver artículos No Publicados.</div>

## Iniciar sesión como Eddie

Eddie, el Editor, tiene permiso para ver artículos no publicados, por lo que la página del Boletín muestra cualquier artículo no publicado para que él pueda editarlo.

### Revisar el artículo

Selecciona el artículo redactado por Eddie y realiza los cambios necesarios para mejorarlo. Cuando estés satisfecho, en la *Pestaña de Publicación*:

- El **Estado del flujo de trabajo** debe configurarse en **Ejecutar Transición** *Revisar/Aprobar*.

A diferencia de Arthur, que no puede ver su artículo después de guardarlo, Eddie puede ver y editar el artículo nuevamente. También puede establecer la transición para la siguiente etapa para Aprobar/Publicar. La transición funcionará, pero el artículo no se publicará ya que Eddie no tiene permiso para publicar.

## Iniciar sesión como Pru

Cuando se estableció la etapa de Aprobación en el flujo de trabajo, Pru debería haber recibido un mensaje solicitando acción. Así que inicia sesión como Pru para revisar el artículo y establecer su Etapa de Flujo de Trabajo en **Ejecutar Transición** *Publicar*. *Guardar y Cerrar* el artículo para ver el resultado publicado. Cierra sesión para ver el resultado sin el enlace de edición.

Reflexión: se necesita otra etapa para permitir que Pru revierta la etapa de Publicar a Revisar si quiere que Eddie arregle algo.

## Flujo de Trabajo del Backend

Los grupos de usuarios Autor, Editor y Editor jefe están destinados para el uso en el frontend. El problema para Arthur es que no puede acceder a sus artículos en borrador desde el frontend porque su grupo de usuarios no tiene acceso de visualización para artículos no publicados.

Puedes permitir el acceso al backend para todos los miembros de estos grupos de la siguiente manera:

- Ve a la página de **Configuración Global**.
- Selecciona la pestaña de **Permisos**.
- Selecciona *Autor* y configura el **Inicio de Sesión del Administrador** como *Permitido*.
- **Guardar**
- Ve a la página de **Artículos: Opciones**.
- Selecciona su pestaña de **Permisos**.
- Selecciona *Autor* y configura el **Acceso a la Interfaz de Administración** como *Permitido*.

Esto permitirá a Arthur, Eddie y Pru iniciar sesión en el backend con acceso a los ítems de contenido. Un panel principal de inicio mucho más reducido:

![Panel principal para arthur](../../../en/images/workflows/example-1-backend-home.png)

Pero Arthur tiene acceso a sus artículos en borrador:

![Lista de artículos para Arthur](../../../en/images/workflows/example-1-backend-articles.png)

Observa que Arthur no puede editar el último artículo en la lista porque no es uno de sus propios artículos. El título del artículo no está vinculado. De manera similar, Arthur no puede editar ninguna de las categorías existentes porque no tiene permiso y ellas tampoco están vinculadas. Puede crear una nueva Categoría, pero está sin publicar ¡y él no puede publicarla!   

## Solución para Flujo de Trabajo Incorrecto

Si asignas un artículo al flujo de trabajo incorrecto, hay dos métodos disponibles para solucionar el problema.

### Método de Súper Usuario

- Ve a la lista de **Artículos**.
- Marca la casilla de verificación del artículo problemático.
- Selecciona el botón **Acciones** en la barra de herramientas.
- Selecciona el botón **Lote** de la lista.
- Selecciona **Cambiar Etapa** en el diálogo *Procesar Lote Artículos Seleccionados*.
- Selecciona un Flujo de Trabajo y Etapa apropiados como destino.
- Selecciona el botón **Procesar**.

![Lista de artículos para Arthur](../../../en/images/workflows/example-1-backend-batch.png)

### Método Alternativo

Alternativamente, puedes editar una tabla de la base de datos con phpMyAdmin o similar.

Información requerida:

- El ID del artículo desde la última columna en la lista de Artículos.
- El ID de una etapa en el flujo de trabajo requerido desde la última columna de la
  lista de Etapas del Flujo de Trabajo que deseas usar.

En phpMyAdmin:

- Navega la tabla #__workflow_associations para encontrar el item_id que contiene
  el ID de tu artículo.
- Cambia el valor de stage_id al ID de la etapa que buscaste en el flujo de trabajo requerido.

Vuelve a tu lista de artículos y verifica que el ítem problemático ahora esté usando 
el flujo de trabajo correcto.

