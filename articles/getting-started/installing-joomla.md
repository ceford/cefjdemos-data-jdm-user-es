<!-- Filename: J4.x:Installing_Joomla / Display title: Instalación de Joomla -->

## Introducción

Instalar Joomla! por primera vez es muy fácil. Después de completar los pasos preliminares, configurar un entorno de alojamiento y crear una base de datos, el instalador web incorporado de Joomla configurará tu nuevo sitio en solo unos minutos. Los pasos previos:

### Configuración del Alojamiento

Si aún no has configurado un entorno de alojamiento, debes hacerlo ahora, ya sea en un servicio de alojamiento o en tu computadora local.

Además, hay algunas configuraciones de PHP que necesitan ser suficientes para que Joomla se instale. Las configuraciones suelen estar en un archivo de configuración *php.ini* o *user.ini* en el servidor. Si estás en un alojamiento compartido, habla con tu servicio de alojamiento sobre cómo cambiar estas configuraciones, si es posible hacerlo. Si trabajas en un localhost, por ejemplo con XAMPP, o en un VPS o servidor dedicado, no deberías estar restringido por estas configuraciones y puedes configurarlas tú mismo.

Los valores mínimos para el archivo *php.ini* se muestran a continuación:

- *memory_limit:* 256M
- *upload_max_filesize:* 64M
- *post_max_size:* 64M
- *max_execution_time:* 30

Es posible trabajar con valores más bajos de upload_max_filesize y post_max_size, pero las extensiones más grandes no se cargarán y causarán problemas impredecibles.

### Configuración de la Base de Datos

Si aún no has configurado una base de datos, hazlo ahora. Está cubierto para un servicio de alojamiento con cPanel en el tutorial [Alojamiento con cPanel](jdocmanual?article=user/hosting/cpanel-hosting). También hay un tutorial *Creando una Base de Datos para Joomla!* que cubre los métodos localhost y phpMyAdmin.

Necesitarás tener en cuenta la información básica de la base de datos necesaria cuando comience la instalación real de Joomla.

- Ubicación de la base de datos, generalmente *localhost* incluso en un servicio de alojamiento. Puede ser el servidor de un host específico como *`dbserver1.yourhost.com`*.
- El nombre de la base de datos
- El nombre de usuario de la base de datos
- La contraseña del usuario de la base de datos

## Prepararse para la Instalación

### Descarga y Carga de Archivos de Paquete de Joomla!

Descarga la versión actual de Joomla! desde el enlace en la
[página de descargas de Joomla](https://downloads.joomla.org/).

Mueve el archivo zip del paquete de instalación de Joomla descargado al servidor.
Para un servicio de alojamiento, puedes usar la función de Subida de Archivos del Administrador de Archivos de cPanel o puedes usar un Cliente FTP para transferir el archivo zip de Joomla 5.x descargado a tu servidor. Hay varios clientes FTP disponibles. Aquí tienes una [Comparativa detallada de software cliente FTP](https://en.wikipedia.org/wiki/Comparison_of_FTP_client_software).
Si tienes dudas, usa FileZilla.

La *raíz* de la Carpeta de tu Servidor

Es mejor mover el paquete zip descargado a tu servidor y
descomprimirlo allí que descomprimirlo localmente y luego mover el árbol de archivos.
Normalmente subes tus archivos web a la carpeta raíz de tu servicio de alojamiento.
Esto suele llamarse `public_html`, pero otras variaciones
incluyen `htdocs` y esto depende de cómo tu proveedor ha configurado el
servidor. Para propósitos de Joomla, puedes cargar los archivos directamente en 
*public_html* o en una subcarpeta que hayas creado dentro de ella.

**Advertencia:** Si descomprimes los archivos en tu propia computadora, luego los copias a
tu servidor, asegúrate de mover solo las carpetas y archivos contenidos **dentro**
del paquete de Joomla. Si descomprimes las carpetas y archivos en una carpeta,
por ejemplo, llamada *`Joomla`* y luego subes esa carpeta, se tendrá que 
acceder a tu sitio en *`tu-nombre-de-sitio.com/Joomla`* en lugar de
*`tu-nombre-de-sitio.com`*. Puedes renombrar el sub-directorio de Joomla por 
algo más apropiado para el sitio, como jblog, y podrías encontrarlo
conveniente. **Nota:** los nombres de directorio deben estar en minúsculas, sin
espacios y utilizando guiones en lugar de guiones bajos para separar palabras.

Los archivos del paquete zip se pueden extraer directamente en el host usando
varias herramientas de línea de comandos (por ejemplo, unzip), que deben estar instaladas en
el servidor. Si tu servicio de alojamiento utiliza la herramienta administrativa cPanel, el
botón de Extraer se puede presionar en el Administrador de Archivos. Además de eso, la
herramienta gratuita de terceros Akeeba Kickstart
también puede usarse para este propósito. Los archivos y directorios descomprimidos
se colocarán en la carpeta actual. La extracción en tu computadora local depende
de tu sistema operativo. Intenta hacer clic derecho y observa si hay un menú de extracción. En este caso,
tu sistema operativo puede poner los archivos en una carpeta con el mismo nombre que el archivo zip.
Después de la extracción, puedes eliminar el archivo zip y renombrar la
carpeta extraída a algo corto y adecuado para el uso en una URL.

## Iniciar la Instalación

Con los requisitos anteriores cumplidos, una base de datos creada y los archivos requeridos de Joomla en su lugar, estás listo para instalar Joomla. Inicia el instalador web de Joomla abriendo tu navegador favorito y navegando al nombre de dominio del sitio. En una instalación de alojamiento, usarás *`https://www.nombredetusitio.com`*. Si estás instalando Joomla localmente, usarás *`http://localhost/`* y deberías ver la pantalla de instalación.

![Instalador de Joomla parte 1, idioma de instalación y nombre del sitio](../../../en/images/getting-started/installing-joomla-installer-1.png)

Joomla intentará identificar automáticamente el campo de *Seleccionar Idioma* a partir del idioma de tu navegador. Puedes cambiar esto si es necesario.

Rellena la siguiente información.

- **Nombre del Sitio** El nombre de tu sitio web — esto puede cambiarse en cualquier 
  momento más adelante en la página de Configuración Global del Sitio.

Cuando todo en la primera página esté completado, haz clic en el botón 
*Configurar Datos de Inicio de Sesión* para continuar.

## Datos de Inicio de Sesión

Ahora deberías ver la pantalla de datos de inicio de sesión.

![Instalador de Joomla parte 2, datos de inicio de sesión](../../../en/images/getting-started/installing-joomla-installer-2.png)

Rellena la siguiente información.

- **Nombre Real** El nombre del Super Usuario. Así es como Joomla te
  saludará cuando inicies sesión.
- **Nombre de usuario de la cuenta del Super Usuario** El nombre de usuario
  para el *Super Usuario*. ¡Evita usar *admin* como nombre de Administrador!
- **Contraseña de Administrador** Recuerda que un Super Usuario tiene
  máximo control de las interfaces del Sitio y del Administrador, así que usa
  una contraseña difícil. Utiliza **Mi Perfil** en la interfaz de *Administración*
  para cambiarla más tarde.
- **Correo Electrónico del Super Usuario** La dirección de correo electrónico
  del Super Usuario. Introduce un correo electrónico válido por si olvidas tu
  contraseña. Esta es la dirección de correo donde recibirás un enlace para
  cambiar la contraseña del Super Usuario.

Cuando todo en la segunda página esté completo, presiona el botón *Configurar Conexión a la Base de Datos* para continuar.

## Configuración de la Base de Datos

Introduce la información de la base de datos que anotaste cuando creaste la base de datos para esta instalación.

![Instalador de Joomla parte 3, configuración de la base de datos](../../../en/images/getting-started/installing-joomla-installer-3.png)

Para simplificar, estas instrucciones son una referencia para la instalación con una base de datos MySQLi. Las instrucciones en la página de instalación son autoexplicativas, pero aquí están de nuevo:

- **Tipo de Base de Datos** MySQLi es la base de datos comúnmente utilizada.
- **Nombre del Host** Dónde está ubicada tu base de datos. Comúnmente es *localhost*, incluso en servicios de alojamiento. Sin embargo, algunos hosts usan un servidor de base de datos específico como *dbserver1.yourhost.com*.
- **Nombre de Usuario** El nombre de usuario utilizado para conectar con la base de datos.
- **Contraseña** La contraseña para el usuario de la base de datos (no tu contraseña de Administrador).
- **Nombre de la Base de Datos** El nombre de la base de datos.
- **Prefijo de Tabla** Este se genera automáticamente como una característica de seguridad. Puedes aceptar el valor predeterminado generado al azar o cambiarlo. Solo recuerda poner el carácter de subrayado (`_`) al final del prefijo.
- **Encriptación de Conexión** especifica cómo debe ser encriptada la conexión a la base de datos. Si no lo sabes, es mejor dejar el valor predeterminado. Sin embargo, esto permite a las empresas que usan autenticación en una o dos vías para la conexión de la base de datos proporcionarla.

Todas estas opciones y más pueden ser editadas en la página de Configuración Global del Sitio, bajo *Opciones del Servidor* después de completar la instalación. Nota que romperás tu instalación si cambias estas configuraciones después de la instalación a menos que tengas una copia completa de la base de datos actual utilizada por la instalación de Joomla. Los usos comunes serían actualizar el nombre de usuario y la contraseña de la base de datos o completar el traslado de una instalación existente a un nuevo host con diferentes parámetros.

Después de hacer clic en el botón *Instalar Joomla*, deberías ver la barra de progreso de la instalación de Joomla.

![Instalador de Joomla parte 4, barra de progreso de la instalación](../../../en/images/getting-started/installing-joomla-installer-4.png)

Una vez completada la instalación, deberías ver la página de éxito.

## Finalizando

### Éxito y Finalización de la Instalación

¡Felicidades! Tu sitio de Joomla está listo.

![Joomla instalador parte 5, tu sitio joomla está listo](../../../en/images/getting-started/installing-joomla-installer-5.png)

La captura de pantalla anterior muestra una instalación de desarrollo. Una instalación en producción elimina automáticamente la carpeta de Instalación.

Si deseas comenzar a usar Joomla de inmediato sin instalar idiomas adicionales, puedes seleccionar *Abrir Administrador* para ir al *Panel de Control del Administrador* o seleccionar *Abrir Sitio* para ir a la página de inicio del sitio. Es posible que veas una sección con configuraciones recomendadas de PHP.

- **Configuraciones Recomendadas** Estas configuraciones se recomiendan en tu configuración de PHP, pero no impedirán que Joomla! sea instalado. Puedes consultar las instrucciones anteriores sobre cómo pueden cambiarse si es necesario hacerlo.

### Idiomas Adicionales

Como parte del proceso de instalación de Joomla, se te da la oportunidad de instalar idiomas adicionales antes de completar la instalación.

Para hacer esto, selecciona el botón Instalar Idiomas Adicionales.

Esto te llevará a una página de instalación extra que te permitirá seleccionar los idiomas que necesitas.

#### Instalar Idiomas Adicionales

Se muestra una lista de paquetes de idiomas.

![Joomla instalador parte 6, instalar idiomas adicionales](../../../en/images/getting-started/installing-joomla-installer-6.png)

Selecciona hasta 3 idiomas que deseas instalar. (Instalar más de 3 a la vez puede causar problemas de tiempo de espera; puedes instalar más luego).

Recuerda lo siguiente:

- Los paquetes de idiomas incluidos en distribuciones personalizadas no se enumerarán en esta etapa ya que ya están instalados.
- Una versión de los paquetes propuestos coincidirá con la versión principal de Joomla (5.0.x, 5.1.x, etc.). La versión menor del paquete puede no coincidir, por ejemplo, estás instalando la versión 5.0.3 y se muestra un paquete de idioma 5.0.2.
- Los paquetes de idiomas no coincidentes en el ejemplo anterior pueden tener cadenas sin traducir.
- Los paquetes de idiomas no coincidentes se ofrecerán como una actualización cuando los equipos de Traducción registrados actualicen los paquetes. La actualización disponible se mostrará en el panel de control así como en **Extensiones → Actualizar**. Este comportamiento es similar a **Extensiones → Instalar Idiomas**.

*Next* y una barra de progreso se mostrarán mientras se instalan el o los paquetes de idiomas.

#### Elegir el Idioma Predeterminado

Cuando la instalación de los idiomas esté completa, se te presentará una pantalla similar a *¡Felicidades! Tu sitio de Joomla está listo*. La diferencia será una lista de los idiomas instalados que te permitirá seleccionar el idioma predeterminado para el sitio y la interfaz del administrador.

![Joomla instalador parte 7, elegir idioma predeterminado](../../../en/images/getting-started/installing-joomla-installer-7.png)

- Selecciona el idioma predeterminado que deseas utilizar.
- Cuando hayas seleccionado el idioma predeterminado, el botón *Establecer idioma predeterminado* para confirmar.
- Se mostrará un mensaje del sistema confirmando que Joomla ha establecido el idioma ADMINISTRADOR y del SITIO predeterminado. Ese mensaje puede ser cerrado.

#### Finalizar

Ahora puedes navegar al *Panel de Control del Administrador*. Inicia sesión seleccionando *Abrir Administrador* o ve directamente a la página de inicio de tu sitio seleccionando *Abrir Sitio*.

