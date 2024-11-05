<!-- Filename: Help4.x:Components_Privacy_Outline / Display title: Esquema de Privacidad  -->

## Contenido

El conjunto de herramientas de privacidad de Joomla consta de las siguientes partes:

- **Componente de Administrador** Administra las solicitudes de privacidad de la información del usuario.
- **Módulo - Tablero de Privacidad** Coloca un panel de privacidad en el Tablero de Inicio.
- **Módulo - Solicitudes de Privacidad** Coloca un panel de Solicitudes de Privacidad en el
  Tablero de Privacidad.
- **Módulo - Estado de Privacidad** Coloca un panel de Estado de Privacidad en el
  Tablero de Privacidad.
- **Elemento de Menú - Crear Solicitud** Muestra un formulario para mostrar una
  Solicitud de Información. A ser creada.
- **Plugin - Sistema - Consentimiento de Privacidad** Añade campos de consentimiento a formularios de información personal como el de Registro. A ser habilitado.
- **Plugin - Usuario - Términos y Condiciones** Solicita el consentimiento del usuario a los términos y condiciones del sitio. A ser habilitado.
- **Plugin - Contenido - Confirmar Consentimiento** Añade una casilla de verificación requerida a un formulario, por ejemplo, el formulario de contacto principal. A ser habilitado.
- **Plugin - Privacidad - Varios** Más plugins, habilitados por defecto, sin parámetros significativos a configurar.

Al instalar el conjunto de herramientas de privacidad, está listo para su uso por parte del Administrador sin necesidad de habilitar plugins o crear un elemento de menú.

## Flujo de trabajo

Esta es una secuencia típica de eventos:

- Llega una solicitud de información. Debe incluir una dirección de correo electrónico válida para un Sujeto de datos. El Sujeto no tiene que ser un usuario registrado. Por ejemplo, el Sujeto puede ser un contacto añadido por un Administrador.
- Si el mensaje no es enviado por el Sujeto a través de un formulario de Información Personal del sitio:
  - El Administrador va a **Usuarios → Privacidad → Solicitudes → Nuevo** para crear una nueva solicitud de información. Se envía un mensaje a la dirección de correo electrónico proporcionada, invitando al Sujeto a confirmar que esta es una solicitud genuina.
- Si el mensaje es enviado a través de un formulario de Información Personal del sitio, al Sujeto se le envía automáticamente un mensaje de solicitud de confirmación.
- El Sujeto selecciona el enlace en el mensaje de correo electrónico para abrir el formulario de confirmación. Al enviarlo, el Sujeto ve un mensaje de confirmación.
- El Administrador ve que Mensajes Privados en la Barra de Títulos tiene mensajes pendientes. También habrá un mensaje de correo electrónico del sistema.
- El Administrador va a **Usuarios → Privacidad → Solicitudes** y ve que el estado de la solicitud ha cambiado a **Confirmado**.
- Para una solicitud de Exportación de datos hay botones de Exportar y Enviar por correo electrónico adyacentes.
  - El Administrador selecciona el botón Exportar para ver los datos que se van a exportar. Esto está en formato XML pero se muestra apropiadamente en Firefox.
  - El Administrador selecciona el botón Enviar por correo electrónico para enviar los datos exportados al Sujeto.
- Para una solicitud de Eliminación de datos hay un botón Eliminar adyacente.
  - El Administrador selecciona el botón eliminar para anonimizar los datos para el usuario. El usuario ya no puede iniciar sesión.
- Selecciona la dirección de correo electrónico del Sujeto de datos para abrir el formulario Revisar Solicitud de Información.
- Selecciona el botón Completar en la Barra de herramientas.
- La lista de Solicitudes de Información muestra el Estado como Completo y los botones de Acción han desaparecido.

Tenga en cuenta que este conjunto de aplicaciones no muestra un formulario de permisos de Cookies.

*Traducido por openai.com*

