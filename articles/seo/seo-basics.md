<!-- Filename: jdocmanual?manual=user&heading=seo&filename=seo-basics.md / Display title: Conceptos básicos de SEO -->

## Definición

La optimización para motores de búsqueda es el proceso de mejorar una amplia gama de características de un sitio web con la intención de mejorar la posición en la que se clasifica en los motores de búsqueda.

El proceso de optimización de un sitio web es multifacético, ya que hay muchos factores que afectan la posición de una página en un motor de búsqueda.

- Asegurarse de que el contenido tenga una estructura adecuada utilizando HTML semántico.
- Mejorar la calidad del contenido de las páginas individuales.
- Garantizar que el sitio web pueda gestionar las solicitudes rápidamente.
- Habilitar URLs amigables para los motores de búsqueda para que la dirección web de las páginas sea *legible por humanos*.
- Agregar anotaciones semánticas contextuales usando datos Schema.

Recurso: [Search Engine Optimization (SEO) Starter Guide](https://developers.google.com/search/docs/fundamentals/seo-starter-guide)

## Estructura del sitio y URLs descriptivas

En los primeros días, los sitios web estaban estructurados como archivos HTML individuales en una jerarquía en forma de árbol. Algunos sitios web todavía están estructurados de esa manera. Los CMS son diferentes. Las páginas individuales se ensamblan a partir de contenido almacenado en tablas de bases de datos. Las URL para los primeros y los últimos son diferentes, quizás así:

```
https://www.example.com/user/seo/seo-basics.html
https://www.example.com/index.php?option=com_jdocmanual&view=manual&manual=user&heading=seo&filename=seo-basics
```

Claramente, el primero es más fácil de recordar y más fácil de escribir. Los motores de búsqueda los prefieren.

En el CMS de Joomla, se puede configurar una URL de la primera forma de la siguiente manera:

1. Crea una categoría de contenido llamada **User**.
2. Crea una categoría de contenido llamada **SEO** que sea hija de *User*.
3. Crea un artículo y asígnalo a la categoría *SEO*.
4. Crea un elemento de menú **User** del tipo **Lista de Categorías** usando la categoría *User*.
5. Crea un elemento de menú **SEO** del tipo **Lista de Categorías** usando la categoría *SEO*.
6. Configura la funcionalidad SEO de Joomla en la *Configuración Global*.

Pruébalo con tu URL de SEO: navega a través de las listas de Usuario y SEO hasta la página de Conceptos Básicos de SEO. Las migas de pan deberían mostrar: `Estás aquí: Inicio / Usuario / SEO / Conceptos Básicos de SEO`. ¡Pero no si has creado un tipo de elemento de menú de Artículo Único para *Conceptos Básicos de SEO*!

## Reducir la duplicación

El inconveniente con los CMS es que el mismo contenido puede estar disponible con diferentes URL. En el ejemplo anterior, ambas URL funcionarán (pero no en este sitio), al igual que `https://example.com/index.php?option=com_content&view=category&id=18&ItemID=17`. Solo una de estas debería ser reconocida por los motores de búsqueda y configurada como la URL **canónica**. Pero, ¿cuál y cómo?

El plugin **System - SEF** proporciona algo de ayuda. Tiene tres configuraciones:

- **Dominio del sitio** Si su sitio se puede acceder a través de más de un dominio, ingrese aquí el dominio preferido (a veces referido como canónico). **Nota:** `https://example.com` y `https://www.example.com` son dominios diferentes.
- **Manejo estricto de index.php** Esta opción habilita un manejo más estricto de `index.php` en las URLs cuando **Usar reescritura de URL** está habilitado en la Configuración Global. Eliminará `index.php` si una URL todavía lo contiene y redirigirá las solicitudes entrantes con `index.php` a la versión sin el `index.php`.
- **Barra diagonal final para URLs** Obliga a Joomla a usar solo URLs con o sin barra diagonal final. Cuando está configurado, esto forzará la URL correcta con redirecciones y solo se aplica cuando 'Añadir sufijo a la URL' está desactivado.

De lo contrario, vea la explicación de **Etiquetas Canónicas** por [Daniel Morell](https://www.danielmorell.com/blog/how-to-create-joomla-canonical-tags).

## Calidad del Contenido

Haz que lo que escribas sea interesante y fácil de leer. Los párrafos largos a menudo son abrumadores y difíciles de leer. ¡Los párrafos de una sola línea se ven mal! Tal vez realmente deberían ser viñetas. Apunta a párrafos de tres líneas, más o menos. Lee lo que escribas y elimina cualquier palabra innecesaria.

Mantén tu contenido actualizado y evita copiar información de otros sitios. Si es posible, verifica tu contenido.

### HTML semántico

El contenido debe consistir en una jerarquía de encabezados y párrafos con otros elementos según se requiera (listas, tablas, etc.). No confundas estructura con apariencia, por lo que no utilices un encabezado para poner texto en negrita o texto en negrita para hacer un encabezado. Este es un ejemplo de marcado semántico de un artículo:

```html
  <h2>Using headings</h2>
  <p>This is an article about the importance of headings.</p>

  <h2>Why use headings?</h2>
  <p>It is important to use headings so that search engine bots can tell what
  is an <strong>important</strong> part of your article.</p>

  <h3>Types of headings</h3>
  <p>You can use set types of headings, but they should be ordered, and
  structured, within your page.  H1 will be the page title inserted by Joomla,
  with H2 being used for sub-headings of the page.  Any headings within your
  sub-headings should cascade using H3, H4, and H5 as appropriate.</p>

  <h2>Is it hard to implement headings?</h2>
  <p>It is really easy to implement headings, you just use the appropriate
  HTML code.</p>
```

Tenga en cuenta que un artículo *Título* se convertirá en un encabezado `<h1>` si es necesario, así que no lo use en el cuerpo del artículo.

## Anticipar términos de búsqueda

Elige títulos explícitos para tus páginas y encabezados dentro de las páginas. Por ejemplo, si no sabes qué es *HTML Semántico* o quieres más información sobre ese tema, esas serían las palabras que ingresarías en un motor de búsqueda. Piensa en las personas que podrían estar interesadas en la información que estás proporcionando. ¿Qué buscarán ellos? Pero mantén los títulos y encabezados bastante cortos; algunas fuentes dicen que no más de 60 caracteres.

## Cuidado con los Anuncios

Nada desalentará más a los visitantes del sitio que los anuncios apareciendo aquí, allá y en todas partes, moviendo la información real ante tus ojos. Los anuncios que cambian cada pocos segundos también son molestos y consumen recursos del usuario final. ¡Muchos usarán bloqueadores de anuncios!

## Cuidado con los enlaces

¡Los enlaces son tanto una bendición como una maldición! Pueden afectar la calificación SEO de tu sitio para bien o para mal, dependiendo de si tienes enlaces a fuentes confiables o no confiables. Y deben mantenerse. Puedes tener enlaces a artículos internos o externos que han desaparecido, presentan información desactualizada o ya no son relevantes. Mejor consejo: enlaza si el destino aporta un beneficio real a los visitantes de tu sitio y utiliza el atributo de enlace `nofollow` si no quieres que el sitio de destino se asocie con tu sitio.

Hay muchas herramientas de verificación de enlaces disponibles, algunas gratuitas o freemium y otras de pago, a menudo como parte de un servicio de monitoreo de sitios.

## Título de la página y descripción

En el `<head>` de cada página debe haber una etiqueta `<title>` y una etiqueta `<description>`. Joomla hace que sea muy fácil establecer un título diferente para cada página. Desafortunadamente, también hace que sea muy fácil descuidar establecer un Título y Descripción adecuados en cada página.

Como ejemplo, toma la página de lista de categoría **SEO** mencionada anteriormente. El código fuente de la página `<title>` dice **SEO** y falta la `<description>`. En el formulario **Menús: Editar Elemento** para este ítem del menú hay una pestaña **Visualización de Página** con un campo de **Título de Página del Navegador**. Inserta `SEO - Lista de Artículos` allí y eso es lo que aparece en la etiqueta `<title>` y en la pestaña del navegador.

En la pestaña de **Metadatos**, con el campo de **Meta Descripción** configurado en `Lista de artículos sobre la optimización de motores de búsqueda.` eso es exactamente lo que aparece en el campo `<description>`. La Descripción a veces se utiliza para acompañar un Título de página en los resultados de búsqueda, por lo que debería ser relevante.

Más información:
* Artículo de revista: [Joomla SEO title tags](https://magazine.joomla.org/all-issues/september/joomla-seo-title-tags)
* [Explora el núcleo: Opciones SEO nativas](https://magazine.joomla.org/all-issues/june/explore-the-core-native-seo-options)

## Optimizar imágenes

Es innecesario decir que las imágenes atractivas pueden mejorar un sitio enormemente. Pero demasiadas imágenes que son demasiado grandes atraen sanciones de SEO. Aquí tienes algunos consejos:

- Coloca las imágenes junto al texto que ilustran.
- Usa texto **alt** descriptivo.
- Usa guiones para separar las palabras en los nombres de las imágenes, por ejemplo, cat-on-hot-tin-roof.jpg.
- Usa el tipo correcto de imagen para la tarea: png para carteles, jpg para fotografías.
- Usa imágenes responsivas - hay un [plugin de Joomla](https://responsive-images.dgrammatiko.dev/) que crea dinámicamente versiones webp de imágenes png y jpg en varios tamaños.

*Traducido por openai.com*

