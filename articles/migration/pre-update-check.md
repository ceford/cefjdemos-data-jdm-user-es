<!-- Filename: Pre-Update_Check / Display title: Comprobación de Pre-Actualización -->

La Comprobación de Pre-Actualización es nuevo para Joomla! 3.10.x. Esta
vista del componente de Actualización de Joomla muestra las
especificaciones técnicas del servidor en el que se encuentra el sitio,
y las extensiones principales y de terceros en forma de lista que
utilizan el servidor de actualización.

**To navigate to the Update-screen:**

- Click the 'Live Update' tab.

**Para navegar a la pantalla de Comprobación de Pre-Actualización:**

- Haga clic en el elemento de menú de la barra superior
  **Componentes **→** Actualización de Joomla!**.
- Si no ve la pantalla de Comprobación de Pre-Actualización, haga clic
  en el botón **Comprobar si hay actualizaciones** o borre la memoria
  caché y actualice la página.

## Especificaciones Técnicas

La parte superior de la Comprobación de Pre-Actualización muestra si el
entorno de servidor actual es compatible con la versión actual de
destino de Joomla, tanto para la configuración requerida de PHP, como
para la base de datos. Los datos de la página
<a href="https://downloads.joomla.org/es/technical-requirements-es"
class="external text" target="_blank"
rel="noreferrer noopener">Requisitos técnicos</a> muestran las
especificaciones que estamos comprobando.

<img
src="https://docs.joomla.org/images/c/cb/Php_and_database_settings-es.png"
class="thumbborder" decoding="async" data-file-width="800"
data-file-height="428" width="800" height="428"
alt="Requiere parte de los Ajustes de PHP y Base de Datos del componente de Comprobación de Pre-Actualización" />
<img
src="https://docs.joomla.org/images/4/43/Recommended_php_settings-es.png"
class="thumbborder" decoding="async" data-file-width="800"
data-file-height="307" width="800" height="307"
alt="Requiere parte de los Ajustes de PHP del Componente de Comprobación de Pre-Actualización" />

Lo importante es comprobar si algo está en rojo y no es compatible con
Joomla 4.x. Si es así, debe hablar con su proveedor de hosting o cambiar
de proveedor antes de migrar a Joomla 4.x. Durante una migración, es un
buen momento para cambiar de proveedor. Consulte  ¿Por qué
migrar?
para obtener más información sobre la planificación y las instrucciones
paso a paso.

## Comprobación de Pre-Actualización de Extensiones

Parte de la extensión del componente Comprobación de Pre-Actualización
extrae extensiones de terceros.

La lista está dividida en secciones según la etiqueta "targetplatform",
con las extensiones que están o no en uso. Para desarrolladores,
consulte  Implementación de un Servidor de
Actualización
para obtener más información sobre estas etiquetas y cómo implementar un
servidor de actualización. Para obtener más información sobre el sistema
de actualización de Joomla, consulte <a
href="https://extensions.joomla.org/support/knowledgebase/submission-requirements/joomla-update-system-requirement/"
class="external text" target="_blank" rel="noreferrer noopener">Joomla!
Update System Requirement</a> y <a
href="https://docs.joomla.org/Help39:Extensions_Extension_Manager_Update/es"
class="external text" target="_blank"
rel="noreferrer noopener">Actualizar Extensiones desde el Gestor de
Extensiones</a>.

Al hacer clic en el enlace **Más información** a la derecha en cada
título de color, puede ver la información adicional sobre las
extensiones instaladas en su sitio.

<img
src="https://docs.joomla.org/images/thumb/4/40/Pre_upgrade_checker_error-en.png/800px-Pre_upgrade_checker_error-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/thumb/4/40/Pre_upgrade_checker_error-en.png/1200px-Pre_upgrade_checker_error-en.png 1.5x, https://docs.joomla.org/images/thumb/4/40/Pre_upgrade_checker_error-en.png/1600px-Pre_upgrade_checker_error-en.png 2x"
data-file-width="1850" data-file-height="648" width="800" height="280"
alt="Información de actualización no disponible" />

Las extensiones enumeradas aquí aún no son compatibles con el sistema de
actualización de Joomla o, al menos, no tienen una etiqueta
targetplatform que indique compatibilidad con la versión de Joomla de
destino seleccionada. (consulte  Implementación de un Servidor de
Actualización.
Comunique con el desarrollador de las extensiones enumeradas para
asegurarse que sean compatibles con 4.x

<img
src="https://docs.joomla.org/images/2/21/Pre_upgrade_checker_warning-es.png"
class="thumbborder" decoding="async" data-file-width="800"
data-file-height="138" width="800" height="138"
alt="Actualización requerida" />

Las extensiones enumeradas aquí requieren una actualización para
funcionar correctamente en 4.x. Comunique con el desarrollador de las
extensiones enumeradas para asegurarse si debes actualizar el componente
antes o después de la actualización.

<img
src="https://docs.joomla.org/images/9/98/Pre_upgrade_checker_ok-es.png"
class="thumbborder" decoding="async" data-file-width="800"
data-file-height="250" width="800" height="250"
alt="No se necesita actualización" />

Las extensiones aquí enumeradas afirman ser compatibles con 4.x y no se
requiere su actualización.

## ¿De qué trata este *Problema Potencial de Actualización*

Los plugins del tipo ('system', 'user', 'authentication', 'actionlog',
'twofactorauth') podrían activarse mientras estamos procesando la
actualización. Cuando existe un problema crítico en estos plugins, puede
resultar una actualización rota e inutilizar el sitio. Por esta razón,
cualquier plugin de ese tipo que no esté explícitamente listado como
compatible, debe revisarse muy detenidamente antes de presionar el botón
de la actualización. Se recomienda **encarecidamente** deshabilitar los
plugins en cuestión y consultar con el desarrollador original.

<img
src="https://docs.joomla.org/images/thumb/1/1e/Pre_upgrade_checker_popup-en.png/200px-Pre_upgrade_checker_popup-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/1/1e/Pre_upgrade_checker_popup-en.png/300px-Pre_upgrade_checker_popup-en.png 1.5x, https://docs.joomla.org/images/thumb/1/1e/Pre_upgrade_checker_popup-en.png/400px-Pre_upgrade_checker_popup-en.png 2x"
data-file-width="492" data-file-height="446" width="200" height="181"
alt="The popup warning for potencial upgrade issue" />

En la pestaña *Actualización en vivo*, se ofrece nuevamente la lista
completa de extensiones de potencial ruptura.

<img
src="https://docs.joomla.org/images/thumb/b/b1/Live_upgrade_tab_errors-en.png/800px-Live_upgrade_tab_errors-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/thumb/b/b1/Live_upgrade_tab_errors-en.png/1200px-Live_upgrade_tab_errors-en.png 1.5x, https://docs.joomla.org/images/thumb/b/b1/Live_upgrade_tab_errors-en.png/1600px-Live_upgrade_tab_errors-en.png 2x"
data-file-width="2042" data-file-height="787" width="800" height="308"
alt="The Live Update message on potential breaking extensions" />

Se recomienda **encarecidamente** deshabilitar todas las extensiones,
incluidos los plugins enumerados aquí, antes de ejecutar la
actualización porque las extensiones aquí listadas parecen no ser
compatibles con la versión de destino, y podrían interrumpir su
actualización.

¿Sabe lo que está haciendo? Si desea optar por ignorar las advertencias
y ejecutar la actualización de todos modos, puede hacerlo marcando la
casilla de verificación. Ya que eso hace que su sitio corra el riesgo de
romperse sin una recuperación fácil, esta es la última advertencia para
recordarle que haga una copia de seguridad.

## Preguntas y Respuestas

Dividamos esto en algunas preguntas y respuestas.

**P: ¿Qué significan las etiquetas?**

R: La etiqueta verde **No se necesita actualización** significa que la
extensión ha sido etiquetada por el desarrollador como lista para Joomla
4. *Debería* migrar con un solo clic de 3.10.x a 4.x. Se sugiere
verificar con el desarrollador.

La etiqueta roja **Información de actualización no disponible**
significa que la extensión no ha agregado información de compatibilidad
con dicha extensión. Consulte con el desarrollador sobre el
procedimiento a seguir para la migración de 3.10.x a 4.x.

La etiqueta amarilla/naranja **Sí (x.x.x)** significa que la extensión
ha sido etiquetada por el desarrollador porque puede necesitar una
actualización para ser compatible con Joomla 4. Actualice la extensión y
observe si se convierte en un Sí verde. Si no es así, consulte con el
desarrollador sobre la ruta de migración de 3.10.x a 4.x.

La **Etiqueta de Compatibilidad Ausente** de color gris significa que la
extensión no tiene una etiqueta **o** no utiliza el servidor de
actualización. El desarrollador no ha dicho que sí o no o necesita una
actualización. En algunos casos, es posible que se haya instalado un
paquete y la parte del componente tenga una etiqueta, pero a los
complementos o módulos adicionales les faltan etiquetas. Como siempre,
deberá consultar con cada desarrollador de extensiones para verificar la
ruta de migración de 3.10.x a 4.x.

**P: ¿Qué pasa con los componentes del núcleo de Joomla?**

R: Las extensiones del núcleo de Joomla migrarán de 3.10.x a 4.x con un
solo clic, salvo estas excepciones:

Los paquetes de idioma aún no están listos para Joomla 4 (a partir de
septiembre de 2020). Con el tiempo, lo serán. Si su sitio depende de
otros paquetes de idiomas, espere a migrar hasta que todos los paquetes
de idiomas estén listos.

El componente Enlaces Web aún no está listo para Joomla 4 (a partir de
septiembre de 2020). Si va a continuar usando Enlaces Web en su sitio
Joomla 4, espere a migrar hasta que el componente de Enlaces Web esté
listo.

**P: ¿Qué sucede con las plantillas?**

R: Debido a los cambios en Joomla 4, su plantilla puede ser o no
compatible con Joomla 4. Las plantillas del núcleo como Protostar,
Beez3, Beez5, etc. se *convertirán* a la nueva plantilla Cassiopeia con
un solo clic, y las plantillas más antiguas se eliminarán por completo.
Si está utilizando una plantilla del club de un desarrollador externo
que no es compatible con Joomla 4, deberá cambiar su plantilla
predeterminada a Protostar (o Beez3) antes de hacer un clic. Si tiene
plantillas de administrador o plantillas principales más antiguas, se
recomienda desinstalarlas todas, excepto la que establezca como
predeterminada. Esto incluye Bluestork, Hathor y las otras plantillas de
beez. Mantenga a Isis como plantilla de administrador. Mantenga su
plantilla de terceros compatible, o bien Protostar o Beez3 como
predeterminada. Desinstale el resto.

**P: ¿Puedo desinstalar plg_content_geshi?**

A: Sí. Se trata de los restos del ciclo de vida de 2.5 y **debe** ser
desinstalado.

**P: ¿Qué hay acerca de FOF, fef, etc.?**

R: Muchas extensiones con los encabezados rojo o amarillo/naranja
**pasarán/puede que pasen** por un clic y migrarán correctamente. Se
recomienda que vaya a Extensiones→Gestionar→Gestionar y chequee todas
las extensiones. Por lo general, las creadas por Joomla migrarán con un
solo clic. Normalmente las extensiones de Akeeba también lo harán.
Nuevamente, consulte con los desarrolladores de extensiones para
verificar la ruta de migración de **todas** las extensiones de terceros.

'*P: ¿La Comprobación de Pre-Actualización de Extensiones muestra todas
las extensiones instaladas en mi sitio?'*

R: La Comprobación de Pre-Actualización mostrará todas las extensiones.
Solo las extensiones que utilizan el servidor de actualización reciben
información de compatibilidad. Aquellas extensiones que no utilicen el
servidor de actualización se mostrarán en la lista con la **Etiqueta de
Compatibilidad Ausente**.

## Resumen

Desde la perspectiva de migración, creemos que la Comprobación de
Pre-Actualización debe utilizarse como guía. Es recomendable tener una
segunda pestaña abierta con *Extensiones→Gestionar→Gestionar* para
desinstalar cualquier extensión o verificar quién es su autor, para que
pueda comunicarse con los desarrolladores de extensiones de terceros
dentro de la ruta de migración que ha establecido para migrar sus
extensiones.
