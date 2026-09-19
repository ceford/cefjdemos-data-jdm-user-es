<!--
{
    "source": "https://docs.joomla.org/J4.x:Setting_Up_Your_Local_Environment",
    "title": "Configuraci\u00f3n del entorno local",
    "description": "",
    "author": ""
}
-->

Desde Joomla! 4 hemos cambiado el proceso de desarrollo. Ya no es
posible clonar el repositorio y disponer de una instalación de Joomla
utilizable.
Seguimos las prácticas recomendadas e implementamos un proceso de
compilación para el CMS.

## Guía de inicio rápido

Los pasos para configurar su entorno de desarrollo dependen de su sistema
operativo. No podemos escribir documentación para todos los sistemas
operativos (SO); utilice su motor de búsqueda favorito para encontrar una guía.

### Herramientas necesarias

1.  PHP: básicamente lo mismo que necesita para ejecutar un sitio Joomla, pero
    necesita la versión CLI de PHP (interfaz de línea de comandos). (Consulte
    la página [Configuración de un servidor LAMPP para el desarrollo con PHP](https://docs.joomla.org/Special:MyLanguage/Configuring_a_LAMPP_server_for_PHP_development "Special:MyLanguage/Configuring a LAMPP server for PHP development").)
2.  Composer: para gestionar las dependencias de PHP de Joomla. Para obtener ayuda
    sobre la instalación de Composer, lea la documentación
    en <a href="https://getcomposer.org/doc/00-intro.md" class="external free"
    target="_blank"
    rel="nofollow noreferrer noopener">https://getcomposer.org/doc/00-intro.md</a>.
3.  Node.js: para compilar los archivos JavaScript y SASS de Joomla. Para obtener ayuda
    sobre la instalación de Node.js, siga las instrucciones disponibles
    en <a href="https://nodejs.org/en/" class="external free" target="_blank"
    rel="nofollow noreferrer noopener">https://nodejs.org/en/</a>. Nota,
    necesitará NodeJS 12 o superior para instalar Joomla.
4.  Git - para la gestión de versiones.

### Pasos para configurar el entorno local

1.  Clona el repositorio
2.  Cambia a la rama de la versión más reciente.
3.  Ejecuta `composer install` (composer = administrador de paquetes para PHP) desde la
    raíz del repositorio de git. (Puedes añadir *--ignore-platform-reqs* si no
    tienes PHP-LDAP instalado localmente y no lo necesitas).
4.  Ejecuta `npm ci` (npm = administrador de paquetes para JavaScript, el parámetro "ci"
    significa "instalación limpia") desde la raíz del repositorio de git.
    (Nota: necesitas npm 10.1.0 o superior para esto.
    Ejecuta `npm install -g npm@lts` para actualizar tu versión de npm a la
    versión LTS).

Los usuarios de Linux y OSX pueden configurar el siguiente alias de bash colocando lo siguiente dentro del archivo *~/.bashrc*:

```
    alias jclean="rm -rf administrator/templates/atum/css; \
    rm -rf templates/cassiopeia/css; \
    rm -rf administrator/templates/system/css; \
    rm -rf templates/system/css; \
    rm -rf media/; \
    rm -rf node_modules/; \
    rm -rf libraries/vendor/; \
    rm -f administrator/cache/autoload_psr4.php; \
    rm -rf installation/template/css"
    alias jinstall="jclean; composer install; npm ci"
```


Esto eliminará todos los archivos compilados de tu sistema y ejecutará una instalación limpia como un solo comando al llamar a `jinstall` dentro de tu instalación de Joomla.

## Guía de inicio un poco más larga

Joomla es similar a muchas otras herramientas web actuales. Tiene una gran
parte en PHP y cada vez más código JavaScript. Aunque la programación en PHP no
necesita tanta preparación, JavaScript requiere muchas herramientas adicionales.
La razón principal es que nadie escribe código de una forma que todos los
navegadores entiendan, por lo que el código debe transpilarse, por ejemplo, de
ES6 a una versión compatible de JavaScript. Lo mismo ocurre con CSS. Para Joomla
usamos SASS, que se convertirá a CSS nativo para que cualquier navegador lo
entienda. Como desventaja, configurar un entorno de desarrollo es un poco más
complicado, pero las herramientas hacen que programar sea más cómodo. Gracias a
los observadores y a la recarga automática del navegador, puedes ver tus cambios
en tiempo real.

### PHP

Debería ser suficiente ejecutar `composer install`, ya que esto instalará las dependencias de PHP guardadas en el archivo *composer.lock*. Puede hacerlo tantas veces como desee. Solo instalará paquetes nuevos cuando se modifique el archivo *composer.lock*. No ejecute `composer update`, ya que esto actualizará todos los paquetes a versiones más recientes y actualizará el archivo *composer.lock*.

**Nota:** Es posible que deba ejecutar `composer install` con la opción `--ignore-platform-reqs` para ignorar los requisitos de plataforma especificados en Composer. Es decir, si no tiene instalada la extensión LDAP de PHP.

### Scripts de Node/npm

Node.js incluye un gestor de paquetes llamado NPM (en algunos aspectos, igual que Composer). NPM tiene un comando `run` y hemos preparado algunos scripts para facilitarle la tarea. Debe ejecutar los comandos en la raíz del repositorio cuando haya modificado archivos JS o SASS. Anteriormente, era necesario ejecutar `npm ci` una vez para instalar las dependencias.

#### npm run build:css (hasta Joomla 6.1)

Compilará los archivos SASS a CSS y también creará los archivos minimizados.

#### npm run build:js (hasta Joomla 6.1)

Compilará y transpilara los archivos JavaScript al formato correcto
y creará archivos minimizados.

#### A partir de Joomla 6.2, use los siguientes comandos:

- npm run build -- -n <extension> para volver a compilar una extensión específica
- ejecute npm run builders-list para encontrar el nombre de la extensión
- npm run build -- --all para volver a compilar todo

## Posibles problemas

Al ejecutar composer install, puedes encontrarte con estos errores:

```
    Problem 1
        - Installation request for joomla/ldap 2.0.0-beta -> satisfiable by joomla/ldap[2.0.0-beta].
        - joomla/ldap 2.0.0-beta requires ext-ldap * -> the requested PHP extension ldap is missing from your system.
    Problem 2
        - Installation request for symfony/ldap v5.1.5 -> satisfiable by symfony/ldap[v5.1.5].
        - symfony/ldap v5.1.5 requires ext-ldap * -> the requested PHP extension ldap is missing from your system.
```


La solución es ejecutar composer install con la opción
`--ignore-platform-reqs` para ignorar los requisitos de plataforma
especificados en Composer. Es decir, si no tienes instalada la extensión
LDAP de PHP.

```
    composer install --ignore-platform-reqs
```


Si recibes un error de inicio de sesión como el que se muestra a continuación, elimina
el archivo `administrator/cache/autoload_psr4.php`.

![pantalla de error de inicio de sesión de Joomla 4](../../../en/images/hosting-local/local-environment-setup/01-joomla-4-login-error-screen.png
)



*Traducido por openai.com*