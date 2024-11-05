<!-- Filename: J4.x:User_Profile / Display title: Perfil del Usuario  -->

## Datos de Registro

La información del usuario recopilada mediante el formulario de registro de usuario predeterminado se limita a Nombre, Nombre de usuario y Dirección de correo electrónico. Sin embargo, los propietarios de sitios a menudo requieren datos adicionales, como Dirección y Teléfono. Tales datos pueden obtenerse con el complemento User - Profile.

- Seleccione **Home Dashboard → Plugins** desde el menú del administrador.
- Busque y abra el formulario de entrada de datos **Plugins: User - Profile**.
- En la primera parte del formulario, establezca en Deshabilitado cualquier elemento que no desee que aparezca en el formulario de registro de usuario.
- En la segunda parte del formulario, establezca en Deshabilitado cualquier elemento que no deba aparecer en el formulario de perfil de usuario.
- Guardar y cerrar.

![complemento de perfil de usuario](../../../en/images/users/user-profile-plugin.png)

- Si se permite el auto-registro, abra el formulario de registro de usuario para verificar que estén presentes los campos adicionales del perfil de usuario.
- Desde el menú del administrador, cree un nuevo usuario o edite un usuario existente. Seleccione la pestaña **User Profile** y verifique que estén presentes los campos adicionales del perfil de usuario.

## Datos del Perfil de Usuario

Un usuario que ha iniciado sesión en el front end puede tener acceso a un elemento de menú **Editar Perfil** que enlaza con un formulario de perfil. Esta es una manera conveniente para que el usuario cambie la contraseña y complete cualquier dato faltante del perfil.

Desde el menú del Administrador:

- Selecciona **Menús → Menú Principal → +** o cualquier otro menú adecuado.
- Ingresa un título adecuado como **Editar Perfil**.
- En el campo **Tipo de Elemento de Menú** usa el botón **Seleccionar**.
- En el diálogo popup **Tipo de Elemento de Menú**, selecciona **Usuarios** → **Editar Perfil de Usuario**.
- Establece el campo **Acceso** en **Registrado**. ¡Esto es IMPORTANTE! el elemento de menú solo debe verse al haber iniciado sesión.
- Guardar y Cerrar.

![formulario de elemento de menú de perfil de usuario](../../../en/images/users/user-profile-menu-item-form.png)

- Inicia sesión en el sitio y usa el enlace para verificar el Perfil de Usuario.

![resumen de perfil de usuario](../../../en/images/users/user-profile-summary.png)

- Prueba el botón **Editar Perfil**.

*Traducido por openai.com*

