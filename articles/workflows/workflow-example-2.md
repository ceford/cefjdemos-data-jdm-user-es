<!-- Filename: J6.x:Workflow_Scenarios_Example_2 / Display title: Ejemplo de Flujo de Trabajo 2 -->

## Introducción

Este ejemplo involucra a dos usuarios, Alice y Bob, quienes son respectivamente la presidenta y el secretario de un comité. El flujo de trabajo involucra la preparación y aprobación de agendas y actas de las reuniones del comité. Charlie es un miembro del comité que tendrá acceso a los documentos del comité cuando sean publicados. El flujo de trabajo utiliza solo el frontend.

## Grupos de Usuarios

Primero crea nuevos Grupos de Usuarios, todos hijos de *Registrado*.

- **Comité** Un hijo de *Registrado*
- **Presidente** Un hijo de *Comité*
- **Secretario** Un hijo de *Comité*

![Grupos de usuarios personalizados](../../../en/images/workflows/example-2-user-groups.png)

## Nivel de Acceso del Usuario

- Crea un nuevo nivel, **Comité** y añade *Comité* a los Grupos de Usuarios Con Acceso de Visualización.
- En el Nivel de Acceso *Especial* añade *Comité* a los Grupos de Usuarios Con Acceso de Visualización.

![Niveles de Acceso de Visualización](../../../en/images/workflows/example-2-viewing-access-levels.png)

## Crear Usuarios

- **Alicia** en el grupo de *Presidenta*.
- **Beto** en el grupo de *Secretaría*.
- **Carlos** en el grupo de *Comité*.

## Crear el Flujo de Trabajo

- **Nombre** *Flujo de Trabajo del Comité*
- **Descripción** *Flujo de trabajo para la preparación de documentos del Comité.*
- **Permisos**
  - **Comité** Todo configurado a *Heredado* No permitido (heredado).
  - **Presidente** Todo configurado a *Permitido* excepto *Eliminar*. Quizás...
  - **Secretario** Todo configurado a *Permitido* excepto *Eliminar* y *Editar Estado*.

![Lista de flujos de trabajo](../../../en/images/workflows/example-2-workflows-list.png)

### Crear las Etapas del Flujo de Trabajo

- **Borrador** 
  - **Nota** *Documentos en preparación.* 
  - **Permisos** Todo dejado en *Heredado*.
- **Revisión**
  - **Nota** *Documentos en espera de aprobación.* 
  - **Permisos** Todo dejado en *Heredado*.
- **Publicar**
  - **Nota** *Documentos publicados.* 
  - **Permisos** Todo dejado en *Heredado*.

![Etapas del flujo de trabajo](../../../en/images/workflows/example-2-stages-committee-workflow.png)

### Crear las Transiciones del Flujo de Trabajo

#### Borrador a Revisión

Esta es la transición normal hacia adelante en la secuencia de etapas.

- **Nombre** *Borrador/Revisión*
- **Pestaña de Transición**
  - **Etapa Actual** *Borrador*
  - **Etapa Objetivo** *Revisión*
  - **Nota** *Transición a la siguiente etapa.*
- **Pestaña de Acciones de Transición**
  - **Estado Destacado** *- Ninguno Seleccionado -*
  - **Estado de Publicación** *- Ninguno Seleccionado -*
- **Pestaña de Notificación**
  - **Enviar Notificación** *Sí* Los destinatarios necesitan tener *Recibir Emails del Sistema* habilitado para recibir notificaciones por correo electrónico. 
  - **Texto Adicional del Mensaje** ¿Algo específico para este flujo de trabajo?
  - **Grupos de Usuarios** *Presidente*
  - **Usuarios** Una alternativa al uso de Grupos de Usuarios.
- **Pestaña de Permisos** Todo configurado a **Heredado**.

#### Revisión a Borrador

Esta es la reversión a una etapa anterior en la secuencia invocada cuando el
Presidente requiere más trabajo por parte del Secretario. Los campos del formulario son similares a los campos de Borrador/Revisión excepto por la Nota y el *Etapa Actual* y *Etapa Objetivo* que están invertidos.

#### Revisión a Publicar

Esta es la transición que cambia el estado de un elemento de *No Publicado* a *Publicado*. Solo el Presidente tiene permiso para realizar ese cambio.

- **Nombre** *Revisión/Publicar*
- **Pestaña de Transición**
  - **Etapa Actual** *Revisión*
  - **Etapa Objetivo** *Publicar*
  - **Nota** *La transición final a publicación.*
- **Pestaña de Acciones de Transición**
  - **Estado Destacado** *- Ninguno Seleccionado -*
  - **Estado de Publicación** *Publicado*
- **Pestaña de Notificación**
  - **Enviar Notificación** *Sí* Los destinatarios necesitan tener *Recibir Emails del Sistema* habilitado para recibir notificaciones por correo electrónico. 
  - **Texto Adicional del Mensaje** *Un documento del comité ha sido publicado y ahora está disponible para ver.*
  - **Grupos de Usuarios** *Comité*
  - **Usuarios** Una alternativa al uso de Grupos de Usuarios.
- **Pestaña de Permisos**
  - **Secretario** Establecer *Ejecutar Transición* a *Denegado*.

#### Publicar a Revisión

Este es un cambio de Publicar de nuevo a Revisión. ¿Es realmente necesario? Un
artículo publicado aún puede ser editado por el Secretario o el Presidente. Tal vez un documento del Comité con datos sensibles ha sido publicado por error.

Si es necesario, crear una Transición similar a la transición *Revisión a Publicar* pero con las Etapas invertidas, las *Acciones de Transición / Estado de Publicación* configuradas a *No Publicado* y un mensaje genérico de *Texto Adicional del Mensaje*.

#### Archivo

Esta es la transición que se ejecuta cuando un documento del Comité ya no es necesario.
En el flujo de trabajo permanece en la etapa Publicar pero el estado del artículo se
cambia de Publicado a Archivado.

- **Nombre** *Archivo*
- **Pestaña de Transición**
  - **Etapa Actual** *Publicar*
  - **Etapa Objetivo** *Publicar*
  - **Nota** *Cambiar el estado del elemento de Publicado a Archivado.*
- **Pestaña de Acciones de Transición**
  - **Estado Destacado** *- Ninguno Seleccionado -*
  - **Estado de Publicación** *Archivado*
- **Pestaña de Notificación**
  - **Enviar Notificación** *No* Esta no es una transición que requiera acción. 
- **Pestaña de Permisos**
  - **Secretario** Establecer *Ejecutar Transición* a *Denegado*.

![Transiciones del flujo de trabajo](../../../en/images/workflows/example-2-transitions-committee-workflow.png)

## Crear una Nueva Categoría

<div class="alert alert-warning">¡Este paso es muy importante! Los nuevos documentos del Comité deben crearse con esta categoría o adoptarán el flujo de trabajo predeterminado que necesita que un Súper Usuario lo cambie.</div>

- **Título** *Comité*
- **Flujo de Trabajo** Seleccione *Flujo de Trabajo del Comité* de la lista de Flujos de Trabajo.
- **Permisos**
  - Autor, Editor y Publicador: Todos configurados en *No Permitido* o dejados en *No Permitido (Heredado)*.
  - Comité: Todos dejados en *Heredado*.
  - Presidente: Todos excepto *Eliminar* configurados en *Permitido*.
  - Secretario: Todos excepto *Eliminar* y *Editar Estado* configurados en *Permitido*.

## Crear un Ítem de Menú

- **Título** *Documentos del Comité*
- **Tipo de Ítem de Menú** Lista de Categoría
- **Elegir una Categoría** *Comité*
- **Acceso** *Comité*

![Ítem de menú de documentos del comité](../../../en/images/workflows/example-2-menu-item.png)

## Verificar el Sitio

Inicia sesión como Alice, Bob, Charlie y un Súper Usuario por turno para ver lo que pueden ver:

Alice, Bob y Charlie pueden ver el elemento del Menú, pero nadie más puede, ni siquiera un Súper Usuario. Después de seleccionar el elemento del menú, Alice y Bob pueden ver una tabla de documentos del Comité, incluyendo aquellos que no han sido publicados. Charlie solo puede ver una tabla de documentos publicados del Comité o un mensaje explicativo si no se ha publicado ninguno.

Alice y Bob también pueden ver un enlace de Editar para cada artículo y un botón de **Nuevo Artículo**. Este generalmente es utilizado por Bob para crear un documento del Comité, pero Alice también puede hacerlo.

![Vista de Bob de la página de la lista de categorías de documentos del comité](../../../en/images/workflows/example-2-committee-papers.png)

### Para Crear y Publicar un Documento del Comité

- Inicia sesión como Secretario y selecciona el botón **Nuevo Artículo** en la 
  página de *Documentos del Comité*.
- Ingresa el texto y *Guarda*. Esto se puede hacer en varias sesiones de edición,
  tal vez durante varios días o semanas. El artículo permanece No publicado y en 
  etapa de Borrador hasta que...
- Selecciona la pestaña *Publicación* en el formulario de edición y establece la 
  *Etapa de Flujo de Trabajo* en Ejecutar Transición **Borrador/Revisión**. 
- Selecciona **Guardar y Cerrar** para ejecutar la transición.
- El trabajo del Secretario está completo por ahora y se ha enviado un mensaje al
  Presidente del Comité.
- El Presidente inicia sesión, revisa el documento listo para Revisión y utiliza la 
  transición **Revisión/Publicar** para hacer que el documento sea *Publicado*. El trabajo del
  Presidente está completo por ahora y se envía un mensaje a los miembros del Comité.
- Los miembros del Comité pueden iniciar sesión y acceder al documento publicado.

