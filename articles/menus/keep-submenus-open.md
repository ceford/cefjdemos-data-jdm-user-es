<!--
{
    "source": "https://docs.joomla.org/https:",
    "title": "Mantener abiertos los submen\u00fas",
    "description": " ",
    "author": ""
}
-->

Un módulo de menú se puede utilizar para mostrar un menú horizontal (normalmente en la parte superior de la página) o un menú vertical (normalmente en una barra lateral, a la izquierda o a la derecha). En un menú horizontal (superior) no es deseable mantener abierto el submenú. Por eso, el comportamiento predeterminado de un módulo de menú es cerrar los submenús al cargar la página.

## Alternar el comportamiento de estado *abierto*

Sin embargo, en un menú vertical (de barra lateral), a menudo es deseable dejar abierto un submenú cuando contiene el elemento de menú activo. En Joomla 6.0 se introdujo una nueva clase CSS, `nav-active-open`, específicamente para permitir controlar si los submenús se abren automáticamente al cargar la página para el elemento de menú activo. Al establecer esta clase ahora es posible lograrlo. La clase se establece en el módulo mediante el panel de administración.

![configuración de la clase del menú en el panel de administración para nav-active-open para mantener abierto el alternador en el menú activo](../../../en/images/menus/keep-submenus-open/01-menu-class-setting.png)

## Cómo crear un menú de barra lateral sin alternador desplegable

Si desea mantener abiertos todos los submenús, no necesita un alternador desplegable. En su lugar, utilice una [anulación de plantilla](jdocmanual?article=user/templates/template-overrides).

Así se realiza esta anulación de plantilla específica:

1. Comience seleccionando Sistema → Plantillas → Plantillas del sitio en el menú del administrador y, a continuación, seleccione el elemento Detalles y archivos de Cassiopeia. Se abrirá el formulario Plantillas: Personalizar (Cassiopeia).

2. Cambie a la pestaña Crear anulaciones y seleccione mod_menu:

![selección de anulación de plantilla del menú del módulo](../../../en/images/menus/keep-submenus-open/02-create-override-select-mod-menu.png)

Esto copiará todos los archivos de diseño del menú del módulo en la anulación. A continuación, volverá a la pestaña Editor.

3. En la pestaña Editor, expanda las entradas de HTML → mod_menu.  Aquí encontrará el archivo `default.php`. Abra el archivo y copie su contenido en un lugar seguro. Cierre el archivo.

4. Cree un archivo nuevo en la carpeta html → mod_menu. Debe tener un nombre que no incluya un guion bajo. En este ejemplo, el archivo nuevo se denomina `treedefault.php`. Esto permite seleccionar el diseño de menú predeterminado o este diseño de menú alternativo en cualquiera de sus módulos de menú. En la siguiente lista de archivos de anulación, el original está marcado en rojo y la nueva alternativa está marcada en verde.

![pestaña de edición de anulación de mod_menu: abrir default.php](../../../en/images/menus/keep-submenus-open/03-edit-mod-menu.png)

4. Edite el archivo de diseño nuevo. Los siguientes pasos se enumeran en orden inverso para
preservar los números de línea durante el proceso de edición:

Cambie la línea 104 para que contenga lo siguiente:

```
        echo '<ul class="list-unstyled ps-3" aria-hidden="false">';
```

Esto mantiene abierto el menú y añade sangría a los submenús.

Reemplace las líneas 98 - 101 con `break`

```php
                    echo '<button class="mod-menu__toggle-sub" aria-expanded="false">' .
                 break;
                    '<span class="icon-chevron-down" aria-hidden="true"></span>' .
                    '<span class="visually-hidden">' . Text::sprintf('MOD_MENU_TOGGLE_SUBMENU_LABEL', $item->title) . '</span>' .
                    '</button>';
```

Elimine las líneas 93 - 94

```php
                    echo '<span class="icon-chevron-down" aria-hidden="true">' .
                        '</span></button>';
```

Elimine las líneas 66-71

```php
    // The next item is deeper - add toggle only here it is a heading or separator
    if ($item->deeper && (int) $item->level === $startLevel && in_array($item->type, ['separator', 'heading'])) {
        // Add a toggle button.
        echo '<button class="mod-menu__toggle-sub" aria-expanded="false">';
    }
```

Elimine las líneas 15 - 20

```php
/** @var Joomla\CMS\WebAsset\WebAssetManager $wa */
$wa = $app->getDocument()->getWebAssetManager();
$wa->getRegistry()->addExtensionRegistryFile('mod_menu');
$wa->usePreset('mod_menu.menu');
```

Este es el archivo de anulación `treedefault.php` completo:

```
<?php

/**
 * @package     Joomla.Site
 * @subpackage  mod_menu
 *
 * @copyright   (C) 2009 Open Source Matters, Inc. <https://www.joomla.org>
 * @license     GNU General Public License version 2 or later; see LICENSE.txt
 */

defined('_JEXEC') or die;

use Joomla\CMS\Helper\ModuleHelper;
use Joomla\CMS\Language\Text;

$tagId      = $params->get('tag_id', '') ?: 'mod-menu' . $module->id;
$id         = ' id="' . htmlspecialchars($tagId, ENT_QUOTES, 'UTF-8') . '"';
$startLevel = (int) $params->get('startLevel', 1);

// The menu class is deprecated. Use mod-menu instead
?>
<ul<?php echo $id; ?> class="mod-menu mod-list nav <?php echo $class_sfx; ?>">
<?php foreach ($list as $i => &$item) {
    $itemParams = $item->getParams();
    $class      = 'nav-item item-' . $item->id;

    if ($item->id == $default_id) {
        $class .= ' default';
    }

    if ($item->id == $active_id || ($item->type === 'alias' && $itemParams->get('aliasoptions') == $active_id)) {
        $class .= ' current';
    }

    if (in_array($item->id, $path)) {
        $class .= ' active';
    } elseif ($item->type === 'alias') {
        $aliasToId = $itemParams->get('aliasoptions');

        if (count($path) > 0 && $aliasToId == $path[count($path) - 1]) {
            $class .= ' active';
        } elseif (in_array($aliasToId, $path)) {
            $class .= ' alias-parent-active';
        }
    }

    if ($item->type === 'separator') {
        $class .= ' divider';
    }

    if ($item->deeper) {
        $class .= ' deeper';
    }

    if ($item->parent) {
        $class .= ' parent';
    }

    echo '<li class="' . $class . '">';

    switch ($item->type) :
        case 'separator':
        case 'component':
        case 'heading':
            require ModuleHelper::getLayoutPath('mod_menu', 'default_' . $item->type);
            break;
        default:
            require ModuleHelper::getLayoutPath('mod_menu', 'default_url');
            break;
    endswitch;

    // The next item is deeper.
    if ($item->deeper) {
        // Check type - add only on first level
        // @todo aria-label - set in menu item ???
        if ((int) $item->level === $startLevel) {
            switch ($item->type) {
                case 'heading':
                case 'separator':
                    break;

                default:
                    break;
            }
        }
        echo '<ul class="list-unstyled ps-3" aria-hidden="false">';
    } elseif ($item->shallower) {
        // The next item is shallower.
        echo '</li>';
        echo str_repeat('</ul></li>', $item->level_diff);
    } else {
        // The next item is on the same level.
        echo '</li>';
    }
}
?></ul>
```

## Resultado

El resultado es una lista simple, sin funcionalidad de alternancia para el módulo de menú lateral, que se muestra aquí a la izquierda:

![resultado con anulación de plantilla: lista simple sin botones ni funcionalidad de alternancia](../../../en/images/menus/keep-submenus-open/05-site-result.png)

*Traducido por openai.com*
