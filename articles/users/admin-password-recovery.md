<!-- Filename: How_do_you_recover_or_reset_your_admin_password%3F / Display title: Recuperación de Contraseña de Administrador  -->

## Introducción

Normalmente, un Superusuario puede añadir, editar y eliminar usuarios y contraseñas de la lista de Usuarios. En algunas situaciones esto puede no ser posible. Por ejemplo, la persona que conocía la contraseña de un Superusuario ya no está disponible. O tal vez el Superusuario ha olvidado la contraseña que se usó.

En tales casos, hay dos métodos disponibles que permiten a un Administrador del sitio iniciar sesión como Superusuario.

## Método 1: Editar el archivo configuration.php

Si tienes acceso al archivo `configuration.php` de la instalación de Joomla en tu servidor, entonces puedes restablecer una contraseña de Super Usuario o crear un nuevo Super Usuario si puedes iniciar sesión como Gerente o Administrador.

Necesitas abrir el archivo `configuration.php` en un editor de texto. Primero cambia los permisos del archivo a 644. Tus herramientas de gestión del sitio, como cPanel o Plesk (hay otras), generalmente te permiten hacer esto en línea. Si no, es posible que necesites usar FTP para descargar el archivo, cambiarlo localmente y subirlo de nuevo.

Añade esta línea al final del archivo, pero antes de la llave de cierre:
```
    public $root_user='myname';
```
donde **myname** es un nombre de usuario con acceso al grupo de *Gerente* o *Administrador* para el que conoces la contraseña. Un nombre de usuario que esté en los grupos de *Autor*, *Editor* o *Publicador* no funcionará porque esos grupos no tienen acceso al backend.

Este usuario será ahora un Super Usuario temporal.

Inicia sesión en el backend y cambia la contraseña del Super Usuario para el que no tienes la contraseña o crea una nueva cuenta de Super Usuario. Si creas un nuevo usuario, puedes querer bloquear o eliminar al usuario antiguo dependiendo de tus circunstancias.

Cuando termines, asegúrate de usar el enlace *Seleccionar aquí para intentar hacerlo automáticamente* que aparece en el cuadro de alerta para eliminar la línea que fue añadida al archivo configuration.php. Si usar el enlace no fue exitoso, vuelve y elimina la línea añadida de tu archivo configuration.php usando un editor de texto.

Si no tienes usuarios que conozcan sus contraseñas, es posible que necesites hacer un cambio en tu base de datos.

## Método 2: Editar la Base de Datos

Si los métodos anteriores no funcionaron, tienes dos opciones más, ambas
requieren trabajar directamente con la base de datos MySQL.

### Cambiar una Contraseña en la Base de Datos

La opción más sencilla es cambiar la contraseña del Super Usuario en la base
de datos a un valor conocido. Esto requiere que tengas acceso a la base de
datos MySQL usando phpMyAdmin u otro cliente. Estas instrucciones muestran cómo
cambiar una contraseña a la palabra **secret**.

Este método solo funcionará si el usuario seleccionado está en los grupos
de *Manager* o *Administrator*.

**¡Asegúrate de cambiar la contraseña del Super Usuario una vez que recuperes el acceso!**

1. Abre phpMyAdmin y selecciona la base de datos del sitio Joomla!. Esto
   mostrará las tablas de la base de datos en el lado izquierdo de la pantalla.
2. Encuentra y selecciona la tabla *#__users* donde *#_* es el prefijo de la
   tabla para tu sitio.
3. En la vista *Browse*, busca el usuario cuya contraseña deseas cambiar y
   selecciona el icono de Editar para esta fila.
   - si la lista es larga, selecciona el botón SQL en la parte superior y usa esta consulta:<br>
   `SELECT * FROM `xxxxx_users` WHERE `username` = 'username'`<br>
   donde usas tu prefijo de base de datos para reemplazar `xxxxx` y el nombre de usuario
   que necesitas encontrar en lugar de `username`.
4. En el formulario de edición cambia la contraseña a<br>
   `d2064d358136996bd22421584a7cb33e:trd7TvKHx6dMeoMmBVxYmg0vuXEA4199`<br>
   y selecciona el botón *Go* al final del formulario. phpMyAdmin debería
   mostrar el mensaje *Affected rows: 1*. En este punto, la contraseña debería
   ser **secret**.
5. Inicia sesión con este usuario y contraseña y cambia la contraseña de este
   usuario por un valor seguro. Revisa todos los usuarios para asegurarte de que
   son legítimos. Si has sido hackeado, es posible que quieras cambiar todas las
   contraseñas del sitio.

### Añadir un Nuevo Super Usuario

Si cambiar la contraseña no funciona o no estás seguro de qué usuario es
miembro del grupo Super Usuario, puedes usar este método para crear un nuevo
Super Usuario.
1. Abre phpMyAdmin y selecciona la base de datos del sitio Joomla!.
2. Selecciona el botón *SQL* en la barra de herramientas para ejecutar una
   consulta SQL en la base de datos seleccionada. Esto mostrará un campo llamado
   "Ejecutar consulta/consultas SQL en la base de datos xxxxx".
3. Elimina cualquier texto en este campo y copia y pega la siguiente consulta.
   Recuerda reemplazar `xxxxx` con tu propio prefijo de base de datos.
   ```
   INSERT INTO `xxxxx_users`
      (`name`, `username`, `password`, `params`, `registerDate`, `lastvisitDate`, `lastResetTime`)
   VALUES ('Administrator2', 'admin2',
       'd2064d358136996bd22421584a7cb33e:trd7TvKHx6dMeoMmBVxYmg0vuXEA4199', '', NOW(), NOW(), NOW());
   INSERT INTO `xxxxx_user_usergroup_map` (`user_id`,`group_id`)
   VALUES (LAST_INSERT_ID(),'8');
   ```
   Selecciona el botón *Go* para ejecutar la consulta y añadir el nuevo Super Usuario a
   la tabla.

En este punto, deberías poder iniciar sesión en el backend de Joomla!
con el nombre de usuario *admin2* y la contraseña *secret*.

Después de iniciar sesión, ve a la lista de Usuarios y cambia la contraseña a un nuevo valor seguro
y añade una dirección de correo electrónico válida a la cuenta.

Si existe la posibilidad de que hayas sido *hackeado*, asegúrate de comprobar que todos los usuarios
son legítimos, especialmente cualquier miembro del grupo Super Usuario.

## Contraseñas Temporales Alternativas

**Advertencia:** Los valores de contraseña que se muestran en esta página son de conocimiento público y son solo para recuperación. Para evitar ser hackeado, asegúrate de cambiar una contraseña temporal por un valor seguro después de iniciar sesión.

    password = "esta es la contraseña con hash MD5 y salada"
    ------------------------------------------------------
    admin  = 433903e0a9d6a712e00251e44d29bf87:UJ0b9J5fufL3FKfCc0TLsYJBh2PFULvT
    secret = d2064d358136996bd22421584a7cb33e:trd7TvKHx6dMeoMmBVxYmg0vuXEA4199
    OU812  = 5e3128b27a2c1f8eb53689f511c4ca9e:J584KAEv9d8VKwRGhb8ve7GdKoG7isMm

*Traducido por openai.com*

