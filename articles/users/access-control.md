<!-- Filename: J4.x:Access_Control / Display title: Control de Acceso  -->

## Introducción

Joomla tiene un mecanismo sofisticado para controlar quién puede ver y manipular contenido en un sitio de Joomla. La parte de **quién** se configura en las opciones del componente Usuarios con Grupos de Usuarios y Niveles de Acceso. La parte de **manipular** se configura en los Permisos de Acción, ya sea en la Configuración Global, en la configuración de Componentes o en la configuración de Artículos. Por ejemplo, los valores predeterminados configurados en los Permisos Globales pueden ser anulados en los Permisos de Artículos (todos los artículos) y los Permisos de Artículos pueden ser anulados en los Permisos de Artículos individuales.

## Grupos de Usuarios

Los Grupos de Usuarios se utilizan para dividir a los usuarios del sitio en grupos con diferentes responsabilidades. Por ejemplo, los miembros del grupo de usuarios Autor tienen permiso para iniciar sesión en el sitio, crear artículos y editar sus propios artículos. ¡Nada más! Los miembros del grupo Super Usuarios tienen responsabilidad sobre todos los aspectos de la gestión y operación del sitio. Joomla ofrece nueve grupos de usuarios por defecto y puedes crear más si los necesitas.

![Lista de grupos de usuarios](../../../en/images/users/access-control-users-groups-list.png)

Los grupos de usuarios por defecto están configurados con relaciones de padre e hijo para minimizar la duplicación de permisos. Ejemplos de herencia:

- Un miembro del grupo Registrado no tiene permiso para el inicio de sesión de Administrador. Tampoco lo tienen Editor o Publicador.
- Un miembro del grupo Autor tiene permiso para Crear y Editar Propios. Lo mismo ocurre con Editor y Publicador, pero tienen permisos adicionales.

Puedes crear nuevos grupos de usuarios para propósitos especiales según sea necesario. Por ejemplo, podrías querer crear un grupo que tenga permiso de inicio de sesión de Administrador pero con acceso restringido a un solo componente. Hay un ejemplo de tal grupo de usuario personalizado hacia el final de este tutorial.

## Niveles de Acceso

Cada vez que creas un objeto, como un artículo, un módulo o un elemento de menú, verás un campo de Acceso, que usualmente se encuentra en la columna derecha del formulario de entrada de datos. Es una lista desplegable que ofrece una opción entre Público, Invitado, Registrado, Especial y Superusuarios. El valor predeterminado es Público. Los niveles de acceso predeterminados se muestran en la siguiente captura de pantalla:

![Niveles de acceso de visualización de usuarios](../../../en/images/users/access-control-users-access-levels.png)

Ejemplos:

- Si creas un módulo del sitio y configuras el Acceso como Registrado, solo será visto por usuarios que hayan iniciado sesión en el sitio.
- Si creas un elemento de menú del sitio y configuras el Acceso como Superusuarios, solo será visto por Superusuarios que hayan iniciado sesión en el sitio.

## Permisos

Los Permisos de Configuración Global son el punto de partida desde el cual las configuraciones de permisos en componentes o elementos individuales pueden heredar o anular. Captura de pantalla:

![permisos de configuración global](../../../en/images/users/access-control-global-configuration-permissions.png)

La captura de pantalla muestra que los miembros del grupo Público no tienen permiso para realizar ninguna acción. Si seleccionas cada grupo a su vez, verás cómo cambian los permisos de grupo en grupo. Nota que a los Gerentes y Administradores se les permite el Inicio de Sesión del Administrador, pero a los Autores, Editores y Publicadores no. Estos últimos son efectivamente roles de Sitio en lugar de roles de Administrador.

Todos los permisos de grupo heredan del grupo Público. No tiene permiso para ninguna acción. Sin embargo, por defecto, los elementos en el grupo Público pueden ser vistos, por lo que asignar permiso Público a un ítem permitirá que sea visto por todos los visitantes del sitio, ya sean iniciados en sesión o no.

### Permisos de Artículos

Las acciones de Permisos de Artículos difieren de las acciones de Permisos de Configuración Global. No están presentes los elementos relacionados con el inicio de sesión y sí están presentes los elementos relacionados con flujos de trabajo. Este es un patrón bastante típico: un componente tendrá permisos relevantes para el componente; un ítem de componente (como un artículo) tendrá permisos relevantes para ese único ítem.

![permisos de contenido](../../../en/images/users/access-control-global-content-permissions.png)

### Permisos de un Solo Artículo

Los permisos de un solo artículo tienen solo tres elementos: Eliminar, Editar y Editar Estado:

![permisos de artículo único](../../../en/images/users/access-control-article-permissions.png)

## Ejemplo de Control de Acceso: Usuario de Propósito Especial

Suponga que necesita crear un Grupo de Usuarios para usuarios que tienen solo una responsabilidad, en este ejemplo un Administrador de Artículos. Los usuarios de este grupo deben tener permiso para iniciar sesión como Administrador, pero no deben ver nada más que los elementos de Contenido. Procedimiento:

### Crear un nuevo Grupo de Usuarios

- Seleccione **Usuarios → Grupos** en el menú del Administrador.
- Seleccione el botón `Nuevo` en la barra de herramientas.
- Llene el campo Título del Grupo: Administrador de Artículos.
- El Grupo Padre debe ser Público - no tiene permisos para nada.

![Formulario de nuevo grupo de usuarios](../../../en/images/users/access-control-new-group.png)

### Asignar a Especial

- Seleccione **Usuarios → Niveles de Acceso** en el menú del Administrador.
- Seleccione el elemento **Especial**.
- Marque la casilla de Administrador de Artículos en el formulario **Usuarios: Editar Nivel de Acceso de Visualización**.
- Guardar y Cerrar.

![Seleccionar acceso para el grupo](../../../en/images/users/access-control-select-access-for-group.png)

### Permisos de Configuración Global

- Seleccione **Panel de Inicio → Configuración Global** en el menú del Administrador.
- Seleccione la pestaña **Permisos**.
- Seleccione el grupo **Administrador de Artículos**.
- Establezca **Inicio de Sesión de Administrador** en Permitido.
- Guardar y Cerrar.

![Seleccionar acceso para el grupo](../../../en/images/users/access-control-article-administrator-global-permissions.png)

### Permisos de Opciones de Artículos

- Seleccione **Contenido → Artículos** en el menú del Administrador.
- Seleccione el botón `Opciones` en la barra de herramientas.
- Seleccione la pestaña **Permisos**.
- Seleccione el grupo **Administrador de Artículos**.
- Establezca todos los elementos, excepto los dos primeros (Configurar ACL y Opciones y
  Configurar solo Opciones), en Permitido.
- Guardar y Cerrar.

![Seleccionar acceso para el grupo](../../../en/images/users/access-control-article-administrator-content-permissions.png)

### Crear o Editar Usuario

- Cree un nuevo usuario o edite un usuario existente que no esté asignado a ningún grupo.
- Seleccione **Administrador de Artículos** en la pestaña **Grupos de Usuarios Asignados** del formulario de edición del Usuario.
- Guardar y Cerrar.
- Inicie sesión como un usuario en el Grupo de Administrador de Artículos solamente. El menú debe mostrar solo los elementos relacionados con artículos:

![Seleccionar acceso para el grupo](../../../en/images/users/access-control-article-administrator-home-dashboard.png)

*Traducido por openai.com*

