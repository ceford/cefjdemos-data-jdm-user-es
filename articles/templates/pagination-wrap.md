<!--
{
    "source": "https://jdocmanual.org/jdocmanual?article=user/templates/pagination-wrap",
    "title": "Ajuste de la paginaci\u00f3n",
    "description": "Aprende un m\u00e9todo sencillo para ajustar la lista de paginaci\u00f3n en pantallas estrechas.",
    "author": ""
}
-->

En Joomla, las listas de artículos, usuarios y otros elementos pueden ser muy largas, por lo que se muestran en grupos, 20 de forma predeterminada. 

## La barra de paginación normal

Para navegar por los grupos, hay una barra de paginación debajo de la lista de elementos que permite al usuario seleccionar el siguiente grupo de elementos, como se muestra en esta ilustración:

![la barra normal de paginación de la lista](../../../en/images/templates/pagination-wrap/01-pagination-wide-screen.png)

## Paginación en pantallas estrechas

La barra de paginación funciona bien en pantallas anchas. Sin embargo, en pantallas estrechas, la barra de paginación puede ser más ancha que la pantalla. Esto hace necesario desplazarse hacia la derecha para encontrar otros elementos de la página, como los menús de hamburguesa.

![la barra de paginación en una pantalla estrecha](../../../en/images/templates/pagination-wrap/02-pagination-narrow-screen.png)

En la ilustración anterior, cualquier elemento ubicado en el área gris de la derecha está *fuera de la pantalla* inicialmente y es probable que pase desapercibido. El usuario debe desplazarse hacia la derecha para verlo. En este caso, los elementos fuera de la pantalla son el icono de la barra de herramientas en la esquina superior derecha y el icono del menú en la esquina inferior derecha.

## Solución con una anulación de plantilla

Esta solución añade una clase *flex-wrap* en el código que genera la barra de paginación.

- En el backend, ve a Sistema > Plantillas de administrador > Detalles y archivos de Atum
- Opcionalmente, selecciona html > layouts solo para ver qué contiene
- Selecciona la pestaña **Crear anulaciones**
- En el cuadro Diseños, selecciona **joomla** y después **pagination**
- En la pestaña Editor, selecciona html > layouts > joomla > pagination > **links.php**
- Busca la línea 70 que contiene `<ul class="pagination ms-auto me-0">`
- Añade `flex-wrap` a la lista de clases: `<ul class="pagination ms-auto me-0 flex-wrap">`
- **Guardar y cerrar**
- Opcional: puedes eliminar /html/layouts/joomla/pagination/link.php y /html/layouts/joomla/pagination/links.php

Observa el resultado tanto en pantallas anchas como estrechas. La pantalla estrecha ahora muestra el icono de la barra de herramientas y el icono del menú con el ancho normal de la pantalla:

![la barra de paginación modificada en una pantalla estrecha](../../../en/images/templates/pagination-wrap/02-modified-pagination-narrow-screen.png)

Para la plantilla del sitio, sigue estas instrucciones, pero crea una anulación en la plantilla Cassiopeia.

*Traducido por openai.com*