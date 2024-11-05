<!-- Filename: J4.x:CLI_Database_Exporter_Importer / Display title: Exportación e Importación de Base de Datos CLI  -->

## Introducción

Antes de actualizar Joomla! o instalar una extensión de terceros, se recomienda encarecidamente que realice una copia de seguridad de su sitio. La interfaz de línea de comandos de Joomla! (CLI) proporciona comandos para exportar (hacer copias de seguridad) e importar (restaurar) su base de datos de Joomla!. Tenga en cuenta que no realiza copias de seguridad de su sistema de archivos, lo cual debe hacerse por separado.

## Requisitos

Para utilizar estos comandos, necesitas acceso a la terminal del host donde está instalado el sitio. ¡Esto puede ser un problema en un alojamiento compartido! También necesitas conocimientos básicos de comandos de shell de Linux, como ls y cd. Si todo esto te resulta desconocido, probablemente deberías usar Akeeba Backup, la extensión de copia de seguridad y restauración más popular, y gratuita para uso básico.

## Ubicación Temporal de Almacenamiento de Copias de Seguridad

Ten cuidado al elegir una ubicación de almacenamiento para una copia de seguridad. Debe estar dentro de tu espacio de archivos personal, pero fuera de tu árbol web. El objetivo es crear un archivo de copia de seguridad que puedas descargar a tu computadora local u otro lugar seguro, después de lo cual puedes eliminar el archivo de copia de seguridad para ahorrar espacio. Además, ten cuidado de no usar la carpeta del sistema /tmp, que puede ser leída por cualquier usuario. La mejor ubicación es tu carpeta personal tmp. La estructura del árbol de carpetas:

```
|-/home/username/tmp - tu carpeta personal tmp
|-/home/username/public_html - tu carpeta raíz de Joomla
```

## Instrucciones

Inicia sesión en tu host y accede a la carpeta raíz de tu sitio.
```
cd /home/usuario/public_html
```

- Enumera todos los comandos CLI disponibles:
```sh
  php cli/joomla.php list
```
- Exporta la base de datos a la carpeta tmp de la cuenta:
```sh
  php cli/joomla.php database:export --folder /home/usuario/tmp/mibasededatos
```
- Importa la base de datos desde la carpeta:
```sh
php cli/joomla.php database:import --folder /home/usuario/tmp/mibasededatos
```

También puedes:

- Exportar la base de datos como un archivo .zip:
```sh
php cli/joomla.php database:export --zip --folder /home/usuario/tmp/mibasededatos
```
- Exportar una tabla:
```sh
php cli/joomla.php database:export --table xxxxx_action_log_config --folder /home/usuario/tmp/mibasededatos
```
- Exportar una tabla como un archivo .zip:
```sh
php cli/joomla.php database:export --table xxxxx_action_log_config --zip --folder /home/usuario/tmp/mibasededatos
```
- Importar una tabla:
```sh
php cli/joomla.php database:import --table xxxxx_action_log_config --folder /home/usuario/tmp/mibasededatos
```
- Si necesitas ayuda:
```sh
php cli/joomla.php database:export --help
php cli/joomla.php database:import --help
```

## Respaldo

Para hacer una copia de seguridad completa de carpetas, archivos y la base de datos, ejecuta estos comandos:

1. Archiva tu directorio raíz de Joomla:
```sh
tar --exclude='/home/username/public_html/tmp' -zcvf /home/username/tmp/joomla_bak.tgz /home/username/public_html > /home/username/tmp/joomla_bak.log
```
2. Exporta toda la base de datos de Joomla, desde la carpeta raíz de Joomla:
```sh
php cli/joomla.php database:export --folder /home/username/tmp/db_bak
```

## Restaurar

Y para restaurarlo, primero asegúrate de que la base de datos y el usuario de la base de datos existan. Luego, ejecuta estos comandos:

1. Extrae el archivo comprimido:
```sh
tar -xvf /home/username/tmp/joomla_bak.tgz --directory /home/username/public_html
```
2. Asegúrate de estar en la raíz de tu sitio:
```sh
cd /home/username/public_html
```
2. Importa la base de datos de Joomla:
```sh
php cli/joomla.php database:import --folder /home/username/tmp/db_bak
```

## Notas

En las opciones del comando tar -zcvf y -xvf, la v significa verbo, lo que provoca que una lista de archivos procesados se desplace rápidamente por la pantalla del terminal. Omite la v para no ver la lista.
*Traducido por openai.com*

