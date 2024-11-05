<!-- Filename: Changing_user_groups / Display title: Cambiando los Grupos de Usuario -->

## Herencia de Grupo

Las listas de grupos utilizan un patrón de herencia. Por ejemplo, un usuario en el grupo de Autores hereda todos los privilegios del grupo de Registrados y obtiene algunos privilegios adicionales. De igual manera, un usuario en el grupo de Editores hereda todos los privilegios del grupo de Autores y gana algunos privilegios más adicionales. Los grupos del backend heredan el nivel más alto de privilegios en el frontend.

Por esta razón, solo necesitas seleccionar un grupo para un usuario individual: el grupo con más privilegios.

## Pasos

Puedes cambiar el grupo de un usuario siguiendo estos pasos. Debes iniciar sesión como Administrador o Usuario Super para poder cambiar los grupos de un usuario. Además, un Administrador no puede convertirse a sí mismo ni a otros en un Usuario Super.

1. Desde el *Tablero de Inicio*, selecciona el elemento **Usuarios**. O...
2. Desde el menú de *Usuario*, selecciona **Usuarios** y luego **Administrar**.
3. Encuentra al usuario requerido en la lista de usuarios. Puedes buscar por nombre, nombre de usuario, correo electrónico o id: prefijo.
4. Selecciona el nombre del usuario para editar.
5. Selecciona la pestaña *Grupos de Usuarios Asignados*.
6. Selecciona el grupo al que un usuario necesita pertenecer.
7. Selecciona *Guardar*.

## Lista de Control de Acceso (ACL) para Joomla

La siguiente es la Lista de Control de Acceso (ACL) para Joomla. Se enumera el grupo de usuarios y a continuación las viñetas describen los permisos asociados con ese grupo.

### Grupos del Frontend

#### Invitado

- Ver el sitio público y artículos públicos

#### Registrado

- Privilegios del Grupo Invitado
- Ver artículos registrados
- Sin acceso a elementos restringidos al Grupo Invitado

#### Autor

- Privilegios del Grupo Registrado
- Crear nuevos artículos
- Editar los artículos que poseen
- Ver contenido especial

#### Editor

- Privilegios del Grupo Autor
- Editar todos los artículos, incluidos los no publicados

#### Publicador

- Privilegios del Grupo Editor
- Publicar artículos

### Grupos del Backend

Estos grupos te permiten iniciar sesión en el Administrador a través de la URL */administrator*.

#### Gerente

- Privilegios del Grupo Publicador
- Acceder al Backend del Administrador

#### Administrador

- Privilegios del Grupo Gerente
- Crear nuevos usuarios
- Instalar extensiones

#### Super Usuario

- Privilegios del Administrador
- Cambiar la plantilla del sitio
- Cambiar la configuración global

*Traducido por openai.com*

