<!-- Filename: J3.x:Updating_Joomla_(Update_Method) / Display title: Actualización de Joomla! (Método de Actualización) -->

Esta es el método de actualización recomendado de un sitio web del CMS
Joomla!.

Este además de ser el método recomendado, es el método más fácil para
actualizar el CMS Joomla!. A veces este método se conoce como un
**Actualización de un clic**. Si no puedes utilizar este método por
alguna situación en particular (distribuciones, idiomas, velocidad del
alojamiento web), puedes actualizar el CMS Joomla!, utilizando el
** método de
instalación**.

Este método es adecuado para

- Todos los CMS Joomla!, **3.x.x** a **3.x.x** - actualizaciones
  (actualización de mantenimiento)

Este método no es adecuado para

- Joomla CMS **3.1.2** a **≥ 3.1.3** - mira [Instrucciones Especiales
  para las Actualizaciones de la Versión
  3.1.2](https://docs.joomla.org/J3.x:Detailed_instructions_for_updating_from_3.1.2_to_3.1.4 "Special:MyLanguage/J3.x:Detailed instructions for updating from 3.1.2 to 3.1.4")

## Cómo Actualizar

¿Necesitas actualizar tu instalación de Joomla!? Si una actualización
está disponible, habrá un mensaje que indica una actualización con un
botón para realizarla.

<img
src="https://docs.joomla.org/images/thumb/a/af/J3-update-control-panel-notify-es.PNG/450px-J3-update-control-panel-notify-es.PNG"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/a/af/J3-update-control-panel-notify-es.PNG 1.5x"
data-file-width="643" data-file-height="383" width="450" height="268"
alt="J3-update-control-panel-notify-es.PNG" />

También verás un aviso en la parte inferior de la 'barra vertical de la
izquierda'.

<img
src="https://docs.joomla.org/images/a/a5/J3-update-control-panel-notify-alternative-es.PNG"
class="thumbborder" decoding="async" data-file-width="246"
data-file-height="256" width="246" height="256"
alt="J3-update-control-panel-notify-alternative-es.PNG" />

Joomla! te notificará en la página de inicio tu de Administrador (panel
de control) cuando haya una actualización disponible. Esta no se hace
automáticamente. Es responsabilidad del administrador para iniciarla y
verificar que la actualización se ha realizado correctamente.

Se recomiendan los siguientes pasos para completar una actualización de
una instalación del CMS Joomla.

### Paso 1: Copia De Seguridad

¡Asegúrate que tienes un **COPIA de seguridad ACTUALIZADA** de su sitio!
En muchos casos, tu alojamiento web hace, periódicamente, copias de
seguridad del sitio. ¡**NO** dependas de estas copias de seguridad! Se
**RECOMIENDA ENCARECIDAMENTE** que hagas tu propia copia de seguridad.

### Paso 2: El Componente de Actualización

Tendrás que navegar a actualización de componentes. Has clic en el
*botón* actualización o el 'enlace de la barra lateral' que se muestra
arriba o usa el menú principal, selecciona y has clic en
**Componentes **→** Actualización de Joomla!**. Ahora podrás ver una
imagen similar a la siguiente.

<img
src="https://docs.joomla.org/images/a/a0/J3-joomla-update-component-es.PNG"
class="thumbborder" decoding="async" data-file-width="1044"
data-file-height="528" width="1044" height="528"
alt="J3-joomla-update-component-es.PNG" />

Selecciona, 'Escribir archivos directamente' (predeterminado) o
'Escribir archivos a través de FTP" como el método de subir los nuevos
archivos del núcleo para su instalación. ¿Hiciste una copia de
seguridad? Consulta el Paso 1 anterior.

### Paso 3: Iniciar la Actualización

Has clic en el botón *Instalar la Actualización* y la actualización
comenzará.

<img
src="https://docs.joomla.org/images/6/66/J3-updating-your-joomla-files-es.PNG"
class="thumbborder" decoding="async" data-file-width="643"
data-file-height="270" width="643" height="270"
alt="J3-updating-your-joomla-files-es.PNG" />

Cuando la actualización se haya completado, verás un aviso de éxito, con
la nueva versión.

<img
src="https://docs.joomla.org/images/9/97/J3-jooml-update-successful-es.PNG"
class="thumbborder" decoding="async" data-file-width="670"
data-file-height="243" width="670" height="243"
alt="J3-jooml-update-successful-es.PNG" />

Cuando la actualización se haya completado, puedes necesitar vaciar la
caché del navegador para ajustar cualquier cambio CSS a las plantillas.

## Joomla Configuraciones de Actualización

En la mayoría de los casos, no tendrás que cambiar estas
configuraciones. Las opciones predeterminadas aseguran que la
instalación de tu CMS Joomla!, siempre comprueba si hay una correcta
actualización en el servidor y cuando ingresa la persona adecuada, con
acceso de administrador y que pueda actualizar la instalación.

A la pantalla de opciones se llega haciendo clic en el botón 'opciones'
en la pantalla principal de Actualización de Joomla! (arriba a la
derecha). Una vez que hagas clic en el botón 'opciones', verás la
siguiente imagen. También puedes acceder desde Configuración global
 **→**  Actualización de Joomla!

<img
src="https://docs.joomla.org/images/d/d0/J3-update-component-configure-server-es.PNG"
class="thumbborder" decoding="async" data-file-width="753"
data-file-height="513" width="753" height="513"
alt="J3-update-component-configure-server-es.PNG" />

### Configurar el Servidor de Actualización

El aviso de actualización que se ve en el inicio del administrador,
depende de la configuración del Servidor de Actualización y el
almacenamiento en caché.

<img
src="https://docs.joomla.org/images/2/2b/J3-update-component-configure-server-options-es.PNG"
class="thumbborder" decoding="async" data-file-width="466"
data-file-height="238" width="466" height="238"
alt="J3-update-component-configure-server-options-es.PNG" />

La primera opción muestra la última actualización de la versión mayor en
uso (valor predeterminado). La segunda opción muestra la última
actualización de la última mayor. El almacenamiento en caché puede
causar la no detección de una actualización disponible y debes purgar la
caché.

### Permisos

<img
src="https://docs.joomla.org/images/9/91/J3-update-component-configure-server-permissions-es.PNG"
class="thumbborder" decoding="async" data-file-width="787"
data-file-height="535" width="787" height="535"
alt="J3-update-component-configure-server-permissions-es.PNG" />
