<!-- Filename: J4.x:Site_Offline / Display title: Sitio Fuera de Línea  -->

## Solo Usuarios del Sitio

Puede haber ocasiones en las que necesite hacer que su sitio web Joomla!
esté temporalmente inaccesible para los visitantes. Hay un simple interruptor de configuración **Sitio Fuera de Línea** para este propósito, que se puede cambiar de **No** a **Sí** según se requiera. Cuando está configurado en *Sí*, todos los visitantes del sitio ven una página de mensaje de fuera de línea con un formulario de inicio de sesión. El formulario predeterminado de Fuera de Línea puede personalizarse con una imagen:

![Pantalla de sitio fuera de línea](../../../en/images/configuration/site-offline.png)

El interruptor de Sitio Fuera de Línea no se aplica a la interfaz de administrador y los usuarios que pueden iniciar sesión en el backend pueden seguir iniciando sesión en el frontend. El inicio de sesión en el frontend se niega solo a los usuarios en los grupos de usuario Registrado, Autor, Editor y Publicador.

## Para Activar/Desactivar Sin Conexión

- Selecciona **Tablero Principal → Configuración Global** desde el menú del Administrador.
- En la pestaña **Sitio**, coloca el interruptor **Sitio Sin Conexión** en **Sí**.
- Luego puedes elegir usar
  - **Usar Mensaje Personalizado**, que es el texto en el cuadro de Mensaje Personalizado. O...
  - **El Mensaje Predeterminado del Idioma del Sitio** que es **Este sitio está 
    fuera de servicio por mantenimiento. Por favor, vuelve a comprobar pronto.** 
    en inglés o su equivalente en el idioma seleccionado del sitio. Esto también
    permite seleccionar una imagen. O...
  - **Ocultar** para no mostrar ningún mensaje.
- Selecciona **Guardar y Cerrar** en la Barra de Herramientas.
- Realiza cualquier mantenimiento que sea necesario.
- Regresa al formulario de Configuración Global.
- Cambia el interruptor de Sitio Sin Conexión a **No**.
- Selecciona **Guardar y Cerrar** en la Barra de Herramientas.

## Todos los Usuarios

Puede limitar el acceso a su sitio web protegiendo con contraseña el directorio de Joomla. Solo los usuarios que conozcan el nombre de usuario y la contraseña de acceso al directorio podrán acceder al sitio. Puede configurar más de un usuario de este tipo. Con el Panel de Control de Alojamiento cPanel:

- Inicie sesión en su cuenta de cPanel.
- En la sección Archivos, seleccione **Privacidad de directorios**.
- Si la raíz de su sitio está en un subdirectorio de public_html
  - Seleccione el directorio public_html
- Seleccione el botón Editar para el directorio que contiene su sitio (public_html si su sitio está en la raíz web).
- Marque la casilla **Proteger con contraseña este directorio.**
- Ingrese un nombre para el directorio protegido: el predeterminado puede ser suficiente.
- Seleccione el botón **Guardar**.
- Habrá una página de mensaje de Éxito con un enlace Volver, seleccione ese enlace.
- Cree un usuario para acceder al directorio protegido.
- Ingrese un nombre de usuario.
- Ingrese una contraseña y repítala (recuerde o anote).
- Seleccione **Guardar**.

Ahora, verifique que el directorio requiera una contraseña para acceder desde la web. Cuando visite su sitio, se le solicitará su nombre de usuario y contraseña de acceso al directorio. Pueden ser completamente diferentes de su nombre de usuario y contraseña de Joomla.

Para eliminar la protección con contraseña del directorio:

- Inicie sesión en su cuenta de cPanel.
- En la sección Archivos, seleccione **Privacidad de directorios**.
- Si la raíz de su sitio está en un subdirectorio de public_html
  - Seleccione el directorio public_html
- Seleccione el botón **Editar** para el directorio que contiene su sitio (public_html si su sitio está en la raíz web). Ahora mostrará un símbolo de candado y Sí bajo el encabezado Privado.
- **Desmarque** la casilla **Proteger con contraseña este directorio.**
- Seleccione el botón **Guardar**.

Para verificar que la protección con contraseña ha sido eliminada, use un navegador diferente para acceder a su sitio o cierre y vuelva a abrir su navegador existente y luego acceda a su sitio nuevamente.

*Traducido por openai.com*

