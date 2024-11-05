<!-- Filename: How_do_you_block_directory_scans_using_htaccess%3F / Display title: Deshabilitar el Listado de Directorios  -->

## Antecedentes

Por defecto, en un servidor web Apache, un directorio que no contiene un archivo de índice definido en la configuración (index.html o index.php) mostrará una lista de todos los archivos y subdirectorios en el directorio. Esto puede ser útil en un servidor de pruebas personal, pero representa un grave riesgo de seguridad en un servidor de producción en vivo.

En el pasado, era una práctica común incluir un archivo index.html vacío en todos los directorios de Joomla para prevenir este problema en servidores mal configurados. Esto ya no es así. Se espera una configuración adecuada del servidor, ya sea en los archivos de configuración del servidor o en archivos .htaccess individuales. La primera opción es preferida ya que se aplica a todos los sitios web en el servidor.

Sin embargo, los sitios en un entorno de hosting compartido pueden esperar que cada sitio modifique la configuración del servidor usando archivos .htaccess. El servidor debe estar configurado para "AllowOverride Options" o "AllowOverride All" para permitir overrides en .htaccess.

## Uso de .htaccess

El archivo htaccess.txt suministrado con Joomla se puede utilizar en servidores Apache renombrándolo o copiándolo a .htaccess. Contiene muchas configuraciones para contrarrestar ataques de hackers en sitios Joomla. Entre otras, verás las siguientes configuraciones para evitar listados de directorios:

```
Options -Indexes

## Sin listados de directorios
<IfModule mod_autoindex.c>
	IndexIgnore *
</IfModule>
```

## Prueba tu sitio

Una forma de probar tu sitio es ingresar la URL de tu carpeta de imágenes en la barra de URL del navegador: `https://tudominio.com/images/`. Como la carpeta de imágenes normalmente no contiene un archivo index.html o index.php, deberías ver una página completamente vacía. Si ves una lista de todos los archivos y carpetas, entonces no estás impidiendo el escaneo de directorios para ninguna parte de tu sitio. ¡Arréglalo!

