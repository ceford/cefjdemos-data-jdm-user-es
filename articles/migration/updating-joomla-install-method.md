<!-- Filename: J3.x:Updating_Joomla_(Install_Method) / Display title: Actualizar Joomla (Método de instalación) -->

<img
src="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/25px-Stop_hand_nuvola.svg.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/38px-Stop_hand_nuvola.svg.png 1.5x, https://docs.joomla.org/images/4/41/Stop_hand_nuvola.svg.png 2x"
data-file-width="40" data-file-height="40" width="25" height="25"
alt="Stop hand nuvola.svg.png" />Warning!

From Joomla 3.5 you can no longer use this to update Joomla, useinstead.

En algunos casos no es posible usar el método de Gestor de extensiones:
Actualizar para actualizar su sitio. Una razón puede ser que estás
usando una distribución no estándar (por ejemplo, una distribución con
un idioma predeterminado diferente). Otra razón puede se que no tengas
una buena conexión a internet para la instalación automática.

En este caso todavía es posible una instalación fácil usando el Gestor
de extensiones: Instalar. Así como en la opción de actualizar, este
método actualizará la base de datos autommáticamente y actualizará el
sistema sin ningún paso adicional.

## Paso 1: Asegúrate que tienes una copa de seguridad de tu sitio

En muchos casos tu proveedor de almacenamiento hace copias de seguridad
periódicas.

## Paso 2: Localizar el archivo de actualización

Localizar el archivo requerido (por ejemplo un archivo .zip, .tar.gz o
.tar.bz2) para tu versión. Si estás actualizando a una versión x.x.0
(por ejemplo de 1.7.3 a 2.5.0), este archivo normalmente se llamará
Joomla_2.5.0-Stable-Update_Package.zip. Si estás actualizando dentro de
la misma versión mayor (por ejemplo, 2.5.0 a 2.5.1), el archivo se
llamará algo similar a Joomla_2.5.0_to_2.5.1-Stable-Patch_Package.zip

En este punto, tienes tres opciones:

1.  Instalar desde URL
2.  Instalar desde un directorio
3.  Subir archivo de paquete

Instalar desde URL es la forma más sencilla, con esta opción el archivo
de actualización es cargado directamente por el servidor, así que
funcionará bien aún si tu computador local tiene una conexión lenta o no
muy buena a internet.

Instalar desde un directorio es el método más seguro si el servidor como
tal tiene una conexión lenta a internet. Con este método puedes usar FTP
para subir los archivos de actualización descomprimidos en una carpeta
temporal en el servidor, posteriormente apuntas a ese directorio en el
servidor para la instalación.

Subir un archivo de paquete es muy simple, pero requiere que tengas una
buena conexión entre tu computador local y el servidor.

The screen below shows the Extension Manager: Install screen with the
three options labeled.

<img
src="https://docs.joomla.org/images/9/93/Update-screenshot-20120124-03-en.png"
class="thumbimage" decoding="async" data-file-width="809"
data-file-height="365" width="809" height="365"
alt="Update-screenshot-20120124-03-en.png" />

### Instalar desde URL

Esta opción es la más sencilla si el archivo comprimido está disponible
en un sitio web.

1.  En la pantalla de Gestor de extensiones: Instalar, ingresa la URL
    del archivo comprimido en el campo URL de instalación.
2.  Haz clic en el botón instalar.

El sistema trabajará durante un tiempo - hasta dos minutos o más si es
una actualización completa de versión. A continuación se mostrará un
mensaje indicando una instalación completa.

### Instalar desde directorio

Esta opción requiere que descomprimas el archivo en un directorio en tu
servidor. Este es el mejor método si tienes una conexión lenta a
interner o si tienes problemas de tiempo de espera agotado durante el
proceso de actualización.

1.  Descomprime el archivo en un directorio temporal en tu máquina
    local.
2.  Sube todos los archivos en este directorio (por ejemplo, usando FTP)
    a un directorio temporal que es visible por el servidor web. Por
    ejemplo, puedes crear un subdirectorio en el directorio tmp en la
    raíz de Joomla. Para este ejemplo, digamos que el directorio en el
    servidor es `/home/myuser/myjoomla/tmp/upgrade250`.
3.  En el Gestor de extensiones: Instalar, ingresa la ruta completa del
    directorio temporal (en el servidor) del paso 2 (por ejemplo
    `/home/myuser/myjoomla/tmp/upgrade250`).
4.  Haz clic en el botón Instalar.

El sistema trabajará por un corto tiempo (tal vez un minuto o menos,
dependiendo del servidor), y a continuación se mostrará un mensaje
indicando que la instalación fue exitosa.

### Subir un archivo comprimido

Esta opción requiere que descargues primero el archivo comprimido a tu
máquina local.

1.  Desargar el archivo a tu computador local.
2.  En Gestor de extensiones: Instalar, haz clic en el botón Explorar,
    al lado del campo Archivo de paquete y localiza el archivo
    comprimido.
3.  Hacer clic en el botón instalar.

El sistema trabajará por un periodo de tiempo - hasta dos minutos o más
para una actualización completa, a continuación, aparecerá un mensaje
indicando que la instalación fue exitosa.

1.  ¡Felicitaciones! En este punto tu sitio está actualizado.

**Importante:** Limpia la caché de tu navegador y verifica que tu sitio
está trabajando correctamente. Mira a continuación Verificando tu sitio.
