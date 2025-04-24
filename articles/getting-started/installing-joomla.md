<!-- Filename: J4.x:Installing_Joomla / Display title: Instalando Joomla -->

## Introducción

Instalar Joomla! por primera vez es muy fácil. Después de completar los pasos preliminares, configurar un entorno de alojamiento y crear una base de datos, el instalador web integrado de Joomla configurará tu nuevo sitio en solo unos minutos. Los pasos previos:

### Configuración de Alojamiento

Si aún no has configurado un entorno de alojamiento, necesitas hacerlo ahora, ya sea en un servicio de alojamiento o en tu computadora local.

Además, hay algunas configuraciones de PHP que necesitan ser suficientes para que Joomla se instale. Las configuraciones suelen estar en un archivo de configuración *php.ini* o *user.ini* en el servidor. Si estás en un alojamiento compartido, habla con tu proveedor de alojamiento sobre cómo cambiar estas configuraciones si es posible hacerlo. Si trabajas en un localhost, por ejemplo con XAMPP, o en un VPS u host dedicado, no deberías estar restringido por estas configuraciones y puedes establecerlas tú mismo.

Los valores mínimos para el archivo *php.ini* se muestran a continuación:

- *memory_limit:* 256M
- *upload_max_filesize:* 64M
- *post_max_size:* 64M
- *max_execution_time:* 30

Es posible trabajar con valores más bajos de upload_max_filesize y post_max_size, pero las extensiones más grandes no se cargarán y causarán problemas impredecibles.

### Configuración de la Base de Datos

Si aún no has configurado una base de datos, hazlo ahora. Está cubierto para un servicio de alojamiento cPanel en el tutorial [cPanel Hosting](jdocmanual?article=user/hosting/cpanel-hosting). También hay un tutorial sobre *Crear una base de datos para Joomla!* que cubre métodos de localhost y phpMyAdmin.

Necesitarás anotar la información básica de la base de datos necesaria cuando se inicie la instalación real de Joomla.

- Ubicación de la base de datos, generalmente *localhost* incluso en un servicio de alojamiento. Puede ser el servidor de un host específico como *`dbserver1.yourhost.com`*.
- El nombre de la base de datos
- El nombre del usuario de la base de datos
- La contraseña del usuario de la base de datos

## Preparar para la instalación

### Descarga y carga de archivos del paquete Joomla!

Descarga la versión actual de Joomla! desde el enlace en la página de [Descarga Joomla](https://downloads.joomla.org/)

Mueva el archivo zip del paquete de instalación descargado de Joomla al servidor. Para un servicio de alojamiento, puede usar la función de carga del Administrador de Archivos de cPanel o puede usar un cliente FTP para transferir el archivo zip de Joomla 5.x descargado a su servidor. Hay varios clientes FTP disponibles. Aquí hay una [Comparativa detallada del software cliente FTP](https://en.wikipedia.org/wiki/Comparison_of_FTP_client_software). En caso de duda, use FileZilla.

Es mejor mover el paquete zip descargado a tu servidor y descomprimirlo allí que descomprimirlo localmente y luego mover la estructura de archivos. Normalmente subes tus archivos web a la carpeta raíz de tu servicio de hosting. Esto típicamente se llama `public_html`, pero otras variaciones incluyen `htdocs` y esto depende de cómo tu proveedor de hosting haya configurado el servidor. Para propósitos de Joomla, puedes cargar los archivos directamente en *public_html* o en una subcarpeta que hayas creado dentro de ella.

**Advertencia:** Si descomprimes los archivos en tu propia computadora y luego los copias a tu servidor, asegúrate de mover solo las carpetas y archivos contenidos **dentro** del paquete de Joomla. Si descomprimes las carpetas y archivos en una carpeta, por ejemplo llamada, *`Joomla`* y luego cargas esa carpeta, tu sitio tendrá que ser accedido en *`tusitio.com/Joomla`* en lugar de *`tusitio.com`*. Puedes renombrar el subdirectorio de Joomla a algo más apropiado para el sitio, como jblog, y puede que lo encuentres conveniente. **Nota:** los nombres de directorios deben estar en minúsculas, sin espacios y usar guiones en lugar de subrayados para separar palabras.

Los archivos del paquete zip se pueden extraer directamente en el host usando varias herramientas de línea de comandos (por ejemplo, unzip), que deben estar instaladas en el servidor. Si su servicio de hosting utiliza la herramienta de administración cPanel, se puede presionar el botón Extraer en el Administrador de Archivos. Aparte de eso, también se puede usar la herramienta gratuita de terceros Akeeba Kickstart con este propósito. Los archivos y directorios descomprimidos se colocarán en la carpeta actual. La extracción en su computadora local depende de su sistema operativo. Intente hacer clic derecho y vea si hay un menú de extracción. En este caso, su sistema operativo puede colocar los archivos en una carpeta con el mismo nombre que el archivo zip. Después de la extracción, puede eliminar el archivo zip y renombrar la carpeta de extracción a algo corto y adecuado para usar en una url.

## Comenzar Instalación

Con los requisitos anteriores cumplidos, una base de datos creada y los archivos necesarios de Joomla en su lugar, estás listo para instalar Joomla. Inicia el instalador web de Joomla abriendo tu navegador favorito y navegando al nombre de dominio del sitio. En una instalación de hosting, usarás *`https://www.yoursitename.com`*. Si estás instalando Joomla localmente, usarás *`http://localhost/`* y deberías ver la pantalla de instalación.

![Joomla installer part 1, installation language and site name](../../../en/images/getting-started/installing-joomla-installer-1.png)

Joomla intentará identificar el campo *Seleccionar idioma* automáticamente a partir del idioma de tu navegador. Puedes cambiar esto si es necesario.

Complete la siguiente información.

- **Nombre del Sitio** El nombre de su sitio web — esto se puede cambiar en cualquier momento más adelante en la página de Configuración Global del Sitio.

Cuando todo en la primera página esté completado, selecciona el botón *Setup Login Data* para continuar.

## Datos de Inicio de Sesión

Ahora deberías ver la pantalla de datos de inicio de sesión.

![Joomla installer part 2, login data](../../../en/images/getting-started/installing-joomla-installer-2.png)

Complete la siguiente información.

- **Nombre Real** El nombre del Super Usuario. Así es como Joomla te saludará cuando inicies sesión.
- **Nombre de usuario de la cuenta de Super Usuario** El nombre de usuario para el *Super Usuario*. ¡Evita usar *admin* como nombre de Administrador!
- **Contraseña de administrador** Recuerda que un Super Usuario tiene el control máximo de las interfaces del Sitio y Administrador, así que usa una contraseña difícil. Usa **Mi Perfil** en la interfaz de *Administración* para cambiarla más tarde.
- **Dirección de correo electrónico del Super Usuario** La dirección de correo electrónico del Super Usuario. Ingresa un correo válido en caso de que olvides tu contraseña. Esta es la dirección de correo donde recibirás un enlace para cambiar la contraseña del Super Usuario.

Cuando todo en la segunda página esté completado, selecciona el botón *Setup Database Connection* para continuar.

## Configuración de la base de datos

Ingrese la información de la base de datos anotada cuando creó la base de datos para esta instalación.

![Joomla installer part 3, database configuration](../../../en/images/getting-started/installing-joomla-installer-3.png)

Para simplificar, estas instrucciones son una referencia para la instalación
con una base de datos MySQLi. Las instrucciones en la página de instalación son autoexplicativas, pero aquí están de nuevo:

- **Tipo de base de datos** MySQLi es la base de datos comúnmente utilizada
- **Nombre del host** Donde se encuentra su base de datos. Común es *localhost*,
  incluso en servicios de hosting. Sin embargo, algunos hosts utilizan un servidor
  de base de datos específico como *dbserver1.yourhost.com*.
- **Nombre de usuario** El nombre de usuario utilizado para conectar a la base de datos
- **Contraseña** La contraseña para el usuario de la base de datos (no la contraseña del administrador)
- **Nombre de la base de datos** El nombre de la base de datos
- **Prefijo de la tabla** Esto se genera automáticamente como una característica de seguridad. Puede aceptar el predeterminado generado aleatoriamente o cambiarlo. Solo asegúrese de no olvidar colocar el carácter de guion bajo (`_`) al final del prefijo.
- **Cifrado de conexión** especifica cómo debe cifrarse la conexión a la base de datos. Si no lo sabe, lo mejor es seguir con el predeterminado. Sin embargo, esto permite a las empresas que utilizan autenticación de una o dos vías para la conexión a la base de datos proporcionarla.

Todas estas opciones y más se pueden editar en la página de Configuración Global del Sitio, bajo *Opciones del Servidor* después de completar la instalación. Nota, romperás tu instalación si cambias estas configuraciones después de la instalación, a menos que tengas una copia completa de la base de datos actual que esté siendo usada por la instalación de Joomla. Los usos comunes serían actualizar el nombre de usuario y la contraseña de la base de datos o completar un traslado de una instalación existente a un nuevo host con diferentes parámetros.

Después de seleccionar el botón *Install Joomla*, deberías ver la barra de progreso de la instalación de Joomla.

![Joomla installer part 4, installation progress bar](../../../en/images/getting-started/installing-joomla-installer-4.png)

Una vez que se complete la instalación, deberías ver la página de éxito.

## Terminando

### Éxito y finalización de la instalación

¡Felicidades! Tu sitio Joomla está listo.

![Joomla installer part 5, your joomla site is ready](../../../en/images/getting-started/installing-joomla-installer-5.png)

La captura de pantalla de arriba muestra una instalación de desarrollador. Una instalación de producción elimina automáticamente la carpeta de Instalación.

Si deseas comenzar a usar Joomla de inmediato sin instalar idiomas adicionales, puedes seleccionar *Abrir Administrador* para ir al *Panel de Administración* o seleccionar *Abrir Sitio* para ir a la página de inicio del sitio. Puede que veas una sección con configuraciones recomendadas de PHP.

- **Configuraciones Recomendadas** Estas configuraciones se recomiendan en tu configuración de PHP, pero no impedirán que Joomla! sea instalado. Puedes consultar las instrucciones anteriores sobre cómo se pueden cambiar si hay necesidad de hacerlo.

### Idiomas adicionales

Como parte del proceso de instalación de Joomla, se le ofrece la oportunidad de instalar idiomas adicionales antes de completar la instalación.

Para hacer esto, seleccione el botón Instalar idiomas adicionales

Esto te llevará a una página de instalación adicional que te permitirá seleccionar los idiomas que necesites.

#### Instalar idiomas adicionales

Se muestra una lista de paquetes de idiomas.

![Joomla installer part 6, install additional languages](../../../en/images/getting-started/installing-joomla-installer-6.png)

Seleccione hasta 3 idiomas que desee instalar. (Más de 3 a la vez puede causar problemas de tiempo de espera; puede instalar más posteriormente.)

Recuerda lo siguiente:

- Los paquetes de idiomas incluidos en distribuciones personalizadas no se listarán en esta etapa ya que ya están instalados.
- Una versión de los paquetes propuestos coincidirá con la versión principal de Joomla (5.0.x, 5.1.x, etc.). La versión menor del paquete puede no corresponder, por ejemplo, estás instalando la versión 5.0.3 y se muestra un paquete de idioma 5.0.2.
- Los paquetes de idiomas no coincidentes en el ejemplo anterior pueden tener cadenas sin traducir.
- Los paquetes de idiomas no coincidentes se ofrecerán como una actualización cuando los paquetes sean actualizados por los equipos de traducción registrados. La actualización disponible se mostrará en el panel de control así como en **Extensiones → Actualizar**. Este comportamiento es similar a **Extensiones → Instalar Idiomas**.

Seleccione *Siguiente* y se mostrará una barra de progreso mientras se instala el o los paquetes de idioma.

#### Elige el idioma predeterminado

Cuando la instalación de los idiomas se complete, ahora se te presentará una pantalla similar a *¡Felicidades! Tu sitio Joomla está listo.* La diferencia será una lista de los idiomas instalados que te permitirá seleccionar el idioma predeterminado para el Sitio y la interfaz del Administrador.

![Joomla installer part 7, choose default language](../../../en/images/getting-started/installing-joomla-installer-7.png)

- Seleccione el idioma predeterminado que desea usar.
- Cuando haya seleccionado el idioma predeterminado, seleccione el botón *Establecer idioma predeterminado* para confirmar.
- Se mostrará un mensaje del sistema confirmando que Joomla ha establecido el idioma predeterminado del ADMINISTRADOR y del SITIO. Ese mensaje se puede cerrar.

#### Finalizar

Ahora puedes navegar al *Panel de Administrador*. Inicia sesión seleccionando *Abrir Administrador* o ve directamente a la página de inicio de tu sitio seleccionando *Abrir Sitio*.

*Traducido por openai.com*

