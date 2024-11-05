<!-- Filename: J3.x:Plugin_Joomla_Update_Notification / Display title: Notificación de actualización de Joomla!   -->

## Icono y Tarea

Existen dos plugins con nombres similares:

* **Quick Icon - Notificación de Actualización de Joomla!**
* **Tarea - Notificación de Actualización de Joomla!**

El primero verifica actualizaciones de Joomla y te notifica cuando visitas la página del Tablero Principal. Tiene un parámetro: el Grupo de este plugin (este valor se compara con el valor del grupo utilizado en los módulos de Iconos Rápidos para inyectar los iconos).

El segundo verifica periódicamente la disponibilidad de nuevas versiones de Joomla!. Cuando se encuentra una, dispara una tarea para enviar un recordatorio de actualización por correo electrónico a los Super Usuarios. El correo electrónico puede personalizarse a través de *Sistema → Plantillas de Correo*.

Los correos electrónicos enviados por los plugins del Sistema de Notificación de Actualización de Joomla! están diseñados para ayudar a mantener el software actualizado, lo cual ayuda a que el sitio web permanezca seguro. Las actualizaciones deben instalarse lo más pronto posible después de su lanzamiento.

## Estado del Plugin

Los dos plugins separados pueden estar Activados o Desactivados.

- Con **Quick Icon ... Desactivado** el icono de *Checking Joomla ...* en el Tablero Principal permanece inactivo, aunque puedes seleccionarlo para ir a la página de actualización de Joomla.
- Con **Tarea ... Desactivada:** la tarea para enviar un correo electrónico no se activa.

## Parámetros de la Tarea

Desde el menú del Administrador, vaya a **Sistema / Tareas Programadas** y seleccione el elemento **Notificación de Actualización** de la lista de *Tareas Programadas*. Allí hay varias pestañas de parámetros e información para ver y cambiar si es apropiado.

### Frecuencia de Correos de Notificación

La frecuencia de ejecución de la tarea está configurada por defecto para cada 24 horas. Eso significa que el sitio web de Joomla revisará si hay una actualización para el núcleo y todas las extensiones, plugins, módulos y plantillas instaladas a intervalos de 24 horas. Un valor de 0 enviaría un correo de actualización cada vez que se acceda al sitio. ¡0 es solo para pruebas!

Tenga en cuenta que la tarea es activada por la actividad del sitio. Si usted es el único usuario, se activará en su próxima visita si ha pasado más de 24 horas.

### Correos de Super Usuario

La notificación por correo electrónico se envía solo a los usuarios que tienen el privilegio de Super Usuario. Este campo le permite seleccionar qué Super Usuarios recibirán las notificaciones por correo electrónico.

- Si se deja en blanco, todos los Super Usuarios del sitio recibirán el correo electrónico de notificación de actualización.
- Para limitar qué Super Usuarios reciben la notificación de actualización, ingrese aquí las direcciones de correo electrónico de los Super Usuarios. Si hay múltiples direcciones de correo electrónico de Super Usuarios, use una coma para separarlas.

### Idioma del Correo Electrónico

La notificación se puede enviar en cualquier idioma que esté utilizando en su sitio web.

- **Auto (predeterminado)** envía el correo electrónico de notificación de actualización en el idioma predeterminado del sitio.
- Seleccionar un idioma distinto de Auto (predeterminado) fuerza a que los correos electrónicos de notificación de actualización se envíen en este idioma específico.

## Consejos

- Para desactivar las notificaciones de actualización de Joomla! por correo electrónico, simplemente deshabilita el complemento.
- El asunto y el texto del cuerpo del correo electrónico se pueden modificar a través de la lista **Sistema / Plantillas de correo electrónico**. Selecciona el elemento **Joomla: Notificación de actualización**. En un sitio multilingüe, estará en el idioma seleccionado actualmente.
  - **Asunto** Ten en cuenta que los marcadores de posición {SITENAME} – {URL} se sustituyen cuando se envía el mensaje.
  - **Cuerpo** ¡También hay más marcadores de posición allí!

*Traducido por openai.com*

