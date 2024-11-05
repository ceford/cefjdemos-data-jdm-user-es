<!-- Filename: jdocmanual?manual=user&heading=help&filename=administrator-help.md / Display title: Ayuda del Administrador -->

## Introducción

Casi todas las páginas del Administrador de Joomla tienen una Barra de Herramientas que contiene un botón de **Ayuda** cerca de la parte superior derecha de la página. Solo los Tableros carecen de una Barra de Herramientas y, por lo tanto, de un botón de Ayuda.

Muchas páginas también tienen un botón etiquetado como **Alternar Ayuda en Línea**. Esto simplemente muestra u oculta una descripción del campo si está disponible. Su propósito es reducir el desorden pero proporcionar un mecanismo de recordatorio donde esto sería útil. No se cubre más aquí.

El botón de **Ayuda** activa la apertura de una nueva ventana usando una URL incrustada en el botón. Un ejemplo:
```
data-url="https://help.joomla.org/proxy/index.php?keyref=Help51:Articles&lang=en"
```
En este caso, el contenido de la página de Ayuda proviene de una fuente externa.  

## La Fuente de Ayuda - un sitio de MediaWiki

MediaWiki es el software utilizado por Wikipedia. Es un paquete de Software Libre y de Código Abierto (FOSS) que utiliza PHP y MySQL, al igual que Joomla. Puedes descargarlo e instalarlo tú mismo. En teoría, podrías crear tu propio servidor de ayuda y utilizarlo en lugar del servidor de ayuda comunitario de Joomla. En la práctica, debes saber que las páginas de MediaWiki necesitan cierto procesamiento para que sean adecuadas para mostrarse como páginas de ayuda.

Ahí es donde entra en juego el **proxy**. Este obtiene la página requerida de la instalación de MediaWiki y la prepara para su visualización como una página de ayuda. Puedes ver una página original de MediaWiki en este ejemplo en https://docs.joomla.org/Help5.x:Articles y puedes editarla si ves algo incorrecto.

## La URL de Ayuda Global

El archivo **configuration.php** en la raíz de una instalación de Joomla contiene una variable `$helpurl`:

```
$helpurl = 'https://help.joomla.org/proxy/index.php?keyref=Help{major}{minor}:{keyref}&lang={langcode}';
```

Cuando se selecciona un botón de Ayuda, cada uno de los elementos entre llaves se reemplaza. Los valores {major} y {minor} son las configuraciones de versión para su instalación. El {langcode} es el código de su idioma de administrador actualmente seleccionado, que podría ser en, de o fr.

La variable {keyref} es el nombre de archivo de una página en el servidor de Ayuda, menos su espacio de nombres. Entonces, para la página de Artículos, el nombre de archivo relevante resulta ser *Articles*.

**Nota:** `https://docs.joomla.org/` es el sitio para editar páginas de Ayuda. Pero `https://help.joomla.org/proxy` es el sitio para recuperar páginas de Ayuda.

No hay una disposición para cambiar la URL predeterminada del servidor de Ayuda desde los formularios de Configuración Global del Administrador, pero puede cambiarla con un editor de texto.

La lista completa de códigos de sustitución disponibles es:

| Código        | Será sustituido por                                                            |
|---------------|--------------------------------------------------------------------------------|
| {app}         | Nombre de la aplicación (por ejemplo, "Administrator" en el backend de Joomla CMS)             |
| {component}   | Nombre del componente (por ejemplo, "com_content" en el Administrador de Artículos)          |
| {keyref}      | Referencia de clave de la pantalla de ayuda (después de pasar por el sistema de traducción)       |
| {major}       | Número de revisión mayor de Joomla (por ejemplo, "5" en Joomla 5.6).                       |
| {minor}       | Número de revisión menor de Joomla (por ejemplo, "1" en Joomla 5.1).                         |
| {maintenance} | Número de revisión de mantenimiento de Joomla (por ejemplo, "3" en Joomla 5.1.1).                  |
| {language}    | Código completo de idioma (por ejemplo, "en-GB")                                               |
| {langcode}    | Parte del código de idioma del tag de idioma (por ejemplo, "en" si el código completo es "en-GB") |
| {langregion}  | Parte del código de región del tag de idioma (por ejemplo, "GB" si el código completo es "en-GB")   |

## Ayuda global en el futuro

El uso de un sitio MediaWiki para ofrecer páginas de ayuda es algo así como una carga para aquellos que mantienen la documentación, y el procedimiento puede cambiar en el futuro. Si hay un cambio, es probable que la fuente consista en archivos HTML preconstruidos a los que se accede con un simple cambio del dominio de origen $helpurl.

## Componente Personalizado Ayuda Local

Si tienes un componente personalizado y te sientes cómodo editando código fuente PHP y creando contenido, puedes crear tus propias páginas de ayuda individuales. Toma el componente Jdocmanual como ejemplo. Como componente personalizado, no hay páginas de ayuda en el sitio MediaWiki docs.joomla.org. Los componentes de terceros no tienen permitido servir páginas de ayuda desde allí.

Echa un vistazo a este fragmento de código de administrator/components/com_jdocmanual/src/View/Manual/ViewHtml.php:
```
        $tmpl = $app->input->getCmd('tmpl');
        if ($tmpl !== 'component') {
            ToolbarHelper::help('jdocmanual', true);
        }
```
La especificación de la llamada a ToolbarHelper::help es la siguiente:
```
@param $ref: El nombre del archivo destino (excluyendo la extensión del archivo).
@param $useComponent: Usar el archivo de ayuda en el directorio del componente.
@param $url: Usar esta URL en lugar de cualquier otra.
@param $component: Nombre del componente para obtener Ayuda (nulo para el componente actual)
function Toolbar::help(
    string $ref,
    bool $useComponent = false,
    string $url = null,
    string $component = null
): HelpButton
Escribe un botón de ayuda para una opción dada (abre una ventana emergente).
```
En este ejemplo, **$ref** es un nombre de archivo a usar, en este caso `'jdocmanual'` (debe coincidir con el caso del archivo objetivo) y **$useComponent** es `true`, lo que significa que la página de ayuda a usar se localizará dentro de los archivos del componente en administrator/component/com_jdocmanual/help/en-GB/jdocmanual.html

Usar un archivo de ayuda dentro del componente debería garantizar que nunca falte la Ayuda y tal vez siempre esté actualizada.

## Ayuda Remota para Componente Personalizado

Al crear el botón de Ayuda, puedes establecer $useComponent = false y fijar
la URL para que apunte a una ubicación específica en tu propio sitio o en un sitio remoto.

```
    ToolbarHelper::help('jdocmanual', false, 'http://example.com/help/en-GB/jdocmanual.html');
```

Así que todo lo que se necesita es una página HTML con el nombre correcto en el lugar correcto.

*Traducido por openai.com*

