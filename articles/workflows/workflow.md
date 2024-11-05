<!-- Filename: J4.x:Workflow / Display title: Flujo de Publicación  -->

## Introducción

En Joomla, un flujo de trabajo es una secuencia de pasos en la vida de un artículo desde su concepción hasta su desaparición. Los pasos suelen ser realizados por diferentes individuos con distintas responsabilidades. Por ejemplo, en el mundo periodístico, un subeditor toma una historia de un reportero y revisa su precisión, gramática, legibilidad y extensión, y quizás más. El subeditor luego pasará la historia al editor quien puede aceptarla o rechazarla, decidir dónde colocarla en el periódico, etc.

El componente de Flujo de Trabajo se utiliza para añadir **etapas** a los artículos y así mejorar los estados estáticos (no publicado, publicado, desechado y archivado) con **transiciones**. Los estados estáticos y las transiciones se registran por separado para que los flujos de trabajo puedan habilitarse o deshabilitarse según sea necesario sin afectar el estado de los elementos de contenido. Los flujos de trabajo se habilitan o deshabilitan en la pestaña *Integración* de la página de *Opciones: Artículos*.

Hay una página de tutorial que contiene pasos para la creación de un ejemplo de flujo de trabajo: [Escenarios de Flujos de Trabajo](jdocmanual?article=user/workflows/workflow-scenarios).  

## Términos y Definiciones

- *Flujo de trabajo:* Un flujo de trabajo es una secuencia completa de pasos. Se pueden crear varios flujos de trabajo diferentes para diferentes propósitos. El componente de Flujo de trabajo contiene un *Flujo de trabajo básico* y los datos de muestra del blog tienen un *Flujo de trabajo de blog* más complejo.
- *Etapa:* Una etapa es una ubicación dentro de un flujo de trabajo. Por ejemplo, un artículo no publicado puede estar en la Etapa 1: En preparación o en la Etapa 2: Listo para revisión, y así sucesivamente. Es la etapa del elemento la que se registra en la base de datos.
- *Transición:* Una transición es un cambio de una etapa a otra, a menudo a la siguiente en el flujo de trabajo, pero podría ser a la etapa anterior o inicial.
- *Estado:* El estado de un artículo puede ser no publicado, publicado, eliminado o archivado. Un estado puede cambiarse ejecutando una transición de flujo de trabajo, siempre que el usuario tenga permiso para cambiar el estado.
- *Categoría:* Cuando se utilizan flujos de trabajo, se puede seleccionar un flujo de trabajo específico para una categoría en la pestaña *Flujo de trabajo* del formulario *Artículo: Editar categoría*.

## La Lista de Flujos de Trabajo

Cuando los flujos de trabajo están habilitados, la lista de flujos de trabajo disponibles puede verse seleccionando **Contenido → Flujos de Trabajo** desde el menú del Administrador.

![Lista de flujos de trabajo](../../../en/images/workflows/workflows-list.png)

- El **Estado** de un flujo de trabajo puede ser Habilitado, Deshabilitado o Eliminado.
- El **Nombre** es un enlace al formulario de edición del flujo de trabajo.
- El elemento **Predeterminado** se utiliza para nuevos elementos que no están asignados a una categoría que tenga un flujo de trabajo definido.
- El elemento **Etapas** es un botón que muestra el número de etapas y un enlace a la lista de etapas del flujo de trabajo.
- El elemento **Transiciones** es un botón que muestra el número de transiciones y un enlace a la lista de transiciones del flujo de trabajo.
- El **ID** es el valor numérico del flujo de trabajo utilizado internamente.

## Etapas

Se accede a las etapas a través de la lista de *Flujos de Trabajo*. Selecciona el botón amarillo que muestra el número de etapas.

![Lista de etapas de flujo de trabajo](../../../en/images/workflows/workflow-stages-list.png)

Selecciona el nombre de una etapa para editarla.

![Formulario de edición de etapas de flujo de trabajo](../../../en/images/workflows/workflow-stage-edit.png)

## Transiciones

En los flujos de trabajo, los artículos pasan de una etapa a otra. Las transiciones se gestionan a través de la lista de *Transiciones*.

![La lista de transiciones](../../../en/images/workflows/workflow-transitions-list.png)

- La *Etapa Actual* define dónde comienza esta transición.
- La *Etapa Objetivo* define dónde termina esta transición.

### Etapas de Transición

Las etapas *Actual* y *Objetivo* se establecen en el formulario *Editar Transición*:

![Formulario de edición de transición](../../../en/images/workflows/workflow-transition-edit.png)

La pestaña de *Acciones de Transición* se utiliza para definir el *Estado* en el que estará el elemento después de completar la transición.

![Pestaña de acciones del formulario de edición de transición](../../../en/images/workflows/workflow-transition-edit-actions-tab.png)

- **Estado de Destacado** Si el elemento estará o no *Destacado*.
- **Estado de Publicación** Selecciona de la lista el estado objetivo.

La pestaña de *Notificaciones de Transición* se utiliza para definir si se envía una notificación para ese estado. Por ejemplo, si un artículo ha sido escrito pero necesita ser revisado, se podría enviar un correo electrónico para notificar al editor.

![Pestaña de notificaciones del formulario de edición de transición](../../../en/images/workflows/workflow-transition-edit-notifications-tab.png)

- **Enviar Notificación** Si se establece en *Sí*, aparecen campos adicionales.
- **Texto de Mensaje Adicional** Agrega texto adicional al mensaje o utiliza una cadena de idioma para hacer que el texto del mensaje sea traducible.
- **Grupos de Usuarios** Selecciona quién recibirá la notificación, por ejemplo, todos los usuarios en el grupo de usuarios *Editor*.
- **Usuarios** Selecciona usuarios individuales para recibir esta notificación.

### Permisos

La pestaña de permisos controla el acceso a esta transición por medio de grupos de usuarios seleccionados. Normalmente, los permisos se heredan de la configuración de permisos en *Artículos: Opciones*.

### Plugins de Transición de Flujos de Trabajo

Los plugins de flujos de trabajo se utilizan para acciones invocadas por transiciones. Dirígete a **Sistema → Plugins** y cambia el filtro *- Seleccionar Tipo -* a *flujo de trabajo*. Cada uno de estos plugins se puede desactivar si no se requiere.

![Lista de plugins de flujos de trabajo](../../../en/images/workflows/workflow-plugins.png)

- **Destacado de Flujo de Trabajo** Esta acción implementa el cambio del estado *Destacado* de un artículo de *Sí* a *No*.
- **Notificación de Flujo de Trabajo** Esta acción implementa la notificación a un usuario de que un cambio de etapa requiere atención.
- **Publicación de Flujo de Trabajo** Esta acción implementa un cambio de estado de un artículo de uno a otro de *Publicado*, *No publicado*, *Papelera* o *Archivado*. Si el usuario no tiene permiso para cambiar el estado, fallará con un mensaje explicativo. ¡La transición que solicitó el cambio de estado aún tendrá éxito!

## Categorías

Los artículos se pueden asignar a categorías. Estas corresponden a un cierto flujo de trabajo y se pueden personalizar de diversas maneras. Puedes establecer un estado, una categoría principal y también restringir el acceso así como los permisos. Esta opción no se encuentra en la pantalla de flujos de trabajo. Para esta opción, necesitas ir a **Contenido → Categorías**. Una vez allí, abre cualquier categoría y verás una pestaña de *Flujos de Trabajo*.

![Flujo de trabajo de edición de categorías de artículos](../../../en/images/workflows/workflow-categories-blog.png)

### Ejemplo

Ciertos artículos necesitan estar disponibles solo para administradores o usuarios de un rango superior.

- Crea una categoría llamada *Restringido*
- Establece todos los permisos en *Permitido* para administradores o superiores.
- Mueve los artículos correspondientes a la categoría *Restringido*.

Esto ahorra la configuración de permisos en artículos individuales.

## Control de versiones

Cuando el flujo de trabajo está habilitado, los campos gestionados por el flujo de trabajo se excluyen del control de versiones (como "estado" y "destacado") para evitar conflictos de permisos.

## Ejemplos

Algunos ejemplos específicos están disponibles para ilustrar cómo utilizar los Flujos de Trabajo para diferentes grupos de usuarios:

- [Ejemplo 1](jdocmanual?article=user/workflows/workflow-example-1) utiliza los grupos de usuarios predeterminados de Autor, Editor y Publicador para preparar elementos para un Boletín Informativo.
- [Ejemplo 2](jdocmanual?article=user/workflows/workflow-example-2) utiliza grupos de usuarios personalizados para preparar elementos para reuniones de comité.

*Traducido por openai.com*

