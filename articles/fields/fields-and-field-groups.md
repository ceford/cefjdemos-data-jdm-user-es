<!-- Filename: J4.x:Fields_and_Field_Groups / Display title: Campos y Grupos de Campos -->

## Introducción

Los campos se utilizan para mostrar atributos adicionales de Artículos, Contactos o Usuarios. Los datos se ingresan en un formulario de edición del Administrador y se muestran en el Sitio. Un ejemplo:

Supongamos que escribes artículos sobre aspectos de la naturaleza, a veces Flores, a veces Animales. Un campo que podrías querer registrar y mostrar para ambos es el Nombre Latino, que requiere un campo de texto. Otro podría ser Hábitat: Bosque, Estanque, Prado, etc., que requiere una lista desplegable. Para las flores, podrías querer registrar la Temporada de Floración usando 4 casillas de verificación, una para cada estación, o 12 casillas, una para cada mes.

Los campos vacíos en el formulario de entrada no se muestran en la salida del Sitio, por lo que podrías mantener todos los campos en una lista larga. Sin embargo, generalmente es mejor usar categorías para tus Artículos, por ejemplo, Flores y Animales. Los campos se pueden asignar a más de una Categoría. Así que los campos de Nombre Latino y Hábitat se asignarían a ambos, pero Temporada de Floración solo se asignaría a la categoría de Flores.

Si un campo no se asigna a un grupo, aparecerá en el formulario de edición en una pestaña de Campos. Si un campo se asigna a un grupo, aparecerá en una pestaña con ese nombre. Así que, para el grupo de Flores, parece apropiado crear un grupo de campos llamado Datos de Flores (o simplemente Flores, aunque usar el mismo nombre para cosas diferentes puede ser confuso). Y para los otros campos comunes podrías usar un grupo llamado Naturaleza.

## Un Ejemplo Práctico - Notas Sobre la Naturaleza

Para los artículos sobre la Naturaleza, la categoría del artículo y las subcategorías para cada rama del mundo viviente podrían aparecer como en el siguiente ejemplo:

![Categorías de artículos para la naturaleza](../../../en/images/fields/fields-articles-categories-list.png)

Algunas características evidentes de la Naturaleza para tener en cuenta:

- La categoría Naturaleza es para artículos que tratan sobre la naturaleza en general en lugar de tipos específicos de plantas o animales.
- Las subcategorías son para artículos más específicos y pueden necesitar sus propias subcategorías.
- Todas las formas de vida tienen nombres comunes y nombres latinos.
- Las Flores y los Árboles tienen una Temporada de Floración, Altura y Extensión, pero las Aves y los Mamíferos no.
- Las Aves tienen Envergadura y Longitud mientras que los Mamíferos tienen Altura y Longitud.
- El Color puede ser constante o variado.

El punto aquí es que puede ser necesario establecer Campos o Grupos de Campos para características comunes, como el Nombre Latino, y Grupos de Campos separados para cada categoría de naturaleza.

## Grupos de Campos

Crear grupos de campos para artículos es muy sencillo:

- Selecciona **Contenido → Grupos de Campos** desde el menú del administrador.
- Selecciona el botón **Nuevo** en la barra de herramientas.
- Ingresa un **Título** adecuado.
- Ingresa una **Descripción**. Esta aparece debajo del campo en el formulario de edición del artículo cuando se selecciona *Alternar Ayuda en Línea*.
- Selecciona **Guardar y Cerrar** desde la barra de herramientas.

![Lista de grupos de campos de contenido](../../../en/images/fields/fields-field-groups-list.png)

### Ordenación

En el formulario de entrada de datos del artículo, los grupos de campos aparecerán en el orden visto en esta lista. Arrastra y suelta los elementos para cambiar el orden.

## Campos

Para crear un nuevo Campo de artículo, selecciona **Contenido → Campos** en el menú del Administrador y llena el formulario. Algunos ejemplos se ilustran a continuación.

### Texto - Nombre Latín

Ten en cuenta que en la captura de pantalla a continuación, este campo ha sido asignado al Grupo de Campos de Naturaleza y a la categoría Naturaleza. Esto asegura que siempre aparezca en los artículos de la categoría Naturaleza y cualquier subcategoría.

![Campo de texto - nombre latín en el grupo de naturaleza](../../../en/images/fields/fields-latin-name.png)

### Casillas de Verificación - Temporada de Floración

Las casillas de verificación aparecen en el formulario de edición de artículos para que puedas marcar la temporada de floración. En la visualización del artículo, solo se listarán aquellas que estén marcadas. Por ejemplo, si marcas Primavera y Verano, la salida mostrará Temporada de Floración: Primavera, Verano.

Ten en cuenta que en esta captura de pantalla, el Campo ha sido asignado al grupo de Flores y a la Categoría de Flores. Esto debería asegurar que el campo solo esté presente en artículos sobre flores.

![Campo de casillas de verificación - temporada de floración](../../../en/images/fields/fields-flowering-season.png)

### Color - Color

Solo para ser confuso, el nombre del tipo de campo es Color (Ortografía de EE.UU.) pero la etiqueta en la documentación es Colour (Ortografía Británica).

![Campo de color](../../../en/images/fields/fields-colour.png)

El campo de Color está asignado al grupo de campos de Naturaleza y a la categoría Naturaleza, ya que no es exclusivo de las flores.

### Entero - Resistencia

La resistencia de una planta se puede representar como un número entero de 1 a 7. No hay un campo para un número real, por lo que la longitud y el ancho podrían ser números enteros con una escala (cm o m o ft) incluida en la etiqueta. Hay configuraciones de *Prefijo* y *Sufijo* en la pestaña *Opciones*. Si no hay un límite superior obvio, entonces deja el campo *Último:* vacío.

![Campo de resistencia](../../../en/images/fields/fields-hardiness.png)

¡La Resistencia RHS es una propiedad que generalmente se aplica a las flores!

Hay un problema con el campo entero. Siempre tiene un valor y, por lo tanto, siempre aparece en la salida. Puedes solucionar ese problema con una anulación de plantilla para *Complementos / Entero*. Por ejemplo, podrías usar un valor por encima o por debajo de los límites esperados para omitir el campo de la salida.

## Formulario de Edición de Artículo

Cuando se abre un formulario de Artículos: Nuevo, la categoría predeterminada es No categorizado y las pestañas del formulario no incluyen Campos y Flores. Selecciona la categoría Flores y el formulario se recargará con esas pestañas presentes.

### Pestaña de Naturaleza

![pestaña de naturaleza del artículo bluebell](../../../en/images/fields/field-article-bluebell-nature-tab.png)

- **Nombre Latino** Este es un campo de entrada de texto, así que solo es cuestión de escribir el nombre latino de la forma de vida que cubre el artículo. Sin embargo, la categoría Naturaleza cubre la vida en general, así como animales o plantas específicos. Por lo tanto, este no es un campo *obligatorio*.
- **Color** El campo de selección de color puede aceptar una entrada de teclado de un valor de color hexadecimal o un color seleccionado de la herramienta de selección de color. El número hexadecimal es xrrggbb, donde rr son valores de rojo, gg son valores de verde y bb son valores de azul. En la salida, el sitio muestra el valor hexadecimal, lo cual no es muy útil.

### Pestaña de Flores

![pestaña de naturaleza del artículo bluebell](../../../en/images/fields/field-article-bluebell-flowers-tab.png)

- **Temporada de Floración** El campo de casillas de verificación - los jacintos de los bosques son flores de primavera bien conocidas, por lo que la selección de una casilla de verificación es apropiada.
- **Resistencia** El campo de enteros. Hay un problema aquí: no hay un método disponible para dejar este campo vacío. Por lo tanto, siempre está presente en la salida, incluso para artículos más generales sobre flores donde no es adecuado. Hay una solución alternativa que involucra una anulación de plantilla.

## Resultado del Sitio

Echa un vistazo al resultado visualizado en tu sitio. En este ejemplo, se creó un elemento de menú de un solo artículo:

![Vista del sitio del artículo Bluebell](../../../en/images/fields/field-article-bluebell-site.png)

### El Color Hexadecimal

La visualización predeterminada de datos es el valor del color hexadecimal, lo cual no es muy útil. La solución sencilla es crear una plantilla de sobreescritura para el plugin de campos / color, que es lo que se muestra en la captura de pantalla anterior.

Simplemente reemplaza esta línea:
```
echo htmlentities($value);
```
con estas líneas:
```
if (is_array($value)) {
  $list = [];
  foreach ($value as $v) {
    $x = htmlentities($v);
    $list[] = '<span class="ps-5 pe-5" style="background-color: ' . $x . ';">&nbsp</span> ' . $x;
    echo implode(', ', $list);
  }
} else {
    $x = htmlentities($value);
    echo '<span class="ps-5 pe-5" style="background-color: ' . $x . ';">&nbsp</span> ' . $x;
}
```
Y el valor hexadecimal será precedido por una muestra con el color de fondo del valor.

*Traducido por openai.com*

