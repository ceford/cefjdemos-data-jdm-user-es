<!-- Filename: J4.x:Using_the_CLI / Display title: Uso de la CLI  -->

## La Interfaz de Línea de Comandos (CLI)

Si tienes acceso al terminal del servidor que ejecuta tu sitio web, puedes usar la CLI de Joomla para realizar tareas rutinarias sin la necesidad de usar las credenciales de inicio de sesión de usuario de Joomla. Incluso sin acceso al terminal, como en algunas cuentas de alojamiento compartido, puedes ejecutar comandos CLI usando trabajos cron. Los comandos CLI a menudo son más rápidos o más convenientes que sus equivalentes logrados a través de la interfaz de Administrador de Joomla (o cPanel). La copia de seguridad del sitio y el establecimiento del estado del sitio como fuera de línea/en línea son ejemplos donde podrías preferir usar la CLI.

El núcleo de Joomla tiene alrededor de 30 comandos útiles y puedes agregar más con extensiones adicionales. Por ejemplo, podrías obtener datos externos como los de geolocalización o datos de tipo de cambio para un componente personalizado.

## Usando la CLI

La CLI se utiliza invocando el ejecutable de línea de comandos php. Esto
a menudo es diferente del que utiliza un servidor web como Apache. Si estás
usando un trabajo cron, es posible que debas suministrar la ruta completa al ejecutable php,
así:

    /usr/local/bin/php /home/usuario/public_html/[subcarpeta opcional]/cli/joomla.php

De lo contrario, al usar la línea de comandos del terminal, cambia el directorio al
directorio cli de Joomla y comienza ejecutando el comando sin
parámetros:

    cd /home/usuario/public_html/[subcarpeta opcional]/cli
    php joomla.php

![Lista de comandos](../../../en/images/command-line-interface/cli-command-list.png)

Y pruebe algunos comandos de ayuda para familiarizarse con lo que esperar:

    php joomla.php help
    php joomla.php list
    php joomla.php help cache:clean
    php joomla.php help config:get

Cada una de las descripciones de Ayuda y cadenas de uso están codificadas
en archivos de la biblioteca Console o en plugins de terceros.

Pruebe algunos comandos de acción simples:

    php joomla.php config:get debug
    php joomla.php cache:clean
    php joomla.php site:down
    php joomla.php site:up

## Opciones

Si estás ejecutando comandos desde un cron, es posible que no desees ver ninguna salida:

    php joomla.php -q cache:clean

Ten en cuenta que las opciones pueden usar un espacio o el signo =, pero las variables deben usar el signo =:

    php joomla.php session:gc --application administrador
    php joomla.php session:gc --application=administrador

    php joomla.php config:set debug=true

## Comandos

Una breve explicación de cada comando principal.

### Caché

Limpiar las entradas expiradas de la caché del sistema:

    php joomla.php cache:clean --help
    php joomla.php cache:clean

![Resultado de cache:clean](../../../en/images/command-line-interface/cli-cache-clean.png)

    php joomla.php cache:clean expired

![Resultado de cache:clean expired](../../../en/images/command-line-interface/cli-cache-clean-expired.png)

### Configuración

Obtener o establecer una variable de configuración, una de las variables en
configuration.php o un grupo de variables. Los grupos válidos son db, sesión, 
correo,

    php joomla.php config:get debug --help
    php joomla.php config:get debug

![Resultado de config:get debug](../../../en/images/command-line-interface/cli-get-debug.png)

    php joomla.php config:set debug=true

![Resultado de config:set debug](../../../en/images/command-line-interface/cli-set-debug.png)

    php joomla.php config:get --group session

![Resultado de config:get grupo sesión](../../../en/images/command-line-interface/cli-config-get-group-session.png)

### Núcleo

Comprobar actualizaciones o actualizar Joomla.

    php joomla.php core:check-updates --help
    php joomla.php core:check-updates

![Resultado de core check updates](../../../en/images/command-line-interface/cli-check-updates.png)

    php joomla.php core:update --help
    php joomla.php core:update

![Resultado de core:update](../../../en/images/command-line-interface/cli-core-update.png)

### Base de Datos

Exportar o importar la base de datos. Puedes exportar o importar todas las tablas o una
tabla seleccionada. No uses esta función para importar todas las tablas de un
sitio multilingüe. Hay un problema que podría detener el funcionamiento del Búsqueda Inteligente por completo.

    php joomla.php database:export --help
    php joomla.php database:export --table f4rc2_banners --folder /home/username/tmp/mydb (una tabla)
    php joomla.php database:export --folder /home/username/tmp/mydb (todas las tablas)

    php joomla.php database:import --help
    php joomla.php database:import --table /home/username/tmp/mydb/f4rc2_banners (una tabla)
    [ERROR] El archivo /home/username/tmp/mydb/f4rc2_banners.xml no existe.
    php joomla.php database:import --folder /home/username/tmp/mydb (todas las tablas en esta carpeta)

### Extensión

Listar, descubrir, instalar o eliminar extensiones.

    php joomla.php extension:list --help
    php joomla.php extension:list
    php joomla.php extension:list --type component
    php joomla.php extension:list --type file
    php joomla.php extension:list --type language
    php joomla.php extension:list --type library
    php joomla.php extension:list --type module
    php joomla.php extension:list --type package
    php joomla.php extension:list --type plugin
    php joomla.php extension:list --type template

    php joomla.php extension:discover --help
    php joomla.php extension:discover
    php joomla.php extension:discover:list
    php joomla.php extension:discover:install --eid=

    php joomla.php extension:install --help
    php joomla.php extension:install --path=
    php joomla.php extension:install --url=

    php joomla.php extension:remove --help
    php joomla.php extension:remove

### Buscador

Purgar y reconstruir el índice (los filtros de búsqueda se preservan).

    php joomla.php finder:index --help
    php joomla.php finder:index
    php joomla.php finder:index purge

![Resultado de finder:index purge](../../../en/images/command-line-interface/cli-finder-index-purge.png)

### Programador

Listar, cambiar el estado o ejecutar tareas programadas.

    php joomla.php scheduler:list --help
    php joomla.php scheduler:list

    php joomla.php scheduler:state --help
    php joomla.php scheduler:state (solicitud interactiva para el id de tarea)

    php joomla.php scheduler:run --help
    php joomla.php scheduler:run --id ID
    php joomla.php scheduler:run --all

### Sesión

Realizar recolección de basura de la sesión.

    php joomla.php session:gc --help
    php joomla.php session:gc
    php joomla.php session:gc --application administrator

    php joomla.php session:metadata:gc --help
    php joomla.php session:metadata:gc

### Sitio

Poner el sitio en modo fuera de línea o en línea.

    php joomla.php site:down --help
    php joomla.php site:down

    php joomla.php site:up --help
    php joomla.php site:up

### Actualizar

Verificar actualizaciones pendientes de extensiones. Eliminar archivos antiguos que 
deberían haber sido eliminados durante una actualización de Joomla

    php joomla.php update:extensions:check --help
    php joomla.php update:extensions:check

    php joomla.php update:joomla:remove-old-files --help
    php joomla.php update:joomla:remove-old-files

![Resultado de update:joomla:remove-old-files](../../../en/images/command-line-interface/cli-update-remove-old-files.png)

### Usuario

Listar y gestionar usuarios.

    php joomla.php user:list --help
    php joomla.php user:list

    php joomla.php user:add --help
    php joomla.php user:add --username cinderella --name Cinderella --email cinders@localhost --usergroup Manager (se solicita la contraseña)
    php joomla.php user:add (se solicita información)

![Resultado de user: add con solicitudes](../../../en/images/command-line-interface/cli-add-user.png)

    php joomla.php user:addtogroup --help
    php joomla.php user:addtogroup (se solicita información)
    php joomla.php user:addtogroup --usernam=cinderella --group=Manager

    php joomla.php user:removefromgroup --help
    php joomla.php user:removefromgroup (se solicita información)
    php joomla.php user:removefromgroup --usernam=cinderella --group=Manager

    php joomla.php user:reset-password --help
    php joomla.php user:reset-password (se solicita información)
    php joomla.php user:reset-password --username=cinderella (se solicita contraseña)

    php joomla.php user:delete --help
    php joomla.php user:delete (se solicita nombre de usuario)
    php joomla.php user:delete --username=cinderella (se solicita confirmación - y para confirmar)

*Traducido por openai.com*

