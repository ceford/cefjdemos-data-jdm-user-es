<!-- Filename: category-list-override.md / Display title: Anulación de la Lista de Categorías -->

## El Elemento de Menú de Lista de Contactos en una Categoría

Puede que sea una opinión personal, pero para mí, el diseño predeterminado de la lista de categorías de Contactos no es del todo satisfactorio. Mis problemas:

* Las fotos de contacto son demasiado grandes, con casi 500 píxeles de ancho.
* El nombre del contacto no está suficientemente destacado.
* La lista de viñetas con los detalles personales no tiene encabezado y parece aislada.
* La posición no tiene encabezado, por lo que podría parecer aislada.
* Los campos de dirección y código postal están ausentes.
* Los datos de ubicación están incompletos.
* Falta la declaración personal.
* La lista está dispuesta en una tabla que es un poco mejor en pantallas estrechas, pero bastante apretada.

Entonces, ¿cómo solucionarlo a mi gusto?

## Estilo

La imagen tiene el estilo CSS `contact-thumbnail img-thumbnail`. Las herramientas de desarrollo del navegador indican que img-thumbnail está configurado con `max-width: 100%;` pero contact-thumbnail no se utiliza. La única aparición de este último estilo en todo el sitio está en esta ubicación, por lo que parece seguro establecer una anulación en user.css para restringir el ancho de la imagen. Y el tamaño de fuente del nombre de contacto se puede aumentar usando su etiqueta `a` que lo encierra:

```
.contact-thumbnail {
  max-width: 200px;
  margin-right: 1rem;
}
a:has(.contact-thumbnail) {
  font-weight: 700;
  font-size: larger;
}
```
La lista de viñetas de campos personalizados se puede mejorar eliminando las viñetas y el relleno al seleccionar solo listas de viñetas que aparecen dentro de una etiqueta que tiene una clase de contactList:
```
#contactList ul {
  list-style-type: none;
  padding-left: 0;
}
```
![comité empresarial estilizado](../../../en/images/contacts/contact-business-committee-styled.png)

Eso es todo lo que se puede hacer con el estilo. Mejor, pero aún no lo suficiente. Para agregar más elementos y cambiar el diseño se requerirá una anulación de diseño.  

## Reemplazo de Plantilla de Diseño

La carpeta com_contact/tmpl/category contiene tres archivos PHP: default.php, default_children.php y default_items.php. El último de esta lista contiene el diseño de la tabla para la lista.

Los archivos de reemplazo se crean a través de Sistema / Plantillas del Sitio / Detalles y Archivos de Cassiopeia / Crear Overrrides. Selecciona com_contact y luego category. La carpeta html entonces contendrá com_contact/category con los tres archivos de plantilla mencionados anteriormente. El default_items.php es el que debe seleccionarse para editar. Las líneas 83 a 203 contienen la tabla utilizada para el diseño.

Puede que no sea obvio, pero $this->items es un arreglo de miembros de categoría y cada miembro contiene en realidad todos los datos de cada artículo, no solo aquellos mencionados en la configuración del menú.

A continuación se muestra un reemplazo para la sección `<table>...</table>` del archivo default_items.php utilizando una cuadrícula de Bootstrap. En pantallas estrechas, las tres columnas están apiladas. En pantallas más anchas que 768 píxeles, las columnas están una al lado de la otra. Más explicaciones siguen al código.

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
                                'alt'   => 'imagen oficial de ' . $item->name,
                                'class' => 'contact-thumbnail img-thumbnail',
                            ]
                        ); ?>
                    <?php endif; ?>
                <?php endif; ?>
            </div>
            <div class="col-12 col-md-3">
                <a href="<?php echo Route::_(RouteHelper::getContactRoute($item->slug, $item->catid, $item->language)); ?>">
                    <span class="fs-2"><?php echo $this->escape($item->name); ?></span>
                </a>
            </div>
            <div class="col-12 col-md-6 text-start">
                <?php if ($this->params->get('show_position_headings') && !empty($item->con_position)) : ?>
                    <strong>Posición</strong><br>
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
                        <strong>Dirección</strong><br>
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
### Explicación

La lista de contactos puede contener ítems que no están publicados, o tienen fechas de publish_up y publish_down que no son actuales. Necesitan ser excluidos de la visualización y se necesita un contador separado para mantener la alternancia de colores de fondo en cada fila.

La etiqueta img se renderiza como:
```
<img src="/j51/images/parliament/Official_portrait_of_Liam_Byrne_crop_2.jpg"
alt="imagen oficial de Liam Byrne" class="contact-thumbnail img-thumbnail"
width="479" height="639" loading="lazy">
```
La clase `<span class="fs-2">...</span>` establece el nombre del contacto en tamaño de fuente 2, que sería el mismo que Heading 2.

El ítem `show_suburb_headings` se está utilizando como un proxy para mostrar la dirección completa, ya que algunos de los ítems individuales de dirección no tienen selectores de Mostrar/Ocultar en el ítem del menú.

### Estilo Adicional

La versión grilla de la lista de contactos necesita estilo adicional en user.css:
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
```

### Resultado

![comité de negocios en cuadrícula](../../../en/images/contacts/contact-business-committee-grid.png)

*Traducido por openai.com*

