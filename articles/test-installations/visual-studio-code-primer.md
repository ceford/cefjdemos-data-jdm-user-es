<!-- Filename: Visual_Studio_Code_Primer / Display title: Introducción a Visual Studio Code  -->

## VS Code - Un IDE Gratuito y Popular

De Wikipedia:

> Visual Studio Code, comúnmente conocido como VS Code, es un editor
> de código fuente creado por Microsoft para Windows, Linux y macOS.
> Sus características incluyen soporte para depuración, resaltado de
> sintaxis, autocompletado inteligente de código, fragmentos de código,
> refactorización de código y Git integrado. Los usuarios pueden cambiar
> el tema, los atajos de teclado, las preferencias e instalar extensiones
> que añaden funcionalidad adicional.

## Instalación

La página por defecto del sitio de VS Code tiene una lista desplegable para cada plataforma soportada. Lo más probable es que tu plataforma esté preseleccionada. Así que descarga e instala, y estarás listo para empezar.

### Comenzando

La página de *Comenzar* de VS Code tiene algunos elementos de *Inicio*, una lista de elementos *Recientes*, y una breve lista de *Recorridos*. Si eres completamente nuevo en VS Code, se recomienda que los veas. Solo toman unos minutos.

La documentación de VS Code está disponible en el menú *Ayuda / Documentación*. Los [Videos Introductorios](https://code.visualstudio.com/docs/getstarted/introvideos) definitivamente valen la pena verlos. Cada uno dura de 2 a 6 minutos y ofrecen una excelente introducción a las características de VS Code.

La documentación oficial es el lugar al que acudir si deseas buscar información específica.

### Extensiones de VS Code

VS Code puede ser utilizado para cualquier tipo de texto, incluyendo una amplia gama de lenguajes de programación. Funciona con JavaScript sin necesidad de añadir extensiones. Otros lenguajes se detectan por contexto, por lo que si comienzas a crear y guardar código PHP, es probable que se te pida instalar un paquete de Soporte PHP.

Haz clic en el icono de *Extensiones* en la *Barra de Actividades* de la izquierda para ver qué tienes instalado y qué se recomienda. ¡Necesitarás la extensión PHP Debug!

### Disposición de la Pantalla de VS Code

Algunos términos usados en instrucciones posteriores:

- **Barra de Actividades**: la barra estrecha a la izquierda de la pantalla. Selecciona cualquier icono para abrir o cerrar la Barra Lateral Principal.
- **Barra Lateral Principal**: cuando está abierta, muestra detalles de la actividad seleccionada.
- **Barra de Estado**: en la parte inferior de la pantalla. Muestra lo que está sucediendo.
- **Panel**: un área debajo de los editores de texto para mostrar otra información.

Selecciona un icono de disposición en la parte superior derecha para abrir o cerrar cualquiera de estos elementos.

## Codificación de una Extensión Joomla

Para crear una extensión, tu objetivo es crear un archivo zip que puedas instalar en un sitio Joomla en funcionamiento. Por lo tanto, necesitas una carpeta para contener tu código. Esto debe estar dentro de tu espacio personal de archivos en tu computadora portátil o de escritorio usado para el desarrollo local. No debe estar en el árbol de tu sitio web. Por ejemplo, podrías usar *~/jextensions* para contener subcarpetas para diferentes extensiones. Yo uso *~/git* porque es corto y fácil de deletrear, aunque potencialmente confuso porque cada subcarpeta utiliza un repositorio git separado.

### Código de Ejemplo

Si te gustaría trabajar con algún código de ejemplo, hay una extensión disponible en GitHub llamada *mod_debugme*. Como su nombre implica, es un módulo con algunos errores. Además del código del módulo, hay un archivo *build.xml* para ilustrar una manera de automatizar la construcción para pruebas y la creación de un archivo zip.

El módulo está diseñado para mostrar los próximos eventos (3 por defecto) de una lista almacenada en una tabla de base de datos. Podrías imaginarte esto siendo usado en un sitio de oficina o familiar con la expectativa de un pastel.

Puede ser mejor comenzar utilizando comandos git desde la línea de comandos. Primero crea una carpeta para tu código y luego clona el repositorio remoto:
```sh
    mkdir ~/git
    cd ~/git
    git clone https://github.com/ceford/j4xdemos-mod-debugme
```
La respuesta debería tomar solo unos pocos segundos:
```sh
    Cloning into 'j4xdemos-mod-debugme'...
    remote: Enumerating objects: 23, done.
    remote: Counting objects: 100% (23/23), done.
    remote: Compressing objects: 100% (16/16), done.
    remote: Total 23 (delta 3), reused 23 (delta 3), pack-reused 0
    Unpacking objects: 100% (23/23), done.
```
Deberías tomarte un momento para mirar el contenido de la carpeta:
```sh
    cd j4xdemos-mod-debugme
    ls -al
    total 16
    drwxr-xr-x   6 ceford  staff   192  2 Sep 17:48 .
    drwxr-xr-x   3 ceford  staff    96  2 Sep 17:48 ..
    drwxr-xr-x  12 ceford  staff   384  2 Sep 17:48 .git
    -rw-r--r--   1 ceford  staff  1402  2 Sep 17:48 README.md
    -rw-r--r--   1 ceford  staff   927  2 Sep 17:48 build.xml
    drwxr-xr-x   8 ceford  staff   256  2 Sep 17:48 mod_debugme
```
La carpeta *.git* contiene información sobre el repositorio. El archivo *README.md* es un documento markdown que describe este repositorio. El archivo *build.xml* es un archivo usado para construir la extensión con una herramienta externa, Phing, que se describe más adelante. La carpeta *mod_debugme* contiene el código de la extensión.

### Instalar en Joomla

Comprime la carpeta de la extensión para crear un archivo zip instalable:
```sh
    zip -r mod_debugme.zip mod_debugme
```
Ahora puedes instalar el archivo zip en el sitio Joomla que usas para pruebas. Después de la instalación, necesitas crear un módulo del Sitio y asignarlo a una posición de módulo. Como es un módulo con errores, podrías asignarlo a una posición en *Todas las páginas* mientras trabajas en él; o podrías asignarlo a una posición en una sola página; o podrías posicionarlo en un artículo que tiene su propio ítem de menú.

Después de la instalación, elimina el archivo zip.

### Activar el Modo de Depuración

En la Configuración Global de Joomla, configura *Sistema de Depuración* a *Sí* y *Informe de Errores* a *Máximo*.

Cuando abres una página que contiene el módulo defectuoso, verás un rastro de llamadas (stack trace) que te indicará dónde se originó un error.

![traza de pila de vscode](../../../en/images/test-installations/vscode-primer-stack-trace.png)

A veces el error de codificación está en la primera línea del rastro de llamadas. De lo contrario, si el error es generado en el código de la biblioteca, por ejemplo, al pasar datos inválidos a una función de base de datos, el error de codificación puede estar más abajo en la lista de llamadas a funciones.  

## Abrir la carpeta de extensiones en VS Code

En VS Code, usa el menú Archivo / Abrir carpeta para localizar y abrir la carpeta que contiene tu copia local del código de la extensión *mod_debugme*. Deberías ver algo similar a lo siguiente:

![vista de carpeta de vscode](../../../en/images/test-installations/vscode-primer-screen.png)

Es posible que puedas diagnosticar el problema simplemente leyendo el código. En el caso del error *Clase "DebugHelper" no encontrada*, verás que una declaración de *uso* ha sido comentada unas pocas líneas antes. ¡Olvidar insertar una declaración de *uso* es un error común durante el desarrollo inicial!

Soluciona ese problema y luego comprime e instala el módulo nuevamente. Ese paso se vuelve un poco tedioso cuando tienes múltiples problemas. Es allí donde las herramientas de construcción son útiles.

## Phing

Phing es una herramienta de línea de comandos, disponible para todas las plataformas, utilizada para construir paquetes de software usando instrucciones almacenadas en un archivo XML, llamado build.xml por defecto. Para trabajar con el código de extensión, se puede utilizar para hacer dos cosas:

- copiar archivos modificados desde tu carpeta de origen de la extensión hacia los lugares correctos en tu carpeta de sitio web.
- generar un nuevo archivo zip para nuevas instalaciones.

Descarga e instala Phing. ¡Hay otras herramientas de construcción disponibles! Podrías instalar Phing en tu propia carpeta bin o en una carpeta bin del sistema. Necesitas anotar la ruta a tu código de Phing. En este ejemplo es *~/bin/phing-latest.phar*. Puedes probarlo desde la línea de comandos después de cambiar al directorio que contiene tu código de extensión:
```sh
    cd ~/git/j4xdemos-mod-debugme
    php ~/bin/phing-latest.phar
```
Respuesta:
```sh
    Buildfile: /Users/ceford/git/j4xdemos-mod-debugme/build.xml

    mod_debugme > main:
          ... Aquí se mencionarán los archivos copiados
          [zip] Construyendo zip: /Users/ceford/zips/mod_debugme.zip

    CONSTRUCCIÓN FINALIZADA

    Tiempo total: 0.0863 segundos
```

## Tareas de VS Code

Para ejecutar Phing desde dentro de VS Code necesitas crear un archivo *tasks.json* en la carpeta *.vscode* en la raíz de la carpeta *j4xdemos-mod-debugme*. Si esta última no existe, primero debes crearla. Luego crea el archivo *tasks.json* e introduce el siguiente código:
```json
    {
        // Consulta https://go.microsoft.com/fwlink/?LinkId=733558
        // para la documentación sobre el formato de tasks.json
        "version": "2.0.0",
        "tasks": [
          {
            "label": "Construir mod_debugme",
            "type": "shell",
            "command": "php ~/bin/phing-latest.phar",
            "windows": {
              "command": "php ~/bin/phing-latest.phar"
            },
            "group": "build",
            "presentation": {
              "reveal": "always",
              "panel": "shared"
            }
          }
        ]
    }
```
Los usuarios de Windows necesitan corregir el comando específico de Windows. Ahora puedes construir la extensión usando el menú *Terminal / Run Build Task*. El resultado del comando debería aparecer en el Panel de Terminal debajo del área de Edición.
```sh
      *  Ejecutando tarea: php ~/bin/phing-latest.phar

    Buildfile: /Users/ceford/git/gitdemo/j4xdemos-mod-debugme/build.xml

    mod_debugme > principal:

          [zip] No hay nada que hacer: /Users/ceford/zips/mod_debugme.zip está actualizado.

    CONSTRUCCIÓN FINALIZADA

    Tiempo total: 0.1031 segundos

     *  El Terminal será reutilizado por las tareas, presiona cualquier tecla para cerrarlo.
```
Puede haber mensajes de error incomprensibles. La causa más probable es tener rutas inválidas a carpetas en el archivo *build.xml* o que una carpeta no haya sido creada. ¡Solo otro tipo de problema a depurar!

## Depuración

Deberías poder solucionar el primer error mediante la inspección del código. Problemas más complicados requieren recorrer el código con el depurador. Esto te permite inspeccionar variables para ver si contienen los valores que esperas, por ejemplo, cuando pasas argumentos a funciones de la biblioteca.

### Configuraciones de *php.ini*

Para configurar la depuración con Xdebug, necesitas hacer algunas entradas al principio de tu archivo *php.ini*.
```ini
    zend_extension="xdebug.so"
    xdebug.mode="debug"
    xdebug.client_port=9003
    xdebug.start_with_request = yes
```
Después de guardar los cambios, reinicia tu servidor Apache.

### Añadir Ventana de Sitio Web

Tu carpeta de extensión contiene solo unos pocos archivos, las ***fuentes*** de los archivos instalados en tu sitio web. La depuración en tiempo de ejecución implica establecer puntos de interrupción en tus archivos del ***sitio***, por lo que necesitas acceso a esos archivos. Podrías usar el menú *File / Add Folder to Workspace...* para añadir la carpeta del sitio a tu Espacio de Trabajo. Sin embargo, es muy probable que termines haciendo cambios en los archivos del sitio en lugar de en los de fuente. Así que probablemente sea mejor abrir una ventana separada de VS Code para depurar.

- **Abrir nueva ventana:** Desde el menú de VS Code, selecciona *File / New Window* y selecciona la carpeta que contiene tu sitio web Joomla.
- **Abrir carpeta:** En la nueva ventana abierta, selecciona *File / Open Folder...* desde el menú de VS Code. Encuentra y selecciona la carpeta de tu sitio web. Deberías ver una lista de todos los archivos de tu sitio web Joomla en la barra lateral principal.

### Configuración de Lanzamiento

Para que la depuración realmente funcione en VS Code, necesitas una configuración de lanzamiento. En la raíz de tu sitio web, crea una carpeta llamada *.vscode* (nota el punto al principio) que contenga un archivo llamado *launch.json* con el siguiente contenido:
```json
    {
        "configurations": [
            {
                "name": "Listen for XDebug",
                "type": "php",
                "request": "launch",
                "hostname": "0.0.0.0",
                "port": 9003,
                "stopOnEntry": true,
                "pathMappings": {
                    "/Users/ceford/Sites/j421rc2": "${workspaceFolder}"
                }
            }
        ]
    }
```
Recuerda reemplazar el elemento pathMappings en este ejemplo con el pathMappings real en tu propio sitio. El elemento stopOnEntry pausará la ejecución en la primera línea del código PHP ejecutado.

### Depurar *mod_debugme*

Ahora estás listo para encontrar y corregir los errores en el módulo instalado.

- **Encontrar código del módulo:** Encuentra el primer error en la línea 16 de JROOT/modules/mod_debugme/mod_debugme.php.
- **Establecer punto de interrupción:** Haz clic en el espacio a la izquierda del número 16. Aparecerá un punto rojo pálido al pasar el cursor y se volverá rojo completo después de hacer clic para indicar que se ha establecido un punto de interrupción.
- **Iniciar depuración:** Desde el menú de VS Code, selecciona *Run / Start Debugging*. En tu navegador, recarga tu sitio. Tu ventana de VS Code debería reaparecer con el código detenido en la primera línea del archivo *index.php* del sitio. En la parte superior de la pantalla hay algunos iconos para controlar el proceso de depuración. Deberían ser autoexplicativos. Si no, consúltalos en la Ayuda/Documentación de VS Code.
- **Continuar:** Selecciona el botón de continuar: el código se ejecutará hasta tu primer punto de interrupción. Examina el código para ver cuál es el problema.
- **Pasar el cursor:** Si pasas el cursor sobre una variable a la que se le ha asignado un valor, aparecerá un pequeño Tooltip resumiendo los atributos de esa variable. No hay Tooltip para variables a las que no se les ha asignado valores.
- **Variables:** La columna de la izquierda contiene más información sobre el estado del código en el punto de interrupción. Hay demasiadas para cubrir aquí. ¡Explóralas según sea necesario!
- **Detener Depuración:** Probablemente sea mejor seleccionar el icono de Continuar, de lo contrario, la página web se entrega en blanco. De lo contrario, podrías usar el botón de Detener o el menú Run / Stop Debugging.

### Corregir un Error

**Recuerda:** ¡No corrijas el error en el código del sitio web! Corrígelo en el código fuente.

Corrige el código fuente y luego usa *Terminal / Run Build Task...*.

Reinicia la depuración.

### Consejos

Algunos problemas no tan obvios:

- Corregiste el primer error pero aún falla en esa línea. Mira en mod_debugme.xml para ver dónde se define el src de las clases con espacios de nombres. Cuando se corrigen en la fuente, necesitas reinstalar el archivo zip o eliminar *administrator/cache/autoload_psr4.php*. Cuando está ausente, Joomla reconstruye ese archivo a partir de archivos de manifiesto. Pero si tiene una entrada incorrecta o falta una, no se corrige hasta que se reinstala la extensión.
- A veces necesitas establecer un punto de interrupción unas pocas líneas antes de la línea donde ocurre el error, especialmente si deseas verificar los valores pasados a llamadas de funciones.
- La tabla *xxx.yyy\\debugme* no existe. Ah sí, el código para crear una tabla al instalar y eliminar al desinstalar nunca se creó. Necesitarás ejecutar una consulta SQL en phpMyAdmin usando el contenido del archivo *mod\\debugme.sql*. Recuerda cambiar *\#\\* en los nombres de las tablas por el prefijo de tu base de datos. Y cuando aún falla, verifica el nombre de la tabla en el código.

## Captura de pantalla

Cuando todo esté solucionado, esto es lo que podrías ver:

![vista del módulo depurado en vscode](../../../en/images/test-installations/vscode-primer-debugme-fixed.png)

¿Días de pastel?

## Referencias

De la Documentación de Joomla: [Visual Studio Code](https://docs.joomla.org/Visual_Studio_Code) también cubre la configuración de otras herramientas, por ejemplo, CodeSniffer y PHPUnit.

*Traducido por openai.com*

