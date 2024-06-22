<!-- Filename: How_do_you_put_a_module_inside_an_article%3F / Display title: ¿Como se puede poner un módulo dentro de un artículo? -->

Joomla!  <span class="small">≥ </span>2.5 series

Normalmente, se quiere asociar de alguna manera, los módulos con los
artículos. Los módulos son asignados a las posiciones de los módulos y
las posiciones de los módulos aparecen en algún lugar de la página Web
según lo determinado por la plantilla. Sin embargo, a veces es útil
tener un módulo incrustado dentro de un artículo. El núcleo de Joomla!
proporciona dos maneras de hacerlo: *loadposition* y *loadmodule*.

Sintaxis:

- {loadposition position,\[style\]}
- {loadmodule mod_type,the title,\[style\]}
- {loadmoduleid moduleId}

### loadposition

Para insertar un módulo dentro de un artículo, se publica el módulo en
una posición y se carga la posición en el artículo de la siguiente
manera:

1.  Crea un módulo y establecer su posición de ***miposicion***.
    ***miposicion*** puede ser cualquier valor que no entre en conflicto
    con una posición existente en la plantilla. Escribe en la posición
    ***miposicion*** y pulsa enter en lugar de seleccionar de la lista
    desplegable.
2.  Asigna el módulo a **Todos** los Ítems del Menú. Esto asegurará que
    siempre aparecera, no importa cómo el visitante accedió al artículo.
    El módulo no se mostrará a menos que se ponga el comando para cargar
    el módulo en un
    artículo.
3.  Edita los artículos donde deseas que este módulo aparezca e insertar
    ***{loadposition miposicion}*** en el texto del artículo en el lugar
    donde deseas que el módulo quede posicionado.

\*Ten en cuenta que esto sólo funciona cuando el [Plugin *Contenido -
Cargar Módulo* está
habilitado](https://docs.joomla.org/Help25:Extensions_Plugin_Manager_Edit#Content_-_Load_Modules "Special:MyLanguage/Help25:Extensions Plugin Manager Edit").
Si este plugin está deshabilitado, el texto *{loadposition miposicion}*
no muestra cambios en el artículo. También, el nombre de la posición
debe estar en minúsculas. Fallará com Mayúsculas/minúculas.

### loadmodule

Una alternativa a "{loadposition xx}" "{loadmodule yyy}" variación que
es manejada por el mismo plugin.

En este caso el plugin busca el primer módulo cuyo **tipo** coincide con
la cadena 'yyy'. Por lo tanto, puedes cargar el módulo "mod_login"
colocando {loadmodule login} en el texto. Si deseas cargar una instancia
específica de un módulo, debido a que tienes más de un módulo de inicio
de sesión, por ejemplo: titulados como Login1, Login2, etc. Tienes que
usar {loadmodule mod_modType, modTitle} donde mod \_**modType** sería
mod_login y **modTitle** es el nombre/título dado a su instancia de ese
módulo. Así que en el ejemplo anterior terminas con **{loadmodule
mod_login Login 2}**. También puedes agregar un estilo que se utiliza
para representar el módulo. Para ello se agrega el estilo como el tercer
parámetro como en {loadmodule login,login2,xhtml}. Si no agregas un
estilo se usará "none".

## loadmoduleid

Since Joomla! version 3.9.0 an alternative to `{loadposition xx}` and
`{loadmodule yyy}` is the variation `{loadmoduleid z}` which is handled
by the same plugin.

In this case the plugin looks for the module who's `id` matches the
number `z`. So you could load the module with id 200 by placing
`{loadmoduleid 200}` in your text. This variant does not "understand"
additional parameters like the `style` parameter.

## Editor Button (since Joomla! version 3.5)

If the editor-xtd plugin "Button - Module" is activated you can use the
editor button "Module" to insert above described tags more easily into
the editor text. Since Joomla! 3.9 also the `loadmouleid` variant.

### Módulos dentro de Módulos

En Joomla! 2.5+ y Joomla! 3.x+ es
posible incluir un módulo dentro de un módulo "HTML Personalizado". Que
son procesados por los plugins de contenido de la misma manera que los
artículos.

Para realizar este trabajo, la opción **Preparar el contenido** debe
estar habilitada como se muestra en esta captura de pantalla:

<img
src="https://docs.joomla.org/images/4/48/J3x_custom_html_prepare_content_option-es.png"
decoding="async" data-file-width="635" data-file-height="300"
width="635" height="300"
alt="Mostrando la opción Preparar el Contenido en un módulo HTML Personalizado." />

Debes recordar que cuando se hace esto podrías experimentar problemas de
formato como el "chrome" del módulo "HTML Personalizado" que rodea al
"chrome" del módulo incluido puede tener potenciales efectos indeseables
del formato o diseño.
