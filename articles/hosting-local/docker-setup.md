<!--
{
    "source": "https://docs.joomla.org/https:",
    "title": "Configuraci\u00f3n de Docker",
    "description": "",
    "author": ""
}
-->

## Configuración de un entorno local de Joomla mediante Docker

Para ejecutar Joomla en tu ordenador se necesitan cuatro cosas: 
- descargar y configurar un servidor web **Apache** o **nginx**, 
- un servicio de base de datos como **MySQL o** **MariaDB**, 
- y, por supuesto, necesitamos **PHP** 
- y **Joomla.** 

Para conseguir que todas estas piezas diferentes se comuniquen realmente entre sí, la mayoría
recurrimos a paquetes de software como **XAMPP**, **Laragon** o **FlyEnv**.

Sin embargo, las configuraciones tradicionales pueden provocar fácilmente conflictos de puertos o
servidores de bases de datos que misteriosamente se niegan a iniciarse. Cuando un servidor local
se bloquea, es posible que tengas que descargar y reinstalar manualmente sitios completos de Joomla
una y otra vez solo para probar un único PR,
con la posibilidad de perder tu trabajo mientras solucionas un error. Consume un tiempo valioso y
las soluciones suelen ser solo parches temporales.

**El cambio a Docker ([Más información sobre Docker](https://docs.docker.com/get-started/))** 
Con Docker, puedes
omitir por completo la configuración manual. En lugar de instalar
servidores web directamente en tu ordenador, solo tienes que escribir un
único archivo de «receta». Docker descarga, aísla y conecta todo
automáticamente en segundo plano. Si algo falla, no tienes que reinstalar
toda la configuración; simplemente reinicias el contenedor.

En esta guía, aprenderás la forma más sencilla de poner en marcha un
entorno local de Joomla usando Docker, lo que te permitirá dedicar menos
tiempo a solucionar problemas de servidores y más tiempo a contribuir.

### Requisitos previos

Solo necesitas tener instalado un elemento antes de empezar: **Docker Desktop**.

- Descárgalo desde [**docker.com**](https://www.docker.com/) y ejecuta el
  instalador
- En Windows, deja marcada la opción «Use WSL 2 instead of Hyper-V»:
  hace que todo sea más rápido
- Abre Docker Desktop y espera hasta que la esquina inferior izquierda
  muestre el estado verde **Motor en ejecución**.

![Docker Desktop](../../../en/images/hosting-local/docker-setup/01-docker-setup-desktop.png
)

Eso es todo.

### El archivo docker-compose.yml

Cuando necesitas que varios servicios se comuniquen —como un servidor
web (Apache/Nginx), PHP y una base de datos (MySQL/MariaDB)— utilizas un archivo
especial de orquestación llamado `docker-compose.yml`. Este archivo actúa como el
plano de tu proyecto, definiendo todos los servicios necesarios y cómo
colaboran entre sí. (La imagen oficial de Docker para Joomla está, de hecho,
basada en una imagen de PHP y Apache. Esto significa que, al utilizar solo esta
imagen de Joomla, obtienes PHP, Apache y Joomla, todo incluido).

Primero, crea una carpeta nueva en tu ordenador para tu proyecto (por
ejemplo, en tu Escritorio, crea una carpeta llamada `joomla-docker`).

Dentro de esa carpeta, crea un archivo de texto nuevo y asígnale exactamente este nombre:

    docker-compose.yml

Abre ese archivo en cualquier editor de texto (como VS Code o el Bloc de notas), pega el
siguiente código exactamente tal como aparece y guárdalo:

```
    services:
      joomla:
        image: joomla:latest
        ports:
          - "8080:80"
        environment:
          - JOOMLA_DB_HOST=db
          - JOOMLA_DB_USER=joomla
          - JOOMLA_DB_PASSWORD=joomlapass
          - JOOMLA_DB_NAME=joomladb
        depends_on:
          - db
      db:
        image: mariadb:10.11
        environment:
          - MYSQL_ROOT_PASSWORD=rootpass
          - MYSQL_DATABASE=joomladb
          - MYSQL_USER=joomla
          - MYSQL_PASSWORD=joomlapass
        volumes:
          - db_data:/var/lib/mysql
    volumes:
      db_data:
```
### Iniciar el entorno

Abre tu terminal (o PowerShell en Windows), navega hasta tu carpeta `joomla-docker`
y ejecuta:

```
    docker compose up -d
```


La primera vez que ejecutes esto, Docker descargará las imágenes de Joomla y MariaDB,
lo que podría tardar uno o dos minutos, dependiendo de la velocidad de tu conexión a
Internet. Después, cada inicio posterior será casi instantáneo, como puedes ver a continuación.

![Salida de inicio de Docker en la terminal](../../../en/images/hosting-local/docker-setup/02-docker-setup-terminal-transcript.png)

### El instalador de Joomla

Abre tu navegador y ve a `http://localhost:8080`. Deberías ver la
pantalla de instalación de Joomla.

![Configuración del instalador de Joomla: nombre del sitio](../../../en/images/hosting-local/docker-setup/03-docker-setup-joomla-installer-sitename.png)

Introduce el nombre de tu sitio y los datos del administrador en la primera pantalla.

![Datos de inicio de sesión del instalador de Joomla](../../../en/images/hosting-local/docker-setup/04-docker-setup-joomla-installer-login-data.png)

Cuando llegues a la pantalla de **Configuración de la base de datos**, aquí es donde la mayoría
de las personas se atascan:

**No escribas `localhost` como nombre del host.**

Como la base de datos se está ejecutando en su propio contenedor, Joomla necesita el nombre del servicio del contenedor, no localhost. Usa estos valores exactos:

- **Tipo de base de datos:** MySQLi
- **Nombre del host:** `db`
- **Nombre de usuario:** `joomla`
- **Contraseña:** `joomlapass`
- **Nombre de la base de datos:** `joomladb`

![Configuración de la base de datos del instalador de Joomla](../../../en/images/hosting-local/docker-setup/05-docker-setup-joomla-installer-database-config.png)

Haz clic para continuar, termina la instalación y listo.

Cuando termines de trabajar por hoy, ejecuta `docker compose stop` parapausa los contenedores y libera memoria. Tu sitio estará exactamente donde
lo dejaste la próxima vez.

------------------------------------------------------------------------

### Problemas comunes

- **La página en localhost:8080 no se carga justo después de iniciar:** El
  contenedor de la base de datos tarda unos segundos en terminar de
  inicializarse. Espera 30 segundos y actualiza la página.
- **El puerto 8080 ya está en uso:** Cambia `"8080:80"` por `"8081:80"` en
  el archivo de composición y accede a `localhost:8081` en su lugar.
- **Los contenedores se iniciaron, pero Joomla muestra un error de base de datos:** Comprueba
  que el Nombre del host en el instalador sea `db` y no `localhost`.
  
### Consejo profesional: Acceder a los archivos de Joomla para el desarrollo

Ahora mismo, tu sitio de Joomla está en ejecución, pero los archivos PHP reales están
ocultos dentro del contenedor de Docker. Si quieres contribuir a Joomla,
probar PR o escribir tus propios plugins, necesitas esos archivos en tu
ordenador para poder abrirlos en VS Code o en tu editor favorito.

Para sincronizar los archivos del contenedor con tu disco duro local, solo
tienes que añadir dos líneas (`volumes: `) y (`- ./site_joomla:/var/www/html`)
a la sección `joomla` de tu archivo `docker-compose.yml`, como se muestra a continuación:

```yml
services:
  joomla:
    image: joomla:latest
    ports:
      - "8080:80"
    volumes:
      - ./site_joomla:/var/www/html
    # ... (rest of your settings)
```

**Qué hace esto:** 

La próxima vez que ejecutes `docker compose up -d`, Docker creará automáticamente
una carpeta llamada `site_joomla` justo al lado de tu archivo de compose. En ella
copiará todo el núcleo de Joomla (incluido el panel de administración,
los componentes y las plantillas).

![Explorador del IDE de la instalación de Joomla en Docker](../../../en/images/hosting-local/docker-setup/06-docker-setup-ide-explorer.png)

¡Cualquier cambio de código que realices en esa carpeta de tu ordenador se actualizará instantáneamente dentro del contenedor en ejecución! Ya tienes todo listo para el desarrollo local.

### Consejo adicional 1: Pruebas de versiones específicas de Joomla y PHP

Al probar PR, los mantenedores a menudo te pedirán que realices pruebas con
versiones específicas de PHP. Con XAMPP, cambiar a una versión anterior o
posterior de PHP es una pesadilla. Con Docker, solo toma dos segundos.

En lugar de usar `image: `**`joomla:latest`** en tu
**`docker-compose.yml`**, puedes especificar versiones exactas mediante etiquetas. Por
ejemplo, si necesitas probar **Joomla 5.2** en **PHP 8.3**, solo cambia
esa línea por: **`image: joomla:5.2-php8.3-apache`**

Ejecuta **`docker compose up -d`** de nuevo y Docker cambiará instantáneamente tu
entorno de servidor. Puedes encontrar todas las etiquetas de versión disponibles en
la <a href="https://hub.docker.com/_/joomla" class="ng-star-inserted"
target="_blank" rel="noopener" data-hveid="0"
data-ved="0CAAQ_4QMahgKEwjl8vi347CTAxUAAAAAHQAAAAAQkgI">página oficial de Joomla
en Docker Hub</a>.

### Consejo adicional 2: Añadir phpMyAdmin

Si vienes de **XAMPP**, es posible que eches de menos tener una
interfaz visual para consultar tu base de datos. Puedes añadir fácilmente
**phpMyAdmin** a tu configuración agregando un nuevo **bloque de servicio**
al final de tu archivo **`docker-compose.yml`**:

```yml
    phpmyadmin:
        image: phpmyadmin/phpmyadmin:latest
        ports:
          - "8081:80"
        environment:
          - PMA_HOST=db
        depends_on:
          - db
```

Reinicia tus contenedores y ahora podrás acceder a phpMyAdmin visitando
**http://localhost:8081** en tu navegador. Solo tienes que iniciar sesión con
**`joomla`** como nombre de usuario y **`joomlapass`** como contraseña.

*Traducido por openai.com*