<!-- Filename: Debugging_a_translation / Display title: Depurar una traducción -->

<img
src="https://docs.joomla.org/images/thumb/6/69/Split-icon.png/25px-Split-icon.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/6/69/Split-icon.png/38px-Split-icon.png 1.5x, https://docs.joomla.org/images/thumb/6/69/Split-icon.png/50px-Split-icon.png 2x"
data-file-width="200" data-file-height="67" width="25" height="8"
alt="Split-icon.png" />Split Page into Specific Joomla! Versions - J2.5
and 3.x

It has been suggested that this article or section be split into
specific version
*Namespaces*.
(<a
href="https://docs.joomla.org/index.php?title=Talk:Debugging_a_translation/es&amp;action=edit&amp;redlink=1"
class="new"
title="Talk:Debugging a translation/es (page does not exist)">Discuss</a>).
If version split is not obvious, please allow split request to remain
for 1 week pending discussions. <span class="small">*Proposed since **2
years ago***.</span>


Joomla! es compatible con algunosmecanismos de depuración útiles que
pueden facilitar la localización de cadenas sin traducir y diagnosticar
los problemas con las traducciones en las extensiones instaladas.

#### Depurar el Idioma

<img
src="https://docs.joomla.org/images/thumb/a/ac/Global-config-language-debug-es.png/250px-Global-config-language-debug-es.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/a/ac/Global-config-language-debug-es.png/375px-Global-config-language-debug-es.png 1.5x, https://docs.joomla.org/images/a/ac/Global-config-language-debug-es.png 2x"
data-file-width="410" data-file-height="152" width="250" height="93"
alt="Global-config-language-debug-es.png" />

Activa la depuración del idioma a través de la Administración del Lado
Servidor, entra en Configuración Global y has clic en la pestaña
Sistema. Encuentra el campo la Depuración de Idioma, cambia el valor a
"Sí" y guardar los cambios.

Con esta opción activa todas las cadenas traducibles se muestra rodeado
de caracteres especiales que indican su estado

|                    |                                                                                                                                                                               |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Código             | Estado                                                                                                                                                                        |
| \*\*Joomla CMS\*\* | *(El texto rodeado por asteriscos)* indica que la *clave* ha sido encontrada en el archivo de definición de idioma y la cadena *valor* ha sido traducida.                     |
| ??Joomla CMS??     | *(texto rodeado por pares de signos de interrogación)* indica que la cadena es traducible, pero no se encontró concordancia de *clave* en el archivo de definición de idioma. |
| Joomla CMS         | *(texto sin caracteres adyacentes)* indica que la cadena no es traducible.                                                                                                    |

#### Depurar el Sistema

Información adicional para depuración del idioma puede ser obtenida
mediante la activación de la depuración del sistema. Esto se hace yendo
a la Configuración Global y has clic en la pestaña Sistema. Encuentra el
campo Depuración del Sistema, cambia el valor a "Sí" y guarda los
cambios.

Con esta opción activa todas las pantallas tienen información de
depuración adicional al final de cada página. Actualmente, esto incluye

- **Información del perfil.** Esta el tiempo necesario para ejecutar
  código en diferentes puntos marcados en el código.
- **Uso de la memoria.** La cantidad de RAM del sistema utilizada.
- **Consultas SQL ejecutadas.** Todas las consultas SQL ejecutadas en el
  proceso de construcción de la página.
- **Archivos de idioma cargados.** Una lista de todos los archivos de
  idioma cargado en el proceso de construcción de la página, incluyendo
  la información de la ruta de acceso completa. Esto puede ser útil para
  comprobar que los archivos se han cargado. El número después de cada
  ruta de acceso del archivo es el número de veces que se hace
  referencia al archivo.
- **Diagnóstico de cadenas no traducidas.** Una lista de todas las
  cadenas sin traducir encontradas y la probable ubicación del archivo
  donde **JText** realizó la llamada.
- **Diseño de las cadenas no traducidas.** Una lista de todas las
  cadenas sin traducir pero aparece en un formato CLAVE=Valor, de manera
  que se pueda copiar y pegar directamente en un archivo de definición
  de idioma (INI).

#### Depurar los Plugin

<img src="https://docs.joomla.org/images/c/c2/Debug-plugin-es.png"
decoding="async" data-file-width="580" data-file-height="455"
width="580" height="455" alt="Debug-plugin-es.png" />

Este plugin del sistema controla lo que se muestra cuando la depuración
está activada en **Configuración Global**. Está activado por defecto.
Puedes acceder a los parámetros del plugin en **Extensiones → Gestor de
plugins**. Busque el plugin "Sistema - Depurador" y has clic en él. Hay
tres opciones de interés para los traductores.

- **Mostrar archivos de idioma**. Si se establece en "Sí", a
  continuación, la información de depuración incluye una lista de los
  archivos de idioma que se intentaron cargar cuando la página actual se
  generó.
- **Mostrar cadenas de idioma.** Si se establece en "modo de
  diagnóstico", a continuación, una lista de cadenas sin traducir y la
  ubicación del archivo que contiene la llamada a "'JText"' se incluye
  en la información de depuración. Si se establece en "modo de
  diseñador", a continuación, una lista de cadenas sin traducir en un
  formato que se puede copiar y pegar directamente en un archivo de
  definición de idioma se incluye en la información de depuración. Es
  decir, se muestra la lista en formato CLAVE=Valor. Si se establece a
  "Todos los modos", a continuación, tanto las listas en modo de
  diagnóstico y diseñador se incluyen en la información de depuración.
- **Quitar la primera palabra.** Sólo se utiliza cuando "'Mostrar
  cadenas de idioma"' está establecido en "modo Diseñador" o "Todos los
  modos". Esto permite que usar un prefijo de la cadena para formar la
  clave. Esto es útil si el diseñador utiliza un prefijo común para sus
  extensiones al usar métodos **JText**. Ver el ejemplo de abajo.

Ten en cuenta que la pantalla de cadenas sin traducir sólo mostrará el
valor pasado al adecuado método **JText**. Por ejemplo, con el siguiente
código:

    echo JText::_( 'Reports Import Configuration' );

Si no es traducida, Diseñador de modo mostrará esto:

    # /administrator/components/com_reports/views/reports/tmpl/default.php
    REPORTS IMPORT CONFIGURATION=Reports Import Configuration

Si la Quitar la primera palabra se establece en "Informes", a
continuación, la pantalla podría cambiar ligeramente a:

    # /administrator/components/com_reports/views/reports/tmpl/default.php
    REPORTS IMPORT CONFIGURATION=Import Configuration

Ten en cuenta que la ruta que se muestra es sólo una conjetura basada en
una llamada a la función "debug_backtrace" de PHP. A veces es preciso, a
veces no lo es y también hay casos donde no se puede determinar. En esos
casos, tienes que utilizar tu mejor juicio.
