<!-- Filename: Entering_raw_HTML_in_editors / Display title: Filtros HTML  -->

## Etiqueta HTML Textarea

En HTML, un campo de entrada de varias líneas se conoce como textarea. Cualquier texto entre las etiquetas de apertura y cierre se muestra como texto que puede contener marcado HTML. Ejemplo:
```
<textarea><p class="poem">El rápido zorro marrón<br>
salta sobre el perro perezoso.</textarea>
```
Editores, como TinyMCE o Code Mirror, usan JavaScript para superponer el textarea con una vista diferente que permite la entrada de datos WYSIWYG o el resaltado de sintaxis. El botón de alternar debajo de un campo del editor alterna entre la vista de textarea y la vista WYSIWYG.

Las vistas del editor se utilizan para el contenido de Artículos y algunos Módulos. Sin embargo, debes tener en cuenta que no todos los etiquetas y atributos HTML (como class="xyz") están permitidos para todos los usuarios. Algunos o todos pueden desaparecer cuando guardas el contenido de un campo de textarea o de edición.

Esto es causado por mecanismos de filtrado, ya sea en la Configuración Global de Joomla! o en la configuración del editor. Puedes evitar un filtro de editor seleccionando *Sin Editor* en la configuración de tu *Perfil de Usuario*. No puedes evitar los filtros globales, pero puedes cambiarlos para adaptarlos a los propósitos de tu sitio.

## Selección de Editor de Usuario

Puedes seleccionar uno de los editores disponibles, incluyendo Ninguno, desde tu Perfil de Usuario disponible a través del menú Cuenta de Usuario / Editar Perfil en la parte superior derecha de la pantalla del Administrador. El formulario Editar: Perfil contiene una pestaña de Configuración Básica con un campo para seleccionar un Editor. Normalmente está configurado como *- Usar Predeterminado -*, que usualmente es TinyMCE. Puedes seleccionar *Editor Ninguno*. Esto evitará cualquier filtrado de etiquetas y atributos HTML no permitidos por la configuración de TinyMCE.

**Advertencia:** si seleccionas *Editor - Ninguno* para crear contenido que contenga etiquetas HTML no permitidas por un filtro de editor y luego vuelves al editor predeterminado, deberás tener cuidado de no editar y guardar ese contenido nuevamente o perderás cualquier etiqueta y atributo filtrado. Es fácil hacerlo por error y no hay una advertencia.

## Configuración Global: Filtros de Texto

Desde el Panel de Control principal, selecciona Configuración Global y luego la pestaña de Filtros de Texto. La configuración predeterminada tiene *Sin HTML* seleccionado para los grupos de usuarios Invitado, Público y Registrado. Cualquiera de estos grupos podría tener la oportunidad de completar un campo de área de texto, por ejemplo, en un formulario de contacto que busca información adicional sobre un problema, por lo que la eliminación automática de todas las etiquetas HTML suele ser apropiada. Otros grupos, excepto los Super Usuarios, están restringidos por la Lista Prohibida Predeterminada. Los Super Usuarios no tienen filtros.

![configuración global de los filtros de texto](../../../en/images/configuration/global-configuration-filters-tab.png)

Las notas explican qué se incluye en la lista prohibida por defecto y cómo usar las otras listas.

## Configuración de TinyMCE para Filtros de Texto

Los editores se implementan como plugins en Joomla. El editor CodeMirror no tiene configuraciones de filtro de texto. Para personalizar el editor TinyMCE, búscalo y selecciónalo en la lista de plugins. A mitad de la larga lista de configuraciones, verás un campo etiquetado como *Usar Filtro de Texto de Joomla*, que está **Desactivado** por defecto. Los siguientes tres campos son:
* **Elementos Prohibidos**: una lista de etiquetas que siempre serán eliminadas. La lista por defecto de *script,applet,iframe* tiene preocupaciones de seguridad.
* **Elementos Válidos**: usa esta lista para limitar las etiquetas válidas a un subconjunto de todas las etiquetas HTML comunes. Ejemplo: `a[href|target=_blank],strong/b,div[align],br`
* **Elementos Válidos Extendidos**: usa esta lista para añadir un elemento al conjunto de reglas existentes por defecto o para modificar un elemento en el conjunto de reglas por defecto. Ejemplo: `img[class|src|border=0|alt|title|hspace|vspace|width|height|align|onmouseover|onmouseout|name]`

Consulta la Documentación de TinyMCE para más explicaciones.

Para omitir los filtros de texto de TinyMCE y usar los filtros de texto de Joomla, establece *Usar Filtro de Texto de Joomla* en **Activado**. Los tres campos adicionales descritos anteriormente desaparecen ya que no se utilizan.

