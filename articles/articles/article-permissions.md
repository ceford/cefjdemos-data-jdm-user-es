<!-- Filename: J6.x:Access_Control / Display title: Artículo: Editar - Permisos  -->

## Introducción

Joomla ofrece un sistema sofisticado de *Control de Acceso* basado en *Niveles de Acceso* y *Grupos de Usuarios*. Se describe en el artículo sobre [Control de Acceso](jdocmanal?article=user/users/access-control) en la sección de *Usuarios* de este manual.

La descripción aquí es para la pestaña de *Permisos* del formulario *Artículo: Editar*. Sus configuraciones pueden parecer extrañas a menos que estés familiarizado con el sistema de Control de Acceso de Joomla.

## Captura de pantalla

![La pestaña de permisos del artículo con autor seleccionado](../../../en/images/articles/articles-edit-permissions-tab.png)

¡Puede ser sorprendente que un autor no parezca tener permiso para editar un artículo!

## Grupos de Usuarios de Frontend y Backend

Si no estás familiarizado con los Grupos de Usuarios estándar de Joomla, es útil saber que *Autor*, *Editor* y *Publicador* son grupos de usuarios de frontend. No pueden iniciar sesión en el backend. Su trabajo de crear, editar y publicar artículos se realiza con formularios de edición de artículos del frontend. *Gerente* y *Administrador* son grupos de usuarios con acceso tanto al frontend como al backend y pueden editar artículos utilizando formularios de edición del backend o del frontend.

## Acceso de Edición del Autor

¿Por qué en el formulario de Permisos aparece mostrar *Editar* como **No Permitido (heredado)**
para el grupo de Autores?

Hay una explicación sencilla. Si cierras el formulario de edición y vas a la
página *Artículos: Opciones* a través del botón de *Opciones* en la lista de *Artículos* en la Barra de Herramientas,
la pestaña de *Permisos* allí muestra que un miembro del grupo de Autores tiene
permisos adicionales: *Crear* y *Editar Propio*. Estos son los permisos que
permiten a un autor crear artículos y editar sus propios artículos.

Así que los permisos en el formulario *Artículos: Editar* no permiten a un miembro del
grupo de Autores editar artículos creados por otra persona.
*Traducido por openai.com*

