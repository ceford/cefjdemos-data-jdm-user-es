<!-- Filename: Unable_to_connect_to_the_database / Display title: Conexión a la Base de Datos -->

## Error de Conexión

Si recibes un error de "**Incapaz de conectarse a la base de datos**" durante la instalación, verifica que hayas ingresado correctamente los detalles de tu base de datos MySQL/MariaDB. El script de **instalación** no te permitirá continuar a menos que los detalles sean correctos.

Ten en cuenta que no se espera que crees un usuario y una contraseña de base de datos durante la instalación. Deben haber sido creados previamente.

Si el error ocurre después de mover tu sitio a otro host, revisa los siguientes elementos de tu archivo *configuration.php*. Las configuraciones normales de la base de datos son las siguientes:

    public $dbtype = 'mysqli';
    public $host = 'localhost';
    public $user = 'yourdbuser';
    public $password = 'yourdbpassword';
    public $db = 'yourdbname';
    public $dbprefix = 't6q6i_';

Si el error ocurre en un sitio que ha estado funcionando, hay varias posibles razones, a veces temporales y a veces accidentales.

## Las fallas más comunes

1. A veces verás este mensaje si MySQL/MariaDB ha dejado de funcionar en tu servidor. El administrador de tu servidor puede cerrar temporalmente MySQL/MariaDB para realizar mantenimiento. En tales circunstancias, es probable que tu sitio vuelva a estar en línea en breve.
2. Tu usuario de base de datos ha sido eliminado. Si este es el caso, necesitarás recrear tu usuario de base de datos con el mismo nombre de usuario y contraseña que existían cuando instalaste Joomla por primera vez. Usa el panel de control de tu dominio para administrar esto o contacta a tu administrador de servidor.
3. Tu nombre de usuario o contraseña de la base de datos ha cambiado.

*Traducido por openai.com*
