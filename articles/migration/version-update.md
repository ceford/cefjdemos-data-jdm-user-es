<!-- Filename: J4.x:Updating_from_an_existing_version / Display title: Actualización de Versión  -->

## Introducción

**Recuerda: Siempre haz una copia de seguridad de tu sitio antes de actualizar.**

La forma recomendada para actualizar las instalaciones de Joomla! es utilizar el *Componente de Actualización de Joomla*.

Una instalación estándar de Joomla 4 y posteriores incluye un panel de notificaciones útil en el Tablero Principal después de iniciar sesión. Puedes ver de un vistazo si hay una actualización disponible y el número de versión.

El mensaje de actualización que aparece en el panel de notificaciones depende del *Canal de Actualización* configurado en la página *Opciones de Actualización de Joomla* y la versión *Menor* actual. Con el **Canal de Actualización** configurado en **Predeterminado**, se notifican actualizaciones dentro de la versión *Mayor* actual. Con el parámetro configurado en *Joomla Siguiente*, puedes actualizar a la última versión actual y luego seleccionar el botón **Buscar Actualizaciones** para ver si la siguiente versión *Mayor* está disponible.

Aunque Joomla te notificará cuando haya una actualización disponible, requiere que tú realices la actualización. Es un proceso simple que debe realizarse lo antes posible para mantener el sitio actualizado.

## Acceder al Componente de Actualización

Si el panel de notificaciones se muestra en el Panel de Inicio, selecciona el botón **x.y.z Disponible - ¡Actualizar Ahora!** para ir al Componente de Actualización.

![notificación de actualización de joomla en el panel de inicio](../../../en/images/migration/version-update-notification-home-dashboard.png)

Alternativamente, para acceder al Componente de Actualización desde el menú de Administración, selecciona **Sistema** para ir a través del **Panel del Sistema**.

![notificación de actualización de joomla en el panel del sistema](../../../en/images/migration/version-update-notification-system-dashboard.png)

El Panel del Sistema tiene un *Panel de Actualización* que incluye un enlace de Joomla que mostrará el número de versión de actualización disponible. Selecciona el enlace **Joomla** para ir al Componente de Actualización.

## Realización de la Actualización

¡Joomla! 4 y 5 ofrecen una Verificación Previa a la Actualización para actualizaciones a versiones menores. Esta vista del componente de Actualización de Joomla muestra especificaciones técnicas del servidor en el que se encuentra el sitio y extensiones del núcleo y de terceros que utilizan el Servidor de Actualización en forma de lista.

**Nota:** La pantalla de *Verificación Previa a la Actualización* no se muestra si el sitio está en la versión **Menor** actual.

![verificación previa a la actualización de joomla](../../../en/images/migration/version-update-pre-update-check.png)

Preste mucha atención a los resultados de la verificación y tome medidas para rectificar cualquier problema resaltado antes de actualizar. Es posible que necesite actualizar, deshabilitar o desinstalar extensiones incompatibles antes de actualizar Joomla.

No es raro ver advertencias para *Configuraciones Recomendadas* ya que a menudo son específicas del servidor y relacionadas con el alojamiento. Es probable que existieran cuando instaló Joomla y lo más probable es que no impedirán que se complete la actualización.

*¡Tenga en cuenta el recordatorio de que se recomienda encarecidamente hacer una copia de seguridad si aún no lo ha hecho!*

Hay un enlace debajo del botón de actualización. En la mayoría de los casos, puede ignorar este enlace. Proporciona una opción para cargar manualmente los archivos de actualización si su servidor está detrás de un cortafuegos o no puede contactar con los servidores de actualización de Joomla.

Cuando haya revisado la Verificación Previa a la Actualización y esté satisfecho, seleccione **Actualizar**.

### Confirmando la Actualización

![página de inicio de actualización](../../../en/images/migration/version-update-start-update.png)

Marque la casilla para confirmar que ha realizado una copia de seguridad y comprobado que las extensiones son compatibles, luego haga clic en **Iniciar Actualización**.

### Progreso de la Actualización

![página de progreso de actualización](../../../en/images/migration/version-update-progress.png)

Una vez que la actualización comienza, aparecerá una barra de progreso mientras se actualizan los archivos de Joomla.

### Finalización

![página de actualización completada](../../../en/images/migration/version-update-completion.png)

Cuando la barra de progreso alcance el 100%, un mensaje del sistema confirmará que su sitio ha sido actualizado y mostrará el número de versión. El número de versión también se actualizará en la barra de herramientas superior, junto al nombre del sitio.

Haga clic en el botón **Atrás** y volverá al Componente de Actualización de Joomla, donde es posible verificar actualizaciones nuevamente.

## Comprobaciones después de la actualización

Una vez que la actualización esté completa, debes realizar algunas comprobaciones para asegurarte de que todo salió como se esperaba, que no hay errores presentes y que no ha habido cambios que requieran acciones adicionales.

### Comprobación del Frontend

Dirígete al frontend del sitio web y verifica que funcione y se muestre como lo hacía antes de la actualización. Utiliza la combinación *Shift + Recargar* para forzar a tu navegador a recargar cualquier cambio en las hojas de estilo y scripts.

### Comprobaciones del Sistema

Desde el menú lateral, selecciona **Sistema** para dirigirte al Panel de Control del Sistema. Esto te dará una visión general del estado actual de tu sitio Joomla.

![panel de control del sistema post actualización](../../../en/images/migration/version-update-after-update.png)

En este ejemplo, podemos ver que desde la actualización tenemos dos elementos que requieren atención. Están marcados con una etiqueta que incluye un número. El número indica cuántos elementos requieren atención. Al hacer clic en cada uno de ellos, podrás solucionarlos.

**Nota:** El Panel de Control del Sistema realiza una verificación cada vez que se carga la página. Ten en cuenta que la configuración de caché del navegador podría afectar esto. Es buena práctica limpiar la caché del navegador al verificar utilizando *Shift + Recargar*.

### Comprobación de la Base de Datos

Navega a **Sistema → Mantenimiento → Base de Datos**. Si tu base de datos está actualizada, deberías ver una pantalla similar a la siguiente:

![comprobación de la base de datos post actualización sin problemas](../../../en/images/migration/version-update-after-update-database-check-no-problems.png)

Si tu base de datos no está actualizada, verás una pantalla que enumera los problemas encontrados, similar a la siguiente:

![comprobación de la base de datos post actualización con problemas](../../../en/images/migration/version-update-after-update-database-check-problems.png)

En este caso, selecciona el *Nombre* de la extensión con problema y luego el botón de Actualizar Estructura en la Barra de Herramientas. Joomla actualizará tu base de datos para corregir los problemas enumerados y luego volverá a mostrar la pantalla. Si la corrección fue exitosa, la pantalla indicará que la base de datos está actualizada.

**Nota:** Si aún existen errores, asegúrate de que todas las tablas de la base de datos estén seleccionadas.

## Descubrir Sistema

En algunos casos, cuando actualizas a una nueva versión de Joomla, se añaden nuevas extensiones principales. Si hubo problemas con la actualización de la base de datos, es posible que estas extensiones no se hayan instalado correctamente. Para verificar esto, navega a **Sistema → Descubrir**. Luego selecciona el icono de Descubrir en la barra de herramientas. La pantalla debería mostrarse de la siguiente manera:

![Pantalla de Descubrir Sin Extensiones Para Instalar](../../../en/images/migration/version-update-after-update-discover.png)

Si es así, sabes que cualquier nueva extensión añadida durante la actualización se instaló correctamente en la base de datos.

Si hay extensiones no instaladas, se mostrarán de manera similar a la siguiente pantalla:

![Pantalla de Descubrir Con Extensiones Encontradas Para Instalar](../../../en/images/migration/version-update-after-update-discover-found.png)

En este caso, marca las casillas y haz clic en el icono de Instalar en la barra de herramientas. Joomla instalará la(s) extensión(es) y luego mostrará la pantalla indicando que no se descubrieron extensiones. En este punto, las nuevas extensiones se han instalado en la base de datos.

## Solución de problemas

Si tienes alguna pregunta, problema o error antes, durante o después
de la actualización, por favor pregunta en el
[Foro de Migración y Actualización a Joomla! 4.x](https://forum.joomla.org/viewforum.php?f=812).

Si tienes problemas o errores durante el proceso de actualización, aquí hay algunos
consejos:

- Limpia la caché de tu navegador. Puede haber cambios en el CSS o
  JavaScript que necesitarán ser recargados por tu navegador web después de una
  actualización.
- Si después de la actualización aparecen mensajes de error de base de datos, asegúrate de revisar
  el enlace **Sistema → Panel de Mantenimiento → Base de Datos**. En algunos
  casos, si ocurre un error en la base de datos, impedirá que se ejecuten todas las actualizaciones de la base de datos. En este caso, puedes ejecutarlas desde el enlace de Base de Datos y luego usar el método **Sistema → Instalar → Descubrir** para verificar e instalar cualquier extensión nueva.
- El proceso de actualización crea o agrega a un archivo de registro llamado
administrator/logs/joomla_update.php que puedes abrir con un editor de texto para
ver los pasos registrados en el log. Mostrará los pasos principales (descargar zip,
instalar, ejecutar sentencias SQL, limpiar), algo así:

```
2024-04-17T09:13:16+00:00    INFO 127.0.0.1    update    Actualización iniciada por el usuario Jimmy (139). La versión antigua es 5.0.3.
2024-04-17T09:13:18+00:00    INFO 127.0.0.1    update    Descargando el archivo de actualización desde...
2024-04-17T09:13:28+00:00    INFO 127.0.0.1    update    Archivo Joomla_5.1.0-Stable-Update_Package.zip descargado.
2024-04-17T09:13:28+00:00    INFO 127.0.0.1    update    Comenzando la instalación de la nueva versión.
2024-04-17T09:13:40+00:00    INFO 127.0.0.1    update    Finalizando instalación.
2024-04-17T09:13:40+00:00    INFO 127.0.0.1    update    Inicio de actualizaciones SQL.
2024-04-17T09:13:40+00:00    INFO 127.0.0.1    update    La versión actual de la base de datos (esquema) es 5.0.0-2023-09-11.
... Muchas consultas SQL individuales
2024-04-17T09:13:41+00:00    INFO 127.0.0.1    update    Fin de las actualizaciones SQL.
2024-04-17T09:13:41+00:00    INFO 127.0.0.1    update    Desinstalando extensiones
2024-04-17T09:13:41+00:00    INFO 127.0.0.1    update    Eliminando archivos y carpetas eliminados.
2024-04-17T09:13:44+00:00    INFO 127.0.0.1    update    Limpiando después de la instalación.
2024-04-17T09:13:44+00:00    INFO 127.0.0.1    update    Actualización a la versión 5.1.0 completada.
```

*Traducido por openai.com*
