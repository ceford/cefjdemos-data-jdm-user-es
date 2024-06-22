<!-- Filename: How_do_you_convert_an_htaccess.txt_file_into_a_.htaccess_file%3F / Display title: ¿Cómo convertir un archivo htaccess.txt en uno .htaccess? -->

### Introducción

Cuando se usa PHP como un módulo de Apache, puede cambiar las opciones
de configuración usando directivas en archivos de configuración de
Apache (p. ej. archivos httpd.conf y .htaccess). necesitará los
privilegios "AllowOverride Options" o "AllowOverride All" para poder
hacerlo. Si controla su propia configuración de Apache, puede y debería
usar httpd.conf. Si no control su configuración de Apache (como en un
alojamiento compartido), debe usar archivos .htaccess.

### Instrucciones

1.  Primero, busque el archivo htaccess.txt en su directorio raíz usando
    FTP para conectarse a su servidor. Este archivo debería haber sido
    instalado durante la instalación de Joomla (fíjese en que el nombre
    de este archivo no empieza con un punto). Abra y lea cuidadosamente
    el archivo. Contiene sugerencias importantes sobre cómo proteger su
    sitio.
2.  Haga cualquier ajuste a este archivo que sea apropiado a su sitio, y
    a continuación guárdelo en el directorio raíz de su sitio como
    .htaccess (incluyendo el punto). Asegúrese de desactivar la casilla
    "Esconder nombres de archivo que empiezan con un punto" en su
    cliente FTP.
3.  Pruebe las interfaces pública y privada de su sitio. Si se producen
    errores en alguna de ellas, vuelva a renombrar el archivo a
    htaccess.txt y revise sus ediciones del htaccess en busca del origen
    del problema. Si le resulta imposible conseguir hacerlo funcionar,
    puede tener que dejar el archivo como htaccess.txt (o sea,
    desactivado).
4.  Use phpinfo() para asegurarse de que todas las opciones se han
    configurado como se pretendía. Nota: los archivos accesibles desde
    la web que incluyen la llamada phpinfo() suponen riesgos potenciales
    de seguridad, pues ofrecen a los atacantes mucha información útil
    acerca de su servidor. Elimine esos archivos después de usarlos.

### Más información

- <a href="http://us2.php.net/configuration.changes" class="external text"
  target="_blank" rel="nofollow noreferrer noopener">Manual oficial de
  PHP: Cómo cambiar las opciones de configuración</a>
- <a href="http://us2.php.net/manual/en/ini.php#ini.list"
  class="external text" target="_blank"
  rel="nofollow noreferrer noopener">Manual oficial de PHP: Lista de
  directivas PHP INI</a>
