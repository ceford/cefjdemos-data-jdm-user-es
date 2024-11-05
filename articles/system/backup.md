<!-- Filename: jdocmanual?manual=user&heading=system&filename=backup.md / Display title: Respaldo -->

## ¡Los accidentes ocurren!

Se invierte mucho tiempo, esfuerzo y dinero en la creación y mantenimiento de un sitio web. Sería una pena perderlo todo por un accidente inesperado. Hacer copias de seguridad es fácil para sitios promedio. Los sitios grandes o especializados probablemente necesiten asesoramiento especializado.

## Estrategia de Respaldo

¡Los sitios web de Joomla! consisten en dos partes:

* Los **archivos** ubicados en el árbol de directorios raíz de Joomla. Entre actualizaciones, los archivos pueden no cambiar mucho ya que están principalmente relacionados con el código. Se pueden agregar nuevas imágenes y documentos, y tal vez modificaciones de plantillas.
* La **base de datos** ubicada en otro lugar en el servidor anfitrión. La base de datos contiene la mayor parte del contenido del sitio y puede cambiar mucho a medida que los usuarios agregan o editan contenido.

Todo propietario de un sitio necesita una estrategia para la recuperación del sitio en caso de desastre. El consejo común en los Foros es **restaurar la última copia de seguridad**. Por lo tanto, decide qué respaldar y con qué frecuencia hacerlo.

Los servicios de alojamiento a menudo toman **instantáneas** de los sitios de los clientes y pueden ser capaces de restaurar un sitio a su estado de ayer, la semana pasada o el mes pasado. Pero eso podría cubrir todo en la cuenta, como correos y otros paquetes de software. No confíes en eso para la recuperación de un sitio Joomla.

Este artículo describe algunos métodos comunes **gratuitos** para respaldar sitios web de Joomla. Podrías optar por pagar herramientas y/o servicios de respaldo, pero eso no se cubre aquí.

## Akeeba Backup

Si utilizas el menú del administrador para navegar a **Sistema / Instalar Extensiones / Instalar desde la Web**, el primer elemento en la lista es *Akeeba Backup*. Es el primero en la lista porque tiene el mayor número de reseñas positivas. No hace falta decir que tiene una larga historia y una reputación impecable. Hay una versión gratuita y una versión de pago con algunas características adicionales. Ese es un modelo de negocio común para los desarrolladores de extensiones. ¡No temas! La versión gratuita es fácil de usar, no tiene distracciones y es suficiente para la mayoría de los sitios. Lo que hace:

* Akeeba Backup analiza tu instalación para determinar las configuraciones óptimas para crear un archivo de respaldo.
* Hace un archivo de respaldo compuesto que contiene todos los archivos del sitio web y el contenido de la base de datos.
* Almacena las copias de seguridad con marca de tiempo para gestionar, descargar o eliminar según sea necesario.
* La descarga es un archivo .jpa. Se recomienda usar FTP para realizar la descarga.
* Hay una aplicación separada de Akeeba Kickstart para descomprimir el archivo .jpa. Todo esto se describe en la página Administrar Copias de Seguridad de Akeeba.
* Después de descomprimir, el sitio se instala con un instalador de Akeeba en una secuencia similar a la instalación de Joomla.
* El instalador cambia la configuración para restaurar en una ubicación diferente y solicita los nuevos detalles de la base de datos.

El único problema que podría ocurrir es que el archivo de respaldo puede ser muy grande y podrías exceder tu cuota de espacio de archivos si permites que las copias de seguridad se acumulen.

¡Pruébalo! No cuesta nada y toma minutos en lugar de horas.

## Herramientas del Anfitrión

La mayoría de los servicios de alojamiento ofrecen herramientas de respaldo. Ejemplo:

### cPanel

En la página de **Herramientas**, el elemento *Archivos* tiene un enlace de *Respaldo* (Backup). La página de **Respaldo** ofrece tres opciones:

*  **Respaldo Completo:** Un respaldo completo crea un archivo de todos los archivos y la configuración de tu sitio web. Puedes usar este archivo para mover tu cuenta a otro servidor o para mantener una copia local de tus archivos.
* **Respaldo Parcial**
    - Descargar un Respaldo del Directorio Principal
    - Descargar un Respaldo de la Base de Datos (con una lista de bases de datos)

También hay opciones para **Restaurar** cada uno de estos tipos de respaldo. Es posible que haya opciones disponibles para producir respaldos automáticos.

Los directorios individuales se pueden comprimir en varios formatos adecuados para la descarga utilizando el Administrador de Archivos de cPanel. Una base de datos se puede exportar usando phpMyAdmin. Ninguno de estos métodos se aborda aquí.

## Herramientas Locales

Hay ocasiones en que puedes necesitar respaldar un sitio localmente en una laptop o computadora de escritorio en la oficina. Por ejemplo, puede que quieras copiar un sitio hacia/desde un servicio de hosting hacia/desde tu computadora local. Si tienes una instalación local de Joomla, puedes usar Akeeba Backup como se describió anteriormente. De lo contrario, puedes respaldar la base de datos y los archivos de Joomla por separado.

### mysqldump

Si estás usando MySQL, es probable que tengas disponible la herramienta de línea de comandos *mysqldump*. Prueba este comando:

```bash
/usr/local/mysql/bin/mysqldump -u root -p dbname > ~/tmp/dbname-dump.sql
```
donde `root` es un usuario que tiene acceso a la base de datos y `dbname` es el nombre de la base de datos que deseas exportar. Es posible que se te pida ingresar la contraseña.

También puedes canalizar la salida a un comando zip o gzip:
```bash
/usr/local/mysql/bin/mysqldump -u root -p dbname | gzip > ~/tmp/dbname-dump.sql.gz
```

### phpMySQL

Para realizar la misma tarea con tu instalación local de phpMyAdmin, ábrelo y selecciona la base de datos que deseas exportar. Selecciona el botón **Exportar** en la parte superior de la pantalla. Por defecto, la exportación *Rápida* usa SQL como formato de salida. Selecciona el botón **Exportar** para probar eso. Se te pedirá que nomines un archivo de salida.

Si seleccionas la opción *Personalizada*, te permite seleccionar una opción de Compresión de Salida, ya sea ninguna, comprimida con zip o gzip. Prueba una exportación comprimida y selecciona el botón **Exportar**.

Debes **comprobar** la base de datos exportada. Crea una nueva base de datos, quizás `animporttest`, para que esté cerca de la parte superior de tu lista de bases de datos. Con la nueva base de datos vacía seleccionada, usa el botón **Importar** en la parte superior de la pantalla. En el formulario de importación, **Navegar** para encontrar el archivo que exportaste y luego selecciona el botón **Importar**.

Valió la pena la **comprobación**. La exportación gzip solo exportó tres tablas. La exportación zip funcionó bien. Eso era evidente en los tamaños del archivo exportado. El archivo zip era de 4Mb, pero el gzip solo era de 75Kb. ¡Debe haber un error en alguna parte!

### Zip y Gzip

Estas herramientas de línea de comandos son bastante ubicuas y a menudo se utilizan desde interfaces gráficas. Por ejemplo, en el Finder de Mac, puedo seleccionar un directorio que contiene un sitio Joomla, hacer clic con el botón derecho y seleccionar **Comprimir**. Toma unos pocos segundos crear un archivo zip y no afecta al original.

## Restaurar una Copia de Seguridad

Consejos comunes del Foro de Joomla:

* No restaures una copia de seguridad sobre un sitio defectuoso.
* Vacía tu base de datos eliminando todas las tablas o crea una nueva base de datos y asigna un usuario de base de datos para ella.
* Elimina todos los directorios y archivos dentro de tu directorio raíz de Joomla.

## Inicio Rápido de Akeeba

Si has usado Akeeba Backup, entonces utiliza Akeeba Quickstart para restaurar tu respaldo.
* Consulta el [Tutorial en Video](http://akee.ba/abrestoreanywhere "").
* Descarga Akeeba Quickstart (PDF 94Kb) gratuitamente.
* Verifica que el sitio restaurado funcione correctamente.

Akeeba Quickstart restaura tanto la base de datos como los archivos de Joomla. Otros métodos restauran la base de datos y los archivos de Joomla por separado.

## Restaurar la Base de Datos

Si tienes una copia de seguridad de la base de datos, es mejor usar herramientas del sistema para restaurarla. *phpMyAdmin* puede instalar bases de datos de tamaño moderado, pero podría quedarse sin tiempo o memoria en bases de datos grandes.

Si estás utilizando cPanel en un servicio de alojamiento, puedes importar una base de datos desde la página de *Copia de Seguridad / Restaurar*. Eso no se describe aquí.

Si tienes acceso a la línea de comandos, ya sea en un servicio de alojamiento o en tu computadora portátil o de escritorio local, puedes usar el comando de línea `mysql` para hacer la importación. Sube el archivo de la base de datos a una ubicación temporal fuera de tu árbol web y expándelo para que tengas un archivo con la extensión `.sql`. Luego utiliza el siguiente comando:
```
mysql -u nombredeusuario -p -D nombredb < archivo_de_volcado.sql
```
Reemplaza `nombredeusuario`, `nombredb` y `archivo_de_volcado.sql` con los valores reales de tu sitio. Puede que se te solicite la contraseña del nombre de usuario de la base de datos. Puede llevar un tiempo, pero debería completarse.

## Restaurar los archivos

Esto es un asunto simple de expandir el archivo comprimido de tu última copia de seguridad. Excepto que a veces no es tan simple. Dependiendo de tu sistema operativo y el método elegido, las carpetas y archivos archivados podrían aparecer todos en el directorio actual o en un nuevo directorio, o se te podría pedir que indiques un directorio de destino. Hasta que sepas cómo actúa tu sistema, podría ser mejor colocar el archivo en un directorio vacío, expandirlo allí y luego mover el directorio contenedor al lugar donde necesita estar.

Algunos usuarios prefieren usar SFTP para cargar archivos a un servicio de alojamiento desde los archivos del archivo extraídos localmente. Hay miles de archivos, por lo que esto consume bastante tiempo.

En la raíz de tu sitio hay un archivo llamado `configuration.php`. Contiene el nombre de la base de datos y las credenciales de acceso. Asegúrate de que sean correctos para tu sitio restaurado. El archivo tiene permisos de acceso configurados en 444. Eso necesita ser cambiado a 644 para que puedas guardar cualquier edición necesaria.

Si todo va bien, tu sitio restaurado debería funcionar y estar en el estado en que estaba cuando se hizo la copia de seguridad.

## Copiar un sitio

Hay varias buenas razones para copiar un sitio web completo de un servidor a otro. Por ejemplo, los expertos del foro a menudo recomiendan que los usuarios creen una versión local de un sitio en una computadora portátil o de escritorio para fines de prueba, como probar nuevas extensiones o diseños. A veces, una persona decide cambiar a un nuevo servicio de alojamiento por razones de costo o rendimiento.

Cualquiera que sea el motivo, el proceso es relativamente sencillo: realiza una copia de seguridad en el sitio original y restáurala en el sitio de destino. Hay algunos aspectos a tener en cuenta:

* Asegúrate de que el host de destino cumpla con los requisitos técnicos mínimos de Joomla. Eso generalmente significa versiones del servidor, PHP y base de datos
* Después de la instalación, es posible que encuentres que algunos módulos esenciales no se han habilitado. La mayoría de los servicios de alojamiento solucionarán tales problemas a pedido.

*Traducido por openai.com*

