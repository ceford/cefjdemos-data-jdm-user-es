<!-- Filename: How_do_you_put_a_module_inside_an_article%3F / Display title: Módulos dentro de Artículos  -->

## Introducción

Generalmente, querrás asociar módulos con artículos de alguna manera. Los módulos suelen asignarse a posiciones de módulo y estas posiciones aparecen en algún lugar de la página web, según lo determine la plantilla. Sin embargo, a veces es útil tener un módulo realmente incrustado dentro de un artículo. Joomla tiene un plugin llamado *Content - Load Modules* para hacer eso. Cuando está habilitado, un módulo puede ser incrustado en un artículo de tres maneras diferentes:

```
    {loadposition posición,[estilo]}
    {loadmodule tipo_de_modulo,título,[estilo]}
    {loadmoduleid idDelModulo}
```

Donde `estilo` es uno de los valores de Estilo de Módulo de la pestaña Avanzado del formulario de entrada de datos del módulo, por ejemplo, html, esquema, tabla, tarjeta o sinTarjeta.

## loadposition

Para insertar un módulo dentro de un artículo, publica el módulo en una posición y carga esa posición en el artículo de la siguiente manera:

1. Crea un módulo y configura su posición a ***myposition***. ***myposition*** puede ser cualquier valor que no entre en conflicto con una posición de plantilla existente. En el formulario de edición del módulo, escribe la posición ***myposition*** y presiona enter en lugar de seleccionarla de la lista desplegable.
2. Asigna el módulo a **Todos** los Ítems de Menú. Esto asegurará que siempre aparezca, sin importar cómo llegó el visitante al artículo. El módulo no se mostrará a menos que uses el comando para cargar el módulo en un artículo.
3. Edita el artículo e inserta el texto ***{loadposition myposition}*** en el lugar donde quieres que aparezca el módulo.

**Nota:** Si el plugin *Content - Load Modules* está deshabilitado, el texto *{loadposition myposition}* se mostrará sin cambios en el artículo. Además, el nombre de la posición debe estar en minúsculas. La CapitalizaciónCamel fallará.

## loadmodule

La sintaxis *{loadmodule yyy}* busca el primer módulo cuyo **tipo** coincide con la cadena 'yyy'. Por lo tanto, podrías cargar un módulo *mod_login* colocando {loadmodule login} en tu texto. ¡El tipo no es tan obvio! Por ejemplo, el Selector de Idiomas es de tipo **languages**. Para encontrar el tipo, necesitas revisar la lista de carpetas del módulo con un administrador/explorador de archivos y eliminar la parte *mod_* del nombre de la carpeta.

Si deseas cargar una instancia específica de un módulo, porque tienes más de un módulo de inicio de sesión, por ejemplo, titulado como Login 1, Login 2, etc., debes usar {loadmodule mod_modType, modTitle} donde **mod_modType** sería mod_login y **modTitle** sería el nombre/título dado a tu instancia de ese módulo. Así que en el ejemplo anterior terminarías con **{loadmodule mod_login Login 2}**.

También puedes agregar el estilo que se utiliza para representar el módulo. Para hacerlo, agrega el estilo como el tercer parámetro, como {loadmodule login,Login 2,xhtml}. Si no agregas un estilo, entonces no se utiliza ninguno.

## loadmoduleid

La sintaxis *{loadmoduleid z}* busca el módulo cuyo `id` coincide con el número `z`. Por lo tanto, podrías cargar el módulo con id 200 colocando *{loadmoduleid 200}* en tu texto. Esta variante no utiliza parámetros adicionales como el parámetro `style`.

## Botón del Editor

Si el plugin editor-xtd *Botón - Módulo* está activado, puedes usar el
botón del editor *Módulo* para insertar las etiquetas descritas arriba más fácilmente en
el texto del editor. La lista de Módulos tiene un botón en la columna de Título para insertar
por id y un botón en la columna de Posición para insertar por posición.

## Módulos dentro de Módulos

Es posible incluir un módulo dentro de un módulo *HTML Personalizado*. Son procesados por los plugins de contenido de la misma manera que los artículos.

Puede haber problemas de formato ya que el estilo del módulo *HTML Personalizado* rodeará el estilo del módulo incluido. Esa es la razón por la cual el botón del editor de *Módulo* no está disponible en los módulos de tipo *Personalizado*.

*Traducido por openai.com*

