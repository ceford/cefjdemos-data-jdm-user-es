<!-- Filename: Joomla_3.x_to_4.x_Step_by_Step_Migration / Display title: Joomla 3 a 4 Paso a Paso   -->

## Introducción

**Advertencia:** Esta guía asume que estás comenzando en Joomla 3.10.x. Si estás en una versión anterior, asegúrate de actualizar a Joomla 3.10 primero antes de pasar a Joomla 4. No hay prisa. Asegúrate de que todas tus extensiones estén preparadas para Joomla 4.x. Joomla 3.10.x tiene soporte hasta el 16 de agosto de 2023.

A continuación, se presentan instrucciones paso a paso para migrar un sitio 3.10.x a Joomla 4.x. Si bien hay cientos de escenarios diferentes, esto te dará el procedimiento básico a seguir. Las migraciones muy complejas probablemente serán un resultado de las extensiones de terceros instaladas. Se te anima a contactar a los desarrolladores de las extensiones de terceros instaladas en tu sitio Joomla para su camino sugerido de migrar sus extensiones.

## Paso a Paso

### Configurar una Ubicación de Desarrollo

1.  Asegúrate de estar ejecutando la última versión de Joomla 3.10.x antes de
    continuar.
2.  Haz una copia de seguridad de tu sitio en vivo 3.10.x. Puedes usar una herramienta recomendada
    (consulta las *Herramientas Sugeridas* al final de la página) o puedes hacer esto
    manualmente.
    -  [Conceptos Básicos de Copias de Seguridad para un Sitio Web Joomla!](https://docs.joomla.org/Special:MyLanguage/Backup_Basics_for_a_Joomla!_Web_Site/es)
    -  [¿Cuáles son las mejores prácticas para copias de seguridad de sitios?](https://docs.joomla.org/Special:MyLanguage/What_are_the_best_practices_for_site_backups%3F/es)
3.  Asegúrate de que tu entorno cumpla con los
    [requisitos técnicos para Joomla 4](https://downloads.joomla.org/technical-requirements)
    antes de continuar.
4.  Crea una nueva base de datos y un nuevo usuario para restaurar tu sitio 3.10.x.
5.  Crea un sitio de prueba o área de trabajo para restaurar la
    copia de seguridad de tu sitio 3.10.x en uno de los siguientes lugares:
    - Un subdominio.
    - Un subdirectorio.
    - Un dispositivo local. Joomla tiene un tutorial detallado sobre la instalación
      de XAMPP. Sin embargo, [WAMP](https://www.wampserver.com/en/),
      [MAMP](https://www.mamp.info/en/windows/) y
      [LAMP](https://sourceforge.net/projects/lampas/) son
      alternativas adecuadas.
    - Una nueva cuenta de hosting en un dominio temporal en la raíz. (Si deseas
      cambiar de host durante el proceso de migración.)
      - Restauración de un sitio en un dispositivo local.
        Consulta [Instalación de Joomla localmente](https://docs.joomla.org/Special:MyLanguage/Installing_Joomla_locally/es) y [Configuración de tu estación de trabajo para el desarrollo de Joomla](https://docs.joomla.org/Special:MyLanguage/Setting_up_your_workstation_for_Joomla_development/es).
      - Restauración de un sitio con una herramienta indicada al final de la página.
        (Lee la documentación para desarrolladores.)
6.  En tu ubicación de prueba, actualiza tu instancia de Joomla 3.10.x a la
    última versión de mantenimiento.
7.  Asegúrate de tener el esquema de base de datos más reciente actualizado a la última
    versión 3.10.x yendo a la pestaña **Administrador de Extensiones → Base de Datos**. Si tu esquema no está actualizado como en
    la siguiente imagen, haz clic en el botón **Reparar**:<br>
    ![joomla 3 extensiones base de datos](../../../en/images/migration/admin-extension-database-fix.png)
8.  Vaciar papelera: ¿Tienes artículos en la papelera? Si es así, elimínalos
    (y cualquier medio aplicable que pueda estar asociado con ellos si no se usa en otro lugar en el sitio). Los artículos (categorías y elementos del menú también) dejados en la papelera pueden causar problemas en la migración completa sin errores.
9.  Prueba.
10. Haz una copia de seguridad de nuevo.

### Evaluar Cada Extensión

En tu planificación, determinaste qué extensiones de terceros fueron mantenidas o 
eliminadas y cómo se migran. Para esta parte del Paso a Paso, utilizarás extensamente dos secciones diferentes del sitio: el *Chequeo Pre-Actualización* en
**Componentes → Actualización de Joomla** y **Extensiones → Administrar → Administrar**. Vas
a examinar cada extensión instalada en tu sitio. Determinarás si necesitan ser actualizadas a la última versión o desinstaladas. 
Más detalles en el [Chequeo Pre-Actualización](https://docs.joomla.org/Special:MyLanguage/:Pre-Update_Check).

1.  Usando el **Chequeo Pre-Actualización** para utilizarlo, necesitarás configurar el componente de 
    Actualización de Joomla ¡a Joomla 4! Para hacer esto, sigue los pasos:
2.  Ve a **Componentes → Actualización de Joomla**. Debería decir no se encontraron actualizaciones. Si no es así, actualiza Joomla a la última versión (debe ser 
    3.10.x) y prueba. Luego realiza otra copia de seguridad. Haz clic en el botón de Opciones en la esquina superior derecha.
3.  Selecciona *Joomla Next* del menú desplegable para Canal de Actualización.<br>
    ![selección de canal de opciones de actualización](../../../en/images/migration/update-options-channel.png)
4.  Haz clic en **Guardar & Cerrar**.
5.  Luego verás tu Versión de Joomla instalada, la versión más reciente de Joomla
    y la URL para el paquete de actualización. Joomla te mostrará los
    requisitos nuevamente para Joomla 4. Si te notifica que tienes un sistema o
    extensiones incompatibles, te lo dirá aquí. Tómate un momento para revisar esta página. <br>
    ![actualización a 4 preverificación de actualización](../../../en/images/migration/update-to-4-pre-update-check.png)
    <div class="alert alert-warning"><strong>Atención:</strong> NO actualices a Joomla! 4 
    ahora mismo. Esto es solo para preparar tus extensiones de terceros y hacer el 
    sitio compatible con Joomla! 4.</div>
6.  Observa el Chequeo Pre-Actualización y el Chequeo Pre-Actualización de Extensiones en
    la pestaña Chequeo Pre-Actualización del componente Actualización de Joomla. Si alguna
    extensión que no está en tu planificación está listada aquí, agrégala a tu
    lista de extensiones para investigar.
7.  Si migraste de Joomla 2.5 a 3.x en el pasado, puede haber
    algunas extensiones sobrantes que necesiten ser limpiadas. Las siguientes
    son extensiones más antiguas de 2.5 o 3.x que necesitan ser desinstaladas antes
    de actualizar a Joomla 4:
    - plg_content_geshi
    - Plantilla de Administrador Bluestork
    - Beez_20
    - Beez5
    - Atomic
    1.  En cuanto a las plantillas, desinstala todas las plantillas de frontend o
        backend centrales excepto Protostar y Beez3 (plantillas de frontend) e Isis o Hathor (plantillas de administrador). **NOTA:
        Protostar NO es compatible con Joomla 4**. Al migrar, desaparecerá. Necesitas tener una plantilla seleccionada como
        *predeterminada* y puedes usar Protostar o Beez3. Protostar
        desaparecerá al migrar a Joomla 4.x.
    2.  Si encuentras otros archivos que necesiten ser desinstalados,
        agréguelos a esta página. Este es un wiki, por lo que cualquiera puede agregar
        contenido a la página. Gracias de antemano por tu servicio.
8.  Notarás las etiquetas sobre si una extensión es compatible o no.
    Estas etiquetas generalmente dicen la verdad si muestran No o Sí.
    Si muestran *Etiqueta de compatibilidad faltante* significa que el desarrollador 
    de la extensión no utilizó una etiqueta en su extensión, por lo que no sabemos si es 
    o no compatible con Joomla 4. Habla con el desarrollador para
    verificarlo.
9.  **Actualizar Extensiones:** actualiza cualquier extensión que mantendrás en
    tu sitio web. En Joomla! 3.10.x, puedes ir a
    **Administrador de Extensiones → Pestaña de Actualización** y hacer clic en **Buscar actualizaciones**, lo que agregará un tooltip en la columna Versión, en la pestaña Administrar, dando 
    información de compatibilidad desde el backend. Esta funcionalidad solo
    admite extensiones que se actualizan a través de la pestaña de actualización del Administrador de Extensiones.
    Si tienes extensiones instaladas que no utilizan la actualización de extensiones de Joomla,
    necesitan ser evaluadas manualmente como se detalla
    a continuación. Lo mismo acontece para aquellas extensiones que tienen un tooltip. 
    Aún necesitarás verificar el tipo de paquete y ruta de migración con el
    desarrollador de la extensión para verificar cómo actualizar/migrar.
10. Investigar y Desinstalar Extensiones: ve a
    **Administrador de Extensiones → Administrar**.
11. Haz clic en el botón *Herramientas de Búsqueda* para mostrar las opciones de filtro.
12. Selecciona Paquete en el menú desplegable *Seleccionar Tipo*.<br>
    ![página gestión de extensiones](../../../en/images/migration/extensions-manage.png)
    <div class="alert alert-info">Seleccionar Paquete
    primero es recomendado porque si hay algo que necesitas
    desinstalar en un paquete, desinstalará automáticamente los
    Módulos, Plugins, o cualquier otra cosa asociada en el paquete al mismo
    tiempo.</div>
13. Desinstala cualquier Paquete que ya no sea necesario o que no migrará
    a Joomla 4.
14. Repite este proceso de revisar la pestaña Administrar para todos los Tipos en
    el menú desplegable: Componente, Archivo, Idioma, Biblioteca, Módulo, Plugin
    y Plantilla. Si el Autor indica Proyecto Joomla!, entonces deja esas
    extensiones intactas. Para todas las demás, asegúrate de desinstalar
    aquellos que no se usan o no son compatibles con Joomla! 4.x. 
    <div class="alert alert-danger"><strong>¡NOTA!</strong> No podrás
    desinstalar ninguna plantilla que esté establecida como predeterminada. Necesitarás seleccionar una plantilla compatible de Core como Beez3 o
    Protostar y luego desinstalar la plantilla si necesitas hacerlo.
    <em>Otro recordatorio:</em> <strong>Protostar no es compatible con 
    Joomla 4</strong>. Al migrar, desaparecerá. Seleccionarlo como
    predeterminado simplemente te permite llegar a Joomla 4.x.</div>
15. Toma nota de las versiones de Paquetes y Componentes que estén
    funcionando y que mantendrás en tu sitio. Puedes copiarlos/pegarlos
    en un documento para referencia.
16. Para cualquier extensión que estés manteniendo pero que no utilices el Administrador
    de Extensiones para actualizar con un solo clic (**Extensiones → Administrar → Actualizar**) actualiza
    todas las extensiones a las últimas versiones.
17. Antes y mientras actualizas, nota si las extensiones tienen ambas versiones 3.10.x y
    4.x en el mismo paquete. Si es así, estarán bien para
    *actualizar con un solo clic*. Si no, y 3.10 y 4.x tienen diferentes
    paquetes, necesitas revisarlas caso por caso. Normalmente caerán en uno de los siguientes escenarios:
    - La extensión tiene paquetes separados, pero al actualizar a 4.x,
      los detectan automáticamente y seguirán funcionando. Asegúrate de que el
      desarrollador confirme esto.
    - La extensión tiene paquetes separados que necesitan ser desinstalados en
      3.10.x y luego instalados con la versión Joomla 4.x una vez que
      el sitio se haya migrado. Un ejemplo de esto podría ser un plugin de contenido. Es 
      muy simple desinstalarlo en 3.10.x y luego instalarlo nuevamente 
      en 4.x.
    - Consulta [Consideraciones de Plantillas](https://docs.joomla.org/Special:MyLanguage/Template_Considerations_During_Migration/es)
      para obtener más información específica sobre plantillas y 
      [Convertir una plantilla de una versión anterior de Joomla!](https://docs.joomla.org/J3.x:Converting_A_Previous_Joomla!_Version_Template/es).

#### Notas sobre la Búsqueda (com_search)

La búsqueda (com_search) se separará en Joomla 4.x. La búsqueda (com_search)
migrará a Joomla 4. Después de la migración, necesitarás actualizarla a
la versión Joomla 4.x a través de com_installer. Continuará siendo
mantenida, pero más como una extensión de terceros recibiendo
actualizaciones a través de com_installer. Se recomienda usar la Búsqueda Inteligente
(com_finder) en adelante. La búsqueda sigue estando disponible desde el
[Directorio de Extensiones de Joomla](https://extensions.joomla.org/category/official-extensions/).

#### Notas sobre los Enlaces Web

Los Enlaces Web fueron separados en Joomla 3.4. Si se utilizaban en un
sitio 2.5, el proceso de migración lo detectaría y migraría el componente
de Enlaces Web y los datos. Para la migración de 3.10.x a 4.x, será lo
mismo. Sigue estando disponible y mantenido en el JED en
[Extensiones Oficiales](https://extensions.joomla.org/category/official-extensions).

#### Notas sobre el Enrutamiento Heredado

El enrutamiento heredado no estará disponible en Joomla 4.x. Solo el
Moderno estará disponible. Cuando realices la migración, si usas el
enrutamiento heredado, el sistema automáticamente los cambiará al enrutamiento
Moderno. Querrás ejecutar un verificador de enlaces rotos en tu sitio después
de migrar a Joomla 4.x y *antes de que entre en funcionamiento*.

### Ir a Joomla! 4.x

Una vez que hayas actualizado o desinstalado tus extensiones de terceros
para que solo aquellas compatibles con Joomla! 4 permanezcan en tu
instalación, continúa con los siguientes pasos:

1.  Ve a **Sistema → Configuración Global → Pestaña de Servidor** y
    cambia la Configuración de Errores de Predeterminada del Sistema a Máxima. Asegúrate de
    Guardar & Cerrar. <br>
    ![sistema unificación global pestaña del servidor](../../../en/images/migration/system-global-configuration-server-tab.png)
2.  Realiza otra copia de seguridad.
3.  Ve a **Componentes → Actualización de Joomla**. (Debería decir no se encontraron actualizaciones. Si no es así, actualiza Joomla a la última versión y prueba.
    Luego realiza otra copia de seguridad.) Haz clic en el botón de Opciones en la esquina
    superior derecha.
4.  Selecciona *Joomla Next* del menú desplegable para el Canal de Actualización.<br>
    ![componente de actualización de joomla seleccionar canal de actualización](../../../en/images/migration/update-select-channel.png)
5.  Haz clic en **Guardar & Cerrar**.
6.  Luego verás tu Versión de Joomla instalada, la Última versión de Joomla
    y la URL para el paquete de actualización. Joomla te mostrará los
    requisitos nuevamente para Joomla 4. Si te indica que tienes un sistema o
    extensiones incompatibles, te lo dirá aquí. Tómate un
    momento para revisar esta página.<br>
    ![revisión de actualización de joomla a 4](../../../en/images/migration/update-check.png)
7.  Si no aparece la actualización, ve a **Administrador de extensiones → Actualizar** y 
    presiona Purgar Caché desde la barra de herramientas. Ahora debería aparecer la actualización a Joomla! 4.
8.  Cruza los dedos y asegúrate de tener disponible esa copia de seguridad en
    caso de necesidad.
9.  Haz clic en el botón Instalar la Actualización.
10. Haz té mientras se carga la barra de estado a verde completo. La cantidad de
    tiempo que esto toma depende de tu sitio, conexión a Internet y
    velocidad del servidor. El proceso dura aproximadamente dos minutos. Cuando la actualización
    termine, probablemente te desconectarás del Administrador.
    Inicia sesión de nuevo. Dos veces.
11. Si todo va bien, llegarás a un aspecto completamente nuevo en el panel
    de administrador del backend.<br>
    ![panel de inicio de joomla 4 o 5](../../../en/images/migration/j4-home-dashboard.png)
12. Ve a **Sistema → Mantenimiento → Base de Datos** y haz clic en *Reparar* si
    aparecen errores.
13. En **Sistema → Instalar → Descubrir** ve si hay extensiones
    para instalar. (¡No debería haber ninguna!)
14. Ve al frontend de tu sitio y observa si aparece, incluso si no es
    la plantilla correcta. Si es así, continúa. Si no, consulta los errores
    comunes durante la migración.
15. Haz una copia de seguridad.
16. Instala tu nueva plantilla u otras extensiones si las tienes por
    instalar. Realiza copias de seguridad con frecuencia.
17. Configúralos. Realiza copias de seguridad con frecuencia.
18. Ejecuta un verificador de enlaces rotos y corrige cualquier enlace roto.
19. Prueba todo. Realiza copias de seguridad con frecuencia.
20. Si todo funciona como se espera, vuelve a cambiar la Configuración de Errores a Predeterminada del Sistema (**Sistema → Configuración Global → Pestaña de Servidor**).
    Asegúrate de **Guardar & Cerrar**.

### Iniciar tu Sitio Joomla! 4.x

1.  Cuando estés listo para publicar, realiza una copia de seguridad de tu
    sitio 3.10 por última vez. Restaúrala en un subdirectorio o subdominio si lo
    deseas.
2.  Haz una copia de seguridad de tu sitio Joomla! 4.x y mueve o restaura tu sitio Joomla! 4.x
    a la raíz (o cambia los servidores de nombres si estabas construyendo en un
    dominio temporal en el nuevo hosting de la cuenta de raíz).
3.  Prueba nuevamente.
4.  SI has hecho cambios de seguridad en el archivo .htaccess en el pasado, puede que
    necesites cambiar una línea (o líneas) para actualizar a la próxima
    versión de Joomla 4. Por favor, visita
    [Cambios de Htaccess después de Joomla 4](https://docs.joomla.org/Htaccess_changes_after_joomla4.0.4)
    para determinar si necesitas cambiar tu archivo o no.
5.  Elimine el sitio Joomla! 3.10 del servidor dentro de un par de días
    a menos que hayas editado tu archivo *robots.txt* para bloquear los
    rastreadores de motores de búsqueda.
6.  Elimina todos los sitios de desarrollo con los que has estado trabajando o mantenlos
    actualizados si están ejecutando una versión actual para evitar
    intentos de hacking en tu servidor.

Si hubo cambios de datos en el sitio 3.10 mientras migrabas a 4.x,
desearás mover esos datos al sitio 4.x antes de entrar en funcionamiento. Puedes hacer esto manualmente (asegúrate de mantener los mismos ID de usuario, ve en orden) o usando una [extensión de terceros](https://extensions.joomla.org/category/migration-a-conversion/data-import-a-export%20transfer%20tool/third-party%20extension/).

## Herramientas Sugeridas

- [Akeeba Backup](http://extensions.joomla.org/extensions/access-a-security/site-security/backup/1606)
  es muy popular para copias de seguridad y restauración.
- Más [herramientas de respaldo](https://extensions.joomla.org/tags/backup/).

*Traducido por openai.com*

