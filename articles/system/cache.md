<!-- Filename: Cache / Display title: Caché  -->

## Para Administradores

Como administrador, Joomla te ofrece la capacidad de almacenar en caché partes de tu sitio. Puedes elegir almacenar en caché páginas web enteras o solo partes de esas páginas. Esta guía explica cómo hacerlo.

En una página web de un sitio Joomla, hay 3 cosas que pueden ser almacenadas en caché:

1. La página completa en sí misma – la cache de Página
2. La salida del componente Joomla para esa página web – conocida como la cache de Vista
3. La salida de los módulos mostrados en esa página – conocida como la cache de Módulo

Tienes varias configuraciones de caché que te permiten controlar qué se almacena en caché:

1. El plugin del sistema "Sistema – Cache de Página"
2. La Configuración Global, pestaña Sistema, Configuración de Cache. Aquí la opción de Cache del Sistema se puede configurar en:
   - OFF – Caché desactivado
   - ON – Caché conservadora
   - ON – Caché progresiva
3. Muchos módulos dentro de sus opciones tienen una pestaña Avanzada en la que el cache puede configurarse para *Usar global* o *Sin caché*

Como se describe a continuación, también existen reglas para el almacenamiento en caché que están implementadas dentro del código de Joomla, y sobre las cuales no tienes control.

Puedes limpiar el caché mediante la selección del menú Administrador → Sistema → Limpiar Caché. En general, puedes considerar que Joomla tiene 3 niveles de caché, aumentando en agresividad:

1. Caché conservadora
2. Caché progresiva
3. Caché de página

Además, los desarrolladores de Joomla pueden utilizar las capacidades de caché para almacenar el resultado de las consultas a la base de datos, por ejemplo, para aumentar la capacidad de respuesta del sitio, pero esto está fuera del alcance de las capacidades del Administrador.

## Almacenamiento en caché de páginas

Para activar esto, vaya a Administrador → Extensiones → Plugins. Luego, busque el plugin Sistema - Caché de Página y actívelo. Esto significa que las páginas del sitio ahora se almacenarán en caché y, cada vez que se soliciten de nuevo, se servirá la página almacenada en caché en lugar de ser generada por Joomla a partir de la información en la base de datos. La página en caché seguirá sirviéndose hasta que venza, según lo definido por el parámetro *Tiempo de Caché* en el panel Administrador → Configuración Global → Pestaña Sistema → Configuración de Caché.

Si está leyendo esta página como un tutorial y desea probar el almacenamiento en caché de páginas, es mejor configurar los ajustes de caché en Configuración Global de la siguiente manera:

- Controlador de Caché – Archivo
- Ruta a la Carpeta de Caché – dejar en blanco
- Tiempo de Caché – 15 (el valor predeterminado de 15 minutos)
- Caché Específica para Plataforma - No
- Caché del Sistema – DESACTIVADO – Caché deshabilitada

Para verificar que el almacenamiento en caché de páginas está funcionando, vaya a una página del sitio web que muestre un artículo. Después de mostrar esa página, debería encontrar en el sistema de archivos un directorio `cache/page` con un archivo dentro que tenga un nombre como `xxx-cache-page-yyy.php`, donde xxx y yyy son largas cadenas hash. Joomla tiene que almacenar páginas de caché separadas para URL separadas, por lo que la segunda cadena de dígitos hexadecimales es un hash de la URL de la página web del sitio, para hacer que el nombre del archivo sea único para esa página.

Luego, utilice la funcionalidad del Administrador para cambiar el texto de ese artículo y vuelva a mostrar la página web del sitio. Debería encontrar la versión en caché, no su texto modificado.

Cambiar un artículo (u otro elemento de Joomla) no borra la caché de la página para la(s) página(s) web donde se muestra ese artículo. Para borrar la caché de la página, vaya a Administrador → Sistema → Limpiar Caché. Haga clic en la casilla de verificación junto al *Grupo de Caché* llamado "página" y presione el botón Eliminar. Cuando vuelva a mostrar su página web, ahora debería mostrar su texto enmendado.

Si su sitio tiene una función como un carrito de compras, aplicar el almacenamiento en caché de páginas causará problemas, ya que las páginas deben mostrar lo que el cliente ya ha seleccionado, en lugar de mostrar una página en caché que es común para todos. Sin embargo, puede configurar el plugin Sistema - Caché de Página para excluir del almacenamiento en caché elementos de menú específicos o URL y rangos de URL especificados (en la pestaña Avanzado), de modo que solo se almacenen en caché las páginas verdaderamente estáticas.

## Caché Conservador

Con el Caché Conservador, puedes almacenar en caché la salida de Vista de componentes y la salida de aquellos Módulos que permiten el caché. Pero ten en cuenta que esto funcionará solo en las páginas que no están en caché usando el Caché de Página. Para esas páginas, toda la página web está en caché, y el Caché Conservador ni siquiera se considera.

Para activar el Caché Conservador:

1. Ve a Administrador → Sistema → Configuración Global → pestaña Sistema y dentro de Configuración de Caché, establece Caché del Sistema en ACTIVADO – caché conservador.
2. Ve a Administrador → Extensiones → Módulos y selecciona los módulos que te gustaría que se almacenen en caché. Si ese módulo permite caché, bajo la pestaña Avanzada deberías poder establecer la opción de Caché a

   - Usar Global – este módulo será almacenado en caché (con la opción Global ahora configurada a caché conservador)
   - Sin caché – este módulo no será almacenado en caché.

(Ten en cuenta que el Tiempo de Caché en la Configuración Global está en minutos, pero el Tiempo de Caché en la configuración del Módulo está en segundos.)

Para comprobar que está funcionando, visita tu sitio, **asegúrate de estar desconectado**, y navega a una página web que muestre un artículo. Revisa tu sistema de archivos y deberías encontrar una carpeta `cache/com_content` que contiene un archivo de caché.

También encontrarás otros directorios como `cache/com_languages` (ya que mostrar la página implica cargar el idioma actual, y esto también se almacenará en caché), y también directorios relacionados con el caché de módulos, por ejemplo, `cache/com_modules`. Estos son el resultado del uso de caché que los desarrolladores han codificado dentro de la aplicación Joomla.

Si editas y guardas ese artículo y luego actualizas la página del sitio, encontrarás que el sitio muestra el texto actualizado esta vez. Esto se debe a que cada vez que se guarda la edición, Joomla borra el caché para ese artículo.

Sin embargo, puedes demostrar que el caché está funcionando si editas el archivo de caché en el directorio `cache/com_content` usando un editor de texto básico. Usando el editor, cambia una letra dentro del texto del artículo en el archivo de caché y guarda el archivo. Luego, cuando actualices la página web, deberías ver el cambio que hiciste en el archivo de caché.

¿Cómo puedes seleccionar qué vistas de componentes se almacenan en caché y bajo qué circunstancias? Lamentablemente, no puedes hacer esto. Esto está determinado por los desarrolladores del componente central de Joomla y codificado en el código PHP del componente. Los criterios son diferentes para cada componente. Sin embargo, puedes descubrir fácilmente qué criterios se utilizan porque para cada uno de los componentes del sitio están codificados en el archivo `DisplayController.php` del sitio. Por ejemplo, en el momento de esta revisión (versión 5 de Joomla) para el componente de Contactos encontramos en `components/com_contact/src/Controller/DisplayController.php`

```php
    public function display($cachable = false, $urlparams = [])
    {
        if ($this->app->getUserState('com_contact.contact.data') === null) {
            $cachable = true;
        }
```

Esto significa que las vistas asociadas con contactos serán almacenables en caché a menos que haya datos de sesión clave por com_contact.contact.data – lo cual será el caso si en la sesión del usuario el usuario ha mostrado un formulario de contacto (por ejemplo, en una página señalada por un elemento de menú de tipo Contactos → Contacto Único).

El archivo equivalente para artículos `components/com_content/src/Controller/DisplayController.php` contiene:

```php
    public function display($cachable = false, $urlparams = false)
    {
        $cachable = true;

        /**
         * Establecer el nombre de vista predeterminado y el formato desde la Solicitud.
         * Nota que estamos usando a_id para evitar colisiones con el enrutador y la página de retorno.
         * El frontend es un poco más desordenado que el backend.
         */
        $id    = $this->input->getInt('a_id');
        $vName = $this->input->getCmd('view', 'categories');
        $this->input->set('view', $vName);

        $user = $this->app->getIdentity();

        if (
            $user->get('id')
            || ($this->input->getMethod() === 'POST'
            && (($vName === 'category' && $this->input->get('layout') !== 'blog') || $vName === 'archive'))
        ) {
            $cachable = false;
        }
```

La expresión `$user->get('id')` es verdadera si se trata de un usuario que ha iniciado sesión. Esto significa que los artículos nunca se almacenan en caché para los usuarios que han iniciado sesión. Las expresiones subsiguientes se relacionan con otras condiciones cuando el almacenamiento en caché no se realiza, incluso si el usuario no ha iniciado sesión.

De esta manera, puedes descubrir las circunstancias bajo las cuales se realiza el almacenamiento en caché, pero no es recomendable cambiar esto. También puedes demostrar que los módulos están siendo almacenados en caché al usar el módulo Breadcrumbs de Joomla, asegurándote de que se muestre en alguna posición del módulo en la página web, configurando su opción de Caché y editando manualmente el archivo almacenado en caché en cache/mod_breadcrumbs.

## Caché Progresivo

Al igual que el Caché Conservador, el Caché Progresivo también almacena en caché la salida de las vistas de componentes y de los módulos. La diferencia funcional entre los dos es que con el Caché Progresivo **para usuarios desconectados todos los módulos siempre se almacenan en caché**. En este caso, configurar la opción *Sin Caché* para un módulo no tiene efecto. Si la opción de almacenamiento en caché está configurada como *Archivo*, puedes encontrar el archivo de caché de los módulos (la salida de todos los módulos se almacena dentro del mismo archivo) dentro del directorio `cache/com_modules`.

Para activar el Caché Progresivo, ve a Administrador → Sistema → Configuración Global → pestaña Sistema y dentro de *Configuración del caché* establece *Caché del sistema* en *ACTIVADO – Caché progresivo*.

En cuanto a las condiciones para el almacenamiento en caché de las vistas del componente principal de Joomla, **no hay diferencia entre el caché conservador y el cache progresivo**. A pesar de lo que puedas leer en algunos sitios web y respuestas a preguntas en Stack Overflow, no es cierto que el Caché Conservador se relacione con cuando el usuario no está conectado y el Caché Progresivo con cuando el usuario está conectado.

## Resumen

A continuación se ofrece un resumen de los tipos de caché.

### Caché de página completa

- **Configuración**: Plugin incorporado (Administrador → Extensiones → 
  Administrador de Plugins → Sistema - Caché de Página)
- **Caché**: cada página completa de tu sitio
- **Basado en**: URL
- **Más información**:
  - Caché opcional del navegador: También se almacena en caché en el navegador/computadora de tus visitantes
  - Solo guarda en caché las páginas para visitantes no registrados (no para visitantes registrados). 
    Ten cuidado al usar este plugin si tienes un sitio interactivo donde 
    deseas servir contenido basado en la información de sesión/cookies 
    en lugar de solo en la URL simple. Funciones como un carrito de compras 
    no funcionarán.

### Caché de vistas

- **Configuración**: Configuración Global → Caché
- **Caché**: cada vista de un componente
- **Basado en**: URL, vista, parámetros, ...
- **Más información**: Los desarrolladores de componentes deben incluir esto en su 
  código para que funcione. La mayoría de las veces esto no se hace. 
  El componente principal de contenido de Joomla lo utiliza, pero solo 
  para visitantes no registrados en tu sitio, aunque no es obligatorio 
  para cada componente.

### Caché de módulos

- **Configuración**: Configuración Global → Caché
- **Caché**: cada módulo (personalizado individualmente a través de los parámetros 
  avanzados de cada módulo)
- **Basado en**: el id del módulo, los niveles de vista del usuario y el 
  parámetro *Itemid* en la solicitud HTTP
- **Más información**: Debes deshabilitarlo en algunos módulos para evitar problemas

### Cachés adicionales

Si deseas explorar otros sistemas de caché y posibilidades, 
puedes echar un vistazo a las extensiones de terceros relacionadas con la caché.

### Motores o almacenamientos de caché

- **Configuración**: Configuración Global → Caché

Aquí puedes elegir qué sistema deseas que use tu sitio para todos 
los cachés. Algunas opciones son: APC, Eaccelorator, Archivo, Memcache, Redis, 
XCache.

APC, por ejemplo, también almacena en caché tu opcode de PHP.

## Para Desarrolladores

<div class="alert alert-warning">
Esta sección necesita revisión para Joomla! 4/5.
</div>

La clase **JCache** permite una gran variedad de tipos y niveles de almacenamiento en caché. Las siguientes subclases están hechas específicamente, pero puedes añadir las tuyas o usar la principal de muchas maneras diferentes.

No olvides que el primer nivel de caché que se encuentra, anulará cualquier almacenamiento en caché más profundo. Supongo que demasiados niveles también son contraproducentes (*sin embargo, hay que verificarlo*).

- **JCacheView** almacena en caché y devuelve la salida de una vista específica (en MVC). Un id de caché se genera automáticamente a partir del URI, la vista específica y su método específico, o puedes proporcionar el tuyo propio.

Esto puede hacerse automáticamente a través de la función de visualización del controlador base. Por ejemplo, en el controlador de tu componente:

```php
class DeliciousController extends JController {
    function display() {
        parent::display(true); // true solicita almacenamiento en caché.
    }
}
```

También hay algunos urlparams a considerar. Revisa este
[Joomla StackExchange](http://joomla.stackexchange.com/questions/5781/how-can-i-use-joomlas-cache-with-my-components-view/7000#7000 "")

Además, ten en cuenta que cualquier actualización (como conteos de visitas o impactos) NO se actualizará (a menos que añadas esto fuera de este método y, por lo tanto, cualquier parte más profunda del MVC).

- **JCachePage** almacena en caché y devuelve el cuerpo de la página.
- **JCacheCallback** almacena en caché y devuelve la salida y resultados de funciones o métodos.

Si deseas almacenar en caché consultas, esta es una buena clase para ello, como se ilustra aquí: Usando el almacenamiento en caché para acelerar tu código

- **JCacheOutput** almacena en caché y devuelve la salida.

Esto está destinado más bien a almacenar en caché una parte específica del código PHP. Actúa como un buffer de salida, pero en caché.

*Traducido por openai.com*

