<!-- Filename: Backup_Basics_for_a_Joomla!_Web_Site / Display title: Conceptos básicos sobre copia de seguridad de un sitio web Joomla! -->

Mantén siempre una copia de seguridad reciente de tu sitio. Los
accidentes ocurren, pero hay muchas otras razones donde es de ayuda
tener tus archivos de copia de seguridad a mano antes cuando surja la
necesidad

Las causas de la pérdida de datos son muchas. Los sitios Joomla! pueden
verse comprometidos por los atacantes si el administrador del sitio no
ha prestado atención a la seguridad o en casos excepcionales, cuando los
hackers sortean una seguridad más elevada. Joomla! está diseñado para el
trabajo en equipo e incluso los buenos editores pueden hacer que un
error de dañe el sitio.

Hay muchas razones por la cual administradores del sitio web necesitan
devolver nuevamente el sitio a un estado de funcionamiento anterior.

Práctica hacer copias de seguridad y restauración. Nadie debe esperar
una emergencia para poner a prueba sus habilidades y herramientas para
lidiar con una emergencia. Muy a menudo la gente cree quqe algo que esta
vacío o dañado es una copia de seguridad y descubre que ninguno de sus
datos críticos fue realmente guardado en su copia de seguridad. A nadie
le gusta un barco que se hunde con sus botes salvavidas vacíos y también
es aconsejable practicar sacar a la gente de los botes salvavidas y en
un nuevo sistema de trabajo.

Tener una copia de seguridad no es sólo por posibles accidentes, porque
una persona versada en copias de seguridad puede ayudar con el
desarrollo seguro de nuevas características. Hacer copias de seguridad y
restauración ayuda a los administradores de las páginas web a crear una
plataforma web donde los nuevos cambios se pueden practicar sin poner en
riesgo sitios web de producción. El clon puede ser creado en una máquina
local que actúa como servidor de prueba o en cualquier otra carpeta o
cuenta de alojamiento web que soporte versiones de SQL y PHP, utilizadas
por el sitio del que has hecho copia de seguridad.

Es fácil para cualquier persona mezclar su sitio en vivo y sitio de
ensayo, por lo tanto, cambia el color de la plantilla de tu sitio de
ensayo para recordar a los desarrolladores que es el sitio de ensayo y
no es vivio para el público.

## Back Up a Joomla Website Using Akeeba (Common method)

This is the preferred method using the Akeeba Backup Extension.

- Akeeba Backup produces a *.jpa* file.
- The compressed *.jpa* file contains all the Website's files and the
  content of the database.
- The *.jpa* file also includes an installer.
- Akeeba's *kickstart.php* unpacks the *.jpa* file.
- You then run the installer and install your site like a Joomla
  install.
- The installer changes the configuration for restoring to a different
  location and prompts for the new database details.

You can download the Akeeba Backup extension from the <a
href="https://extensions.joomla.org/extensions/extension/access-a-security/site-security/akeeba-backup/"
class="external text" target="_blank" rel="noreferrer noopener">Joomla
extension directory</a>. There is a link to full instructions there as
well.

## Introducción

Hay dos partes una copia de seguridad completa de tu sitio Joomla!.
Ellas son:

1.  La información de la base de datos, que normalmente se encuentran en
    tu base de datos mysql.
1.  Los archivos y las carpetas en tu sitio web, alojado en la mayoría
    de los sitios web estático en html.

Si no incluyes en tu copia de seguridad tus archivos y la base de datos,
la copia de seguridad es incompleta.

## Copia de seguridad, parte 1 de 2: La base de datos

Uno de los primeros pasos para hacer la copia de seguridad de tu sitio
Joomla es cerrar el sitio al público, has la copia de seguridad de los
archivos y a continuación, vuelve a abrir el sitio. Los pasos indicados
desde phpmyadmin.net omiten esta operación necesaria. Ir al panel del
Lado Servidor de tu sitio Joomla!, Dentro de la configuración global, en
la pestaña Sitio, establece "Sitio fuera de línea" = sí.

Esto cambiará el aspecto de tu archivo configuration.php en la raíz de
su sitio web Joomla!.

Un administrador tendrá que utilizar su panel de control del alojamiento
web, para ver que el archivo o usar FTP para descargarlo y verlo. Dentro
de configuration.php puedes encontrar el nombre de la base de datos
sobre la cual necesitas hacer la copia de seguridad.

Busca la línea con el código parecido a `var $db = 'x1234';`' o
`public $db = 'x1234';` Donde *x1234* es el nombre de la base de datos.

Utilizando la información de inicio de sesión para el servidor o de la
empresa que te da servicio de alojamiento web, abre la herramienta
PhpMyAdmin. Abre la base de datos y buscar la tabla llamada "users" y, a
continuación, has clic en el icono "ver" los datos de esa tabla.

Debes ver los nombres de las personas que tienen cuentas en tu sitio
Joomla. Esta vista proporciona la seguridad de que estás a punto de
hacer la copia de seguridad de la base de datos correcta.

Haga clic en la ficha exportar y luego en continuar.

El navegador descargará tu base de datos en un archivo SQL.

Encuentra donde navegador puso ese archivo, a continuación, mueve el
archivo a una unidad o ubicación mucho más segura.

El servidor de bases de datos SQL puede hacer una copia de seguridad sin
PhpMyAdmin y en su lugar de usar la línea de comando de SQL. Si sabes
cómo hacerlo, lo más probable es que no necesites de este tipo de
documentación.

Se recomienda hacer una copia de seguridad de la base de datos al menos
dos veces por semana o incluso a diario (y más) si tienes un sitio
activo.

## Copia de seguridad, Parte 2 de 2: Archivos del sistema

Continua con su sitio fuera de línea, mira arriba. Tu carpeta Joomla! y
los archivos pueden ser respaldados con la descarga de ellos con una
utilidad FTP o utilizando el administrador de archivos de su empresa de
alojamiento web. Ambas de estas opciones funcionan, ninguna es mejor que
la otra.

Con herramientas FTP, debes mover miles de archivos de Joomla! y usa más
tiempo. El proceso de FTP puede ser lento e interrumpirse. Muchas
empresas de alojamiento web, proveen un panel de control para tomar
miles de archivos de una carpeta y, luego, crear muy rápidamente un
archivo zip.

Esto significa que tu sitio está fuera de línea por un corto período y
sólo tienes un archivo zip. Ve a su panel de control del servicio de
alojamiento web y busca el icono administrador de archivos.

Si utilizas el administrador de archivos del alojamiento web, practica
el uso de la interfaz para seleccionar la carpeta del servidor y la
creación de un archivo zip. Descarga el archivo zip a tu equipo y, a
continuación, descomprímelo para ver qué archivos están dentro de ese
archivo zip. Esta opción también te permite extraer del mismo archivo
zip para la restauración de un sitio de ensayo.

La copia de seguridad de archivos Joomla! con FTP no es diferente a la
copia de seguridad de un sitio web HTML estático. Descarga todos los
archivos y carpetas que existen en el directorio principal de Joomla!.
La ubicación de la descarga es una carpeta en el equipo local. Asegúrate
que el archivo y la estructura de directorios sigue siendo idéntica,
como es en el sitio en vivo. Al restaurar los archivos, podrás utilizar
la herramienta FTP para subir los archivos a un nuevo servidor.

**Tan pronto como se hayan descargado los archivos vía zip o a través de
FTP, cambia tu sitio para que esté en línea.**

## Más documentación sobre copia de seguridad

La mayoría de los administradores de un sitio web Joomla! tienen acceso
a sus datos MySQL utilizando la interfaz gráfica de usuario llamada
PhpMyAdmin, mira <a
href="https://phpmyadmin.readthedocs.org/en/latest/faq.html#how-can-i-backup-my-database-or-table"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">¿Cómo puedo realizar copias de
seguridad de mi base de datos o tabla?</a> para obtener más información.

Hay varias extensiones para Joomla! que permiten realizar copias de
seguridad situadas en el
<a href="http://extensions.joomla.org" class="external text"
target="_blank" rel="noreferrer noopener">Joomla! Directorio de
Extensiones</a>. Aquí hay un enlace para <a
href="http://extensions.joomla.org/extensions/extension?search=backup"
class="external text" target="_blank" rel="noreferrer noopener">las
extensiones Joomla! sobre Copias de Seguridad</a>.

Cuando los servidores están alojados en el mismo edificio que el
personal, los administradores de web debe hacer un cuidado extra para
almacenar las copias de seguridad de la base de datos/archivos en un
edificio diferente. Incendio, robo, agua u otros daños a menudo eliminan
el sitio en vivo y las copias de seguridad. Sobre una base regular, los
administradores de la web deben grabar tanto la base de datos y archivos
en un CD o guardar en un disco duro externo fuera de sitio.

## Notas especiales

### 2FA (Autenticación de dos factores)

Si usas autenticación de 2 factores (disponible desde Agosto de 2014) y
estás bloqueado fuera de tu sitio, puedes cambiar el nombre de la
carpeta plugins/twofactorauth a twofactorauth.BAK e iniciar sesión en su
sitio web del Lado Servidor. A continuación, desactiva todos los plugins
del grupo "twofactorauth". Finalmente, cambia el nombre de la carpeta
plugins/twofactorauth.BAK de tu sitio de nuevo a twofactorauth.

- Ver también:  Tutorial Autenticación de Dos
  factores
