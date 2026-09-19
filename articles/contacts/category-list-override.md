<!--
{
    "source": "https://docs.joomla.org/category-list-override.md",
    "title": "Anulaci\u00f3n de lista de categor\u00edas",
    "description": "Aprende a crear una anulaci\u00f3n de plantilla para mejorar el dise\u00f1o de una lista de contactos en una categor\u00eda",
    "author": ""
}
-->

## La lista de contactos de una categoría

El diseño predeterminado de los contactos de una categoría está controlado por una plantilla del código del componente 
com_contacts. El diseño predeterminado tiene este aspecto:

![comité cultural utilizando el diseño y estilo predeterminados](../../../en/images/contacts/category-list-override/01-contacts-culture-committee.png)

Puede que sea una cuestión de opinión personal, pero, para mí, el diseño predeterminado de los contactos no es del todo satisfactorio. Mis problemas:

* Las imágenes de retrato originales tenían 500 píxeles de ancho y eran demasiado dominantes.
* El nombre del contacto no está suficientemente destacado.
* La lista de datos personales no tiene un encabezado y parece aislada.
* El cargo de la persona no tiene un encabezado.
* Faltan los campos de dirección y código postal.
* Los datos de ubicación están incompletos.
* Los datos de cada contacto se organizan en una tabla y quedan bastante apretados en pantallas estrechas.

Entonces, ¿cómo solucionarlo a mi gusto? Mi solución es crear una anulación de plantilla 
y añadir algunos estilos personalizados. Este es el resultado:

![comité empresarial utilizando una anulación de plantilla y estilos personalizados](../../../en/images/contacts/category-list-override/02-contacts-business-committee.png)

## Anulación del diseño de la plantilla

La carpeta com_contact/tmpl/category contiene tres archivos PHP: default.php,
default_children.php y default_items.php. El último de esta lista contiene
el diseño de tabla para la lista.

Los archivos de anulación se crean mediante Sistema / Plantillas del sitio /
Detalles y archivos de Cassiopeia / Crear anulaciones. Seleccione com_contact
y, a continuación, category. La carpeta html contiene entonces
com_contact/category con los tres archivos de plantilla mencionados
anteriormente.### Cambiar el archivo default.php a mydefault.php

El archivo `default.php` contiene una línea que especifica qué diseño se debe utilizar para cada registro individual. Seleccione este archivo para editarlo y **cámbiele el nombre** a `mydefault.php` (o use cualquier prefijo que desee en lugar de `my`). ¡No utilice un guion bajo en el nombre del archivo!

Cuando acceda posteriormente al formulario Contactos / Categoría / Editar, el campo Diseño de la pestaña Opciones le permitirá elegir entre el diseño del componente y el diseño sobrescrito. Se ve así:

```
---From Global Options---
  Use Global
---From Component---
  Default
---From cassiopeia Template---
  mydefault

```

### Editar el archivo mydefault.php

La línea 20 de `mydefault.php` contiene `$this->subtemplatename = 'items';`.
Cambie `items` por `myitems` para que las líneas 18 a 23 queden así:

```html
<div class="com-contact-category">
    <?php
        $this->subtemplatename = 'myitems';
        echo LayoutHelper::render('joomla.content.category_default', $this);
    ?>
</div>
```
### Cambiar el archivo default_items.php a mydefault_myitems.php

El archivo `default_items.php` contiene el diseño de cada contacto. Es necesario
cambiarle el nombre para conservar la opción de utilizar el diseño original. La
primera parte del nombre no es importante. Es la parte `myitems` a la que se hace
referencia en el archivo `mydefault.php` la que se utiliza para el diseño.

### Editar el archivo mydefault_myitems.php

La sección `<table>...</table>` de este archivo abarca las líneas 85 a 204. Para
la sustitución del diseño, reemplacé el marcado de la tabla por el siguiente
marcado de cuadrícula de Bootstrap. En pantallas estrechas, las tres columnas se
apilan. En pantallas de más de 768 píxeles de ancho, las columnas se muestran una
al lado de la otra. El marcado revisado ha movido los campos personalizados debajo
del nombre del contacto.

```
<div class="container-fluid text-center border border-2">
<?php $nrows = 0; foreach ($this->items as $i => $item) : ?>
    <?php if ($item->published !== 1 ||
        (!empty($item->publish_up) && strtotime($item->publish_up) > strtotime(Factory::getDate())) ||
        (!empty($item->publish_down) && strtotime($item->publish_down) < strtotime(Factory::getDate()))) { continue; } ?>
        <div class="row cat-list-row<?php echo $nrows % 2; $nrows += 1; ?> align-items-center">
            <div class="col-12 col-md-3">
                <?php if ($this->params->get('show_image_heading')) : ?>
                    <?php if ($item->image) : ?>
                        <?php echo LayoutHelper::render(
                            'joomla.html.image',
                            [
                                'src'   => $item->image,
                                'alt'   => 'official image of ' . $item->name,
                                'class' => 'contact-thumbnail img-thumbnail',
                            ]
                        ); ?>
                    <?php endif; ?>
                <?php endif; ?>
            </div>
            <div class="col-12 col-md-3">
                <div class="parliament-committee-fields">
                <a href="<?php echo Route::_(RouteHelper::getContactRoute($item->slug, $item->catid, $item->language)); ?>">
                    <span class="fs-2"><?php echo $this->escape($item->name); ?></span>
                </a>
                    <?php echo $item->event->beforeDisplayContent; ?>
                </div>
            </div>
            <div class="col-12 col-md-6 text-start">
                <?php if ($this->params->get('show_position_headings') && !empty($item->con_position)) : ?>
                    <strong><?php echo Text::_('COM_CONTACT_FIELD_INFORMATION_POSITION_LABEL'); ?></strong><br>
                    <?php echo $item->con_position; ?><br>
                <?php endif; ?>
                <?php if ($this->params->get('show_suburb_headings')) : ?>
                    <?php $location = []; ?>
                    <?php if (!empty($item->address)) : ?>
                        <?php $location[] = $item->address; ?>
                    <?php endif; ?>
                    <?php if (!empty($item->suburb)) : ?>
                        <?php $location[] = $item->suburb; ?>
                    <?php endif; ?>
                    <?php if (!empty($item->state)) : ?>
                        <?php $location[] = $item->state; ?>
                    <?php endif; ?>
                    <?php if (!empty($item->postcode)) : ?>
                        <?php $location[] = $item->postcode; ?>
                    <?php endif; ?>
                        <strong><?php echo Text::_('COM_CONTACT_FIELD_INFORMATION_ADDRESS_LABEL'); ?></strong><br>
                    <?php echo implode("<br>\n", $location); ?><br>
                <?php endif; ?>
                <?php if (!empty($item->misc)) : ?>
                    <?php echo $item->misc; ?>
                <?php endif; ?>
            </div>
        </div>
    <?php endforeach; ?>
</div>
```

## Estilos

Las clases de estilo de Bootstrap se pueden definir en el archivo `mydefault_myitems.php`.
Por ejemplo, `<span class="fs-2">...</span>` se utiliza para aumentar el tamaño de fuente
del nombre del contacto. Se pueden añadir otros estilos en el archivo `user.css`, por
ejemplo, la personalización de listas con viñetas que solo aparecen dentro de una etiqueta
que tiene una clase `contactList`.

Estos son los estilos introducidos en el archivo `user.css` para obtener el diseño
del Comité Empresarial ilustrado anteriormente.

```
.contact-thumbnail {
  max-width: 200px;
  margin-right: 1rem;
}
a:has(.contact-thumbnail) {
  font-weight: 700;
  font-size: larger;
}
#contactList ul {
  list-style-type: none;
  padding-left: 0;
}
.cat-list-row0 {
  background-color: #efefef;
}
.cat-list-row0:hover, .cat-list-row1:hover  {
  background-color: #ddd;
}
div.parliament-committee-fields {
  text-align: left;
  margin-top: 1rem;
}
div.parliament-committee-fields ul.fields-container {
  list-style-type: none;
  padding-left: 0;
}
div.parliament-committee-fields ul.fields-container span.field-label {
  font-weight: 700;
}
```

*Traducido por openai.com*