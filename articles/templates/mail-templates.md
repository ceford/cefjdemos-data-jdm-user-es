<!-- Filename: J5.x:Managing_Mail_Template_Layout / Display title: Plantillas de Correo -->

## Introducción

Las Plantillas de Correo se utilizan para enviar mensajes de correo del sistema en **texto plano** o **HTML** o ambos, seleccionados en el formulario de *Plantillas de Correo: Opciones*. Si solo se selecciona un método, la alternativa no estará presente en el formulario de edición del mensaje.

La siguiente captura de pantalla muestra una selección de las 26 plantillas de correo estándar disponibles. La lista está disponible seleccionando **Sistema -> Plantillas de Correo** desde el menú del Administrador.

![mail templates list](../../../en/images/templates/mail-templates-list.png)

Los mensajes de correo se pueden personalizar para modificar el diseño, la apariencia y el texto según las necesidades de su sitio. Por ejemplo, podría querer usar un logotipo del sitio y un esquema de colores en esos correos electrónicos enviados a los clientes. La personalización de los correos electrónicos enviados a los administradores es menos importante.

Existen dos métodos de personalización: a través de las *Opciones de Plantilla de Correo* para todas las plantillas de correo y a través de *Configuraciones de Correo por Plantilla*.

## Plantilla de Correo: Opciones

Seleccione el botón **Opciones** en la barra de herramientas de la lista *Plantillas de Correo* para acceder a la configuración general de plantillas de correo. Seleccione el botón *Alternar Ayuda en Línea* para ver si alguno de los campos del formulario tiene ayuda adicional.

![mail templates options](../../../en/images/templates/mail-templates-options.png)

### Formato de Correo

Tenga en cuenta que un destinatario puede configurar un cliente de correo para usar HTML simple o Texto Plano para evitar la descarga de imágenes. Por lo tanto, puede ser mejor configurar el *Formato de Correo* a *Texto Plano* o *Ambos*.

### Configuración de Correo por Plantilla

Si esto está configurado en **Sí**, los formularios de edición de plantillas de correo individuales tienen una pestaña adicional de *Opciones* que te permite cambiar la configuración de correo para esa plantilla y, opcionalmente, te permite enviar una copia (BCC) a una dirección de correo electrónico específica, siempre que el campo **Enviar copia** aquí también esté configurado en **Habilitado**.

## Formulario de Edición de Plantilla

En la lista de Plantillas de Correo puedes seleccionar cualquier plantilla para editar. El enlace del Título lleva al formulario de edición para la plantilla predeterminada en inglés. Cada bandera es un enlace a la misma plantilla en ese idioma.

### La pestaña Correo

![edit mail template form](../../../en/images/templates/mail-template-edit.png)

Los contenidos de las áreas de Asunto y Cuerpo se almacenan inicialmente en cadenas de texto en idioma. Esto facilita el *Restablecer Asunto Predeterminado* o *Cuerpo*. Sin embargo, una vez que se ha editado una plantilla de correo específica, sus campos de Asunto y Cuerpo se almacenan en la tabla `#__mail_templates`.

Los elementos entre llaves son etiquetas de marcadores de posición que se reemplazan por valores reales cuando se envía el correo electrónico. En el ejemplo anterior, `{SITENAME}` sería el nombre que elegiste para tu sitio. `{Method}` sería el método de transporte de correo seleccionado: `PHP Mail`, `Sendmail` o `SMTP`.

Las etiquetas de marcador de posición disponibles varían de correo a correo. Podrías agregar tus propias etiquetas de marcador de posición personalizadas, pero eso requiere un complemento personalizado, descrito en un [artículo de la revista](https://magazine.joomla.org/all-issues/february-2025/joomla-5-email-templates-how-to-add-variables-via-plugin) de febrero de 2025.

### La pestaña Opciones

Esta pestaña solo está presente si la opción de *Configuración de Correo por Plantilla* está establecida en *Sí* en *Plantillas de Correo: Opciones*. La ilustración a continuación muestra una captura de pantalla con *Configuración de Correo* establecida en *No*. Si se establece en *Sí*, aparecen más campos de formulario que anulan las opciones de Correo establecidas en la Configuración Global, pestaña Servidor.

![edit mail template form](../../../en/images/templates/mail-template-edit-options.png)

Si desea enviar una copia oculta de un correo electrónico saliente a una dirección de correo electrónico específica, puede ingresarla en el campo *Enviar copia a correo electrónico*.

## Anulaciones de Plantillas de Correo

Para crear una anulación de plantilla de correo dentro de una plantilla personalizada:

1. Ve a Sistema -> Plantillas del sitio -> Abre tu plantilla (por ejemplo, Cassiopeia).
2. En la pestaña Crear Sobrescrituras, selecciona joomla -> mail.
3. Joomla copiará el archivo `mailtemplate.php` al directorio `/html/layouts/joomla/mail/` de tu plantilla, donde podrás modificarlo según sea necesario.

Una vez que se crea la anulación, puedes ajustar el diseño y los estilos de tus correos electrónicos sin afectar la plantilla base.

## Lista de Plantillas de Correo

| Título | Extensión | Descripción |
|-------|-----------|-------------|
| Registro de Acciones de Usuario: Correo de Notificación | Registro de Acciones de Usuario | Correo enviado a los administradores sobre nuevas entradas en el Registro de Acciones de Usuario. |
| Configuración Global: Correo de Prueba | Configuración | Enviado cuando haces clic en el botón "Enviar Correo de Prueba" en la Configuración Global. Se envía a la dirección de correo de envío que está configurada en los ajustes de correo. |
| Contactos: Correo de Formulario de Contacto | Contactos | El correo del "Formulario de Contacto". |
| Contactos: Copia de Correo de Formulario de Contacto | Contactos | Enviado al remitente de un correo con el formulario de contacto si la opción "Enviar Copia al Remitente" está habilitada y seleccionada. |
| Mensajes: Nuevo mensaje | Mensajería | Correo electrónico que contiene un mensaje creado en el componente de mensajería. |
| Privacidad: Solicitud de Exportación de Datos (Admin) | Privacidad | Correo para informar al usuario que se ha creado una solicitud para exportar los datos de este sitio web por el administrador. |
| Privacidad: Solicitud de Eliminación de Datos (Admin) | Privacidad | Correo para informar al usuario que se ha creado una solicitud para eliminar los datos de este sitio web por el administrador. |
| Privacidad: Solicitud de Exportación de Datos | Privacidad | Correo para verificar que los datos de un usuario deben ser exportados del sitio web. |
| Privacidad: Solicitud de Eliminación de Datos | Privacidad | Correo para verificar que los datos de un usuario deben ser eliminados del sitio web. |
| Privacidad: Exportación de Datos del Usuario | Privacidad | Correo con la exportación de datos de usuario. |
| Usuarios: Correo Masivo a Usuarios | Usuarios | El correo de "Correo Masivo a Usuarios". |
| Usuarios: Restablecimiento de Contraseña | Usuarios | Enviado a un usuario por el enlace "¿Olvidaste tu contraseña?" por ejemplo, en un formulario de inicio de sesión. |
| Usuarios: Notificación de nueva cuenta al admin | Usuarios | Notificación al administrador de que se ha creado una nueva cuenta activada. |
| Usuarios: Solicitud al admin para verificar nueva cuenta | Usuarios | Notificación a los administradores para verificar una nueva cuenta verificada. |
| Usuarios: Cuenta activada por el admin | Usuarios | Notificación enviada al usuario de que la nueva cuenta ha sido activada por un administrador. |
| Usuarios: Nueva cuenta con activación por el admin | Usuarios | Notificación sobre nueva cuenta para el usuario, que ahora deberá ser activada por un administrador. |
| Usuarios: Nueva cuenta con activación por el admin (con PW) | Usuarios | Notificación sobre nueva cuenta para el usuario, que ahora deberá ser activada por un administrador. La contraseña en texto claro está incluida en el correo. |
| Usuarios: Nueva cuenta sin activación | Usuarios | Notificación sobre nueva cuenta para el usuario. La cuenta ya está activada. |
| Usuarios: Nueva cuenta sin activación (con PW) | Usuarios | Notificación sobre nueva cuenta para el usuario. La cuenta ya está activada. La contraseña en texto claro está incluida en el correo. |
| Usuarios: Nueva cuenta con autoactivación | Usuarios | Notificación sobre nueva cuenta para el usuario, que el usuario ahora deberá autoactivar. |
| Usuarios: Nueva cuenta con autoactivación (con PW) | Usuarios | Notificación sobre nueva cuenta para el usuario, que el usuario ahora deberá autoactivar. La contraseña en texto claro está incluida en el correo. |
| Usuarios: Recordatorio de Nombre de Usuario | Usuarios | Enviado a un usuario por el enlace "¿Olvidaste tu nombre de usuario?" por ejemplo, en un formulario de inicio de sesión. |
| Código enviado por correo | Autenticación Multifactor - Código de Autenticación por Correo | Enviado a usuarios desde la página de Autenticación Multifactor cuando se usa la opción "Código de Autenticación por Correo". |
| Tarea - Consentimiento de Privacidad: Renovar Consentimiento | Tarea - Consentimientos de Privacidad | Recordatorio para renovar el consentimiento de privacidad para este sitio web. |
| Joomla: Notificación de Actualización | Tarea - Notificación de Actualización de Joomla! | Enviado a los administradores del sitio cuando el plugin de tareas "Notificación de Actualización de Joomla!" detecta una actualización. |
| Usuarios: Nuevo Usuario | Usuario - Joomla! | Enviado a un nuevo usuario cuando es creado en el backend. |

*Traducido por openai.com*

