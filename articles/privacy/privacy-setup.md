<!-- Filename: J4.x:Privacy_Setup / Display title: Configuración de Privacidad  -->

## Componente de Privacidad

El Componente de Privacidad se utiliza para gestionar la información de privacidad y para recopilar solicitudes de información o solicitudes para eliminar información. Se basa en direcciones de correo electrónico, por lo que, obviamente, se aplica principalmente a los usuarios registrados que deben proporcionar una dirección de correo electrónico durante el registro. También se aplica a los datos de usuarios no registrados cuyas direcciones de correo electrónico fueron proporcionadas a través del componente de Contactos. No implementa el permiso para usar cookies o el seguimiento requerido por el RGPD.

Cuando se recopila información personal identificable, debes asegurarte de que:

- El usuario esté informado de por qué estás solicitando esta información en un lenguaje claro y fácil de entender.
- El usuario sepa qué datos recopilas sobre él.
- El usuario sepa para qué vas a utilizar los datos.
- El usuario haya otorgado activamente su consentimiento para el uso de los datos.

Normalmente, esta información se describe en un artículo de Política de Privacidad.

## Panel de Privacidad

El panel de privacidad proporciona un resumen de las **Solicitudes de Privacidad** y el **Estado de Privacidad** del sitio. Para acceder:

- Selecciona **Usuarios → Privacidad** desde el menú del Administrador.

![panel de privacidad](../../../en/images/privacy/privacy-dashboard.png)

Hay dos módulos que se muestran de forma predeterminada en el Panel de Privacidad:

### Solicitudes de Privacidad

Este módulo proporciona un resumen de las solicitudes de información actuales.

### Estado de Privacidad

Este módulo muestra el estado de las opciones a las que los propietarios del sitio deben atender:

- **Política de Privacidad Publicada** establece un artículo de Política de Privacidad en el
  complemento **Sistema - Consentimiento de Privacidad**.
- **Elemento de Menú de Formulario de Solicitud Publicado** establece un elemento de menú para permitir
  que los usuarios autenticados presenten solicitudes.
- **Solicitudes Urgentes Pendientes** verifica las solicitudes confirmadas que son más antiguas
  que la edad especificada en los parámetros del componente (por defecto 14 días)
  y alerta al propietario del sitio de cualquier solicitud que requiera atención urgente.
- **Envío de Correo Electrónico Habilitado** el sitio debe poder enviar correos electrónicos para
  procesar solicitudes de información.
- **Encriptación de Base de Datos** esto es relevante cuando se utiliza una base de datos remota.

## Complemento: Sistema - Consentimiento de Privacidad

Si este complemento está deshabilitado, el panel de Estado de Privacidad del Tablero mostrará que la Política de Privacidad está **No Disponible** y proporcionará un enlace al formulario de edición del complemento. Cuando está habilitado, el complemento solicita a cualquier nuevo usuario que se registre en su sitio que dé su consentimiento a la Política de Privacidad. Todos los usuarios existentes serán redirigidos a su perfil de usuario para que puedan dar su consentimiento.

Para configurar los consentimientos:

- Seleccione **Tablero de Inicio** → **Complementos** desde el menú de Administrador.
- Encuentre el complemento **Sistema - Consentimiento de Privacidad** (no confundir con el complemento Privacidad - Consentimientos).
- Seleccione para abrir el formulario de entrada de datos del complemento.

![plugin sistema consentimiento de privacidad](../../../en/images/privacy/plugin-system-privacy-consent.png)

- Establezca el **Estado** en **Habilitado**.
- Opcional: Seleccione o cree un artículo para enlazarlo desde el formulario de Registro. O configure el Tipo de Privacidad en Elemento de Menú y seleccione o cree un elemento de menú.
- Seleccione la pestaña **Expiración** y **Activa Ayuda en Línea** para obtener una explicación de cada campo. Habilite y ajuste los parámetros **si** desea que los consentimientos expiren después de un número seleccionado de días.

### Notas sobre el Consentimiento de Privacidad para sitios multilingües:

**Política de Privacidad Corta y Mensaje de Redirección** Si utiliza el texto predeterminado, se mostrará en el idioma del usuario. No es posible traducir el texto personalizado. Si desea personalizar el texto y mostrarlo en varios idiomas, debe dejar este campo en blanco y usar la función de anulación de idioma de Joomla para personalizar las cadenas de idioma `PLG_SYSTEM_PRIVACYCONSENT_NOTE_FIELD_DEFAULT` y `PLG_SYSTEM_PRIVACYCONSENT_REDIRECT_MESSAGE_DEFAULT` para cada idioma instalado.

**Artículo de Privacidad** y **Elemento de Menú de Privacidad** Si asocia este artículo o elemento de menú con alternativas en otros idiomas, entonces la política de privacidad se mostrará en el idioma correcto para el usuario.

## Plugin: Usuario - Términos y Condiciones

Cuando está habilitado, este plugin solicita a cualquier nuevo usuario que se registre en tu sitio que consienta los Términos y Condiciones para usar tu sitio. Todos los usuarios existentes serán redirigidos a su Perfil de Usuario para que puedan consentir.

Este plugin no está habilitado por defecto. Para habilitarlo:

- Selecciona **Tablero Principal → Plugins** desde el menú del Administrador.
- Encuentra el plugin **Usuario - Términos y Condiciones**.
- Selecciona para abrir el formulario de entrada de datos del plugin.
- Configura el **Estado** a **Habilitado**.
- Opcional: Selecciona o crea un artículo para enlazar desde el formulario de Registro.

### Notas sobre Usuario - Términos y Condiciones para sitios multilingües

**Términos y Condiciones Cortos** Si usas el texto por defecto, entonces se mostrará en el idioma del usuario. No es posible traducir el texto personalizado. Si deseas personalizar el texto y mostrarlo en múltiples idiomas, entonces debes dejar este campo en blanco y usar la función de sobrescritura de idioma de Joomla para personalizar las cadenas de idioma `PLG_USER_TERMS_NOTE_FIELD_DEFAULT` para cada idioma instalado.

**Artículo de Términos y Condiciones** Si asocias este artículo con alternativas en otros idiomas, entonces la política de privacidad se mostrará en el idioma correcto para el usuario.

## Vista de Consentimiento de Registro de Usuario

Juntos, los dos complementos aparecen en el formulario de Registro de Usuario como en la siguiente captura de pantalla:

![vista del sitio de consentimientos de privacidad](../../../en/images/privacy/privacy-consents-site.png)

## Elemento del Menú: Solicitud de Información de Privacidad

Los usuarios registrados pueden solicitar un resumen de información o su eliminación a través de un elemento de menú. Configúrelo de la siguiente manera:

- Seleccione **Menús** → **Menú Inferior** desde el menú del Administrador (utilice el menú que sea más conveniente).
- Ingrese un **Título** adecuado, por ejemplo: **Solicitud de Información de Privacidad**.
- Use el botón **Seleccionar** para abrir el cuadro de diálogo emergente de Tipo de Elemento de Menú.
- En la sección **Privacidad**, seleccione el elemento **Crear Solicitud**.
- Configure el campo **Acceso** como **Registrado**.
- **Guardar & Cerrar**.

Vaya a la vista de su sitio y verifique que el elemento de menú no se muestre cuando no ha iniciado sesión y que se muestre después de iniciar sesión. Use el enlace y pruebe la opción **Exportar**. Puede probar la opción **Eliminar** más tarde utilizando una cuenta de prueba. Si hay una solicitud pendiente, verá un mensaje de error:

“No se pudo crear su solicitud de información. Ya existe una solicitud de información activa para esta dirección de correo electrónico y tipo de solicitud. Por favor, contacte al propietario del sitio para obtener actualizaciones sobre esta solicitud.”

## Elemento del Menú: Confirmar Solicitud de Privacidad

Para propósitos de SEF, puedes crear un elemento de menú oculto para que el usuario confirme la solicitud. Este estará en el enlace enviado por correo electrónico.

- Selecciona **Menús**→**Menú Oculto** desde el menú del Administrador (crea un menú oculto sin posición de módulo asignada, o ver debajo).
- Introduce un **Título** adecuado, por ejemplo: **Confirmar Solicitud de Privacidad**.
- Usa el botón **Seleccionar** para abrir el cuadro de diálogo emergente de Tipo de Elemento de Menú.
- En la sección **Privacidad** selecciona el elemento **Confirmar Solicitud**.
- Si no tienes un Menú Oculto, utiliza tu menú principal y en la pestaña Tipo de Enlace, establece **Mostrar en Menú** en **No**.
- **Guardar y Cerrar**.

## Elementos del Menú de Administrador

Echa un vistazo a los otros elementos del menú del Componente de Privacidad.

### Solicitudes de Privacidad del Administrador

Esta pantalla es el lugar central para procesar y gestionar solicitudes de información de usuarios. Por favor, consulta el artículo relacionado sobre el Flujo de Trabajo de Privacidad para obtener orientación sobre cómo procesar las solicitudes.

![solicitudes de información de privacidad](../../../en/images/privacy/privacy-information-requests.png)

### Capacidades de Extensiones

Esta pantalla recopila y muestra información sobre las capacidades relacionadas con la privacidad reportadas por extensiones individuales. Está destinada a ayudar en la preparación de documentación, como un artículo de política de privacidad o un artículo de términos de servicio.

![capacidades de privacidad de extensiones](../../../en/images/privacy/privacy-extension-capabilities.png)

El contenido de la página proviene de cadenas de idioma en el núcleo, en el componente de privacidad y en plugins que implementan el evento onPrivacyCollectAdminCapabilities. Esto incluye:

- Autenticación
- Captcha
- Instalador
- Privacidad
- Sistema
- Usuario

La información se mostrará en el idioma seleccionado para el inicio de sesión del Administrador.

### Consentimientos

Esta pantalla muestra una lista de consentimientos, los más recientes primero. Estará en el idioma utilizado en el formulario de consentimiento, típicamente durante el registro. Puedes buscar por nombre a un usuario específico. Ten en cuenta que el consentimiento para aceptar los Términos y Condiciones del sitio no se registra aquí. Eso solo está en el Registro de Acciones de Usuario.

![consentimientos de privacidad](../../../en/images/privacy/privacy-consents.png)

*Traducido por openai.com*

