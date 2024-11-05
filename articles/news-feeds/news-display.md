<!-- Filename: jdocmanual?manual=user&heading=news&filename=news-display.md / Display title: Visualización de Noticias  -->

## El Módulo de Visualización de Feeds

Hay un módulo *Feed Display* central disponible para mostrar noticias de otros sitios. La siguiente captura de pantalla muestra el formulario de entrada de datos con la URL del feed de noticias de Anuncios de Joomla. Observe que el Contador de Palabras está establecido en 100. De lo contrario, la longitud de un anuncio podría ser excesiva para un módulo de barra lateral.

![Entrada de datos del módulo de visualización de feeds](../../../en/images/news-feeds/news-joomla-news-form.png "Entrada de datos del módulo de visualización de feeds")

El resultado puede ser poco atractivo, pero se puede mejorar con algunos estilos personalizados en user.css:

![Entrada de datos del módulo de visualización de feeds](../../../en/images/news-feeds/news-joomla-news-display.png "Entrada de datos del módulo de visualización de feeds")

## Páginas de Visualización de Fuentes

Como alternativa a la visualización de noticias en un módulo, puedes crear un elemento de menú para mostrar una fuente de noticias en una página web. Desde el menú del Administrador:

* Selecciona **Componentes / Fuentes de Noticias / Fuentes**. Podrías primero crear una Categoría para las noticias.
* Selecciona el botón **Nuevo** en la *Barra de Herramientas*.
* Completa el formulario **Edición de Fuentes de Noticias**:
  - El **Enlace** es el enlace RSS copiado de una fuente remota.
  - La **Descripción** es opcional.
  - La pestaña **Opciones** tiene elementos para controlar la *Visualización* de la fuente.
* **Guardar & Cerrar**

![Entrada de datos del componente de fuente de noticias](../../../en/images/news-feeds/news-feed-data-entry.png "Entrada de datos del componente de fuente de noticias")

Crea un elemento de menú comenzando desde el menú del Administrador:

* Selecciona **Menús / Menú Principal** o cualquier otro menú para este elemento.
* Selecciona **Nuevo** desde la *Barra de Herramientas de Artículos de Menú*.
* En el **Tipo de Elemento de Menú** usa el botón **Seleccionar** para encontrar y seleccionar *Fuentes de Noticias / Fuente de Noticias Única*.
* Completa el resto del formulario según sea apropiado.
* **Guardar & Cerrar**

![Entrada de datos del elemento de menú de fuente de noticias](../../../en/images/news-feeds/news-feed-data-entry.png "Entrada de datos del elemento de menú de fuente de noticias")

Pruébalo: ve al menú del Sitio y selecciona el elemento de menú de la Fuente.

![Visualización de la fuente de noticias](../../../en/images/news-feeds/news-feed-display.png "Visualización de la fuente de noticias")

Cada elemento en la fuente es un `<li>` dentro de una etiqueta `<ul>`, por lo que, por defecto, aparece marcado por un punto. Esto no es tan obvio si los elementos son largos. Puedes aplicar tus propios estilos en *user.css*. Lo siguiente colocará cada elemento en una caja distinta:

```css
ul.com-newsfeeds-newsfeed__items {
  list-style-type: none;
  padding-left: 0;
}

ul.com-newsfeeds-newsfeed__items > li {
  padding: 1rem;
  margin-bottom: 1rem;
  border: 2px solid navy;
}
```
Que aparecerá así:

![Visualización personalizada de la fuente de noticias](../../../en/images/news-feeds/news-feed-custom-display.png "Visualización personalizada de la fuente de noticias")

## Listar fuentes de noticias en una categoría

La página *Fuentes de noticias RSS de Joomla!* enumera ocho fuentes de noticias separadas. Podrías crear una fuente para algunas o todas ellas y asignarlas a una categoría, digamos *Noticias de Joomla*. Luego, puedes crear un elemento de menú con el *Tipo de elemento de menú* configurado en *Listar fuentes de noticias en una categoría* y la categoría configurada en *Noticias de Joomla*.

![Formulario de menú de fuente de noticias por categoría](../../../en/images/news-feeds/news-feed-menu-category-form.png "Formulario de menú de fuente de noticias por categoría")

¡Inténtalo para ver el resultado!
*Traducido por openai.com*

