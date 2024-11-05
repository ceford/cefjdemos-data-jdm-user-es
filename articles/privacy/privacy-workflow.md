<!-- Filename: J4.x:Privacy_Workflow / Display title: Flujo de trabajo de privacidad  -->

## Creación de una Solicitud

Procesar solicitudes para obtener información personal es el principal propósito del componente de privacidad. Los usuarios pueden solicitar un resumen de sus datos personales o que se elimine toda su información personal. Una solicitud se puede crear ya sea por un usuario autenticado a través del formulario de solicitud o por un superusuario.

En este contexto, un usuario significa cualquier individuo u organización que haya realizado una solicitud, independientemente de si hay una cuenta de usuario registrada. Por ejemplo, las solicitudes pueden llegar al administrador del sitio de parte de individuos u organizaciones que han sido añadidos al sitio como contactos.

Los datos personales se basan en direcciones de correo electrónico y el procesamiento automatizado se limita a las extensiones que informan sobre capacidades de privacidad.

*IMPORTANTE* Para crear y procesar solicitudes de información, su sitio web DEBE poder enviar correos electrónicos debido a la necesidad de que el propietario de la información confirme la solicitud.

### Solicitud de Usuario Autenticado

Los usuarios registrados pueden enviar una solicitud de información a través de un enlace de menú de *Solicitud de Información de Privacidad* disponible solo después de iniciar sesión. Un buen lugar para dicho enlace es en el mismo menú donde hay un enlace a la **Política de Privacidad** del sitio. Un menú en la parte inferior del pie de página del sitio suele ser una ubicación preferida. Al enviar una solicitud de información, el usuario debe proporcionar:

- El tipo de solicitud: Exportar o Eliminar, seleccionado de la lista desplegable.

![flujo de trabajo de privacidad solicitud de usuario](../../../en/images/privacy/privacy-workflow-user-request.png)

Al enviar, un mensaje indicará ya sea que la solicitud ha sido aceptada y un correo de verificación está en camino:

![flujo de trabajo de privacidad solicitud de usuario aceptada](../../../en/images/privacy/privacy-workflow-user-request-accepted.png)

o que *No se pudo crear la solicitud de información. Ya hay una solicitud de información activa para esta dirección de correo electrónico y tipo de solicitud. Por favor contacta al propietario del sitio para obtener actualizaciones sobre esta solicitud.*

### Creación de Superusuario

A través de la página **Privacidad: Solicitudes de Información**, cualquier superusuario puede crear una nueva solicitud de información. Esta es la única forma de crear solicitudes de información para usuarios que NO tienen cuentas en el sitio web. Para crear una solicitud:

- Seleccione **Usuarios → Privacidad → Solicitudes** desde el menú del Administrador.
- Seleccione el botón **Nuevo** de la Barra de herramientas.
- En el campo **Correo Electrónico** ingrese la dirección de correo electrónico del usuario.
- En el campo **Tipo de Solicitud** seleccione Exportar o Eliminar de la lista desplegable.
- **Guardar y Cerrar**.

Una vez creada, la solicitud no puede ser editada. Solo puede ser Invalidada o Procesada.

## Confirmación de una Solicitud

Una vez que se ha creado una solicitud, independientemente de cómo se haya creado, el usuario recibirá un correo electrónico que contiene un enlace a un formulario de confirmación.

![flujo de trabajo de privacidad confirmación de solicitud de usuario](../../../en/images/privacy/privacy-workflow-user-request-confirm.png)

El usuario debe ingresar el token proporcionado en el correo electrónico y enviar el formulario. El token es válido por 24 horas. Si una solicitud no se confirma en ese plazo, la solicitud se marcará como **Inválida** en la lista de Solicitudes de Privacidad y se deberá enviar una nueva solicitud.

Una vez que el usuario confirma la solicitud, se enviará un correo electrónico a los Super Usuarios para indicar que se requiere una acción.

- Seleccione **Usuarios → Privacidad → Solicitudes** desde el menú del Administrador.
- Las solicitudes que requieren acción estarán marcadas como **Confirmadas**.

![lista de solicitudes de información del flujo de trabajo de privacidad](../../../en/images/privacy/privacy-workflow-information-requests-list.png)

## Procesamiento de una Solicitud de Exportación

Una vez que se ha confirmado una solicitud de exportación, hay dos acciones disponibles para los superusuarios.

- Exportar Datos: Esto recopilará todos los datos del sujeto de la solicitud de información y creará un archivo XML que se descargará en su computadora. Esto es útil para permitir que los propietarios del sitio revisen la exportación de datos antes de enviarla al usuario.
- Enviar por Correo Electrónico la Exportación de Datos: Esto recopilará todos los datos del sujeto de la solicitud de información, creará un archivo XML (el mismo generado por la acción Exportar Datos) y enviará un correo electrónico al usuario con el archivo de datos exportado adjunto.

**Importante:** La acción de exportación solo puede recopilar datos de extensiones que tengan soporte de privacidad. Por lo tanto, el superusuario que actúe en la solicitud debería revisar la exportación y, si es necesario, incluir los datos contenidos en extensiones que almacenen datos personales pero que no tengan soporte de privacidad.

## Procesamiento de una Solicitud de Eliminación

Una vez que se haya confirmado una solicitud de eliminación, solo hay una acción disponible para los superusuarios.

- Eliminar Datos: Este proceso anonimizará y/o eliminará los datos relacionados con el sujeto de la información. Para las solicitudes donde el propietario de la información también tiene una cuenta de usuario registrada, este proceso anonimizará el nombre de la cuenta, el nombre de usuario y la dirección de correo electrónico, así como bloqueará la cuenta para que no se pueda iniciar sesión y cerrará la sesión del usuario si están conectados en el momento en que se procesa la solicitud.

**Importante:** La acción de eliminación solo puede recopilar datos de extensiones que tienen soporte de privacidad. Por lo tanto, el superusuario que está actuando en la solicitud debe revisar la exportación y, si es necesario, anonimar o eliminar manualmente los datos contenidos en extensiones que almacenan datos personales pero no tienen soporte de privacidad.

Al seleccionar el botón **Eliminar Datos** hay un mensaje de confirmación de **Datos Eliminados** pero la lista de Solicitudes de Información de Privacidad no se modifica. Los datos del usuario se eliminan o anonimizan, pero no los datos en las tablas \#\_\_action_logs, \#\_\_messages y \#\_\_privacy_requests (ver más abajo).

## Finalizando una Solicitud

Una vez que la solicitud ha sido procesada, debe ser marcada como completada. Esto indicará que la solicitud ha sido cumplida y no hay más acciones que realizar.

- En la lista de **Privacidad: Solicitudes de Información**, selecciona la dirección de correo electrónico de la solicitud que se está procesando.
- En el formulario de **Privacidad: Revisar Solicitud de Información**:
  - Revisa los datos.
  - Selecciona el botón apropiado de **Exportar**, **Correo Electrónico** o **Eliminar** desde la barra de herramientas si no se ha hecho ya desde la vista de lista.
- Selecciona el botón de **Completar** de la barra de herramientas (o el botón de **Invalidar** si se considera que es una solicitud no válida).

![revisión de flujo de trabajo de privacidad de solicitud de información](../../../en/images/privacy/privacy-workflow-review-information-request.png)

## Finalmente

Para eliminar los datos del Registro de Acciones del Usuario:

- Seleccione **Usuarios → Registro de Acciones del Usuario** en el menú de Administrador.
- Busque el nombre de usuario o la dirección de correo electrónico del usuario eliminado.
- Marque la casilla **Seleccionar todos los elementos**.
- Seleccione el botón **Eliminar** en la barra de herramientas.

Para eliminar los datos de Mensajes Privados y los datos de Solicitud de Privacidad:

- No hay una manera fácil de eliminar en lote ninguno de estos tipos de datos
  desde Joomla. El método más rápido es buscar el Nombre de Usuario
  (dirección de correo electrónico) en la base de datos con phpMyAdmin y eliminar los registros
  allí. Aquí hay un ejemplo de captura de pantalla:

![flujo de privacidad eliminar con phpmyadmin](../../../en/images/privacy/privacy-workflow-delete-with-phpmyadmin.png)

## Recursos Adicionales

- [Guía del Desarrollador para el Conjunto de Herramientas de Privacidad](https://docs.joomla.org/Special:MyLanguage/J3.x:Integrate_Extensions_with_the_Privacy_Component)

*Traducido por openai.com*

