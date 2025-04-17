<!-- Filename: J3.x:Adding_custom_fields/Overrides / Display title: Ejemplo de Anulación de  Plantilla -->

## Visualización Automática de Campos

Cada uno de los campos disponibles tiene una opción denominada *Visualización Automática*, que se puede establecer en una de las siguientes opciones:

* Después del Título
* Antes del Contenido a Mostrar
* Después del Contenido a Mostrar
* No mostrar automáticamente

Si se selecciona el último de estos elementos, entonces el campo no se mostrará a menos que crees una anulación de plantilla para gestionar la visualización tú mismo. O podrías añadir `{ID del campo}` en un artículo para colocar el campo donde desees. Pero debes recordar hacer esto en cada artículo.

Este ejemplo muestra cómo crear una anulación de plantilla para un Contacto. Los métodos también se aplican a los componentes de Contenido y Usuario.

## Crear una Anulación de Plantilla

Desde el menú de Administrador:

* Seleccione **Sistema / Plantillas del Sitio / Detalles y Archivos de Cassiopeia**
* Seleccione la pestaña **Crear Anulaciones**.
* Seleccione **com_contact** del panel de *Componentes*.
* Seleccione **Contacto** de la lista de vistas disponibles. Este es el diseño para un solo contacto.

En el panel **Editor**:
* Seleccione **html / com_contact / contact / default.php**, que es el archivo que configura el diseño general de la página de contacto único.
* Desplácese hacia abajo en este archivo y observe una serie de bloques `<php if (...) : ?>`. Cada uno mostrará u ocultará una sección de texto dependiendo de la configuración del contacto.
* Observe las líneas que contienen
```
    <?php echo $this->item->event->afterDisplayTitle; ?> (línea 73)
    <?php echo $this->item->event->beforeDisplayContent; ?> (línea 98)
    <?php echo $this->item->event->afterDisplayContent; ?> (línea 189)
```
Una de estas variables, o ninguna de ellas, se llena dependiendo del valor del campo de Visualización Automática.

## Usar campos en tu sobreescritura

Tienes todos los campos correspondientes al elemento actual accesibles a través de la propiedad `$this->item->jcfields`, que es un array que contiene los siguientes datos para cada campo (este ejemplo es para un campo de Editor):

```php
    Array
    (
        [4] => stdClass Object
            (
                [id] => 4
                [title] => editor-de-artículo
                [name] => editor-de-artículo
                [checked_out] => 0
                [checked_out_time] => 0000-00-00 00:00:00
                [note] =>
                [state] => 1
                [access] => 1
                [created_time] => 2017-04-07 12:08:59
                [created_user_id] => 856
                [ordering] => 0
                [language] => *
                [fieldparams] => Joomla\Registry\Registry Object
                    (
                        [data:protected] => stdClass Object
                            (
                                [buttons] =>
                                [width] =>
                                [height] =>
                                [filter] =>
                            )

                        [initialized:protected] => 1
                        [separator] => .
                    )

                [params] => Joomla\Registry\Registry Object
                    (
                        [data:protected] => stdClass Object
                            (
                                [hint] =>
                                [render_class] =>
                                [class] =>
                                [showlabel] => 1
                                [disabled] => 0
                                [readonly] => 0
                                [show_on] =>
                                [display] => 2
                            )

                        [initialized:protected] => 1
                        [separator] => .
                    )

                [type] => editor
                [default_value] =>
                [context] => com_content.article
                [group_id] => 0
                [label] => editor-de-artículo
                [description] =>
                [required] => 0
                [language_title] =>
                [language_image] =>
                [editor] =>
                [access_level] => Público
                [author_name] => Súper Usuario
                [group_title] =>
                [group_access] =>
                [group_state] =>
                [value] => Bar
                [rawvalue] => Bar
            )
    )
```

## Representar el campo

La función `FieldsHelper::render()` se utiliza para renderizar cada campo. Primero, añade una declaración `use Joomla\Component\Fields\Administrator\Helper\FieldsHelper;` a la lista de declaraciones `use` en la parte superior del archivo de sobreescritura:

```php
defined('_JEXEC') or die;

use Joomla\CMS\Helper\ContentHelper;
use Joomla\CMS\HTML\HTMLHelper;
use Joomla\CMS\Language\Text;
use Joomla\CMS\Layout\FileLayout;
use Joomla\CMS\Layout\LayoutHelper;
use Joomla\CMS\Plugin\PluginHelper;
use Joomla\CMS\Router\Route;
use Joomla\Component\Contact\Site\Helper\RouteHelper;
use Joomla\Component\Fields\Administrator\Helper\FieldsHelper;
```

Luego, donde desees colocar los campos en tu plantilla, utiliza el siguiente código:
```php
<?php foreach ($this->item->jcfields as $field) : ?>
    <?php echo FieldsHelper::render($field->context, 'field.render', array('field' => $field)); ?><br>
<?php endforeach ?>
```

O para una sobreescritura sin formato, que no traduce la etiqueta:

```php
<?php foreach ($this->item->jcfields as $field) : ?>
    <?php echo $field->label . ':' . $field->value; ?><br>
<?php endforeach ?>
```

## Cargando campos individuales

Para añadir campos individuales a tu contenido, comienza eligiendo nombres específicos para tus campos personalizados, utilizando el campo **Nombre**, que se utilizará para referenciar tu campo directamente en el código de sobreescritura. En la pestaña `Opciones`, selecciona **No** en el campo `Despliegue Automático` para evitar que se muestre automáticamente en cualquiera de las posiciones estándar.

Luego, para habilitar el acceso directo por nombre a los campos personalizados en una sobreescritura, coloca el siguiente código al principio de tu archivo. Debes hacer esto en cada archivo PHP de sobreescritura en el que quieras colocar campos personalizados individuales.

```php
<?php foreach($this->item->jcfields as $jcfield) {
    $this->item->jcFields[$jcfield->name] = $jcfield;
} ?>
```

Y por último, deberías añadir el código de colocación de campo en el lugar donde quieras que se muestre la etiqueta o el valor del campo.

Para añadir la **etiqueta** del campo a tu sobreescritura, inserta el código siguiente, reemplazando `name-of-field` con el nombre del campo.

```php
<?php echo $this->item->jcFields['name-of-field']->label; ?>:&nbsp;
```

Para añadir el **valor** del campo a tu sobreescritura, inserta el código siguiente, reemplazando `name-of-field` con el nombre del campo.

```php
<?php echo $this->item->jcFields['name-of-field']->rawvalue; ?>
```

Puedes añadir este código a cualquier parte de tu sobreescritura. Ejemplos: El contenido de un div, el src en una etiqueta `img`, dentro de un atributo de clase CSS, etc.
