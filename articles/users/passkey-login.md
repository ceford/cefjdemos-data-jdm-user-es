<!--
{
    "source": "https://docs.joomla.org/WebAuthn_Passwordless_Login",
    "title": "Inicio de sesi\u00f3n con clave de acceso",
    "description": " ",
    "author": ""
}
-->

## Introducción

El inicio de sesión con clave de acceso, anteriormente conocido como Autenticación web o WebAuthn para abreviar, permite a un usuario iniciar sesión de forma segura en un sitio sin utilizar una contraseña, aunque sigue siendo necesario un nombre de usuario. Utiliza criptografía robusta de una forma extremadamente resistente a los problemas más comunes de las contraseñas:

* alguien la adivinó (ataque de fuerza bruta)
* alguien la interceptó (ataque de intermediario)
* alguien le engañó para que la revelara (ataque de phishing)
* alguien la descifró después de obtener una copia de los datos de su base de datos (ataques de inyección SQL)
* alguien la robó.

El inicio de sesión con clave de acceso no solo es muy seguro; ¡también es muy fácil de usar! Ya no tiene que recordar contraseñas largas ni utilizar un gestor de contraseñas. Todo lo que necesita es un *autenticador*, a veces también llamado *clave de acceso*.

Un autenticador puede tener muchas formas, físicas o virtuales. Puede ser una llave de hardware independiente que se conecta a su dispositivo mediante USB, Bluetooth o NFC. Puede ser su propio dispositivo, que desbloquea su autenticador integrado mediante un PIN, un lector de huellas dactilares, un escaneo facial o una comprobación biométrica similar.

Esta función ya funciona en dispositivos Android e iOS/iPadOS y estamos trabajando para habilitarla también en Windows. Incluso puede ser su teléfono: actualmente esto es posible con teléfonos Android, pero esta función también llegará a dispositivos iOS/iPadOS.

El inicio de sesión con clave de acceso solo funciona mediante HTTPS y únicamente cuando su sitio utiliza un certificado válido y de confianza. No se preocupe, no tiene que gastar dinero adicional; los servicios gratuitos como Let's Encrypt suelen estar integrados en los paneles de control del alojamiento web y funcionan perfectamente con el inicio de sesión con clave de acceso.

El inicio de sesión con clave de acceso utiliza criptografía de clave pública, la misma tecnología probada que mantiene sus sitios seguros con HTTPS, protege su información bancaria y mucho más. La clave privada nunca sale del autenticador. Su sitio solo almacena una clave pública. Incluso si sufre una filtración de datos, el atacante se quedará con una clave pública prácticamente inútil; necesitaría miles o millones de años de CPU para descifrarla, en comparación con los pocos minutos u horas necesarios para descifrar el hash de una contraseña fija que pueda recordar.

El inicio de sesión con clave de acceso es el futuro de la autenticación. Fácil, seguro y sin complicaciones. Todo lo que no son las contraseñas fijas.

La siguiente imagen muestra un dispositivo de hardware insertado en el puerto USB de un ordenador portátil. Costó 15 £ en febrero de 2022.

![fotografía de un dispositivo de hardware](../../../en/images/users/passkey-login/01-hardware-device.jpg)

El inicio de sesión con clave de acceso utiliza un complemento del sistema que está habilitado de forma predeterminada. En las pantallas de inicio de sesión predeterminadas de Joomla 4 y posteriores aparecerá un botón **Iniciar sesión con clave de acceso**, como se muestra en la pantalla de inicio de sesión del administrador:

![formulario de inicio de sesión seguro del administrador](../../../en/images/users/passkey-login/02-login-form.png)

## Configuración del usuario

El usuario debe registrarse primero con un nombre de usuario y una contraseña normales. Después de iniciar sesión, vaya al formulario del perfil de usuario. Para un administrador:

- Seleccione **Menú de usuario → Editar cuenta → Inicio de sesión con clave de acceso** para ver el formulario, inicialmente sin autenticadores registrados.
- Seleccione **Añadir nueva clave de acceso**

La presentación exacta del siguiente paso depende de su navegador. Normalmente, verá una alerta, un mensaje o una ventana que le pedirá seleccionar un tipo de autenticador o, si está utilizando un autenticador de hardware conectado a su dispositivo, le recordará que pulse el botón del autenticador de hardware. Por motivos de seguridad y prácticos, el intervalo de tiempo permitido para activar el autenticador es relativamente corto: 60 segundos.

![aviso de hardware del inicio de sesión seguro del administrador](../../../en/images/users/passkey-login/03-hardware-prompt.png)

Una vez que desbloquee su autenticador —tocando un botón, escaneando su huella dactilar o rostro, introduciendo un PIN o una combinación de lo anterior, según su autenticador—, el mensaje desaparecerá, el autenticador se registrará y la pantalla aparecerá de la siguiente manera:

![autenticador registrado del inicio de sesión seguro del administrador](../../../en/images/users/passkey-login/04-registered-authenticator.png)

Es muy importante tener en cuenta que solo puede registrar o eliminar autenticadores en su propia cuenta de usuario. Por motivos de seguridad, ni siquiera un superusuario puede registrar, editar o añadir autenticadores en las cuentas de otros usuarios.

### Autenticadores

Puedes utilizar cualquier autenticador FIDO U2F o FIDO2. FIDO U2F es un estándar
más antiguo que admite una selección más limitada y menos segura de
métodos criptográficos. FIDO2 es el estándar más reciente, que admite métodos
criptográficos mucho más seguros, incluida la criptografía de curva elíptica,
un método criptográfico que se considera resistente incluso a la computación
cuántica (si algún día llega a convertirse en una realidad práctica). Además,
los autenticadores FIDO2 pueden configurarse para contar con protecciones
adicionales, como un PIN o un control biométrico (por ejemplo, un escaneo de
huella dactilar), lo que significa que, incluso si pierde la posesión física
del propio autenticador, quien lo encuentre no podrá iniciar sesión en sus
sitios.

Si está buscando comprar un autenticador de hardware, puede buscar
«FIDO2» en su tienda favorita, como Amazon. Hay una amplia
selección entre la que elegir.

También puede utilizar una clave FIDO de software, como Krypton, como
autenticador.

Muchos dispositivos cuentan con autenticación integrada compatible con FIDO2:

- Windows 10 y 11 incluyen Windows Hello con un PIN, un escáner de huellas dactilares,
  una cámara de reconocimiento facial o una combinación de clave de hardware y PIN.
- macOS incluye TouchID en todos los portátiles con el chipset T2 o basados en
  Apple Silicon que utilizan el sensor TouchID integrado, así como en todos los
  ordenadores de escritorio basados en Apple Silicon que utilizan el nuevo teclado
  Apple Aluminium con un escáner de huellas dactilares.
- iOS / iPadOS incluye TouchID en todos los dispositivos con un escáner de huellas dactilares
  y FaceID en todos los dispositivos más recientes con una cámara de proyección de puntos
  infrarrojos FaceID.
- Algunos dispositivos Android tienen un escáner de huellas dactilares o una
  cámara de reconocimiento facial. Estos también pueden funcionar como autenticadores
  FIDO2, en Android 9 o posterior utilizando al menos Google Chrome.
- También puede haber otros dispositivos disponibles. Por ejemplo, teléfonos Android que utilizan
  [caBLE](https://groups.google.com/a/fidoalliance.org/g/fido-dev/c/go6GoFW27Dw/m/9flCLR5pBQAJ?pli=1)

### Navegadores compatibles con el inicio de sesión mediante claves de acceso

En la práctica, si su sistema operativo y navegador se publicaron
después de mediados de 2020 no debería tener ningún problema. Solo algunos
navegadores muy poco comunes aún no son compatibles con el inicio de sesión mediante claves de acceso.

## Autenticación

Para iniciar sesión debe introducir su nombre de usuario en el campo Nombre de usuario
del formulario de inicio de sesión. No es necesario que introduzca su contraseña, pero si
su navegador la introduce por usted, simplemente déjela. La contraseña NO se envía
al servidor cuando el formulario se envía mediante el botón Autenticación web.

Por lo tanto, puede iniciar sesión con su nombre de usuario y contraseña o
con su nombre de usuario y una clave de acceso.

## Cómo deshabilitar el plugin

Si no desea permitir el inicio de sesión mediante claves de acceso, vaya a la lista de plugins,
busque el plugin **Sistema - Inicio de sesión mediante claves de acceso (sin contraseña)**
en el grupo Sistema y deshabilítelo. No hay parámetros que configurar.

## Requisitos del servidor

Para que funcione el inicio de sesión mediante claves de acceso, deben cumplirse las siguientes
condiciones previas:

- HTTPS con un certificado válido y firmado. La mayoría de los proveedores de alojamiento permiten utilizar certificados
  gratuitos emitidos por Let's Encrypt. Estos funcionan perfectamente
  con el inicio de sesión mediante claves de acceso.
- La extensión OpenSSL para PHP debe estar instalada y habilitada.
- La extensión GMP de PHP o la extensión BCmath de PHP deben estar instaladas
  y habilitadas (cualquiera de las dos sirve).
- Lo ideal es que la biblioteca Sodium esté habilitada; permite utilizar la
  criptografía de curva elíptica en autenticadores FIDO2 compatibles, que,
  como hemos dicho, es el método criptográfico más seguro.

## Preguntas frecuentes y solución de problemas

### No puedo ver el botón *Iniciar sesión con una clave de acceso*

No está accediendo a su sitio mediante HTTPS. El inicio de sesión mediante claves de acceso solo está disponible
para sitios HTTPS con un certificado válido. Esta es una precaución de seguridad
integrada en el estándar de inicio de sesión mediante claves de acceso. El plugin comprueba realmente si se
accede al sitio mediante HTTPS utilizando la clase Uri de Joomla. En casos excepcionales en los que el
servidor indique incorrectamente el protocolo, es posible que no vea el botón aunque
su sitio (afirme que) utiliza HTTPS. Lo mismo ocurre si ha editado el archivo
configuration.php y ha configurado el parámetro opcional \$live_site
con el prefijo de protocolo http:// en lugar de https://.

Tenga en cuenta también que los módulos y componentes de inicio de sesión de terceros que implementan
su propio formulario de inicio de sesión podrían no mostrar estos botones todavía. Añadimos
nueva infraestructura para admitirlos, de forma similar a lo que tuvimos que hacer en
Joomla! 3.2 para admitir la autenticación de dos factores.

### Todavía necesito proporcionar un nombre de usuario. ¿No se supone que el inicio de sesión con Passkey elimina los nombres de usuario?

En realidad, no. La especificación actual del inicio de sesión con Passkey no proporciona gestión de identidades. Los navegadores web requieren que les enviemos una lista de claves públicas de inicio de sesión con Passkey aceptables durante la fase de inicio de sesión. Esto significa que necesitamos su nombre de usuario para obtenerlas.

Dicho esto, el uso del inicio de sesión con Passkey deja claro por fin que los nombres de usuario *no deben considerarse secretos*. Se consideran información pública que puede transmitirse libremente a un adversario, al igual que las claves públicas almacenadas en la base de datos del sitio. El único secreto se almacena en el autenticador y nunca sale de él.

### He registrado un autenticador, pero al intentar iniciar sesión se me indica que no lo he hecho. ¿Es un error?

Es un error, pero no del propio complemento de inicio de sesión con Passkey.

Uno o más complementos de su sitio generan avisos, advertencias o errores de PHP, corrompiendo así la respuesta enviada por su servidor. Como resultado, el código JavaScript de la página no puede analizar la respuesta del servidor y no sabe con certeza si el usuario ha registrado algún autenticador.

Vaya al backend de su sitio, Sistema, Configuración global y establezca Informes de errores en Ninguno. En la mayoría de los casos de mal funcionamiento de los complementos del núcleo y de terceros, esto es suficiente. De lo contrario, examine el resultado de la solicitud mediante las herramientas de desarrollo de su navegador para ver qué está corrompiendo la solicitud.

### No aparece ninguna solicitud en Safari para usar mi autenticador

Esto ya no debería ocurrir con iOS 13, iPadOS 13 y macOS Catalina, ni con ninguna versión posterior.

Se trata de un error de Safari en versiones anteriores de Safari. Las versiones anteriores de Safari solo incluían compatibilidad con el inicio de sesión con Passkey como función experimental y no estaba completamente terminada.

### No puedo usar un sensor biométrico (TouchID, huella dactilar, Windows Hello)

Algunos navegadores antiguos basados en Chromium (excepto el propio Google Chrome) no tenían compatibilidad completa con los autenticadores integrados. Se bloqueaban o dejaban de responder al intentar utilizar uno. Estos problemas se solucionaron en dichos navegadores aproximadamente a mediados de 2020.

Si utiliza Windows, recuerde que su dispositivo DEBE tener un chip de módulo de plataforma segura (TPM), y este debe estar habilitado en la BIOS. Disponer únicamente de un sensor biométrico compatible con Windows Hello no será suficiente. Se trata de una medida de seguridad del propio estándar de inicio de sesión con Passkey: la información del autenticador debe procesarse mediante hardware seguro y resistente a manipulaciones para evitar la subversión de claves (por ejemplo, que un programa malicioso ejecutándose en el ordenador pueda robar la clave utilizada para la autenticación).

Por último, tenga en cuenta que la compatibilidad con Windows Hello todavía está en desarrollo y se publicará con Joomla 4.2.

### Si puedo usar un autenticador de software, ¿por qué debería usar un token de hardware?

El elemento clave del inicio de sesión con Passkey es el secreto absoluto de la clave privada. Solo el autenticador debe conocerla y debería ser imposible comunicarla al mundo exterior.

En el caso de un autenticador de hardware, ya sea un dispositivo de hardware independiente o un TPM / Secure Enclave integrado en el dispositivo, esto está garantizado por la propia naturaleza de dicho hardware.

Un autenticador de software genera una clave secreta y la almacena en el sistema de archivos. Sin embargo, sigue siendo una aplicación de software normal que se ejecuta dentro del sistema operativo habitual, ya sea el del teléfono o el del ordenador. Como resultado, es susceptible a varias clases de ataques que pueden utilizarse para robar información subrepticiamente (problemas de seguridad en el propio software, programas maliciosos que aprovechan vulnerabilidades de la clase Spectre en las CPU modernas, etc.).

Por tanto, un autenticador de software es mucho más práctico y seguro que una contraseña normal, pero un autenticador de hardware ofrece la máxima seguridad. Elija su autenticador en función de su presupuesto y sus necesidades de seguridad.

Teniendo en cuenta que el precio de una clave FIDO (compatible con el inicio de sesión con Passkey) es inferior a 20 € en Amazon, puede utilizar un autenticador de hardware en la mayoría de los casos prácticos.

### ¿Por qué están cifradas las credenciales en la base de datos? ¿No es esto exagerado?

Lo único que se almacena en la base de datos es la clave pública devuelta por el autenticador cuando realizamos la ceremonia de atestación (ese es el nombre formal de registrar un autenticador según la especificación de inicio de sesión con Passkey). Al ser una clave pública, no es necesario protegerla contra la lectura. Incluso si un usuario no autorizado pudiera leer esta información, no podría suplantar al autenticador, por ejemplo, clonándolo.

Sin embargo, si un usuario malintencionado tuviera acceso de escritura únicamente a la tabla `#__webauthn_credentials` de la base de datos, sin acceso de lectura al sistema de archivos y sin acceso de escritura a ninguna otra tabla, podría **añadir** su propio autenticador y, por lo tanto, suplantar al usuario objetivo en el sistema. Este es un ataque muy teórico, ya que también necesitaría conocer el identificador del usuario al que está atacando, algo que es más difícil de deducir sin ciertos conocimientos internos del propio sitio. Además, es extremadamente improbable tener acceso de escritura únicamente a esta tabla y no a toda la base de datos (en cuyo caso podría crear un nuevo superusuario). Aun así, ciframos las credenciales para hacer imposible que incluso este ataque completamente teórico tenga éxito.

Somos plenamente conscientes de que, si un usuario tiene acceso de lectura al sistema de archivos del servidor, tiene acceso a la clave de cifrado y a la información de conexión de la base de datos, todo lo cual se almacena en configuration.php. Sin embargo, en este caso ya has sido hackeado: el atacante puede leer configuration.php y, por lo tanto, sabe cómo conectarse a tu base de datos. En este caso puede hacer lo que quiera en tu sitio, incluyendo eliminar todos los superusuarios existentes y crear su propia cuenta de superusuario. Por lo tanto, no hay razón para intentar solucionar esta situación; tu sitio estaría completamente comprometido (hackeado). Lo único que podría salvarte son las copias de seguridad periódicas, probadas y almacenadas fuera del sitio.

### He configurado la autenticación de dos factores, pero he iniciado sesión sin proporcionar mi clave secreta. ¿No es esto inseguro?

No, es intencionado y forma parte del diseño.

Cuando añadimos la autenticación de dos factores (TFA) en Joomla! 3.2, solo era posible iniciar sesión en el sitio utilizando un nombre de usuario y una contraseña. Las contraseñas pueden ser robadas o adivinadas. Por lo tanto, la TFA era la única forma de proporcionar un nivel mínimo de seguridad en objetivos de alto riesgo y gran valor. Eso fue en 2013.

El inicio de sesión con Passkey es una solución de autenticación completamente diferente que no presenta ninguno de los problemas de las contraseñas fijas. Utiliza criptografía sólida y hardware seguro para hacer prácticamente imposible subvertir las claves criptográficas de autenticación. También es resistente al phishing, es decir, no pueden engañarte para que la utilices en un sitio que suplanta al original, ya que la credencial de inicio de sesión con Passkey está vinculada al nombre de dominio exacto para el que se emitió (sí, si utilizas varios dominios para tu sitio o transfieres tu sitio a otro dominio, tendrás que volver a registrar todos tus autenticadores de inicio de sesión con Passkey; ¡lo has entendido bien!). Como resultado, la autenticación con el inicio de sesión con Passkey es increíblemente segura y supera las razones que hicieron necesaria la TFA. Esto significa que, si te autenticas correctamente utilizando el inicio de sesión con Passkey, no es necesario comprobar la clave secreta de TFA y, por lo tanto, no se comprueba en absoluto.

En un mundo ideal, solo podrías iniciar sesión en tu sitio utilizando el inicio de sesión con Passkey. Esta es una función en la que estamos trabajando y quizá no quieras activarla; después de todo, si cambia tu nombre de dominio o pierdes el acceso a todos tus autenticadores de inicio de sesión con Passkey o los restableces, no podrías acceder a tu sitio. Por lo tanto, aún deberías activar la TFA en tu cuenta de usuario, teniendo en cuenta que el inicio de sesión mediante contraseña todavía puede utilizarse como alternativa para iniciar sesión en tu sitio y debe protegerse contra los ataques conocidos dirigidos a las contraseñas fijas.

### ¿No es suficiente la TFA? ¿Por qué necesitamos el inicio de sesión con clave de acceso?

La TFA por sí sola es suficiente en la mayoría de los casos, pero presenta dos problemas.

En primer lugar, ofrece una experiencia de usuario bastante incómoda. Es necesario proporcionar la clave secreta que cambia constantemente junto con el nombre de usuario y la contraseña. La mayoría de las personas usan TOTP (el PIN de seis dígitos que cambia cada 30 segundos), lo que ralentiza el inicio de sesión y tiende a frustrar a los usuarios. Usar una YubiKey es mucho más rápido, pero también es más caro y complicado de aprovisionar cuando hay más de un par de usuarios en el sitio. Una YubiKey también tiene una vida útil prevista de unos 2 años de uso diario al generar contraseñas de un solo uso (se queda sin la memoria de escritura única que utiliza para llevar un registro de las firmas que ha emitido).

En segundo lugar, si usa TOTP, sigue siendo susceptible a problemas de seguridad como los registradores de teclas, el phishing y la posibilidad de que roben la clave secreta utilizada para generar el TOTP. Además, con un millón de posibilidades y treinta segundos para intentarlo, es concebible que un atacante tenga suerte, ya que Joomla no bloquea su cuenta ni emplea ningún tipo de limitación de frecuencia para los intentos de inicio de sesión fallidos. Aunque estas protecciones podrían implementarse, la propia implementación podría utilizarse de forma abusiva para crear una situación de denegación de servicio que bloquee a un usuario legítimo fuera de su sitio mientras el atacante está ocupado infiltrándose en él. Es un caso en el que el remedio es peor que la enfermedad.

El inicio de sesión con clave de acceso mejora enormemente la experiencia de usuario. Los principales navegadores han adoptado el inicio de sesión con clave de acceso y ofrecen una experiencia de usuario convincente, guiando a los usuarios para que utilicen correctamente los autenticadores. Iniciar sesión con una clave de acceso es más cómodo incluso en comparación con utilizar la función de autocompletado de un gestor de contraseñas. Con las versiones recientes de los sistemas operativos móviles, incluso esa experiencia, que antes resultaba un poco confusa, se está volviendo rápidamente más sencilla que las contraseñas y la TFA.

Donde el inicio de sesión con clave de acceso realmente destaca es en el ámbito de la seguridad. Gracias al uso de hardware seguro y a la sólida validación del nombre de dominio del sitio, es prácticamente inmune a los registradores de teclas, el phishing y la subversión de claves. Incluso cuenta con protección integrada contra la clonación de claves. Sí, todavía puede perder su hardware, pero los autenticadores FIDO2, ya sean dispositivos externos o integrados, pueden bloquearse con un PIN o datos biométricos. En general, usar el inicio de sesión con clave de acceso con autenticadores FIDO2 ofrece mayor resistencia al robo y la pérdida que las llaves de su casa o de su coche.

## Notas para desarrolladores

### Botones de inicio de sesión adicionales

El módulo del complemento y com_users ahora utilizan el evento onUserLoginButtons,
definido y llamado en
`Joomla\CMS\Helper\AuthenticationHelper::getLoginButtons`, para recuperar las
definiciones de cualquier botón adicional que deba colocarse después del
botón de inicio de sesión normal.

Todos los desarrolladores que implementen un módulo de inicio de sesión o, más generalmente, un formulario de inicio de sesión, también deberían utilizar el método estático público
`Joomla\CMS\Helper\AuthenticationHelper::getLoginButtons` para recuperar dichas definiciones y representar estos botones, a fin de que su
software sea totalmente compatible con Joomla 4.

Los desarrolladores que deseen implementar botones personalizados deberían consultar cómo el complemento del sistema de inicio de sesión con clave de acceso implementa esta funcionalidad. Estos botones pueden utilizarse para implementar servicios de inicio de sesión único de terceros o incluso para iniciar sesión mediante servicios de identidad de terceros, como los ofrecidos por redes sociales populares (Facebook, Google, Twitter, GitHub, etc.).

Este cambio no afecta negativamente a la compatibilidad con versiones anteriores. Los módulos y formularios de inicio de sesión de terceros seguirán funcionando con normalidad aunque no implementen la función de botones de inicio de sesión adicionales, con la omisión destacable de las integraciones proporcionadas por dicha función, como la propia Autenticación web. Es decir, no dejarán de funcionar (lo que supondría una ruptura de compatibilidad), pero no tendrán todas las funcionalidades.

### Permitir com_ajax en la página de inicio de sesión del backend

La página de inicio de sesión del administrador incluye com_ajax en la lista blanca de
AdministratorApplication, por lo que puede utilizarse para gestionar solicitudes de usuarios invitados.

Este cambio no causa problemas de compatibilidad con versiones anteriores siempre que
los desarrolladores utilicen prácticas sensatas y no supongan que ser invocado mediante
com_ajax en el backend demuestra que el usuario ha iniciado sesión en el backend. Eso sería una mala práctica de seguridad. La práctica adecuada es utilizar el objeto User de Joomla para detectar si se trata de un usuario invitado y, si no lo es, comprobar si el usuario tiene permitido el permiso necesario para ejecutar la acción solicitada mediante com_ajax. Es decir, si este cambio ha roto su código, su código ya estaba roto y, de todos modos, necesitaba ser revisado.

## Información adicional

La documentación inicial de esta función se encuentra en la solicitud de incorporación de cambios
[PR #28094](https://github.com/joomla/joomla-cms/pull/28094)

*Traducido por openai.com*