<!-- Filename: Get_locally_hosted_Joomla!_website_e-mail_functions_to_work / Display title: Correo Electrónico del Host Local  -->

## Alojamiento Local

La mayoría de los proveedores de servicios de Internet (ISP) bloquean el puerto 25, por lo que no puede enviar correos electrónicos desde el servidor SMTP de su propia computadora. Esto es para bloquear a los spammers. Si no tiene la intención de hacer spam, puede usar el servidor de correo de su ISP.

Para usar la función de correo electrónico desde el servidor SMTP de su ISP, incluso si está alojando su propio sitio Joomla en su propia computadora, inicie sesión en su sitio Joomla como Super Usuario y navegue hasta la pestaña **Servidor** en la página de **Configuración Global**. En la sección **Correo** sus datos deberían verse como los siguientes:

    Desde Email: alguien@ejemplo.com (usualmente usted)
    Desde Nombre: AlgúnNombre

    Enviador: SMTP
    SMTP Host: smtp.charter.net (Lo que su ISP le diga que use para sus servidores SMTP)
    Ruta de Sendmail: /usr/sbin/sendmail
    Puerto SMTP: 25
    Seguridad SMTP: STARTTLS
    Autenticación SMTP: Sí (o No)
    Nombre de usuario SMTP: johndoe (nombre de usuario de una de sus cuentas de correo electrónico en su ISP)
    Contraseña SMTP: trr33459 (contraseña de una de sus cuentas de correo electrónico en su ISP)
Envíe un mensaje de prueba para verificar que está funcionando.

El nombre de usuario SMTP, la contraseña y el host son los mismos campos que ingresa al agregar una cuenta de Outlook Express, o Eudora, o cualquier cliente de correo electrónico que pueda usar en su computadora.

Puede encontrarse con problemas con extensiones que cambien la dirección de *Remitente* en los correos electrónicos que se envían. Por ejemplo, la extensión ProjectFork a veces envía correos electrónicos como si provinieran de la persona que controla el proyecto. Esto puede causar un problema porque algunos servidores SMTP de ISP no permitirán una dirección de "remitente" que no coincida con el nombre de usuario (por ejemplo, Rogers en Canadá). Recibirá un mensaje como este: "PHPMAILER_FROM_FAILEDnombre@loquesea.com." Una solución es asegurarse de que siempre utilice una dirección de correo electrónico válida de su ISP para sus usuarios.

*Traducido por openai.com*

