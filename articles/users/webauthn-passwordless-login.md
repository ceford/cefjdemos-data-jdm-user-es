<!-- Filename: WebAuthn_Passwordless_Login / Display title: Inicio de sesión con WebAuthn  -->

## Inicio de sesión sin contraseña con WebAuthn

La autenticación web, o WebAuthn para abreviar, permite a un usuario iniciar
sesión de forma segura en un sitio sin usar una contraseña, aunque todavía se necesita un nombre de usuario.
Utiliza criptografía fuerte de una manera que es extremadamente resistente a los problemas más comunes de las contraseñas:
* alguien la adivinó (ataque de fuerza bruta)
* alguien la interceptó (ataque de intermediario)
* alguien te engañó para divulgarla (ataque de phishing)
* alguien la descifró después de obtener una copia de los datos de tu base de datos
(ataques de inyección SQL)
* alguien la robó.

WebAuthn no solo es muy seguro; ¡también es muy fácil de usar! Ya no
tienes que recordar contraseñas largas ni usar un gestor de contraseñas. Todo
lo que necesitas es un *autenticador*, a veces también llamado una *clave de acceso*.

Un autenticador puede tener muchas formas, ya sean físicas o virtuales. Puede ser una
llave de hardware separada que se conecta a tu dispositivo a través de USB, Bluetooth o
NFC. Puede ser tu propio dispositivo, desbloqueando su autenticador integrado
con un PIN, lector de huellas dactilares, escaneo facial o una verificación biométrica similar.

Esta característica ya funciona en dispositivos Android e iOS/iPadOS y estamos
trabajando para habilitarla también en Windows. Incluso puede ser tu teléfono:
actualmente esto es posible con teléfonos Android, pero esta característica también
llegará a dispositivos iOS / iPadOS.

WebAuthn solo funciona a través de HTTPS y solo cuando tu sitio utiliza un certificado
válido y confiable para ello. No te preocupes, no tienes que gastar dinero extra;
servicios gratuitos como Let's Encrypt suelen estar integrados en paneles de control
de alojamiento web y funcionan perfectamente bien con WebAuthn.

WebAuthn utiliza criptografía de clave pública, la misma tecnología comprobada que
mantiene tus sitios seguros con HTTPS, tu información bancaria segura, etc.
La clave privada nunca sale del autenticador. Tu sitio solo almacena una clave pública.
Incluso si sufres una violación de datos, el atacante se quedará con una clave pública
prácticamente inútil; les tomaría miles a millones de años de CPU descifrarla en lugar de
unos pocos minutos u horas necesarios para descifrar el hash de una contraseña fija que puedes recordar.

WebAuthn es el futuro de la autenticación. Fácil, seguro y sin complicaciones.
Todo lo que las contraseñas fijas no son.

La siguiente imagen muestra un dispositivo de hardware insertado en el puerto USB de un
computador portátil. Costó £15 en febrero de 2022.

![fotografía del dispositivo de hardware](../../../en/images/users/passwordless-login-hardware-device.jpg)

WebAuthn utiliza un complemento del sistema que está habilitado por defecto. Un botón de **Autenticación Web** estará presente en las pantallas de inicio de sesión predeterminadas de Joomla 4 y posteriores, como se ilustra en la pantalla de inicio de sesión del Administrador:

![formulario seguro de inicio de sesión de administrador](../../../en/images/users/passwordless-login-login-form.jpg)

## Configuración del Usuario

El usuario debe primero registrarse con un Nombre de Usuario y Contraseña normales. Después de iniciar sesión, vaya al formulario de Perfil de Usuario. Para un Administrador:

- Seleccione **Menú de Usuario → Editar Cuenta → Autenticación Web W3C (WebAuthn) Iniciar Sesión** para abrir el formulario, inicialmente sin autenticadores registrados.
- Seleccione **Agregar Nuevo Autenticador**

La presentación exacta del siguiente paso depende de su navegador. Por lo general, verá una alerta, mensaje o ventana que le pedirá seleccionar un tipo de autenticador o, si está utilizando un autenticador de hardware conectado a su dispositivo, recordándole que presione el botón en el autenticador de hardware. Por razones de seguridad y práctica, hay un intervalo de tiempo relativamente corto permitido para activar el autenticador: 60 segundos.

![aviso de hardware de inicio de sesión seguro de administrador](../../../en/images/users/passwordless-login-hardware-propmpt.png)

Una vez que desbloquee su autenticador —tocando un botón, escaneando su huella digital/cara, ingresando un PIN o una combinación de los anteriores, dependiendo de su autenticador— el mensaje desaparece, el autenticador se registra y la pantalla aparece de la siguiente manera:

![autenticador registrado de inicio de sesión seguro de administrador](../../../en/images/users/passwordless-login-registered-authenticator.png)

Es muy importante tener en cuenta que solo puede registrar o eliminar autenticadores en su propia cuenta de usuario. Por razones de seguridad, incluso a un Superusuario se le prohíbe registrar, editar o agregar autenticadores en otras cuentas de usuario.

### Autenticadores

Puede utilizar cualquier autenticador FIDO U2F o FIDO2. FIDO U2F es un estándar más antiguo que admite una selección más limitada y menos segura de métodos criptográficos. FIDO2 es el estándar más nuevo que admite métodos criptográficos mucho más seguros, incluida la Criptografía de Curva Elíptica, un método criptográfico que se cree resistente incluso a la computación cuántica (si y cuando se convierte en una realidad práctica). Además, los autenticadores FIDO2 pueden configurarse para tener protecciones adicionales como un PIN o un control biométrico (por ejemplo, escaneado de huellas dactilares), lo que significa que incluso si pierde la posesión física del autenticador, quien lo encuentre no podrá iniciar sesión en sus sitios.

Si busca comprar un autenticador de hardware, puede buscar "FIDO2" en su mercado favorito, como Amazon. Hay una amplia selección para elegir.

También puede usar una clave FIDO de software, como Krypton, como su autenticador.

Muchos dispositivos tienen autentificación incorporada compatible con FIDO2:

- Windows 10 y 11 tienen Windows Hello con un PIN, escáner de huellas dactilares, cámara de reconocimiento facial o una combinación de clave de hardware y PIN. El soporte para Windows Hello se está agregando al complemento con un objetivo de lanzamiento de Joomla 4.2.0.
- macOS tiene TouchID en todos los portátiles con el chipset T2 o aquellos basados en Apple Silicon utilizando el sensor TouchID incorporado, así como en todas las computadoras de escritorio basadas en Apple Silicon utilizando el nuevo teclado Apple Aluminium con escáner de huellas dactilares.
- iOS / iPadOS tiene TouchID en todos los dispositivos con un escáner de huellas dactilares y FaceID en todos los dispositivos más nuevos con una cámara de proyección de puntos infrarrojos FaceID.
- Algunos dispositivos Android tienen un escáner de huellas dactilares o una cámara de reconocimiento facial. Estos también pueden funcionar como autenticadores FIDO2, en Android 9 o posterior, utilizando al menos Google Chrome.
- Puede que haya otros dispositivos disponibles también. Por ejemplo, teléfonos Android que utilizan ![caBLE](https://groups.google.com/a/fidoalliance.org/g/fido-dev/c/go6GoFW27Dw/m/9flCLR5pBQAJ?pli=1)

### Navegadores compatibles con WebAuthn

Los navegadores basados en Chromium y Firefox han soportado WebAuthn desde principios de 2019.

Safari y todos los navegadores de iOS/iPadOS (que, de hecho, son Safari con una apariencia diferente) han soportado completamente WebAuthn desde iOS/iPadOS 13, lanzado a finales de 2019.

Prácticamente hablando, si su sistema operativo y navegador fueron lanzados después de mediados de 2020, no debería tener problemas. Solo algunos navegadores muy poco comunes aún carecen de soporte para WebAuthn.

## Autenticación

Para iniciar sesión, debes ingresar tu nombre de usuario en el campo Nombre de usuario del formulario de inicio de sesión. No necesitas ingresar tu contraseña, pero si tu navegador la introduce por ti, simplemente déjala. La contraseña NO se envía al servidor cuando el formulario se envía a través del botón de Autenticación Web.

De esto se desprende que puedes iniciar sesión ya sea con tu Nombre de usuario y Contraseña o con Nombre de usuario y Autenticación Web.  

## Cómo desactivar el plugin

Si no deseas permitir WebAuthn, simplemente ve a la lista de plugins y busca Sistema - Inicio de Sesión Sin Contraseña WebAuthn en el grupo de Sistema y desactívalo. No hay parámetros que configurar.

## Requisitos del Servidor

Para que WebAuthn funcione, deben cumplirse las siguientes condiciones previas:

- HTTPS con un certificado válido y firmado. La mayoría de los anfitriones te permiten usar certificados gratuitos emitidos por Let's Encrypt. Estos funcionan perfectamente con WebAuthn.
- La extensión OpenSSL para PHP debe estar instalada y habilitada.
- La extensión GMP de PHP o la extensión BCmath de PHP deben estar instaladas y habilitadas (cualquiera de las dos es suficiente).
- Idealmente, la biblioteca Sodium debería estar habilitada; permite el uso de Criptografía de Curvas Elípticas en autenticadores FIDO2 compatibles, que, como dijimos, es el método criptográfico más seguro.



## Notas para Desarrolladores

### Botones de inicio de sesión adicionales

El módulo de plugin y com_users ahora utilizan el evento onUserLoginButtons, definido y llamado en `Joomla\CMS\Helper\AuthenticationHelper::getLoginButtons`, para recuperar las definiciones de cualquier botón adicional que necesite colocarse después del botón de inicio de sesión regular.

Todos los desarrolladores que implementen un módulo de inicio de sesión o, de manera más general, un formulario de inicio de sesión, también deben utilizar el método público estático `Joomla\CMS\Helper\AuthenticationHelper::getLoginButtons` para recuperar dichas definiciones y renderizar estos botones para que su software sea totalmente compatible con Joomla 4.

Los desarrolladores que deseen implementar botones personalizados deben observar cómo el plugin del sistema WebAuthn implementa esta funcionalidad. Tales botones pueden usarse para implementar servicios de inicio de sesión único de terceros o incluso para iniciar sesión utilizando servicios de identidad de terceros como los que ofrecen las redes sociales populares (Facebook, Google, Twitter, GitHub, etc.).

Este cambio no afecta negativamente la compatibilidad con versiones anteriores. Los módulos de inicio de sesión y los formularios de inicio de sesión de terceros seguirán funcionando normalmente, incluso si no implementan la característica de botones de inicio de sesión adicionales, con la omisión notable de las integraciones proporcionadas por dicha característica, como la Autenticación Web en sí misma. Es decir, no dejarán de funcionar (lo cual sería una ruptura de compatibilidad), pero no estarán completamente equipados en cuanto a funciones.

### Permitiendo com_ajax en la página de inicio de sesión del backend

La página de inicio de sesión del Administrador incluye en la lista blanca com_ajax en AdministratorApplication para que pueda usarse para manejar solicitudes por parte de usuarios invitados.

Este cambio no causa problemas de compatibilidad hacia atrás siempre y cuando los desarrolladores usen prácticas razonables y no asuman que ser llamado por com_ajax en el backend es prueba de que el usuario ha iniciado sesión en el backend. Eso sería una mala práctica de seguridad. La práctica razonable es usar el objeto User de Joomla para detectar si es un usuario invitado y, si no lo es, si el usuario tiene permiso necesario para realizar la acción solicitada a través de com_ajax. Es decir, si este cambio ha roto tu código, entonces tu código ya estaba roto y necesitaba ser revisado de todos modos.

## Información adicional

La documentación inicial de esta función está en la solicitud de extracción en
[PR #28094](https://github.com/joomla/joomla-cms/pull/28094)

*Traducido por openai.com*

