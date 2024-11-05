<!-- Filename: J4.x:Multi-factor_Authentication / Display title: Autenticación Multifactor  -->

## Introducción

El sistema de autenticación multifactor de Joomla! está basado en Akeeba Loginguard y gran parte de esta documentación se ha derivado con el permiso de Akeeba.

## ¿Qué hace?

Añade múltiples métodos opcionales de Verificación de Dos Pasos para el inicio de sesión en Joomla! Después de iniciar sesión solo con tu nombre de usuario y contraseña, se te pedirá que proporciones tu verificación de segundo paso, por ejemplo, un código generado por Google Authenticator. Hasta que no proporciones una verificación de segundo paso correcta, no podrás acceder a ninguna página del sitio. Siempre serás redirigido a la página de "inicio de sesión cautivo". Esto es similar a lo que hace Google cuando intentas iniciar sesión en GMail.

Esto difiere del método de autenticación de dos factores original de Joomla!, que requería que el segundo factor de autenticación (por ejemplo, el código generado por Google Authenticator) se ingresara junto con el nombre de usuario y la contraseña.

Las ventajas de la Verificación de Dos Pasos son:

- Es menos confusa para el usuario. Ya no es necesario el campo "Clave Secreta", que confunde a los usuarios.
- Puede funcionar con métodos de inicio de sesión sin contraseña, como el inicio de sesión social (por ejemplo, Facebook), tokens de hardware seguros, SSO (inicio de sesión único), etc. 
  Aclaración: La Verificación de Dos Pasos se puede configurar para ser solicitada después de que un usuario inicie sesión con un método de inicio de sesión sin contraseña. No implementa métodos de inicio de sesión sin contraseña.
- Tiene un mejor control de acceso. Puedes establecer Opciones de Usuario para Requerir o Deshabilitar la Autenticación de Múltiples Factores por grupo de usuarios.
- Permite métodos de autenticación alternativos en una sola cuenta. Puedes tener varios métodos de autenticación en tu cuenta. Por ejemplo, puedes configurar una aplicación de Google Authenticator y una YubiKey.
- Soporta métodos que no requieren ingresar un código. Por ejemplo, dispositivos FIDO2, verificación biométrica, etc. Estos necesitan interactuar con el navegador y/o el sistema operativo a través de API nativas de HTML5.
- Soporta métodos que requieren interacción del usuario. Por ejemplo, enviar un código mediante un mensaje push, SMS o correo electrónico. Estos métodos requieren saber qué usuario está siendo autenticado antes de enviar el código de autenticación al usuario.
- Es gratuito. A diferencia de los servicios de terceros que proporcionan autenticación multifactor, no tienes que pagar una tarifa de configuración inicial ni una tarifa mensual/anual de mantenimiento por cada sitio o usuario que use la Verificación de Dos Pasos. El software es gratuito.

## ¿Cómo funciona?

Inicias sesión en tu sitio de manera habitual, por ejemplo, proporcionando un nombre de usuario y contraseña. Es importante notar que no necesitas ingresar tus credenciales de autenticación en el segundo paso en esta etapa.

El sistema detecta que ya has iniciado sesión pero no has realizado la autenticación de segundo paso. Almacena la URL que se suponía debías ver y te redirige inmediatamente a la página de inicio de sesión cautivo. Cualquier intento de navegar a una página diferente resultará en la aparición de la página cautiva.

Los módulos en tu sitio pueden contener información privilegiada. Para asegurar la confidencialidad, los módulos se desactivan forzosamente en el momento de la renderización. Esto significa que ninguna posición de módulo se mostrará en la página. Recuerda esto en caso de que notes que el encabezado u otras áreas clave de diseño de tu sitio faltan en la página de inicio de sesión cautivo.

Ten en cuenta que los complementos, por otro lado, NO están desactivados. Esto se debe tanto a que Joomla hace extremadamente difícil eliminar complementos específicos una vez que están cargados, como al hecho de que la mayoría de los complementos realizan funciones críticas en tu sitio.

Después de proporcionar tu verificación de segundo paso, se establece una bandera en la sesión del usuario, lo que indica que estás completamente autorizado para usar el sitio. Además, serás redirigido a la URL que se almacenó justo después de que inicialmente iniciaste sesión.

## Autenticación de Dos Factores frente a inicios de sesión con WebAuthn

Iniciar sesión con WebAuthn es la opción más segura. Solo proporcionas un nombre de usuario, que se supone debe ser considerado información pública y no privilegiada. El sitio crea un desafío criptográfico que es firmado por el navegador usando hardware seguro: un token de hardware seguro externo o el Módulo de Plataforma Confiable / Enclave Seguro de tu dispositivo, y devuelto al servidor. El servidor valida la firma. Esta validación utiliza criptografía de clave pública y el sitio solo almacena la clave pública. Esto hace que el inicio de sesión sea virtualmente infalible y extremadamente seguro. Si usas eso, no necesitas un segundo factor de autenticación, pero si realmente lo deseas, también puedes usar WebAuthn para ello.

Aparte del uso de métodos de inicio de sesión federados (como iniciar sesión con tu cuenta de redes sociales, un servicio de inicio de sesión único, un servidor LDAP, etc.), un inicio de sesión convencional con nombre de usuario y contraseña no es tan seguro como un inicio de sesión con WebAuthn. Ingresar un nombre de usuario y contraseña puede ser interceptado, robado o adivinado. Esto hace que confiar solo en un nombre de usuario y contraseña sea muy problemático.

Para la autenticación multifactor solo proporcionas tu nombre de usuario y contraseña. Un ataque de phishing exitoso solo obtendría este primer factor de autenticación pero no tu segundo factor de autenticación. Después de un inicio de sesión exitoso, se te presenta una página cautiva. No puedes hacer nada más en el sitio hasta que proporciones tu segundo factor. Dado que la entrada del segundo factor se presenta en su propia página, puede ser interactiva (por ejemplo, WebAuthn), asincrónica (por ejemplo, recibir una OTP por correo electrónico, mensaje de texto o notificación push) o iniciada por el usuario (por ejemplo, un TOTP o una OTP de Yubikey). Aún mejor, un usuario puede tener múltiples métodos de segundo factor habilitados en su cuenta para prevenir bloqueos accidentales del sitio. Por ejemplo, podrías estar usando WebAuthn con un dongle de hardware seguro externo como tu segundo factor primario y más seguro. También podrías tener configurado un TOTP regular en caso de que pierdas el dongle o te olvides de llevarlo contigo. Algunos métodos de segundo factor permiten múltiples instancias; por ejemplo, puedes tener múltiples autenticadores WebAuthn para que puedas usar el autenticador incorporado en tu computadora Windows, tu iPhone y tu tableta Android sin tener que recordar empacar un dongle de hardware y adaptadores cada vez que sales de tu escritorio.

Recapitulemos. De más seguro a menos seguro, tus opciones son:

- WebAuthn como tu método principal de inicio de sesión con Autenticación Multifactor secundaria.
- WebAuthn como tu único método de inicio de sesión.
- Nombre de usuario y contraseña como tu método principal de inicio de sesión con Autenticación Multifactor secundaria.
- Solo un nombre de usuario y contraseña como tu único método de inicio de sesión.

## Plugins

Cada uno de los factores en la Autenticación Multifactor se implementa mediante plugins. Pueden activarse o desactivarse según sea necesario, y se pueden agregar nuevos cuando surjan nuevos métodos. Los plugins incluidos en el núcleo de Joomla son:

- **Código de Verificación**: códigos de verificación de seis dígitos generados por una aplicación de autenticación (Google Authenticator, Authy, LastPass Authenticator, etc.), un gestor de contraseñas (1Password, BitWarden, Keeper, KeePassXC, Strongbox, etc.) o, en algunos casos, su navegador.
- **YubiKey**: Permite a los usuarios de tu sitio usar Autenticación Multifactor usando un token de hardware seguro YubiKey. Los usuarios necesitan su propio YubiKey disponible en www.yubico.com.
- **Autenticación Web**: soportada por todos los navegadores modernos. La mayoría de los navegadores ofrecen autenticación específica del dispositivo protegida por una contraseña y/o biometría (sensor de huellas dactilares, escaneo facial, ...).
- **Código de Autenticación por Correo Electrónico**: Utiliza códigos de seguridad de seis dígitos limitados por tiempo que te son enviados por correo electrónico. La configuración predeterminada es de 2 minutos.
- **Código Fijo**: esto está destinado para pruebas e ilustración y está deshabilitado de forma predeterminada. No debe habilitarse en un sitio de producción.

Ten en cuenta que hay un plugin separado **Sistema - Inicio de Sesión Sin Contraseña WebAuthn** para manejar el inicio de sesión desde el botón de Autenticación Web en el formulario de inicio de sesión.

## Opciones de Usuarios

El formulario de Opciones de Usuarios tiene un formulario de Autenticación Multifactor para configurar cómo funciona la Autenticación Multifactor en Joomla. Selecciona el botón Activar Ayuda en Línea para obtener información sobre cada opción.

![opciones de usuarios formulario de autenticación multifactor](../../../en/images/users/users-configuration-mfa.png)

## Perfil de Usuario

El formulario de Administrador / Usuarios: Editar Perfil tiene pestañas separadas para Inicio de Sesión con WebAuthn y Autenticación Multifactor, pero esta última solo es visible para el propietario de la cuenta. Incluso los Súper Usuarios no ven esta pestaña para otros usuarios.

El formulario Sitio / Editar tu Perfil tiene las pestañas del formulario del backend dispuestas una encima de la otra, lo cual puede ser confuso porque la Autenticación Web aparece dos veces, primero para el inicio de sesión sin contraseña y, segundo, para la Autenticación Multifactor. La siguiente ilustración muestra la parte de Autenticación Multifactor del formulario después de que se ha creado un método. Eso automáticamente configura la característica como Habilitada y muestra la opción de crear Códigos de Respaldo.

![vista del sitio del formulario de autenticación multifactor del usuario](../../../en/images/users/multi-factor-authentication-site-profile.jpg)

Como se mencionó anteriormente, puedes probar cada uno seleccionando el botón + Añadir ..., pero selecciona Cancelar en el formulario posterior si decides no continuar.

*Traducido por openai.com*

