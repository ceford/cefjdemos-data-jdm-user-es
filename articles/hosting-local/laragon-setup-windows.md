<!--
{
    "source": "https://docs.joomla.org/https:",
    "title": "Laragon para Windows",
    "description": "",
    "author": ""
}
-->

## Configuración de un entorno local de Joomla mediante Laragon

Laragon es una herramienta ligera para Windows que gestiona Apache, MySQL y
PHP en una instalación sencilla. Sin archivos de configuración ni
configuración manual: solo descarga, ejecuta y comienza a crear/probar con
Joomla. Consulta este artículo en la Revista de la Comunidad de Joomla: [Laragon: The Effortless, High-Performance
AMP Server for Windows](https://magazine.joomla.org/all-issues/october-2025/laragon-the-effortless,-high-performance-amp-server-for-windows).

Esta guía te lleva desde cero hasta un sitio local de Joomla en
funcionamiento y también aborda un pequeño detalle de la interfaz de
la versión más reciente que es fácil de corregir una vez que sabes qué
está ocurriendo.### Descarga e instalación de Laragon

Para comenzar, dirígete a la [página oficial de descargas de
Laragon](https://laragon.org/download). Descarga la versión completa de Laragon
(actualmente v8.6.1), ya que incluye todo lo que necesitas (como Apache,
MySQL y las versiones más recientes de PHP) directamente desde el principio.
Como alternativa, puedes descargar directamente el [instalador](https://github.com/leokhoa/laragon/releases/download/8.6.1/laragon-wamp.exe).

Una vez descargado el archivo `.exe`, haz doble clic en él para comenzar la
instalación.

**Nota sobre Windows Defender:** Como Laragon es una herramienta potente para desarrolladores, Windows Defender SmartScreen podría impedir que se inicie y mostrar una pantalla azul de advertencia. Esto es normal. Simplemente haz clic en **Más información** y, a continuación, haz clic en el botón **Ejecutar de todas formas** que aparece en la parte inferior.

![advertencia de protección de la configuración de laragon en windows](../../../en/images/hosting-local/laragon-setup-windows/01-laragon-setup-windows-protected-warning.png
)

Avanza por el asistente de configuración. La configuración predeterminada es perfectamente adecuada,pero presta atención a estos dos detalles importantes:

1.  **Ubicación de destino:** Deja la carpeta de instalación como
    `C:\laragon`. Instalarla en una ubicación profunda dentro de `Program Files` o
    `Documents` puede causar problemas de permisos más adelante.
2.  **Opciones de configuración:** Asegúrate de que la casilla **Hosts virtuales automáticos** esté
    marcada. Esta es la función que proporciona a tu sitio local de Joomla una
    dirección limpia (como `http://myjoomla.test`) en lugar de una dirección IP sin formato.

![opciones de configuración de laragon](../../../en/images/hosting-local/laragon-setup-windows/02-laragon-setup-options.jpg
)

Una vez finalizada la instalación, reinicia el equipo. (el asistente
de instalación te pedirá que hagas lo mismo)### Iniciar el servidor y configurar los permisos del firewall

Abra Laragon desde el menú Inicio y haga clic en el botón **Iniciar todo**.

Como es la primera vez que ejecuta un servidor local, Windows debe
verificar que sea seguro. Verá ventanas emergentes del Firewall de
Windows Defender que solicitan acceso a la red para servicios como
**Apache HTTP Server**, **MySQL** y **Mailpit**.

- Simplemente haga clic en **Permitir acceso** en cada una de estas ventanas.

Una vez concedido el permiso, Laragon iniciará su entorno local. Sabrá
que funciona cuando vea aparecer los números de puerto de Apache y MySQL
en la ventana de Laragon.### El inconveniente de «Ya se está ejecutando» (y cómo solucionarlo)

Cuando haya terminado de trabajar, puede hacer clic en «Detener todo» para
apagar Apache y MySQL, y luego hacer clic en la «X» de la esquina superior
derecha para cerrar la ventana de Laragon.

Este es el inconveniente: hacer clic en la «X» no cierra Laragon por
completo. Sigue ejecutándose silenciosamente en segundo plano. Si intenta
abrir de nuevo la aplicación Laragon desde el menú Inicio o el escritorio,
verá una advertencia amarilla en la esquina inferior derecha de la pantalla
que dice:
**«¡Laragon ya se está ejecutando!»**

![aviso de Laragon de que ya se está ejecutando](../../../en/images/hosting-local/laragon-setup-windows/03-laragon-setup-already-running-notice.png
)

**La trampa:** Si hace clic en la «X» de esa pequeña advertencia amarilla para cerrarla,
la ventana principal de Laragon también desaparecerá, dejándole completamente
sin posibilidad de acceder al panel de control. (Nota: También es posible que
ocasionalmente aparezca una ventana emergente de licencia que haga que la
interfaz se congele de forma similar).

**La solución:** Si la interfaz desaparece o se congela, solo tiene que
forzar el cierre del proceso en segundo plano y comenzar de nuevo. Es muy sencillo:

1.  Presiona `Ctrl + Shift + Esc` en tu teclado para abrir el **Administrador de tareas de
    Windows**.
2.  Busca **Laragon** en la lista de procesos en ejecución.
3.  Haz clic derecho sobre él y selecciona **Finalizar tarea**.

¡Eso es todo! Has detenido de forma segura el proceso en segundo plano bloqueado. Ahora puedes
abrir Laragon desde el menú Inicio y se cargará perfectamente, lo que te permitirá hacer clic en
"Iniciar todo" sin errores.### Cómo gestionar las ventanas emergentes de licencia (las pantallas de «insistencia»)

Laragon es gratuito para desarrollo y pruebas no comerciales
sin necesidad de adquirir una licencia. Sin embargo, después de usar la aplicación durante un breve
período, es probable que aparezca un aviso de «Clave de licencia» que le anime a apoyar el proyecto.

Como está utilizando la versión gratuita, simplemente puede cerrar estas
pantallas, pero hay una secuencia específica que debe esperar:

1.  La ventana principal de **Clave de licencia** aparecerá sobre la interfaz de Laragon.
    Haga clic en el texto **Cerrar** o en la «X».<br>
    ![ventana de clave de licencia de configuración de Laragon](../../../en/images/hosting-local/laragon-setup-windows/04-laragon-setup-license-key-window.png
)

2.  Inmediatamente después de cerrarla, aparecerá una segunda ventana emergente de
    **Advertencia**, que le recordará que Laragon se está ejecutando sin licencia.
    Haga clic en **Aceptar** o en la «X».<br>
    ![advertencia de configuración de Laragon sin licencia](../../../en/images/hosting-local/laragon-setup-windows/05-laragon-setup-no-license-warning.png
)

3.  Una vez que cierre esa segunda advertencia, es posible que Laragon abra automáticamente
    tu navegador web y te redirigirá a `https://laragon.org/key`. Simplemente
    puedes cerrar esa pestaña del navegador.
4.  Cuando vuelvas a la interfaz de Laragon y hagas clic en **Start All** para
    volver a iniciar el servidor, es posible que tengas que hacer clic en esas
    mismas dos ventanas emergentes exactas una vez más.

Después de descartarlas esta segunda vez, las ventanas emergentes desaparecerán y
¡podrás usar Laragon con total libertad!

*(Nota: Si en algún momento durante estas ventanas emergentes la interfaz de
Laragon se congela y deja de responder a los clics, recuerda el truco del
Administrador de tareas `Ctrl + Shift + Esc` del paso anterior para finalizar el
proceso en segundo plano y empezar de nuevo)*### Creación de una base de datos para Joomla

Antes de instalar Joomla, necesitas una base de datos vacía para almacenar sus datos.
Laragon incluye un administrador de bases de datos integrado llamado HeidiSQL, por lo que
todo lo que necesitas ya está disponible.

1.  Asegúrate de que los servicios de Laragon estén en ejecución (haz clic en **Iniciar todo**).
2.  Haz clic en el botón **Base de datos** en la interfaz principal de Laragon.
3.  Se abrirá una ventana del Administrador de sesiones. Laragon completa automáticamente
    las credenciales locales predeterminadas (Usuario: `root`, Contraseña:
    *\[dejar en blanco\]*).
4.  Haz clic en el botón **Abrir** en la parte inferior.<br>    
    **Solución de problemas: "Access denied for user 'root'@'localhost'"
    Error: ** Si haces clic en el botón **Abrir** y aparece inmediatamente un error de
    conexión fallida, ¡no te preocupes! Por lo general, esto significa que tienes
    otro programa de MySQL (como XAMPP o MySQL Workbench) ejecutándose en segundo
    plano, lo que bloquea el acceso de Laragon al puerto de la base de datos
    (puerto 3306).<br>    ![solución de problemas de acceso a la configuración de Laragon](../../../en/images/hosting-local/laragon-setup-windows/06-laragon-setup-troubleshooting.jpg
)

    **La solución:**
    1.  Pulsa la tecla de Windows, escribe **Servicios** y presiona Enter.
    2.  Desplázate hacia abajo en la lista para encontrar **MySQL**, **MySQL80** o **MariaDB**.
    3.  Haz clic derecho en el servicio en ejecución y selecciona **Detener**.
    4.  Vuelve a Laragon, haz clic en **Detener todo** y luego en **Iniciar todo**,
        e intenta hacer clic en **Abrir** en el Administrador de sesiones nuevamente. Debería
        conectarse sin ningún error.
5.  Una vez que te hayas conectado correctamente y estés dentro del administrador de bases de datos HeidiSQL, observa la columna izquierda. Haz clic derecho en el nombre del servidor
    (generalmente aparece como `Laragon.MySQL` o `127.0.0.1`).
6.  Pasa el cursor sobre **Crear nuevo** y selecciona **Base de datos**.
7.  Aparecerá un pequeño cuadro de diálogo. Escribe un nombre sencillo para tu base de datos en
    el campo "Nombre" (por ejemplo: `joomla_dev`). Puedes dejar el menú desplegable
    "Intercalación" con su configuración predeterminada.
8.  Haz clic en **Aceptar**.Verás que tu nueva base de datos aparece en la lista de la izquierda. ¡Eso
es todo! Ahora puedes cerrar por completo la ventana del administrador de
bases de datos.### Cómo obtener los archivos de Joomla

Ahora que el servidor y la base de datos están listos, es hora de colocar los
archivos de Joomla. La forma de hacerlo depende completamente de lo que quieras
lograr con esta configuración local:

**Método 1: Para crear un sitio web estándar** Si solo quieres crear
un sitio web o probar extensiones, necesitas la versión estable estándar.

- Dirígete a la [página oficial de descargas de Joomla](https://downloads.joomla.org) 
  y descarga el archivo `.zip` del **paquete completo** más reciente.

**Método 2: Para probar PR de la comunidad (pruebas de parches)** Si tu objetivo es
ayudar a la comunidad probando parches y solicitudes de incorporación de cambios, necesitas un
paquete prediseñado que contenga el código más reciente.

- **La compilación nocturna:** Descarga el `.zip` de la compilación nocturna más reciente desde
  [Compilaciones nocturnas](https://developer.joomla.org/nightly-builds.html).
  Estas se generan todas las noches y son perfectas para usarlas con el componente Joomla Patch Tester.- **El paquete precompilado del PR:** Como alternativa, si estás probando un PR específico en GitHub, desplázate hasta la parte inferior de la página del PR, haz clic en **Show all checks** y busca el enlace **Download Prebuilt packages**.
  ![enlace al paquete precompilado de configuración de laragon](../../../en/images/hosting-local/laragon-setup-windows/07-laragon-setup-prebuilt-package-link.png
)

**Método 3: Para contribuir con código del núcleo** Si planeas escribir código y enviar tus propios Pull Requests, necesitas el código fuente sin procesar y sin compilar.

- Clona directamente el [repositorio de Joomla CMS en GitHub](https://github.com/joomla/joomla-cms) en tu entorno de Laragon usando Git.
- *Importante:* Un clon sin procesar de GitHub no se ejecutará de inmediato; debes abrir la Terminal de Laragon y ejecutar `composer install` y `npm ci` dentro de tu carpeta para compilar las dependencias de PHP y los recursos CSS/JS. (Como instalaste la versión Full de Laragon, Composer y NPM ya están instalados en tu sistema).### **Colocación de los archivos en Laragon:**

Independientemente del método que hayas elegido, poner los archivos en funcionamiento en Laragon
es exactamente el mismo proceso:

1.  Abre la interfaz de Laragon y haz clic en el botón **Root**. Esto
    abre automáticamente la carpeta `C:\laragon\www` en tu equipo.
2.  Dentro de esta carpeta `www`, crea una nueva carpeta para tu proyecto. Mantén
    el nombre de la carpeta simple, en minúsculas y sin espacios (por ejemplo:
    `joomla_dev` o `joomla_pr_test`).
3.  Coloca tus archivos de Joomla dentro de esta nueva carpeta. (Si descargaste un
    `.zip` en el Método 1 o 2, extrae todo el contenido directamente en esta
    carpeta. Si usas Git en el Método 3, clona el repositorio en esta carpeta).
4.  Como habilitaste los «hosts virtuales automáticos» durante la instalación,
    Laragon usa automáticamente el nombre de tu carpeta para crear tu dirección web local. Así, una carpeta
    llamada `joomla_dev` estará disponible en tu navegador en `http://joomla_dev.test`.
    <br>    **Consejo: Mantén tus entornos limpios:** Es una buena idea crear
    diferentes carpetas para distintas versiones de Joomla o pruebas de PR específicas
    (p. ej., una carpeta llamada `joomla5_stable` y otra llamada
    `joomla4_dev`). Laragon las ejecutará todas sin problemas en paralelo con
    sus propias URL `.test` limpias, evitando que tu código y tus bases de datos
    se mezclen.
    <br>
    ![carpetas de proyectos de configuración de Laragon](../../../en/images/hosting-local/laragon-setup-windows/08-laragon-setup-project-folders.png
)## Ejecutar el instalador de Joomla

Ya tienes tu base de datos y los archivos de Joomla se encuentran en su nueva
carpeta (por ejemplo, `C:\laragon\www\joomla_dev`). ¡Ahora es el momento de
instalar Joomla!

**Paso crucial: ¡Recarga Apache!** Si Laragon ya estaba ejecutándose mientras
creabas la carpeta de tu nuevo proyecto, Laragon aún no sabe que existe la carpeta.

- Abre la interfaz de Laragon.

- Haz clic en **"Recargar"** en la esquina superior derecha. *(Esto obliga a Laragon a analizar la
  carpeta `www` y generar la nueva dirección `http://joomla_dev.test`).*

**Completar la configuración:**

1.  Abre tu navegador web e introduce la URL generada automáticamente para tu proyecto
    (p. ej., `http://joomla_dev.test`).
2.  Inmediatamente deberías ver la página del instalador web de Joomla.
3.  Elige tu idioma e introduce un nombre para tu sitio Joomla.
4.  Configura tu cuenta de superusuario (¡recuerda estos datos de inicio de sesión, los
    necesitarás para acceder al panel de administración de Joomla!).5.  En la pantalla de **Configuración de la base de datos**, introduce las credenciales de
    la base de datos de Laragon que creaste anteriormente:
    - **Tipo de base de datos:** `MySQLi` (predeterminado)
    - **Nombre del host:** `localhost`
    - **Nombre de usuario:** `root`
    - **Contraseña:** *\[Déjalo completamente en blanco\]*
    - **Nombre de la base de datos:** El nombre exacto que escribiste anteriormente en HeidiSQL
      (por ejemplo, `joomla_dev`).
    ![configuración de la base de datos del instalador de Joomla en Laragon](../../../en/images/hosting-local/laragon-setup-windows/09-laragon-setup-joomla-installer-database.png
)

6.  Haz clic en **Instalar Joomla**.

Cuando la barra de progreso termine, verás un mensaje de éxito. Ahora puedes hacer clic en **Abrir sitio** para ver tu sitio web local activo, o en **Abrir administrador** para iniciar sesión en el backend de Joomla.

Eso es todo: tu sitio local de Joomla está activo y listo para usarse.

*Traducido por openai.com*