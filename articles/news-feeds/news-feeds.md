<!-- Filename: jdocmanual?manual=user&heading=news&filename=news-feeds.md / Display title: Fuentes de Noticias -->

## Introducción a los Feeds de Noticias

Había una vez en que era una práctica común que un sitio web mostrara noticias de sitios remotos en una página o panel. Los navegadores incluso tenían lectores de noticias integrados para hacer precisamente eso. Los tiempos cambian y los navegadores principales ya no ofrecen esa opción. Y hay nuevos métodos para compartir contenido de sitios, especialmente con redes sociales.

El método para compartir noticias es *Really Simple Syndication*, generalmente abreviado como **RSS**, y esto todavía tiene un lugar en la promoción de sitios web. La siguiente captura de pantalla muestra *NetNewsWire*, un lector RSS gratuito y de código abierto para Mac. Otros lectores RSS están disponibles para otras plataformas. La ilustración muestra el feed RSS de **Anuncios de Joomla!** seleccionado. Se enumeran diez anuncios con Título y una breve descripción. El anuncio seleccionado se muestra completo en la columna de la derecha.

![Feed RSS de Anuncios de Joomla](../../../en/images/news-feeds/news-netnewswire-display.png "Anuncios de Joomla")

¡Imagina lo que uno o más feeds RSS podrían hacer por tu sitio web!

## Configuración de un Canal de Noticias

Tu sitio web tiene Canales de Noticias configurados desde el principio. Un sitio web recién instalado con Joomla 5 tiene estas dos líneas cerca de la parte superior del código fuente de la página de inicio:

```
<link href="/j51/index.php?format=feed&amp;type=rss" rel="alternate" type="application/rss+xml" title="Home">
<link href="/j51/index.php?format=feed&amp;type=atom" rel="alternate" type="application/atom+xml" title="Home">
```
Estas líneas permiten que los sistemas automatizados utilicen ya sea Canales RSS o Atom. Atom es una especificación de sindicación de noticias posterior y ligeramente diferente. Las líneas estarán presentes en todas las páginas **Destacadas** y las páginas de **Blog de Categoría**, pero no en la mayoría de los otros tipos de páginas. Puedes desactivar la inclusión de estos canales RSS si lo deseas.

## Alternar enlace de RSS Feed

La configuración global del enlace de RSS Feed se encuentra en la pestaña **Integración** de la página de Opciones de Artículos. Configúralo en *Mostrar* u *Ocultar* según lo consideres adecuado. El valor predeterminado es **Mostrar**.

La configuración global se puede anular en un elemento de menú de blog de categoría. Nuevamente, selecciona la pestaña *Integración* y configura el *Enlace de RSS Feed* en *Mostrar* u *Ocultar*.

¡El RSS Feed no se puede ocultar en una página de inicio de Artículos Destacados (¿error?)!

## El Módulo de Fuentes de Sindicación

Hay un módulo central que puedes colocar en páginas de Blog Destacadas o de Categoría para proporcionar un enlace de Sindicación. Rellena los campos en la pestaña del Módulo. La mayoría tienen valores predeterminados adecuados. Si el campo de Etiqueta se deja en blanco, la etiqueta predeterminada en inglés es *Feed Entries*. En la pestaña *Asignación de Menú*, selecciona **En todas las páginas**. El módulo solo aparecerá en páginas de Blog Destacadas y de Categoría.

![Entrada de datos de fuentes de sindicación](../../../en/images/news-feeds/news-syndication-feeds-form.png "Entrada de datos de fuentes de sindicación")

Recuerda asignar el módulo a una *Posición* y marcarlo como *Publicado*.

En la vista de la página del sitio, el módulo muestra un enlace. No está destinado a ser clicado a menos que tengas un lector de noticias local configurado. El enlace necesita ser copiado para su uso en un lector de noticias en otro sitio o aplicación de lector de noticias.

![Visualización de fuentes de sindicación](../../../en/images/news-feeds/news-syndication-feeds-display.png "Visualización de fuentes de sindicación")

Ten en cuenta que el enlace es para los elementos de esa página. Así que si tu sitio tiene varias páginas de blog de categoría, tendrás varias fuentes RSS diferentes.

