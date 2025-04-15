<!-- Filename: J4.x:Global_Configuration / Display title: Configuración Global -->

## Resumen

Durante la instalación, un sitio de Joomla crea un archivo llamado **configuration.php** en la raíz del sitio. Este archivo contiene los valores de las variables de configuración que se aplican a todo el sitio. Ejemplos incluyen el nombre del sitio y las credenciales de la base de datos que se ingresaron durante el proceso de instalación. Hay muchas más variables que reciben valores iniciales adecuados.

El formulario de Configuración Global permite a un Súper Usuario cambiar las variables de configuración para adaptarse a las necesidades del sitio. Además de las variables almacenadas en configuration.php, el formulario realiza un seguimiento de la información de Registro, Filtrado y Control de Acceso, algunas de las cuales se almacenan en la base de datos.

## Captura de Pantalla

El formulario de Configuración Global tiene seis pestañas, algunas de las cuales tienen listas largas
de parámetros. Usa el botón *Alternar Ayuda en Línea* en la Barra de Herramientas para ver 
más o menos información sobre cada parámetro.

![Pestaña del sitio de configuración global](../../../en/images/configuration/global-configuration-site-tab.png)

Algunos parámetros muestran u ocultan otros parámetros cuando se seleccionan. Por
ejemplo, el botón **Sitio Fuera de Línea** muestra más campos cuando se configura en *Sí*
que cuando se configura en *No*. Con la ayuda en línea expandida, la mayoría de los campos están
suficientemente bien documentados para no necesitar más explicación aquí, aparte de algunas notas
adicionales para el usuario en cada pestaña.

## Pestaña del sitio

### Panel del sitio

- **Nombre del sitio** Este es el nombre del sitio que aparece en el formulario de inicio de sesión del administrador y en el enlace del sitio en la barra de título. Cámbielo según sea necesario.
- **Sitio fuera de línea** Hay un [tutorial](jdocmanual?article=user/configuration/site-offline) separado sobre este elemento.
- **Límite de lista predeterminado** establece el número máximo predeterminado de elementos por página en las vistas de lista. Por defecto, este parámetro está configurado en 20, pero las vistas de lista generalmente incluyen una lista desplegable para seleccionar otros valores que van de 5 a 100. Menos valores son más rápidos de procesar e implican menos desplazamiento por parte del usuario.

### Panel de metadatos

- **Descripción de metadatos del sitio** Esta es la descripción de metadatos predeterminada que se utiliza si tal descripción no se especifica en un campo de descripción meta de artículo o en un campo de descripción meta de menú. Si los tres están vacíos, la descripción de metadatos se omite de la salida de la página. A menudo, los motores de búsqueda utilizan esto para proporcionar texto descriptivo para una página. Si está ausente, los motores de búsqueda pueden usar texto del contenido de la página, lo cual puede no ser apropiado. Se recomienda una descripción del propósito del sitio de alrededor de 20 palabras.
- **Derechos de contenido** establece la entrada de metadatos *derechos*. Si es apropiado, describe aquí qué derechos tienen otros para usar este contenido. Esta entrada de metadatos se omite de las páginas web si esta entrada está en blanco. Ejemplo: Licencia Creative Commons Atribución 4.0 Internacional (ver [Elegir una licencia Creative Commons](https://creativecommons.org/choose/)).

### Panel SEO

SEO es un acrónimo de *Optimización para Motores de Búsqueda*. Las configuraciones en este grupo modifican el formato de los URLs para las páginas en el sitio web y esto puede tener un efecto significativo en el posicionamiento en los buscadores de páginas individuales y del sitio en su totalidad. Los URLs SEO son más legibles para los humanos.

**Consejo** Después de hacer cualquier cambio en la configuración de este grupo, actualiza cualquiera de las páginas del sitio web que ya estén abiertas en tu navegador (normalmente Ctrl+R o Cmd+R hará esto). No actualizar podría significar que el formato de los enlaces web internos del sitio ya no coincida con el que Joomla espera y, por lo tanto, podría dar la apariencia de enlaces rotos.

**Consejo** Si es posible, evita alterar la configuración de SEO una vez que un sitio web esté establecido. Hacerlo podría resultar en enlaces rotos desde otros sitios y tal vez una caída temporal en los rankings de los motores de búsqueda.

- **Alias Unicode** Cambiar este parámetro no modifica retroactivamente los alias, solo cambia el comportamiento de la generación automática de alias para futuras ediciones y creaciones de contenido. *Transliteración* (No) es la configuración predeterminada.

### Panel de cookies

- **Dominio de la cookie** Sobrescribe el dominio de cookies predeterminado del sitio con el dominio añadido aquí. La situación más probable en la que esto sería necesario es cuando el sitio Joomla está "conectado" con otros sitios (por ejemplo, foros o comercio electrónico) en subdominios del sitio Joomla. El dominio de cookies predeterminado puede ser algo como `www.example.com`, pero utilizar `.example.com` (nota el punto inicial) aquí entregará cookies válidas para cualquier subdominio de example.com.
- **Ruta de la cookie** Sobrescribe la ruta predeterminada del sitio para la cual la cookie es válida con la ruta añadida aquí. Esto puede ser necesario si tienes varias instalaciones de Joomla en carpetas hermanas.

## Pestaña del sistema

![Pestaña de configuración global del sistema](../../../en/images/configuration/global-configuration-system-tab.png)

### Panel de depuración

Los elementos de este panel están bien explicados por la ayuda en línea. Sin embargo, si encuentras un problema que deshabilita el acceso normal a la interfaz de administrador, es posible que necesites configurar el Sistema de Depuración editando configuration.php con un editor de texto. En la mayoría de los sistemas de alojamiento basados en Linux, los permisos de archivo están configurados en 444, lo que impide guardar desde un editor de texto. Cambia el permiso a 644 antes de editar. Luego configura \$debug = `true`; y establece \$error_reporting = `'maximum'`; y guarda. Deberías entonces obtener un rastreo de pila que identifique exactamente dónde ocurre el problema. Puedes usar eso para buscar ayuda en los foros. La mayoría de los problemas surgen de extensiones de terceros incompatibles o de problemas con el entorno de alojamiento.

## Pestaña del servidor

![Pestaña del servidor de configuración global](../../../en/images/configuration/global-configuration-server-tab.png)

### Panel de correo

Un sitio Joomla debería poder enviar correos electrónicos salientes. Entre otras cosas, enviará mensajes automáticos al propietario del sitio cuando haya actualizaciones disponibles. Sin embargo, algunos servicios de alojamiento restringen los métodos mediante los cuales se pueden enviar correos salientes.

#### Enviar correo de prueba

Antes de Joomla 5.3, el botón **Enviar correo de prueba** enviaba un mensaje a la dirección configurada en el campo **Correo del remitente**. Desde la versión 5.3, el correo de prueba se envía directamente a la dirección de correo electrónico del administrador que ha iniciado sesión.

- Primero, prueba con PHP Mail y selecciona el botón *Enviar correo de prueba*. Si el correo electrónico llega, todo está bien. De lo contrario:
- Prueba la opción Sendmail. Si eso no funciona:
- Prueba la opción SMTP. Esto debe configurarse para un servidor de correo específico. Podría ser uno proporcionado por tu servicio de alojamiento. Podría ser una cuenta de Gmail.
- **Host SMTP** El nombre del host del servidor SMTP (por ejemplo, *smtp.ejemplo.com*).
  - **Puerto SMTP** El puerto a usar al conectarse al servidor SMTP. Este usualmente será *25* cuando la Seguridad SMTP esté configurada en *Ninguna*, o *465* o *587* cuando la Seguridad SMTP esté configurada en `SSL/TLS` o `STARTTLS`. Pregunta a tu proveedor de servicios SMTP cuál puerto usar.
  - **Seguridad SMTP** La forma de seguridad requerida por el servidor SMTP: *Ninguna*, *SSL/TLS* o *STARTTLS*. El valor predeterminado es *Ninguna*.
  - **Autenticación SMTP** Indica si el servidor SMTP externo requiere autenticación antes de aceptar correos electrónicos salientes. El valor predeterminado es *No*.
  - **Nombre de usuario SMTP** El nombre de usuario a utilizar al conectarse al servidor SMTP en modo SSL o TLS. Puede dejarse en blanco si no hay autenticación SMTP.
  - **Contraseña SMTP** La contraseña a utilizar al conectarse al servidor SMTP en modo SSL o TLS. Puede dejarse en blanco si no hay autenticación SMTP.

### Usando Gmail como servidor de correo

Si tienes una cuenta de Gmail activa, puedes usar Gmail como tu servidor de correo configurándolo en la configuración global. En la pestaña del servidor, configura lo siguiente:

- Manejador de correo: SMTP
- Host SMTP: smtp.gmail.com
- Puerto SMTP 465
- Seguridad SMTP: SSL/TLS
- Autenticación SMTP: Sí
- Configura las siguientes dos líneas con tu información. Necesitas usar una contraseña específica de aplicación (ASP), descrita a continuación.
- Nombre de usuario SMTP: tu nombre de usuario de Gmail
- Contraseña SMTP: la contraseña específica de la aplicación (ASP) que generaste, descrita a continuación.

Las siguientes también son combinaciones funcionales:

- Puerto SMTP 587
- Seguridad SMTP: STARTTLS
- Puerto SMTP 25
- Seguridad SMTP: STARTTLS

#### Notas

- El módulo SSL no necesita estar habilitado en Apache.
- La extensión OpenSSL necesita estar habilitada en PHP. Los detalles se pueden encontrar en la [página de instalación de php.net](https://www.php.net/manual/en/openssl.installation.php).
- Si estás usando WAMP en Windows, el módulo openssl no está habilitado por defecto y necesitas habilitarlo. Para hacerlo:
  - Abre el archivo php.ini y descomenta la línea `extension=php_openssl.dll` eliminando el punto y coma ; al principio de la línea.
  - Guarda el archivo php.ini y reinicia el servicio Apache.
- Si usas la verificación en dos pasos en Gmail, necesitas agregar una nueva contraseña en Configuración - Cuentas - Cambiar la configuración de cuentas - Otras configuraciones de cuenta de Google - Seguridad - Verificación en dos pasos - Gestionar tus contraseñas específicas de aplicación.
- Cuando se presenta la nueva Contraseña Específica de Aplicación (ASP) en grupos de cuatro caracteres separados por espacios, asegura que **NO ingreses los espacios** en la contraseña SMTP en la configuración del servidor de correo en Joomla.
- Contraseñas Específicas de Aplicación (ASPs): Consulta la página de soporte de Google sobre cómo [Iniciar sesión con contraseñas de aplicaciones](https://support.google.com/accounts/answer/185833).
- Verificación en dos pasos: Consulta la página de soporte de Google sobre cómo [Activar la verificación en dos pasos](https://support.google.com/accounts/answer/185839).

## Pestaña de registro

![Pestaña del sitio de configuración global](../../../en/images/configuration/global-configuration-logging-tab.png)

En el funcionamiento normal, un sitio de Joomla debería tener el registro desactivado. Si hay problemas, puedes habilitar el registro configurando el campo **Registrar Casi Todo** en `Sí`. El campo **Registrar API Obsoleta** es realmente solo para desarrolladores. El campo **Ruta a la Carpeta de Registros** te muestra dónde buscar registros si has configurado el registro para ayudar con la depuración. Los registros de errores que encuentres allí son solo aquellos atrapados por Joomla. Puede haber otros errores que solo aparecerán en los registros de errores de tu servidor.

## La pestaña Filtros de Texto

![Pestaña del sitio de configuración global](../../../en/images/configuration/global-configuration-filters-tab.png)

Los ajustes de filtros de texto se aplicarán a todos los campos del editor de texto enviados por usuarios en los grupos seleccionados. Estas opciones de filtrado ofrecen más control sobre el HTML que envían tus proveedores de contenido. Puedes ser tan estricto o tan liberal como necesites para satisfacer las necesidades de tu sitio. El filtrado es voluntario y la configuración predeterminada ofrece buena protección contra el marcado comúnmente asociado con ataques a sitios web.

## Pestaña de Permisos

![Pestaña de configuración global del sitio](../../../en/images/configuration/global-configuration-permissions-tab.png)

Los permisos controlan lo que los usuarios de cada Grupo de Usuarios pueden ver y hacer. Las entradas en la pestaña de Permisos establecen los permisos predeterminados para el sitio.

Hay descripciones detalladas sobre el uso de las configuraciones bajo esta pestaña y los principios generales de operación y configuración de permisos en un [Tutorial de Lista de Control de Acceso](jdocmanual?article=user/users/access-control).

*Traducido por openai.com*

