<!-- Filename: How_to_debug_SMTP_mail_in_Joomla_4 / Display title: Correo SMTP y Gmail -->

## Introducción

En la página de Configuración Global, en el panel del Servidor, hay una opción para seleccionar un agente de entrega de correo. La configuración predeterminada es *Correo PHP*. Si esto no funciona, se puede recomendar usar SMTP. Este utiliza el mismo mecanismo que su aplicación de correo. Hay varias configuraciones que necesita ajustar correctamente. En resumen:

Vaya a **Configuración Global** y seleccione la pestaña **Servidor**. Busque el panel de *Correo* cerca de la parte inferior del formulario.

- **Sistema de Correo** configurado en SMTP. Aparecen varios campos adicionales.
- **Host SMTP** Este es localhost de manera predeterminada, pero es poco probable que funcione. Necesita configurarse como el host que maneja su correo saliente, por ejemplo, una cuenta de Gmail.
- **Puerto SMTP** El valor predeterminado es 25. Verifique que este sea el valor esperado por su Host SMTP.
- **Seguridad SMTP** El valor predeterminado es *Ninguno*, pero probablemente necesitará STARTTLS.
- **Autenticación SMTP** Esto puede no ser necesario si está utilizando una red doméstica que espera que los correos salientes no requieran autenticación. De lo contrario:
- **Nombre de Usuario SMTP** y **Contraseña SMTP** ingrese los valores que utiliza para acceder a su cuenta de correo electrónico a través de internet.
- Seleccione el botón **Enviar Correo de Prueba**.

## Usando Gmail

Si tienes una cuenta de Gmail activa, puedes usar Gmail como tu servidor de correo configurándolo en la configuración global.

En la pestaña del servidor configura lo siguiente:

- Remitente: SMTP
- Host SMTP: smtp.gmail.com
- Puerto SMTP: 465
- Seguridad SMTP: SSL/TLS
- Autenticación SMTP: Sí
- Configura las dos líneas siguientes con tu información. Necesitas usar una contraseña específica de aplicación (ASP), descrita a continuación.
- Nombre de usuario SMTP: tu nombre de usuario de Gmail
- Contraseña SMTP: la contraseña específica de la aplicación (ASP) que generaste, descrita a continuación.

Las siguientes también son combinaciones funcionales:

- Puerto SMTP: 587
- Seguridad SMTP: STARTTLS
- Puerto SMTP: 25
- Seguridad SMTP: STARTTLS

El módulo SSL no necesita estar habilitado en Apache.

La extensión OpenSSL necesita estar habilitada en PHP. Los detalles se pueden encontrar en la [página de Instalación de php.net](https://www.php.net/manual/en/openssl.installation.php).

Si estás usando WAMP en Windows, el módulo openssl no está habilitado por defecto y necesitas habilitarlo. Para hacerlo:

1. Abre el archivo php.ini y descomenta la línea `extension=php_openssl.dll` eliminando el punto y coma ; del principio de la línea.
2. Guarda el archivo php.ini y reinicia el servicio de Apache.

Ten en cuenta que si usas la verificación en dos pasos en Gmail, necesitas añadir una nueva contraseña en Configuración - Cuentas - Cambiar la configuración de las cuentas - Otras configuraciones de la cuenta de Google - Seguridad - Verificación en dos pasos - Gestionar tus contraseñas específicas de aplicación.

Cuando se presente la nueva Contraseña Específica de la Aplicación (ASP) en grupos de cuatro caracteres separados por espacios, asegúrate de **NO introducir los espacios** en la contraseña SMTP en la configuración del servidor de correo en Joomla.

- Contraseñas Específicas de Aplicación (ASP): Consulta la página de Soporte de Google titulada
  [Iniciar sesión con contraseñas de aplicación](https://support.google.com/accounts/answer/185833).
- Verificación en Dos Pasos: Consulta la página de Soporte de Google titulada 
  [Activar la verificación en dos pasos](https://support.google.com/accounts/answer/185839).

## Depuración

Si el correo no se envía o nunca llega:

- Selecciona **Plugins** desde el **Panel de inicio → Panel del sitio**.
- Busca y habilita el plugin **Sistema - Depuración** y configúralo:
- Establece **Grupos permitidos** en *Super Usuarios* para restringir la salida de depuración a tu propia sesión de inicio tanto en el backend como en el frontend. Si no deseas iniciar sesión en el frontend como Super Usuario, crea un grupo de usuarios único para tus actividades de prueba y selecciona ese grupo de usuarios de la lista de grupos de usuarios permitidos.
- **Guardar y cerrar**

- Selecciona **Configuración global** desde el **Panel de inicio → Panel del sitio**.
- En la pestaña *Sistema*, configura **Depurar sistema** en *Sí*.
- En la pestaña *Servidor*, configura **Informe de errores** en *Máximo*.
- En la pestaña *Registro*, anota el contenido de *Ruta a la carpeta de registros*, generalmente *[algo]/administrator/logs*.
- Configura **Registrar casi todo** en *Sí*.
- En el panel *Registro personalizado*, establece el campo *Categorías de registro* en *correo* (sin comillas).
- **Guardar** para guardar los ajustes de depuración.
- En la pestaña **Servidor**, selecciona el botón *Enviar correo electrónico de prueba* al final de la página.

Si hay problemas en el código durante las pruebas, deberías obtener un *Rastreo de pila* que te ayudará a ti u a otros a diagnosticar el problema. Además, busca un archivo en la carpeta de registros con un nombre como *administrator/logs/everything.php* y ábrelo con un editor de texto. Puede ser útil ver lo que se registró cuando se envió el mensaje.

*Traducido por openai.com*

