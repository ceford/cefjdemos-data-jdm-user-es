<!-- Filename: J4.x:User_Registration / Display title: Registro de Usuario  -->

## Política de Registro

En un sitio Joomla, los usuarios registrados tienen permiso para iniciar sesión y ver contenido o interactuar con contenido que los usuarios no registrados no pueden. El inicio de sesión del sitio y el inicio de sesión del Administrador se tratan por separado, aunque hay una configuración de la Configuración Global que permite combinarlos. Algunos sitios tienen un pequeño número de usuarios creados por un Administrador. Otros sitios tienen tantos usuarios que necesitan auto-registrarse y auto-activar sus cuentas. La manera en que los usuarios se registran en tu sitio se configura en el formulario de *Usuarios: Opciones*.

## Permitir Registro de Usuarios

El auto-registro de usuarios no está permitido por defecto. Cualquier nuevo usuario debe ser creado por un Gerente o Administrador. El auto-registro puede permitirse con algunos cambios simples en el formulario de *Usuarios: Opciones*.

- Seleccione **Usuarios → Administrar** en el menú del Administrador.
- Seleccione el botón *Opciones* en la Barra de Herramientas.
- Configure **Permitir Registro de Usuario** en **Sí**.
- El **Grupo de Registro de Usuario Nuevo** debe ser **- Registrado -**
  a menos que haya una buena razón para que sea algo diferente.
- La **Activación de Cuenta de Usuario Nuevo** debe ser **Propia** o
  **Administrador**.
  - Propia: El usuario recibirá un correo electrónico con un enlace de activación. La cuenta se activará cuando el usuario haga clic en el enlace de activación.
  - Administrador: El usuario recibirá un correo electrónico con un enlace de activación. Cuando el usuario haga clic en este enlace, el Administrador del Sitio será notificado por correo electrónico. Luego, el Administrador del Sitio necesita activar la cuenta del usuario.

![Pestaña de opciones de configuración de usuario](../../../en/images/users/users-configuration-user-options.png)

- **Guardar y Cerrar**
- Añadir un módulo de *Iniciar sesión*. O
- Añadir un ítem de menú de *Usuarios: Formulario de Inicio de Sesión* y un ítem de menú de *Usuarios: Cerrar Sesión*.

## Desactivar el Registro de Usuarios

- Configura **Permitir el registro de usuarios** en **No**.

## Añadir un Nuevo Usuario

Si no se permite el auto-registro, cualquier nuevo usuario debe ser creado por un Administrador. Procede de la siguiente manera:

- Selecciona el icono **Usuarios +** en el panel del sitio del Tablero de Inicio. O
- Selecciona **Usuarios** → **Administrar +** desde el menú del Administrador.
- Completa el formulario **Detalles del Nuevo Usuario**. La mayoría de los campos tienen valores predeterminados adecuados.

![Página de entrada de datos de nuevo usuario](../../../en/images/users/users-new-user.png)

- Selecciona la pestaña **Grupos de Usuarios Asignados** y marca la casilla correspondiente al grupo de usuarios deseado. Registrado está marcado por defecto.
- **Guardar & Cerrar**.
- En la lista de Usuarios, verifica que la cuenta del nuevo usuario esté Habilitada (marca verde en las columnas Habilitado).

## Bloquear a un Usuario

El mejor método para lidiar con un usuario problemático es deshabilitar la cuenta del usuario en lugar de eliminarla. Esta medida se puede utilizar para suspender al usuario y puede revertirse si el usuario promete comportarse adecuadamente. Eliminar una cuenta rompería cualquier vínculo con el contenido contribuido por el usuario, como la autoría de artículos, y podría darle al usuario la oportunidad de registrarse nuevamente con la misma dirección de correo electrónico.

Para bloquear a un usuario:

- Seleccione **Usuarios → Gestionar** desde el menú del Administrador.
- Busque al usuario en la lista de *Usuarios*. Utilice el filtro de texto si es necesario.
- Seleccione el icono de Habilitado que aparece como un tick verde junto al nombre del usuario. Aparece una etiqueta **Bloquear** al pasar el ratón.

![Página de entrada de datos de nuevo usuario](../../../en/images/users/users-hover-block.png)

- Seleccione el icono de *Habilitado*. La página se recargará con el icono de Habilitado apareciendo como una cruz gris.

## Desbloquear a un usuario

Simple:

- Cambia el ícono *Habilitado* de nuevo a una marca verde.

*Traducido por openai.com*

