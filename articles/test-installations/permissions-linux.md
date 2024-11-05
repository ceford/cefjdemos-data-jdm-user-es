<!-- Filename: Verifying_permissions / Display title: Permisos de Archivos: Linux -->

## Introducción

La siguiente información es para servidores basados en Linux. Si tu servidor web es un servidor basado en Microsoft Windows (IIS), deberías consultar [Permisos: Windows](jdocmanual?article=user/test-installations/permissions-windows).

Dependiendo de la configuración de seguridad de tu servidor web, los permisos por defecto recomendados son:

- 755 para directorios
- 644 para archivos
- 444 para el archivo `configuration.php` (cuando se guarda un cambio en la Configuración Global, Joomla primero cambia el permiso a 644, guarda el cambio y luego cambia el permiso de nuevo a 444)

<div class="alert alert-warning">
¡Advertencia!

¡Nunca uses 777 a menos que sepas lo que estás haciendo! No utilices extensiones que requieran permisos 777.
</div>

## Cómo Localizar los Permisos

Existen varios métodos disponibles para ver y cambiar los permisos de los archivos o carpetas del sitio web. El navegador de archivos del panel de control del host o un programa común de [Protocolo de Transferencia de Archivos (FTP)](https://es.wikipedia.org/wiki/Protocolo_de_Transferencia_de_Archivos) deberían proporcionar un método para ver y cambiar los permisos de archivos y carpetas. La línea de comandos es útil para aquellos que tienen acceso al terminal y están familiarizados con los comandos del sistema.

Dependiendo de lo que estés usando, deberías ver algo parecido a esta imagen de parte del sistema de archivos raíz de Joomla tal como se ve en cPanel:

![verificando permisos en cpanel](../../../en/images/test-installations/verifying-permissions-cpanel.png)

Los permisos están a la derecha y precedidos por un cero para indicar que son números octales. Debería haber un formulario para cambiar los permisos de uno o más elementos seleccionados:

![cambiando permisos en cpanel](../../../en/images/test-installations/verifying-permissions-cpanel-change.png)

En una ventana de terminal, los permisos de archivos y carpetas se muestran como grupos de letras en lugar de números (la `d` inicial indica que el elemento es un directorio):

```sh
drwxr-xr-x   20 ceford  staff     640 14 Oct 22:23 components
-r--r--r--    1 ceford  staff    3485 27 Oct 06:56 configuration.php
drwxr-xr-x    2 ceford  staff      64 20 Oct 14:21 files
-rw-r--r--    1 ceford  staff    6899 30 Sep 09:27 htaccess.txt
drwxr-xr-x   15 ceford  staff     480 24 Oct 12:19 images
```

## Números de Permisos

En una visualización de permisos en el formato 777, cada dígito octal corresponde a tres letras para tres diferentes grupos de usuarios:

- Primer dígito = propietario (el propietario del elemento - `ceford` en la lista de la línea de comandos arriba)
- Segundo dígito = grupo (el grupo al que se le permite el acceso - `staff` en la lista arriba)
- Tercer dígito = otros (todos los demás en este ordenador)

## Significado de los números

Cada dígito octal es la suma de los permisos otorgados:
```sh
     r = Leer     = 4
     w = Escribir = 2
     x = Ejecutar = 1
```
Suma los números para cada permiso requerido para un grupo de usuarios dado:

| "Octal" \# | (r)ead | (w)rite | e(x)ecute | Usuario o Grupo u Otros |
|------------|--------|---------|-----------|-------------------------|
| 0          | no     | no      | no        | `---` 0+0+0 = 0         |
| 1          | no     | no      | sí        | `--x` 0+0+1 = 1         |
| 2          | no     | sí      | no        | `-w-` 0+2+0 = 2         |
| 3          | no     | sí      | sí        | `-wx` 0+2+1 = 3         |
| 4          | sí     | no      | no        | `r--` 4+0+0 = 4         |
| 5          | sí     | no      | sí        | `r-x` 4+0+1 = 5         |
| 6          | sí     | sí      | no        | `rw-` 4+2+0 = 6         |
| 7          | sí     | sí      | sí        | `rwx` 4+2+1 = 7         |


## Ejemplos

- 755 es rwx (propietario), r-x (grupo) y r-x (otros) o, en otras palabras, todos pueden leer y ejecutar (correr), pero solo el propietario (tú) puede hacer cambios en el archivo. Cuando todo se junta, se vería así: `-rwxr-xr-x`. Esta es la configuración normal para carpetas.
- 644 es rw-, r--, r-- o TODOS pueden leer el archivo, pero solo el propietario puede escribir en el archivo o `-rw-r--r--`. Esta es la configuración normal para archivos.
- 777 o `-rwxrwxrwx` significa que TODOS pueden leer, escribir y ejecutar CUALQUIER archivo.
  <div class="alert alert-warning">
  Esto es algo que **NUNCA** querrás permitir en tu servidor/sitio web a menos que estés absolutamente seguro de que sabes lo que estás haciendo.
  </div>

Los permisos se utilizan tanto para directorios como para archivos, por lo que podrías ver esto `drwxr-xr-x` donde la `d` es para directorio.

Para una explicación completa, lee el artículo de Wikipedia sobre [Permisos de sistema de archivos](https://en.wikipedia.org/wiki/Filesystem_permissions)

*Traducido por openai.com*

