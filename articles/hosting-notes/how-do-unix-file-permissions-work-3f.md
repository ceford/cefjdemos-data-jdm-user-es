<!-- Filename: How_do_UNIX_file_permissions_work%3F / Display title: # Permisos de Archivos UNIX -->

Los permisos de archivos de Unix/Linux pueden ser confusos. Los permisos básicos de UNIX vienen en tres categorías:

    Permisos del Propietario: Controla tu propio acceso a los archivos.
    Permisos de Grupo: Controla el acceso para ti y cualquier persona en tu grupo.
    Permisos de Otros: Controla el acceso para todos los demás.

En Unix, cuando se configuran los permisos, el servidor te permite definir diferentes permisos para cada una de estas tres categorías de usuarios. En un entorno de servidor web, los permisos se utilizan para controlar qué propietarios de sitios web pueden acceder a qué directorios y archivos.

## ¿Cómo se ven los permisos de Unix?

Cuando ves tus archivos a través de la línea de comandos usando el comando `ls -l` de Unix, verás líneas como las siguientes, una para cada archivo y directorio:
```
drwxr-xr-x@  7 username  usergroup    224 13 Feb 10:48 includes
-rw-r--r--@  1 username  usergroup   1060 13 Apr 21:00 index.php
```
Explicación:
* El primer carácter en la línea es d para directorio o - para archivo, o ...
* Los siguientes 9 caracteres son 3 grupos de 3 que representan lectura (r), escritura (w) y ejecución (x) o un símbolo de menos (-) que significa sin acceso para cada uno de Propietario, Grupo y Otros.
* El símbolo @ es uno de varios atributos extendidos posibles.
* El número antes del nombre de usuario es la profundidad del directorio.
* Los dos nombres son el nombre de usuario del propietario y el grupo del usuario,
* El siguiente número entero es el tamaño del archivo en bytes.
* La fecha que sigue tiene la hora para ítems recientes o el año para ítems más antiguos.
* Finalmente está el nombre del archivo o directorio.

En una utilidad FTP el orden puede ser diferente y puede haber más o menos información.

### Propietario (Usuario) se relaciona con el nombre de usuario

El Propietario (Usuario) eres normalmente tú, estos permisos se aplicarán al nombre de tu cuenta de hosting.

### Grupo se relaciona con el grupo de usuarios

Los permisos de Grupo se aplicarán a otras personas que están en el mismo grupo que tú. Dentro de un entorno de hosting, es muy raro que haya otras personas en el mismo grupo que tú. Esto protege tus archivos y directorios de ser accesibles para cualquier otra persona que también pueda tener una cuenta de hosting en el mismo servidor que tú.

### Otros se relaciona con todos los demás

Los permisos de Otros se aplicarán a cualquier otra persona en el servidor que ni seas tú ni esté en tu grupo. Así que en un entorno de Servidor Web, recordando que normalmente nadie más está en tu grupo, entonces esto se refiere a todos los demás que acceden al servidor excepto tú. Cada uno de los tres conjuntos de permisos se define de la siguiente manera:

    r = Permisos de lectura
    w = Permisos de escritura
    x = Permisos de ejecución

    Propietario Grupo Otros
    r w x r w x r w x

Como muchos de ustedes ya saben, los permisos normalmente se expresan como un valor numérico, algo como 755 o 644. Entonces, ¿cómo se relaciona esto con lo que hemos discutido anteriormente? A cada carácter de los permisos se le asigna un valor numérico, que se asigna en cada conjunto de tres, por lo que solo necesitamos usar tres valores y reutilizarlos para cada conjunto.

    Propietario Grupo Otros
    r w x r w x r w x
    4 2 1 4 2 1 4 2 1

Ahora que tenemos un valor que representa cada permiso, podemos expresarlos en términos numéricos. Los valores simplemente se suman en los conjuntos respectivos de 3, lo que a su vez nos dará solo tres números que nos dirán qué permisos se están estableciendo. Si se nos dice que un archivo tiene los permisos de 777, esto significaría que lo siguiente es cierto.

    Propietario Grupo Otros
    r w x r w x r w x
    4 2 1 4 2 1 4 2 1

Por lo tanto...

      4+2+1 4+2+1 4+2+1
    =   7     7     7

El Propietario del archivo tendría permisos completos de Lectura, Escritura y Ejecución, el grupo también tendría permisos completos de Lectura, Escritura y Ejecución, y el resto del mundo también podría Leer, Escribir y Ejecutar el archivo. Los permisos estándar por defecto que se asignan a archivos y directorios por el servidor son normalmente:

    Archivos = 644
    Directorios = 755

Estos permisos permitirían, para archivos:
    
    644 = rw- r-- r--
    El Propietario tiene Lectura y Escritura
    El Grupo solo tiene Lectura
    Otros solo tienen Lectura

y para directorios:
    
    755 = rwx r-x r-x
    El Propietario tiene Lectura, Escritura y Ejecución
    El Grupo tiene solo Lectura y Ejecución
    Otros tienen solo Lectura y Ejecución

Ahora, las cosas pueden complicarse un poco cuando empezamos a hablar de Servidores Web compartidos, el software del Servidor Web estará ejecutándose con su propio nombre de usuario y nombre de grupo, la mayoría de los servidores están configurados para que usen ya sea "apache" y "apache" o "nobody" y "nobody" como nombre de usuario y nombre de grupo. Aquí está el problema. Tu Servidor Web se ejecuta como su propio usuario, y este usuario no eres tú ni está en tu grupo, así que los dos primeros conjuntos de permisos no se aplican a él. Solo los permisos del mundo (otros) se aplican. Por lo tanto, si configuras un conjunto de permisos similar a 640 en tus archivos del sitio web, tu Servidor Web no podrá ejecutar tus archivos del sitio web.
   
    640 = rw- r-- ---
    El Propietario tiene Lectura y Escritura
    El Grupo solo tiene Lectura
    Otros no tienen derechos

El servidor web no tiene permisos en absoluto y no puede Ejecutar, Escribir o más importante, ni siquiera Leer el archivo para entregar su contenido al navegador de un visitante del sitio web. Si se asignara al directorio permisos de 750, esto tendría el mismo efecto, porque el Servidor Web ni siquiera tiene permisos para leer archivos en el directorio, incluso si los archivos dentro de ese directorio tenían permisos favorables.
    
    750 = rw- r-x ---
    El Propietario tiene Lectura y Escritura
    El Grupo tiene Lectura y Ejecución
    Otros no tienen derechos

Los directorios tienen una peculiaridad adicional, si un directorio no tiene el permiso de Ejecución configurado en el conjunto del Mundo, entonces incluso si se configuran Lectura y Escritura, si el programa no se ejecuta como el usuario o grupo, aún no podrá acceder a los archivos dentro del directorio. La configuración de Ejecución permite al programa "Ejecutar" comandos en el directorio, por lo que sin que esté activada, el programa (en nuestro caso un Servidor Web) no puede ejecutar el comando "Leer", por lo tanto no puede entregar tu archivo al navegador web de los usuarios.

## ¿Cómo se relaciona esto con Joomla?

Buena pregunta, bien, en primer lugar esto sería importante durante el proceso de instalación web. Si puedes recordar cuando ejecutaste el instalador web de Joomla!, buscábamos directorios específicos para ser designados como escribibles. Vemos bastantes publicaciones que afirman que hubo problemas durante la instalación con los permisos o preguntan qué permisos se recomiendan. Algunos incluso consideran que el mensaje que pide permisos "escribibles" es demasiado vago.

Desafortunadamente, como el instalador web no sabe cómo está configurado tu servidor, no puede ser más específico. Sin embargo, una vez que entiendas la configuración de permisos y sepas un poco sobre los entornos de servicios web, en realidad encontrarás que el término *escribible* es muy específico y una descripción más que adecuada de lo que Joomla! necesita. Recordando la información anterior, puedes recordar que hay tres lugares donde se pueden establecer los permisos de *escritura*;

    Escritura del propietario
    Escritura del grupo
    Escritura de otros

Además, recuerda que el servidor web generalmente no se ejecuta como tu propio usuario ni en el mismo grupo. Cuando ejecutas el instalador web desde un navegador, es el servidor web tratando de acceder a los archivos, por lo tanto, son los permisos "Otros" los que se aplicarán. Si los permisos "Otros" no permiten que el servidor web lea, escriba o ejecute comandos en los directorios de Joomla!, recibirás el mensaje de que los directorios no son *escribibles*.

En este caso, necesitarás configurar los permisos de Otros a "7" en los directorios listados en el instalador web. Entonces, tus permisos totales podrían ser algo como 757, en el peor caso podrías necesitar establecer 777. Estos permisos muy abiertos pueden ser reajustados a 755 después de que el instalador se ejecute para ayudar con la seguridad de tus directorios y archivos.

    757 = rwx r-x rwx
    El propietario tiene Lectura, Escritura y Ejecución
    El grupo tiene Lectura y Ejecución
    Otros tienen Lectura, Escritura y Ejecución

Para hacer las cosas aún más confusas, muchas empresas de alojamiento utilizan software llamado phpsuExec o suExec, estas herramientas cambian la forma en que el servidor web se ejecuta, donde el servidor web normalmente no se ejecutaría como tu nombre de usuario, en este caso, sí lo hace. El uso de los permisos *otros* puede no ser requerido, ahora solo podrías necesitar configurar los directorios para que sean *escribibles* solo para tu propio nombre de usuario y nombre de grupo, esto permite que los permisos del directorio se establezcan en 755 o 775 en lugar de 757 o 777.

    755 = rwx r-x r-x
    El propietario tiene Lectura, Escritura y Ejecución
    El grupo tiene Lectura y Ejecución
    Otros tienen Lectura y Ejecución

    775 = rwx rwx r-x
    El propietario tiene Lectura, Escritura y Ejecución
    El grupo tiene Lectura, Escritura y Ejecución
    Otros tienen Lectura y Ejecución

El servidor web todavía necesitará que se configure Ejecución para el nombre de usuario y permisos de Lectura, Ejecución para el nombre del grupo para que pueda ejecutar el comando de Lectura en los archivos dentro del directorio. Nuevamente, estos permisos pueden ser degradados a 755 después de que se complete el instalador web. Eso cubre los conceptos básicos para los directorios, ¿qué hay de los archivos? Aquí es donde las cosas se simplifican un poco. La mayoría de los archivos que Joomla! utiliza estarán bastante felices con los permisos predeterminados de 644.

    644 = rw- r-- r--
    El propietario tiene Lectura, Escritura
    El grupo tiene Lectura
    Otros tienen Lectura

Esto es válido si no necesitas escribir en los archivos desde el servidor web, se aplican las mismas reglas que para los directorios si tienes esta necesidad. Un archivo que podrías querer que sea "Escribible" para el servidor web es tu archivo configuration.php. Este es el archivo de configuración de Joomla!, si planeas cambiar la configuración a través de la interfaz de administración web, entonces este archivo necesitará ser escribible para el servidor web.

Si tu servidor necesitaba que los permisos de directorio se establecieran para "Otros" escribibles para la instalación, entonces probablemente este archivo también necesitará ser 757 o 777. Sin embargo, dejar este archivo como 757 o 777 es peligroso, ya que estás permitiendo que todos tengan acceso de "Escritura", muchas vulnerabilidades de sitios web aprovechan este hecho, por lo general no se recomienda dejar este archivo con estos permisos.

Si tu servidor web tiene una de las herramientas SU instaladas y solo necesitaste configurar 755 en los directorios para la instalación, entonces probablemente también solo necesitarás establecer 755 o 775 en este archivo para permitir la edición a través de la interfaz de administración, y estos permisos generalmente se consideran más seguros que 757 o 777.

En conclusión, ¿qué permisos deberían establecerse para la instalación de Joomla!? Bueno, como puedes ver, ¡depende!

Sé que esto no es tan útil como te gustaría y ciertamente no es una respuesta definitiva, pero en general, después de la instalación, cualquier configuración insegura de "7" puede ser restaurada a algo más seguro. Por ejemplo:

    Archivos = 644
    Directorios = 755

Estos permisos permitirían, para archivos;

    644 = rw- r-- r--
    El propietario tiene Lectura y Escritura
    El grupo tiene solo Lectura
    Otros tienen solo Lectura

y para directorios,

    755 = rwx r-x r-x
    El propietario tiene Lectura, Escritura y Ejecución
    El grupo tiene Lectura y Ejecución
    Otros tienen solo Lectura y Ejecución

Si tienes acceso a un shell SSH, se pueden ejecutar los siguientes comandos desde la línea de comandos para restablecer todos los archivos y directorios a los valores predeterminados del servidor de 755 y 644. Cambia a la carpeta del directorio principal (" / ") de tu instalación de Joomla!, luego ejecuta:

    find . -type f -exec chmod 644 {} \;
    find . -type d -exec chmod 755 {} \;

Si solo tienes acceso FTP, este puede ser un trabajo muy laborioso, sin embargo, a menos que cambies más directorios durante la instalación de los que se solicitaron, solo deberías necesitar restablecer unos 10 directorios y el archivo *configuration.php*.

Ten en cuenta que para instalar cualquier extensión o plantilla después de la instalación de Joomla!, es posible que necesites elevar los permisos predeterminados nuevamente en los directorios apropiados solo para el período de instalación, luego puedes volver a degradarlos después de que se instale el complemento.

Si decides usar *caching* el directorio de caché necesitará ser *escribible* por el usuario del servidor web para permitirle escribir sus archivos temporales.

## Corregir permisos recursivamente

En una ventana de terminal, comenzando desde la raíz del sitio Joomla, utilice los siguientes comandos para establecer los permisos de archivos y carpetas a los valores predeterminados de Joomla.

```bash
find . -type f -exec chmod 644 {} \;
find . -type d -exec chmod 755 {} \;
```

Nota: El comando find asume que debe comenzar desde el directorio actual. Para estar seguro, dirígete a tu directorio public_html y especifica una ruta como el primer argumento. Algunos shells, como bash en Apple OS X, deben tener una ruta especificada en el comando find.

Prueba todas las extensiones de terceros después de cambiar los permisos.

*Traducido por openai.com*

