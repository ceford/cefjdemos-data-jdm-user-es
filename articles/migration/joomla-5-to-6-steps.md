<!--
{
    "source": "https://docs.joomla.org/https:",
    "title": "Joomla 5 a 6 paso a paso",
    "description": "",
    "author": ""
}
-->

<div class="alert alert-warning">
<p class="h3">Advertencia</p>

Esta guía supone que está comenzando con Joomla 5.4.x. Si utiliza una versión anterior, asegúrese de migrar o actualizar a Joomla 5.4.x antes de actualizar a Joomla 6.x.
</div>

## Introducción

Buenas noticias para Joomla 5.4.x a 6.x: es una actualización, no una migración. ¿Por qué? Por dos razones principales:

- Las extensiones de Joomla 5 (J5) que han eliminado todas las partes de código obsoletas, utilizan código actualizado de Joomla y no requieren que el plugin Behaviour - Backward Compatibility esté habilitado, funcionarán en Joomla 6 (J6)
- La mayoría de las demás funcionarán con el nuevo plugin Behaviour - Backward Compatibility 6 habilitado

Esta documentación refleja el proceso más sencillo al combinar la planificación y los pasos detallados en un solo documento. Aun así, necesitará ciertos conocimientos. Consulte la [[Migration Step by Step Self Assessment|Autoevaluación]] para determinar si debería o no encargarse de la actualización por su cuenta.

<div class="alert alert-info">
<p class="h3">Documentación para desarrolladores de Joomla 5.4 a 6.0 destinada a desarrolladores de extensiones de terceros.</p>

- [Elementos eliminados e incompatibilidades](https://manual.joomla.org/60/removed-backward-incompatibility)
- [Nuevas obsolescencias](https://manual.joomla.org/60/new-deprecations)
- [Documentación sobre migraciones](https://manual.joomla.org/migrations)
- [Nuevas funciones](https://manual.joomla.org/60/new-features/)
</div>

## Planificación de 5.4.x a 6.x

### Especificaciones de alojamiento/técnicas

1. Determine si su entorno de alojamiento cumple los requisitos. No podrá actualizar a Joomla 6 si el entorno de su servidor no cumple los [requisitos técnicos](https://manual.joomla.org/docs/get-started/technical-requirements/) mínimos. La opción de actualizar no aparecerá en el componente de actualización de Joomla.
    - PHP 8.3
    - MySQL 8.0.13
    - MariaDB 10.6.x
    - PostgreSQL 14.0

Puede consultar la información de su sistema en el sitio Joomla 5 haciendo clic en Sistema -> Información del sistema. Póngase en contacto con su proveedor de alojamiento si su servidor no cumple los requisitos.

![Panel del sistema con el enlace Información del sistema resaltado](../../../en/images/migration/joomla-5-to-6-steps/01-steps-5-to-6-system-dashboard.png)

El siguiente es un ejemplo de un entorno que cumple los requisitos técnicos. Muestra MySQL 8.0.43, PHP 8.3, Joomla 5.4.x y el complemento de compatibilidad con versiones anteriores deshabilitado.
![Información del sistema que muestra la versión de Joomla, la versión de PHP, el tipo de base de datos, la versión de la base de datos y el complemento de compatibilidad con versiones anteriores desactivado](../../../en/images/migration/joomla-5-to-6-steps/02-steps-5-to-6-system-information.png)

2. Comprueba que todas tus extensiones sean compatibles con Joomla 6. Hay varios escenarios relacionados con extensiones de terceros para esta actualización.

    1. La extensión puede ser compatible con J5 y J6 SIN utilizar el complemento de compatibilidad con versiones anteriores.
    2. La extensión puede ser compatible con J5 y J6 CON el uso del complemento de compatibilidad con versiones anteriores.
    3. La extensión puede parecer funcionar en J6, pero al intentar utilizarla, no funciona.
    4. La extensión puede dejar inutilizable todo el sitio.

¡No te preocupes! ¡No es tan grave como parece! Primero, hablemos de los complementos de compatibilidad con versiones anteriores.

<div class="alert alert-warning">
<p class="h3">Advertencia</p>

Para actualizar de Joomla 5.4.x a 6.x, el complemento de compatibilidad con versiones anteriores para Joomla 5 DEBE estar DESACTIVADO.
</div>

### Los plugins de compatibilidad con versiones anteriores

El plugin [Behaviour - Backward Compatibility 6](https://manual.joomla.org/60/compat-plugin/) incluido con Joomla 5.4.x tiene como objetivo mejorar la compatibilidad con versiones anteriores entre Joomla 5 y Joomla 6. El plugin ayuda a las extensiones de terceros a utilizar clases que ya no se incluyen en Joomla 6. Está implementado como un tipo de plugin «Behaviour» para garantizar que se cargue antes que cualquier otro plugin.

![Página de plugins que muestra los plugins de compatibilidad con versiones anteriores](../../../en/images/migration/joomla-5-to-6-steps/03-steps-5-to-6-bc-plugins.png)

La imagen anterior muestra dos plugins de compatibilidad con versiones anteriores:

1. Behaviour - Backward Compatibility y
2. Behaviour - Backward Compatibility 6

El plugin Behaviour - Backward Compatibility (sin un número en el nombre del plugin) se proporciona con Joomla 4.4.x para crear una capa de compatibilidad con versiones anteriores para las extensiones de Joomla 5. **Este plugin debe desactivarse antes de actualizar a J6**.
El plugin Behaviour - Backward Compatibility 6 se incluye con Joomla 5.4.x para crear una capa de compatibilidad con versiones anteriores para las extensiones de Joomla 6.

Ambos no pueden estar habilitados mientras se actualiza a J6.

Antes de actualizar de Joomla 5 a Joomla 6, el plugin Behaviour - Backward Compatibility (sin ningún número en el nombre del plugin) debe estar deshabilitado. Debe asegurarse de que todas sus extensiones de terceros puedan ejecutarse en su sitio web sin tener habilitado el plugin Behaviour - Backward Compatibility antes de actualizar a J6.

Después de determinar que todas y cada una de sus extensiones de terceros son compatibles y funcionan correctamente en J5 sin tener habilitado el plugin Behaviour - Backward Compatibility, puede deshabilitarlo. Dicho esto, recomendamos actuar con precaución. Antes de deshabilitar el plugin de compatibilidad con versiones anteriores, se sugiere hacer una de las dos cosas siguientes:

1. Hazlo en un sitio de desarrollo/pruebas. De esa forma, si accidentalmente omites una extensión que haga que tu backend sea inaccesible, no dejarás fuera de servicio tu sitio de producción.
2. Asegúrate de tener acceso a la base de datos. De esa forma, si es necesario, podrás volver a habilitar rápidamente el plugin mediante la base de datos. Más información a continuación.

Al realizar una actualización a J5.4.x, el plugin Comportamiento - Compatibilidad con versiones anteriores 6 se habilitará automáticamente. En las nuevas instalaciones de J6, el plugin de compatibilidad con versiones anteriores estará deshabilitado de forma predeterminada.

El plugin Comportamiento - Compatibilidad con versiones anteriores 6, que admite las extensiones que funcionan en J5, estará disponible durante todo J6. En J7, las extensiones de J5 no serán compatibles con versiones anteriores mediante el plugin. Esto proporciona a los desarrolladores de extensiones dos años adicionales para hacer que sus extensiones sean compatibles con J6 sin el plugin de compatibilidad con versiones anteriores. La intención es que, con cada versión del ciclo de vida, un plugin de compatibilidad con versiones anteriores sea compatible con el ciclo de vida anterior hasta el ciclo de vida posterior.
¿Alguna vez puedes desactivar el plugin Comportamiento - Compatibilidad con versiones anteriores 6 en J6? ¡Excelente pregunta! Después de determinar que todas y cada una de tus extensiones de terceros son compatibles y funcionan completamente sin el plugin de compatibilidad con versiones anteriores habilitado, puedes desactivar el plugin Comportamiento - Compatibilidad con versiones anteriores 6. Dicho esto, recomendamos actuar con precaución. Antes de desactivar el plugin Comportamiento - Compatibilidad con versiones anteriores 6, se sugiere hacer una de las siguientes dos cosas:

1. Hazlo en un sitio de desarrollo/pruebas. De esa manera, si accidentalmente pasaste por alto una extensión que hace que tu backend sea inaccesible, no dejarás fuera de servicio tu sitio de producción.
2. Asegúrate de tener acceso a la base de datos. De esa manera, podrás volver a habilitar rápidamente el plugin si es necesario. Más información a continuación.

### Comprobación previa a la actualización o Gestión de extensiones

En teoría, la comprobación previa a la actualización te indicaría si tus extensiones de terceros son compatibles con J6. Sin embargo, la comprobación previa a la actualización solo es útil si todos los desarrolladores de extensiones han hecho que sus extensiones reflejen la compatibilidad con ellas. En un mundo perfecto, la sección de **Extensiones** de la comprobación previa a la actualización te indicaría si una extensión:

* Se puede actualizar sin el complemento de compatibilidad con versiones anteriores habilitado
* Se puede actualizar con el complemento de compatibilidad con versiones anteriores habilitado
* Requiere una actualización de la extensión antes de actualizar de J5 a J6
* Es completamente incompatible
Las pruebas han mostrado discrepancias entre las extensiones que son compatibles y las que no lo son. Esto no es un problema del componente de comprobación previa a la actualización. Más bien, los desarrolladores de extensiones envían información a través de sus extensiones que permitiría que la comprobación previa a la actualización se completara correctamente. Si sus extensiones no están programadas para proporcionar a la comprobación previa a la actualización la información correcta, hay muy poco (o nada) que esta, ni el proyecto Joomla!, puedan hacer al respecto. Una buena fuente de información sería el sitio web del desarrollador de extensiones de terceros para verificar cómo debe gestionarse una extensión específica durante la actualización de J5 a J6.

La imagen que aparece más abajo en esta sección muestra un ejemplo del componente de comprobación previa a la actualización en Joomla 5.4.x, en la sección Extensiones.

La sección superior mostrará las extensiones que requieren una actualización. Vaya a Sistema -> Actualización -> Extensiones y actualice sus extensiones.
La sección intermedia muestra las extensiones cuya información sobre actualizaciones no está disponible por parte del desarrollador de la extensión. No sabrá si son compatibles o no sin probarlas o ponerse en contacto con el desarrollador.

La sección inferior muestra las extensiones que no requieren ninguna actualización. Esto significa que las extensiones están indicando a Joomla que son compatibles con Joomla 6. No se especifica si requieren o no el complemento de compatibilidad con versiones anteriores.

Tenga en cuenta que estas extensiones no cuentan con la recomendación del Proyecto Joomla. Estas extensiones se muestran únicamente como ejemplo. Se seleccionaron aleatoriamente del JED como prueba.

![Sección de extensiones de la comprobación previa a la actualización](../../../en/images/migration/joomla-5-to-6-steps/04-steps-5-to-6-pre-update-check.png)

Se recomienda utilizar únicamente la sección **Extensiones** del componente de comprobación previa a la actualización como una visión general de muy alto nivel, pero no como la fuente de información absolutamente fiable. Dicho de otro modo, es posible que no pueda confiar en el componente de comprobación previa a la actualización dependiendo de las extensiones que esté utilizando.
*¿Cuál es entonces la fuente de verdad?* Sistemas -> Gestionar extensiones

![Panel del sistema con «Gestionar extensiones» resaltado](../../../en/images/migration/joomla-5-to-6-steps/05-steps-5-to-6-system-dashboard-manage.png)

En la pantalla Extensiones: Gestionar, podrá ver todas las extensiones de terceros que está utilizando en el sitio. En la captura de pantalla siguiente se muestra la pantalla principal. En la columna Autor, puede ver el nombre de un desarrollador de extensiones popular en varias filas. También puede ver al autor del proyecto Joomla en varias filas.

![Página principal de Gestionar extensiones](../../../en/images/migration/joomla-5-to-6-steps/06-steps-5-to-6-extensions-manage.png)

Compruebe sus extensiones de terceros. A continuación, deberá determinar si son compatibles con J6 (con o sin el complemento de compatibilidad con versiones anteriores) o no. Si no lo son, la actualización no se realizará correctamente.

### Tres formas de comprobar la compatibilidad de tus extensiones de terceros con J6

1. Consulta el sitio web del desarrollador.
2. Haz una copia de seguridad/copia de tu sitio J5, restáuralo en un subdominio, activa la depuración y sigue paso a paso (a continuación) el proceso de actualización a J6. Comprueba si algo deja de funcionar. Si ocurre, desactiva cada extensión que genere un error y toma nota de ella. Tendrás que ponerte en contacto con el desarrollador, ya que no es compatible con J6.
3. Instala un paquete limpio de J6 en un subdominio, activa el complemento Behaviour - Backward Compatibility, instala todas las extensiones que utilizas y comprueba si funcionan.

NOTA: El directorio de extensiones de Joomla!, JED, mostrará insignias de compatibilidad con Joomla 6 para las extensiones que sean compatibles con o sin el uso del complemento de compatibilidad con versiones anteriores.
Podrías combinar lo anterior. Empieza con una instalación limpia y prueba tus extensiones. Cuando sepas cuáles funcionan y cuáles no, puedes trabajar con los desarrolladores para comprobar en qué punto se encuentran con respecto a su desarrollo para J6. DESPUÉS, cuando todas tus extensiones funcionen en un sitio limpio, sabrás que puedes **probar** una actualización completa de J5.4.x a 6.x.

Quizás quieras determinar si una extensión funciona sin el plugin de compatibilidad con versiones anteriores habilitado. Si ese es el caso, necesitarás acceso a la base de datos. Planifícalo. Asegúrate de tener acceso a la base de datos.

Después de instalar una instalación nueva de J6, el plugin de compatibilidad con versiones anteriores estará deshabilitado. Instala cada extensión una por una. Si inutiliza tu sitio, habilita el plugin de compatibilidad con versiones anteriores mediante la base de datos.
El complemento de compatibilidad con versiones anteriores se encuentra en la base de datos, en la tabla #__extensions. Se llama plg_behaviour_compat6. Establece el campo Enabled en 0 para deshabilitar el complemento y en 1 para habilitarlo. Al volver a habilitar el complemento de compatibilidad con versiones anteriores, es posible que recuperes el acceso al backend de Joomla (siempre que la extensión funcione con el complemento de compatibilidad con versiones anteriores).

O

Puedes deshabilitar extensiones individuales en la base de datos para continuar probando las demás extensiones y comprobar si funcionan sin el complemento de compatibilidad habilitado. Estas entradas se encontrarán en la tabla #__extensions. Cambia el campo Enabled a 0 para deshabilitar la extensión.
En algunos casos, cuando instalas una extensión en J6 que no es compatible, ya sea con el plugin de compatibilidad con versiones anteriores activado o desactivado, tendrás que buscar en la base de datos las entradas correspondientes a esa extensión (puede haber unas pocas o muchas) y desactivarlas hasta que puedas recuperar el acceso al panel de administración. Estas entradas estarán en la tabla #__extensions. Cambiarás el campo Enabled a 0 para desactivar la extensión. Una vez que puedas acceder de nuevo al panel de administración de Joomla, podrás desinstalarla correctamente desde Sistema -> Gestionar -> Extensiones. A continuación, consulta al desarrollador.

### Cassiopeia y Weblinks

#### Cassiopeia

Cassiopeia seguirá siendo la plantilla del frontend de Joomla 6. Tus personalizaciones deberían funcionar correctamente; aun así, recomendamos probarlas en un sitio de desarrollo para asegurarte.

#### com_weblinks

La extensión Weblinks funciona en J6 sin el plugin de compatibilidad con versiones anteriores activado en la versión 5.4.0 o posteriores:

- [Weblinks evolucionado en el JCM](https://magazine.joomla.org/all-issues/september-2025/joomla-weblinks-evolved-insights-from-gsoc-2025). 
- [Weblinks en el JED](https://extensions.joomla.org/extension/weblinks/).

### Prueba

Como parte de su planificación, se recomienda probar la actualización en un subdominio o localmente para determinar si funciona perfectamente. Asegúrese de llevar un registro de cualquier paso que deba realizar para que la actualización se lleve a cabo **perfectamente**.

Una vez que haya probado la actualización en un subdominio o en localhost y funcione **perfectamente**, puede hacer una copia de seguridad de su sitio de producción y realizar la actualización. Las instrucciones paso a paso se encuentran a continuación.

## Actualización paso a paso

El sitio que va a actualizar debe cumplir todos los requisitos técnicos y ejecutar Joomla 5.4.x para poder actualizarse. Si su sitio aún no ejecuta Joomla 5.4.x, actualícelo a 5.4.x antes de actualizar a J6.

1. Siga todas las instrucciones de la sección Planificación (arriba) antes de actualizar.
2. **Haga una copia de seguridad de su sitio web.**
3. Actualice las extensiones que necesiten actualizarse.
4. Desactive o desinstale las extensiones que no sean compatibles con J6.
5. Active la depuración (Configuración global -> pestaña Sistema -> ajuste Sistema de depuración en Sí).
6. **Haga otra copia de seguridad de su sitio web.**
7. **Pruebe la copia de seguridad para asegurarse de que se restaura correctamente.** (Sí, hágalo. Se sentirá mejor.)
8. Vaya a Sistema -> Actualización -> Joomla
![El panel del sistema con la opción Actualizar Joomla resaltada](../../../en/images/migration/joomla-5-to-6-steps/07-steps-5-to-6-system-dashboard-joomla.png)

9. Haga clic en el botón Opciones de la barra de herramientas superior, en el lado derecho.
![La página de actualización de Joomla con el botón Opciones resaltado](../../../en/images/migration/joomla-5-to-6-steps/08-steps-5-to-6-joomla-update.png)
10. Cambia el canal de actualización a Joomla Next.
![Opciones de actualización de Joomla con el canal de actualización resaltado](../../../en/images/migration/joomla-5-to-6-steps/09-steps-5-to-6-joomla-update-options.png)

11. Haz clic en Guardar y cerrar en la barra de herramientas superior.
12. Si tu servidor cumple las especificaciones técnicas, verás la siguiente pantalla con enlaces en la barra lateral izquierda para Configuración necesaria, Configuración recomendada y Extensiones.
![Comprobación previa a la actualización con la barra lateral resaltada](../../../en/images/migration/joomla-5-to-6-steps/10-steps-5-to-6-pre-update-check-for-6.png)

13. Es muy probable que la Configuración necesaria y la Configuración recomendada sean correctas, ya que esta pantalla no se mostrará si tu entorno no cumple los requisitos técnicos. Es posible que las extensiones no sean correctas. Consulta la sección de Planificación (arriba) sobre la comprobación previa a la actualización y por qué puede no mostrar una marca de verificación verde y aun así tener todas las extensiones compatibles. Ya has realizado las pruebas (¿verdad?), así que ya sabes si son compatibles o no.
14. El plugin Compatibilidad con versiones anteriores 6 está habilitado en Joomla 5.4.x. Para actualizar a J6, es necesario deshabilitar el plugin Comportamiento - Compatibilidad con versiones anteriores.
15. **Si no has seguido las instrucciones de Planificación (anteriores) para la ejecución de prueba, detente ahora, vuelve a la sección Planificación y sigue las instrucciones. La planificación es la parte más importante de esta actualización.**
16. Una vez que estés seguro de que todas tus extensiones son compatibles con J6 y hayas probado la actualización con un resultado perfecto, puedes marcar el botón para reconocer las advertencias sobre extensiones potencialmente incompatibles y continuar con la actualización; haz clic en Aceptar en el cuadro emergente y, después, haz clic en el botón Actualizar.
![Aviso de reconocimiento de advertencias](../../../en/images/migration/joomla-5-to-6-steps/11-steps-5-to-6-pre-update-warnings.png)

17. A continuación, tu sitio te pedirá de nuevo que confirmes que has realizado una copia de seguridad (y la has hecho y has comprobado que se restaura correctamente).
![Página de carga y actualización a Joomla 6](../../../en/images/migration/joomla-5-to-6-steps/12-steps-5-to-6-upload-and-update.png)
18. Tu sitio realizará la actualización a J6.  
![Página de progreso de la actualización](../../../en/images/migration/joomla-5-to-6-steps/13-steps-5-to-6-joomla-update-progress.png)

19. Una actualización exitosa te mostrará una pantalla como esta:  
![Página de estado de la actualización que muestra el éxito](../../../en/images/migration/joomla-5-to-6-steps/14-steps-5-to-6-joomla-update-success.png)

20. Verás que tu sitio es Joomla 6 en la esquina superior derecha de la pantalla.  
21. Prueba el frontend de tu sitio.  
22. Prueba el backend de tu sitio.  
23. Desactiva la depuración en Sistema -> Configuración global -> pestaña Servidor.  
24. Ajusta tu nueva búsqueda inteligente si es necesario.  
25. Disfruta de una bebida y maravíllate de lo increíble que eres.

## ¿Qué sucede si algo sale mal?

Si lo probaste todo de antemano, no debería suceder. Pero es posible que algo en el entorno haya cambiado o que algún código de una extensión haya cambiado entre el momento de las pruebas y la actualización.

Como activaste la depuración antes de comenzar, deberías poder ver la extensión que causa el problema y desactivarla (es posible que esto deba hacerse desde la base de datos si ya no puedes acceder al backend para desactivarla). De esta forma, tu sitio estará en funcionamiento mientras averiguas qué salió mal y lo solucionas.

En el peor de los casos, restaura tu copia de seguridad para tener tiempo de analizar lo sucedido en un entorno de pruebas.

La reparación de la base de datos podría resolver algunos de tus problemas. Ve al panel del sistema y haz clic en Base de datos.

![Panel del sistema con el enlace a Base de datos resaltado](../../../en/images/migration/joomla-5-to-6-steps/15-steps-5-to-6-system-dashboard-database.png)
En la página Mantenimiento: Base de datos, se mostrarán los problemas de estructura de la base de datos que pueda tener su sitio. Marque la casilla correspondiente y, a continuación, haga clic en el botón Actualizar estructura de la barra de herramientas superior.

![Página de mantenimiento de la base de datos que muestra un problema](../../../en/images/migration/joomla-5-to-6-steps/16-steps-5-to-6-maintenance-database.png)

## Otros lugares donde obtener ayuda

- [Foro de Joomla: Panel de migración y actualización 6.x](https://forum.joomla.org/viewforum.php?f=866&sid=47959551fb677ee3690f8b61eece277b)
- [Comunidad de Joomla en Mattermost](https://joomlacommunity.cloud.mattermost.com/main/channels/town-square)

*Traducido por openai.com*