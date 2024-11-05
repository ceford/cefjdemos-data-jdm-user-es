<!-- Filename: Purging_expired_cache_files / Display title: Purgar Caché Expirado -->

## Archivos de Caché

Los archivos de caché son archivos temporales creados para mejorar el rendimiento de tu sitio. Debes asegurarte de que los archivos de caché que han caducado, y que ya no son necesarios, se eliminen del sistema. De lo contrario, eventualmente te quedarás sin espacio en disco.

Los archivos de caché caducados pueden ser eliminados desde la interfaz de Administrador o a través de la interfaz de Línea de Comandos (CLI).

## Purga - Método del Administrador

Desde el *Panel de Control Principal*
* Selecciona la opción **Caché** en el panel del *Sistema*.
* En la página *Mantenimiento: Limpiar Caché* selecciona el botón **Limpiar Caché Expirada** en la Barra de Herramientas.

## Purga - Método de Línea de Comandos

Abre una ventana de terminal y navega al directorio cli en la raíz de tu sitio.
Si no sabes qué comandos CLI están disponibles, emite el siguiente comando:
```bash
php joomla.php
```
Verás una lista de comandos disponibles. El comando `cache` es:
```bash
php joomla.php cache:clean
```
Debería aparecer un mensaje de confirmación en verde o tal vez un mensaje de error en granate.

## Purga automática de archivos de caché expirados

Puedes purgar automáticamente los archivos de caché expirados utilizando un trabajo cron. Los servicios de alojamiento facilitan esto proporcionando un formulario para seleccionar con qué frecuencia se ejecuta un trabajo y el comando a utilizar. Así que podrías elegir configurar el cron para que se ejecute a las 05:00 todos los días con el siguiente comando:
```
 /usr/local/bin/ea-php82 /home/username/public_html/cli/joomla.php cache:clean
 ```
La mayoría de los gestores de trabajos *cron* te permiten ingresar una dirección de correo electrónico a la que se enviará la salida del cron. Si no quieres que se envíe un mensaje, añade ` > /dev/null 2>&1` al comando.

La versión de PHP utilizada en la línea de comandos a menudo es diferente de la utilizada para la entrega de un sitio web. Podría no ser compatible con Joomla. Así que utiliza la ruta completa a la versión de PHP que deseas usar en lugar de `php` solo.

*Traducido por openai.com*

