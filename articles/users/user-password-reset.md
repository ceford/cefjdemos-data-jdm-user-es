<!-- Filename: J4.x:User_Password_Reset / Display title: Restablecimiento de Contraseña de Usuario  -->

## Restablecimiento de Usuario

Si a tus usuarios se les permite iniciar sesión en el sitio y un usuario no puede recordar ni el nombre de usuario ni la contraseña, es mejor requerir que el individuo restablezca sus credenciales por sí mismo utilizando los enlaces en el formulario de inicio de sesión:

![módulo de inicio de sesión de usuario del sitio](../../../en/images/users/user-site-login-module.png)

En cada caso, seleccionar un enlace lleva a un formulario para ingresar la dirección de correo electrónico asociada con la cuenta:

![formulario de restablecimiento de contraseña olvidada del sitio](../../../en/images/users/user-forgot-password-reset.png)

Todo el proceso lo lleva a cabo el usuario sin que se requiera intervención de un Administrador. Este es el formulario de verificación de contraseña perdida:

![formulario de confirmación de contraseña olvidada del sitio](../../../en/images/users/user-forgot-password-confirm.png)

Y finalmente, se requiere que el usuario ingrese una nueva contraseña:

![formulario de restablecimiento de contraseña olvidada del sitio](../../../en/images/users/user-forgot-password-complete.png)

## Restablecimiento del Administrador

Si solo hay un inicio de sesión de Administrador, el restablecimiento de la contraseña de un usuario debe ser realizado por un Superusuario o Administrador. Si es el único Superusuario quien no conoce las credenciales de inicio de sesión, consulte el artículo separado sobre Recuperación de Contraseña del Administrador. De lo contrario:

- Seleccione **Usuarios → Administrar** desde el menú del Administrador o seleccione *Usuarios* desde el panel del Sitio en el Tablero de Inicio.
- Encuentre al usuario que necesita un restablecimiento de contraseña.
- Seleccione el **Nombre** enlazado para abrir el formulario de *Usuario: Editar*.
- Ingrese una nueva contraseña en los campos Contraseña y Repetir Contraseña.
- Establezca el campo **Requerir restablecimiento de contraseña** en *Sí*.
- **Guardar y Cerrar**

![formulario de edición de usuario de administradores](../../../en/images/users/users-edit-user-john-doe.png)

Luego deberá enviar un correo electrónico al usuario con la nueva contraseña provisional en texto simple. Después de iniciar sesión, el usuario podrá ver la página de inicio del sitio, pero cualquier intento de navegar a otra página llevará al usuario al formulario de nueva contraseña.

*Traducido por openai.com*

