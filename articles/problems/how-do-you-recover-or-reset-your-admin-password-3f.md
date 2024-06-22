<!-- Filename: How_do_you_recover_or_reset_your_admin_password%3F / Display title: ¿Cómo recuperar o restablecer su contraseña de administrador? -->

Recuperación de contraseña en Joomla! 1.5

Esta página sólo es para la versión 2.5 de Joomla! o posterior. Si aún
usa Joomla! 1.5   puede encontrar instrucciones
aquí.

Normalmente, puede añadir, editar y borrar usuarios y contraseñas desde
el gestor de usuarios del back-end. Para hacer esto, debe haber iniciado
sesión como miembro del grupo de super administradores.

En algunas situaciones, puede que esto no sea posible. Por ejemplo, su
sitio puede haber sido "hackeado" y las contraseñas o usuarios haber
sido cambiados. O quizás la persona que conocía las contraseñas ya no
está disponible. O puede que haya olvidado la contraseña que se usaba.

En estos casos, aún es posible alterar la base de datos de Joomla! para
que pueda volver a iniciar sesión como super administrador. Estos son
los métodos disponicles para los administradores Joomla.

## Método 1: Archivo configuration.php

Si tiene acceso a su archivo `configuration.php` para la instalación
Joomla en su servidor, entonces puede recuperar la contraseña usando el
siguiente método:

1\. Usando un programa de FTP para conectarse a su sitio. Localice el
fichero configuration.php y compruebe sus permisos. Si los permisos son
444 o algún otro valor, a continuación, cambie los permisos del fichero
configuration.php a 644. Esto le evitará problemas al subir los cambios
que haga en el fichero configuration.php más adelante en este proceso.

2\. Descargue el archivo de configuración.

3\. Abra el archivo configuration.php que ha descargado en un editor de
texto como notepad++ y añada esta línea

    public $root_user='myname';

al final de la lista donde myname es un nombre de usuario con acceso de
administrador del que conoce la contraseña. Un nombre de usuario que
posea acceso a la vistas del Grupo Autor o nivel superior también puede
ser utilizado en lugar de un nombre de usuario con acceso de
administrador.

Guarde el fichero configuration.php y súbalo de nuevo al sitio. Puede
dejar los permisos en el fichero configuration.php en 644

Este usuario será ahora un super administrador temporal.

5\. Iniciar la sesión del lado servidor y cambiar la contraseña del
usuario administrador que no tiene la contraseña o crear un nuevo
usuario super admin. Si usted crea el nuevo usuario puede bloquear o
eliminar el antiguo usuario dependiendo de sus circunstancias.

6\. Cuando haya terminado, asegúrese de utilizar el botón "Haga clic
aquí para tratar de hacerlo de forma automática" en el link que aparece
en el cuadro de alerta para quitar la línea que agregó al archivo
configuration.php. Si utilizando el enlace no tuvo éxito, a
continuación, volver atrás y borrar la línea agregada al archivo
configuration.php con un editor de texto. Subir el archivo
configuration.phpde vuelta a la página.

7\. Mediante su programa de FTP compruebe los permisos del archivo
configuration.php, que debe ser 444. Si usted quita manualmente la línea
agregada, a continuación, cambiar los permisos del archivo
configuration.php a 444.

Si no tiene ningún usuario del que conocen su contraseña y no se puede
utilizar lado cliente del registro, puede necesitar hacer un cambio en
su base de datos como se describe a continuación en este documento.

## Método 2: Edición directa de la base de datos

Si el método anterior no funcionó, tiene otras dos opciones, requiriendo
ambas que se trabaje directamente con la base de datos MyQSL.

### Cambiar la Contraseña en la Base de datos

Si el usuario admin esta todavía definido, la opción más sencilla es
cambiar la contraseña en la base de datos a un valor conocido. Esto
requiere que usted tenga acceso a la base de datos MySQL con phpMyAdmin
u otro cliente.

<img
src="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/25px-Stop_hand_nuvola.svg.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/38px-Stop_hand_nuvola.svg.png 1.5x, https://docs.joomla.org/images/4/41/Stop_hand_nuvola.svg.png 2x"
data-file-width="40" data-file-height="40" width="25" height="25"
alt="Stop hand nuvola.svg.png" />Asegúrese de que cambia su contraseña
una vez recupere el acceso

Estas instrucciones muestran cómo cambiar manualmente una contraseña a
la palabra - "secret"

1.  Vaya a phpMyAdmin y seleccione la base de datos de Joomla! del sitio
    en el lado izquierdo del cuadro de la lista desplegable. Esto
    mostrará las tablas de base de datos en el lado izquierdo de la
    pantalla.

2.  Busque y haga clic en la tabla con "\_users" agregado en la lista de
    tablas (nota: usted puede tener un prefijo que no es como jos\_,
    simplemente vaya a la tabla que termina en \_users para su prefijo).

3.  Haga clic en el botón "Examinar" en la parte superior de la barra de
    herramientas. Esto le mostrará a todos los usuarios de este sitio.

4.  Localice el usuario cuya contraseña desea cambiar y pulse el icono
    Editar para esta fila.

5.  Se mostrará un formulario que le permitirá editar el campo de
    contraseña. Copie el valor

        d2064d358136996bd22421584a7cb33e:trd7TvKHx6dMeoMmBVxYmg0vuXEA4199

    en el campo contraseña y pulse el botón "Ir". phpMyAdmin debe
    mostrar el mensaje "Filas afectadas: 1". En este punto, la
    contraseña fue cambiada a que ***secret***.

6.  Inicie la sesión con este usuario y contraseña y cambiar la
    contraseña de este usuario a un valor seguro. Compruebe que todos
    los usuarios mediante el Administrador de usuarios para asegurarse
    de que son legítimos. Si usted ha sido hackeado, es posible que
    desee cambiar todas las contraseñas en el sitio.

### Agregar un Nuevo Usuario Super Administrador

Si el cambio de la contraseña no funciona, o no está seguro de que el
usuario es un miembro del grupo Super Administrador, puede utilizar este
método para crear un nuevo usuario.

1.  Vaya a phpMyAdmin y seleccione la base de datos de Joomla! del sitio
    en el lado izquierdo del cuadro de la lista desplegable. Esto
    mostrará las tablas de base de datos en el lado izquierdo de la
    pantalla.
2.  Pulse el botón "SQL"en la barra de herramientas para ejecutar una
    consulta SQL en la base de datos seleccionada. Esto mostrará un
    campo llamado "Ejecutar consulta SQL/consultas en la base de datos
    ".
3.  Eliminar cualquier texto en este campo, y copiar y pegar la
    siguiente consulta a continuación y pulse el botón "Ir" para
    ejecutar la consulta y agregar el nuevo usuario Administrador a la
    tabla.
4.  Use la consulta SQL de abajo para agregar otra cuenta de
    administrador.

<img
src="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/25px-Stop_hand_nuvola.svg.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/38px-Stop_hand_nuvola.svg.png 1.5x, https://docs.joomla.org/images/4/41/Stop_hand_nuvola.svg.png 2x"
data-file-width="40" data-file-height="40" width="25" height="25"
alt="Stop hand nuvola.svg.png" />¡Asegúrese de que coincida con el
prefijo de tabla de su base de datos!

El código siguiente utiliza jos31\_ como prefijo del nombre de la tabla
que es sólo un ejemplo de prefijo de la tabla. El prefijo cuando se
instala por primera vez Joomla es **ALEATORIO**, o lo que se establece
específicamente. Usted tendrá que cambiar todas las apariciones de
**jos31\_** (su prefijo de la instalación) que se encuentran en el
código de abajo por el prefijo de la instalación que se está usando.

**Código SQL para usar con Joomla
 <img src="https://docs.joomla.org/images/5/53/Compat_icon_2_5.png"
decoding="async" data-file-width="40" data-file-height="17" width="40"
height="17" alt="Joomla 2.5" /> <img src="https://docs.joomla.org/images/4/4d/Compat_icon_3_x.png"
decoding="async" data-file-width="40" data-file-height="17" width="40"
height="17" alt="Joomla 3.x" /> <img src="https://docs.joomla.org/images/b/bd/Compat_icon_4_x.png"
decoding="async" data-file-width="40" data-file-height="17" width="40"
height="17" alt="Joomla 4.x" />**

    INSERT INTO `jos31_users`
       (`name`, `username`, `password`, `params`, `registerDate`, `lastvisitDate`, `lastResetTime`)
    VALUES ('Administrator2', 'admin2',
        'd2064d358136996bd22421584a7cb33e:trd7TvKHx6dMeoMmBVxYmg0vuXEA4199', '', NOW(), NOW(), NOW());
    INSERT INTO `jos31_user_usergroup_map` (`user_id`,`group_id`)
    VALUES (LAST_INSERT_ID(),'8');

En este punto, usted debería ser capaz de iniciar sesión en ellado
servidor de Joomla! con el nombre de "admin2" y la contraseña de
"secret". Después de iniciar sesión, vaya al Administrador de usuarios y
cambie la contraseña a un nuevo valor seguro y agreguer una dirección de
correo electrónico válida a la cuenta. Si hay una posibilidad de que
usted ha sido "hackeado", asegúrese de comprobar que todos los usuarios
son legítimos, especialmente a los miembros del grupo Super
Administrador.

<img
src="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/25px-Stop_hand_nuvola.svg.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/38px-Stop_hand_nuvola.svg.png 1.5x, https://docs.joomla.org/images/4/41/Stop_hand_nuvola.svg.png 2x"
data-file-width="40" data-file-height="40" width="25" height="25"
alt="Stop hand nuvola.svg.png" />Warning!

Advertencia: La los valores de contraseña que se muestran en esta página
son de conocimiento público y son sólo para la recuperación. Su sitio
puede ser hackeado si no cambiar la contraseña a un valor seguro después
de iniciar la sesión. Asegúrese de cambiar la contraseña a un valor
seguro después de iniciar la sesión.


Los ejemplos anteriores cambiarán la contraseña a "secret". Otros dos
posibles valores se muestran a continuación:

    - password = "this is the MD5 and salted hashed password"
    ------------------------------------------------------
    - admin  = 433903e0a9d6a712e00251e44d29bf87:UJ0b9J5fufL3FKfCc0TLsYJBh2PFULvT
    - secret = d2064d358136996bd22421584a7cb33e:trd7TvKHx6dMeoMmBVxYmg0vuXEA4199
    - OU812  = 5e3128b27a2c1f8eb53689f511c4ca9e:J584KAEv9d8VKwRGhb8ve7GdKoG7isMm
