<!-- Filename: Joomla_3.x_to_4.x_Step_by_Step_Migration / Display title: Migración Paso a Paso de Joomla 3.x a 4.x -->

<img
src="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/25px-Stop_hand_nuvola.svg.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/4/41/Stop_hand_nuvola.svg.png/38px-Stop_hand_nuvola.svg.png 1.5x, https://docs.joomla.org/images/4/41/Stop_hand_nuvola.svg.png 2x"
data-file-width="40" data-file-height="40" width="25" height="25"
alt="Stop hand nuvola.svg.png" />¡Advertencia!

Esta guía asume que está comenzando desde Joomla 3.10.x. Si tiene una
versión anterior, asegúrese de actualizar a Joomla 3.10 antes de pasar a
Joomla 4. No hay prisa. Asegúrese de que todas sus extensiones estén
listas para Joomla 4.x. Joomla 3.10.x será compatible hasta el 16 de
agosto de 2023.


Las siguientes son instrucciones paso a paso para migrar su sitio 3.10.x
a Joomla! 4.x. Si bien hay cientos de escenarios diferentes, esto le
dará el procedimiento básico a seguir. Es probable que las migraciones
muy complejas sean el resultado de extensiones de terceros instaladas.
Le recomendamos que se ponga en contacto con los desarrolladores de
extensiones de terceros instaladas en su sitio Joomla para conocer la
ruta sugerida para migrar sus extensiones.

## Introducción

La migración de Joomla! 3.10.x a 4.x se considera una mini-migración.
Esto se debe a que las extensiones del núcleo de Joomla se actualizarán
con "un clic" a través del componente Actualización de Joomla!, desde el
área de administración de Joomla. Muchas extensiones de terceros también
tienen una actualización con un solo clic. Algunas no es posible. Debe
revisar cada extensión y determinar qué camino debe seguir con cada una
para pasar de 3.10 a 4.x. Si aún no lo ha hecho, es posible que le
interese leer la
Autoevaluación
y la  Planificación para
Mini-Migración
antes de seguir los siguientes pasos.

Las Extensiones del Núcleo de Joomla! son:

- Categorías
- Artículos
- Menús
- Módulos (módulos del núcleo, no de terceros)
- Registros de acción
- Anuncios
- Campos
- Histórico de contenido
- Contactos
- Mensajería
- Canales electrónicos
- Redirecciones
- Buscar (desmontada en 4.x. Los sitios 3.x existentes aún la migrarán.
  Sin embargo, recomendamos usar la Búsqueda Inteligente en el futuro.
  Consulte las notas sobre Evaluar Cada Extensión)
- Búsqueda inteligente
- Etiquetas
- Enlaces web (desmontados, pero es posible que su sitio lo esté
  utilizando y se migrará. Consulte las notas sobre Evaluar Cada
  Extensión)

## Paso a Paso

### Preparar la Ubicación de Desarrollo

1.  Asegúrese de estar ejecutando la última versión de Joomla 3.10.x
    antes de continuar.
2.  Realice una copia de seguridad de su sitio 3.10.x en vivo. Puede
    utilizar una herramienta sugerida (consulte las *Herramientas
    sugeridas* en la parte inferior de la página) o puede hacerlo
    manualmente.
    -  Conceptos básicos sobre copia de seguridad de un sitio web
      Joomla!
    - [¿Cuáles son las mejores prácticas para las copias de seguridad
      del
      sitio?](https://docs.joomla.org/What_are_the_best_practices_for_site_backups%3F "Special:MyLanguage/What are the best practices for site backups?")
3.  Asegúrese de que su entorno cumpla con los
    <a href="https://downloads.joomla.org/es/technical-requirements-es"
    class="external text" target="_blank"
    rel="noreferrer noopener">requisitos técnicos para Joomla 4</a>
    antes de continuar.
4.  Cree una nueva base de datos y un nuevo usuario para restaurar su
    sitio 3.10.x.
5.  Cree un sitio de prueba o un área de construcción para trabajar y
    restaure la copia de seguridad de su sitio 3.10.x en uno de los
    siguientes lugares:
    - Un subdominio.
    - Un subdirectorio.
    - Un dispositivo local. Joomla tiene un tutorial detallado sobre la
      instalación de
      <a href="https://sourceforge.net/projects/xampp/" class="external text"
      target="_blank" rel="nofollow noreferrer noopener">XAMPP</a> en
      ​​XAMPP/es. Sin
      embargo,
      <a href="https://www.wampserver.com/en/" class="external text"
      target="_blank" rel="nofollow noreferrer noopener">WAMP</a>,
      <a href="https://www.mamp.info/en/windows/" class="external text"
      target="_blank" rel="nofollow noreferrer noopener">MAMP</a>,
      <a href="https://sourceforge.net/projects/lampas/" class="external text"
      target="_blank" rel="nofollow noreferrer noopener">LAMP</a> son
      todas alternativas adecuadas.
    - Una nueva cuenta de alojamiento en un dominio temporal en la raíz.
      (Si desea cambiar de host en el proceso de migración).
      - Restaurar un sitio en un dispositivo local. Vea [Configuración
        de su espacio de trabajo para el desarrollo de
        Joomla](https://docs.joomla.org/Setting_up_your_workstation_for_Joomla_development/es "Special:MyLanguage/Setting up your workstation for Joomla development/es").
      - Restaurar un sitio con una herramienta que aparece en la parte
        inferior de la página. (Lea la documentación para
        desarrolladores).
6.  En su ubicación de prueba, actualice su Joomla! 3.10.x a la última
    versión de mantenimiento.
7.  Asegúrese de tener el último esquema de base de datos actualizado a
    la última versión 3.10.x yendo a la pestaña **Extensiones **→** Base
    de datos**. Si su esquema no está actualizado como en la siguiente
    imagen, haga clic en el botón **Corregir**:<img
    src="https://docs.joomla.org/images/2/23/J310-admin-extension-database-fix-es.png"
    class="thumbborder" decoding="async" data-file-width="800"
    data-file-height="235" width="800" height="235"
    alt="J310-admin-extension-database-fix-es.png" />
8.  Vaciar papelera: ¿Tiene algún artículo en la papelera? Si es así,
    elimínelos (y cualquier medio aplicable que pueda estar asociado con
    ellos si no están en uso en otra parte del sitio). Los artículos
    (categorías y elementos del menú también) que se dejan en la
    papelera pueden causar problemas para completar una migración sin
    errores.
9.  Probar.
10. Copia de seguridad de nuevo.

### Evaluar Cada Extensión

En su
planning,
determinó qué extensiones de terceros se quedaban o no y cómo se
migrarán. Para esta fase del Paso a Paso, utilizará dos secciones
diferentes del sitio de manera extensa: la Comprobación de
Pre-Actualización en **Componentes **→** Actualización de Joomla!** y
**Extensiones **→** Gestionar **→** Gestionar**. Va a mirar cada una de
las extensiones instaladas en su sitio. Deberá decidir si es necesario
actualizar cada una de ellas a la última versión o desinstalarlas.

1.  Usando la **Comprobación de Pre-Actualización**: para utilizar la
    comprobación previa a la actualización, deberá configurar el
    componente Actualización de Joomla! a Joomla 4. Para hacer esto,
    siga:
2.  Vaya a **Componentes **→** Actualización de Joomla!**. (Debería
    decir que no se encontraron actualizaciones. Si no es así, actualice
    Joomla a la última versión (debe ser 3.10.x) y pruebe. Luego haga
    otra copia de seguridad.) Haga clic en el botón Opciones de la
    esquina superior derecha.
3.  Seleccione *Próximo Joomla* en el menú desplegable de Servidor de
    Actualizaciones.<img
    src="https://docs.joomla.org/images/1/1a/Migration_J3toJ4_update_channel-es.png"
    class="thumbborder" decoding="async" data-file-width="800"
    data-file-height="256" width="800" height="256"
    alt="Migration J3toJ4 update channel-es.png" />
4.  Haga clic en Guardar y cerrar
5.  A continuación, verá su versión de Joomla instalada, la última
    versión de Joomla! y la URL del paquete de actualización. Joomla le
    mostrará los requisitos nuevamente para Joomla 4. Si indica que
    tiene un sistema o extensiones incompatibles, se le notificará aquí.
    Tómese un momento para revisar esta página.<img
    src="https://docs.joomla.org/images/4/40/J310-admin-update_to_4-pre_update_check-es.png"
    class="thumbborder" decoding="async" data-file-width="800"
    data-file-height="319" width="800" height="319"
    alt="J310-admin-update to 4-pre update check-es.png" />
6.  Mire la Comprobación de Pre-Actualización y la Comprobación de
    Extensiones Pre-Actualización en la pestaña de Comprobación previa a
    la actualización del componente Actualización de Joomla!. Si aparece
    aquí alguna extensión que no está en su planificación, agréguela a
    su lista de extensiones para investigar.
7.  Si ha migrado desde Joomla! 2.5 a 3.x en el pasado, puede haber
    algunas extensiones obsoletas que deban limpiarse. Las siguientes
    extensiones de 2.5 o 3.x son muy antiguas y deben desinstalarse
    antes de actualizar a Joomla 4:
    - plg_content_geshi
    - Plantilla de administración Bluestork
    - Beez_20
    - Beez5
    - Atomic

    1.  Cuando se trata de plantillas, desinstale todas las plantillas
        del núcleo tanto para frontend o como para backend, excepto
        Protostar y Beez3 (plantillas de frontend) e Isis o Hathor
        (plantillas de administración). **NOTA: Protostar NO es
        compatible con Joomla 4**. Tras la migración desaparecerá.
        Necesitará tener una plantilla seleccionada como
        "predeterminada", pudiendo usar Protostar o Beez3. Protostar
        desaparecerá al migrar a Joomla 4.x.
    2.  Si encuentra otros archivos que necesitan ser desinstalados,
        agréguelos a esta página. Esta es una wiki para que cualquiera
        pueda agregarla a la página. Gracias de antemano por su
        servicio.
8.  Se dará cuenta de las etiquetas que indican si una extensión es
    compatible o no. Estas etiquetas generalmente cuentan una historia
    real cuando dicen No o Sí. Si dicen "Etiqueta de Compatibilidad
    Ausente", significa que el desarrollador de la extensión no usó una
    etiqueta en su extensión, por lo que no sabemos si es o no
    compatible con Joomla 4. Comunique con el desarrollador para
    verificar.
9.  **Actualizar Extensiones**: actualice las extensiones que mantendrá
    en su sitio web. En Joomla! 3.10.x puede ir a
    **Extensiones **→** pestaña Actualizar** y hacer clic en **Buscar
    actualizaciones**, lo que agregará información sobre la versión en
    la columna Disponible, en la pestaña Gestionar, que brinda
    información de compatibilidad del backend . Esta funcionalidad solo
    admite extensiones que se actualicen a través de la pestaña
    Actualizar del Gestor de Extensiones. Si tiene extensiones
    instaladas que no utilizan la actualización de extensiones de
    Joomla, deben evaluarse manualmente como se detalla a continuación.
    Lo mismo ocurre con las extensiones que tienen información sobre
    herramientas. Aún deberá verificar el tipo de paquete y la ruta de
    migración con el desarrollador de la extensión para verificar cómo
    actualizar/migrar.
10. Investigar y Desinstalar Extensiones: vaya a
    **Extensiones **→** Gestionar**
11. Haga clic en el Botón *Herramientas de búsqueda* para mostrar las
    opciones de filtro.
12. Seleccione Paquete en el menú desplegable *Seleccionar tipo*.<img
    src="https://docs.joomla.org/images/5/5e/J310-admin-extension-manage-package-es.png"
    decoding="async" data-file-width="800" data-file-height="315"
    width="800" height="315"
    alt="J310-admin-extension-manage-package-es.png" />Se recomienda
    seleccionar Paquete primero porque si hay alguno que necesita ser
    desinstalado, de esta forma se desinstalarán automáticamente al
    mismo tiempo los Módulos, Plugins o cualquier otra cosa incluido en
    dicho paquete.
13. Desinstale los paquetes que ya no sean necesarios o que no se
    migrarán a Joomla 4.
14. Repita este mismo proceso pasando por la pestaña Gestionar para
    todos los Tipos del menú desplegable: Componente, Archivo, Idioma,
    Librería, Módulo, Plugin y Plantilla. Si el autor pertenece a
    Joomla! Project, olvídese de estas extensiones. Para todos los
    demás, asegúrese de desinstalar aquellos que no estén en uso o no
    sean compatibles con Joomla! 4.x. **¡NOTA!** No podrá desinstalar
    ninguna plantilla que esté configurada como predeterminada. Deberá
    seleccionar una plantilla del Núcleo compatible, como Beez3 o
    Protostar, y luego desinstalar la plantilla si es necesario.
    *Otro recordatorio:* **Protostar no es compatible con Joomla 4.x**.
    Tras la migración desaparecerá. Seleccionarlo como predeterminado,
    simplemente le lleva a Joomla 4.x.
15. Tome nota de las versiones de paquetes y componentes que se estén
    ejecutando actualmente y que mantendrá en su sitio. Puede
    copiarlos/pegarlos en un documento como referencia.
16. Para cualquier extensión que desee conservar, pero no utilice el
    Gestor de Extensiones para la actualización con un solo clic
    (**Extensiones **→** Gestionar **→** Actualizar**), actualice todas
    las extensiones a las últimas versiones.
17. Tenga en cuenta si las extensiones tienen versiones para 3.10.x y
    4.x en el mismo paquete, antes y durante la actualización. Si es
    así, estarán correctas para "actualizar con un solo clic". Si no es
    así, y para 3.10 y 4.x tienen paquetes diferentes, debe mirarlos
    caso por caso. Normalmente se encontrarán en uno de los siguientes
    escenarios:
    - La extensión tiene paquetes separados pero al actualizar a 4.x, se
      detectan automáticamente y aún funcionan. Asegúrese de que el
      desarrollador lo confirme.
    - La extensión tiene paquetes separados que deben desinstalarse en
      3.10.x y luego instalarse con la versión Joomla 4.x, una vez que
      se migre el sitio. Un ejemplo de esto podría ser un plugin de
      contenido. Es muy sencillo, desinstalarlo en 3.10.x, y luego
      instalarlo nuevamente en 4.x.
    - Mire  Consideraciones sobre la plantilla en la
      migración
      para obtener información más específica sobre plantillas, y
       Conversión de una plantilla de una versión de Joomla!
      anterior.

#### Notas sobre Buscar (com_search)

Buscar (com_search) se desacoplará en Joomla 4.x., pero migrará con
Joomla 4. Después de la migración, deberá actualizarlo a la versión
Joomla 4.x a través de com_installer. Continuará manteniéndose, pero
como si se tratar de una extensión de terceros, recibiendo
actualizaciones a través de com_installer. Se recomienda utilizar la
Búsqueda Inteligente (com_finder) en el futuro. Buscar seguirá estando
disponible en
<a href="https://extensions.joomla.org/category/official-extensions/"
class="external free" target="_blank"
rel="noreferrer noopener">https://extensions.joomla.org/category/official-extensions/</a>.

#### Notas sobre Enlaces Web

Los Enlaces Web se desacoplaron en Joomla 3.4. Si estuviera en uso en un
sitio 2.5, el proceso de migración registrará nota de esto y migrará el
componente y los datos de enlaces. Para la migración de 3.10.x a 4.x,
será lo mismo. Todavía está disponible y se mantiene en el JED en
<a href="https://extensions.joomla.org/category/official-extensions/"
class="external text" target="_blank" rel="noreferrer noopener">Official
Extensions</a>.

#### Notes on Legacy Routing

Legacy routing will not be available in Joomla 4.x. Only Modern will be
available. When you do the migration, if you are using Legacy routing,
the system will automatically change them to Modern routing. You will
want to run a broken link checker on your site after migrating to Joomla
4.x and *before you go live*.

### Pasar a Joomla! 4.x

Una vez que haya actualizado o desinstalado sus extensiones de terceros,
que solo permanezcan en su instalación las que resulten compatibles con
Joomla! 4, continúe con los siguientes pasos:

1.  Vaya a **Sistema **→** Configuración Global **→** pestaña Servidor**
    y cambie Informe de Errores de Predeterminado del sistema a Máximo.
    Asegúrese de Guardar y Cerrar.

<img
src="https://docs.joomla.org/images/1/18/J310-system-global-config-server-tab-es.png"
class="thumbborder" decoding="async" data-file-width="500"
data-file-height="382" width="500" height="382"
alt="J310-system-global-config-server-tab-es.png" />

1.  Realice otra copia de seguridad.
2.  Vaya a **Componentes **→** Actualización de Joomla!**. (Debería
    decir que no se encontraron actualizaciones. Si no es así, actualice
    Joomla a la última versión y pruébelo. Luego haga otra copia de
    seguridad). Haga clic en el botón Opciones en la esquina superior
    derecha.
3.  Seleccione *Próximo Joomla* en el menú desplegable de Servidor de
    Actualizaciones.<img
    src="https://docs.joomla.org/images/7/73/J310-component-joomla-update-select-support-es.png"
    class="thumbborder" decoding="async" data-file-width="500"
    data-file-height="280" width="500" height="280"
    alt="J310-component-joomla-update-select-support-es.png" />
4.  Haga clic en Guardar y cerrar.
5.  A continuación, verá su actual versión de Joomla! instalada, la
    última versión de Joomla! disponible y la URL del paquete de
    actualización. Joomla le mostrará nuevamente los requisitos para
    Joomla 4. Si indica que tiene un sistema o extensiones
    incompatibles, se lo dirá aquí. Tómese un momento para revisar esta
    página.<img
    src="https://docs.joomla.org/images/1/1a/J310-to-j4-dev-update-found-es.png"
    class="thumbborder" decoding="async" data-file-width="800"
    data-file-height="426" width="800" height="426"
    alt="J310-to-j4-dev-update-found-es.png" />
6.  Si la actualización no aparece, vaya a **Gestor de
    Extensiones **→** Actualizar** y presione Purgar Caché en la barra
    de herramientas. Ahora la actualización a Joomla! 4 debería
    aparecer.
7.  Cruce los dedos y asegúrese de tener esa copia de seguridad a mano
    por si acaso.
8.  Haga clic en el botón Instalar la Actualización.
9.  Prepárese un té mientras la barra de estado se carga completamente
    en verde. La cantidad de tiempo que lleva esto depende de su sitio,
    la conexión a Internet y la velocidad del servidor. El proceso puede
    llevar unos dos minutos. Cuando finalice la actualización,
    probablemente se cerrará la sesión del Administrador. Regístrese de
    nuevo. Dos veces.
10. Si todo va bien, obtendrá un aspecto totalmente nuevo del panel de
    administrador del backend.<img
    src="https://docs.joomla.org/images/f/f8/J4-administrator-overview-es.png"
    class="thumbborder" decoding="async" data-file-width="800"
    data-file-height="400" width="800" height="400"
    alt="J4-administrator-overview-es.png" />

\# Vaya a **Sistema **→** Mantenimiento **→** Base de datos** y haga
clic en *Actualizar estructura* si aparece algún problema. \# Vaya ahora
a **Sistema **→** Instalar **→** Descubrir** y vea si hay alguna
extensión para instalar. (¡No debería haber ninguna!).

1.  Vaya a la interfaz de su sitio y vea si se visualiza, incluso si no
    es la plantilla adecuada. Si es así, continúe. De lo contrario,
    consulte  Errores Comunes en la Migración de Joomla 3.10 a
    4.x.
2.  Realice una copia de seguridad.
3.  Instale su nueva plantilla u otras extensiones si las tiene listas
    para instalar. Realice una copia de seguridad a menudo.
4.  Configúrelos. Realice una copia de seguridad a menudo.
5.  Run a broken link checker and fix any broken links.
6.  Pruebe todo. Realice una copia de seguridad a menudo.
7.  Si todo funciona como se esperaba, vuelva a configurar el Informe de
    Errores como Predeterminado del Sistema
    (**Sistema **→** Configuración Global **→** pestaña Servidor**).
    Asegúrese de guardar y cerrar.

### Poner en marcha su Sitio Joomla! 4.x

1.  Cuando esté listo para comenzar, haga una copia de seguridad de su
    sitio 3.10 por última vez. Restáurelo en un subdirectorio o
    subdominio si lo desea.
2.  Haga una copia de seguridad de su Joomla! 4.x y mueva o restaure su
    Joomla! 4.x a la raíz (o cambie los servidores de nombres si estaba
    construyendo un dominio temporal en una nueva raíz de la cuenta de
    alojamiento).
3.  Pruebe nuevamente.
4.  Elimine el sitio Joomla! 3.10 del servidor en un par de días, a
    menos que haya editado su archivo *robots.txt* para bloquear las
    arañas del motor de búsqueda.
5.  Elimine todos los sitios de desarrollo con los que haya estado
    trabajando, o manténgalos actualizados si están ejecutando una
    versión actual para evitar intentos de pirateo en su servidor.

Si hubo cambios de datos en el sitio 3.10 mientras estaba migrando a la
4.x, querrá mover esos datos actualizados al sitio 4.x antes de abrir al
público. Puede hacer esto manualmente (asegúrese de que mantiene los
mismos ID de usuario - vea en orden) o usando una <a
href="https://extensions.joomla.org/category/migration-a-conversion/data-import-a-export%20transfer%20tool/third-party%20extension/"
class="external text" target="_blank"
rel="noreferrer noopener">extensión de terceros</a>.

## Herramientas Recomendadas

- <a
  href="https://extensions.joomla.org/extension/access-a-security/site-security/akeeba-backup/"
  class="external text" target="_blank" rel="noreferrer noopener">Akeeba
  Backup</a> es muy popular para realizar y restaurar copias de
  seguridad. Ver más
  <a href="https://extensions.joomla.org/tags/backup/"
  class="external text" target="_blank"
  rel="noreferrer noopener">herramientas de respaldo</a>.
- <a
  href="http://extensions.joomla.org/extensions/access-a-security/site-security/backup/1606"
  class="external text" target="_blank" rel="noreferrer noopener">Akeeba
  Backup</a> is very popular for backup and restore. See more
  <a href="https://extensions.joomla.org/tags/backup/"
  class="external text" target="_blank" rel="noreferrer noopener">backup
  tools</a>.

## Related information

Pre-Update_Check
