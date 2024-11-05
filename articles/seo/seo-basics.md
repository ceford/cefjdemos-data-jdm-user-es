<!-- Filename: jdocmanual?manual=user&heading=seo&filename=seo-basics.md / Display title: Conceptos Básicos de SEO -->

## Definición

La Optimización para Motores de Búsqueda es el proceso de mejorar una amplia gama de características de un sitio web con la intención de mejorar la posición en la que se clasifica en los motores de búsqueda.

El proceso de optimización de un sitio web es multifacético, ya que hay muchos factores que afectan la posición en la que una página podría clasificarse en un motor de búsqueda.

- Asegurarse de que el contenido tenga una estructura adecuada usando HTML Semántico
- Mejorar la calidad del contenido de páginas individuales.
- Asegurarse de que el sitio web pueda manejar solicitudes rápidamente
- Habilitar URLs Amigables para Motores de Búsqueda para que la dirección web de las páginas sea 'legible por humanos'
- Agregar Marcado Semántico Contextual usando datos de Esquema

Recurso: Guía de Inicio a la Optimización para Motores de Búsqueda (SEO)

## Estructura del Sitio y URLs Descriptivas

En los primeros días, los sitios web se estructuraban como archivos HTML individuales en una jerarquía de árbol. Algunos sitios web todavía están estructurados de esa manera. Los CMS son diferentes. Las páginas individuales se ensamblan a partir de contenido almacenado en tablas de bases de datos. Las URL para el primero y el segundo son diferentes, quizás así:
```
https://www.example.com/user/seo/seo-basics.html
https://www.example.com/index.php?option=com_jdocmanual&view=manual&manual=user&heading=seo&filename=seo-basics
```
Claramente, la primera es más fácil de recordar y más fácil de escribir. Los motores de búsqueda las prefieren.

En el CMS Joomla, una URL de la primera forma se puede configurar de la siguiente manera:

1. Crea una Categoría de Contenido llamada **Usuario**.
2. Crea una Categoría de Contenido llamada **SEO** que sea un subgrupo de *Usuario*.
3. Crea un artículo y asígnalo a la categoría *SEO*.
4. Crea un elemento de menú **Usuario** de tipo **Lista de Categorías** usando la categoría *Usuario*.
5. Crea un elemento de menú **SEO** de tipo **Lista de Categorías** usando la categoría *SEO*.
6. Configura la funcionalidad SEO de Joomla en la *Configuración Global*.

Pruébalo con tu URL SEO: navega a través de las listas de Usuario y SEO hasta la página de Conceptos Básicos de SEO. Las Migas de Pan deberían mostrar: `Usted está aquí: Inicio / Usuario / SEO / Conceptos Básicos de SEO`. ¡Pero no si has creado un tipo de elemento de menú de Artículo Único para *Conceptos Básicos de SEO*!

## Reducir Duplicación

El problema con los CMS es que el mismo contenido puede estar disponible con diferentes URL. En el ejemplo anterior, ambas URL funcionarán (pero no en este sitio), al igual que `https://example.com/index.php?option=com_content&view=category&id=18&ItemID=17`. Sólo una de estas debería ser reconocida por los motores de búsqueda y establecerse como la URL **canónica**. Pero, ¿cuál y cómo?

El complemento **System - SEF** proporciona algo de ayuda. Tiene tres configuraciones:

* **Dominio del Sitio:** Si tu sitio puede ser accedido a través de más de un dominio, ingresa aquí el dominio preferido (a veces referido como canónico). **Nota:** `https://example.com` y `https://www.example.com` son dominios diferentes.
* **Manejo estricto de index.php:** Esta opción permite un manejo más estricto de 'index.php' en las URLs cuando 'Usar reescritura de URL' está habilitado en la Configuración Global. Eliminará 'index.php' si una URL aún lo contiene y redirigirá solicitudes entrantes con 'index.php' a la versión sin 'index.php'.
* **Barra al final para URLs:** Obliga a Joomla a usar solo URLs con o sin barra al final. Cuando está configurado, obligará a usar la URL correcta con redirecciones y solo se aplica cuando 'Agregar sufijo a URL' está desactivado.

Explicación de **Etiquetas Canónicas** por Daniel Morell:

* Cómo Crear Etiquetas Canónicas en Joomla
* Complemento y Documentación:

Para Joomla 4 y 5, antes de habilitar, el complemento necesita que `if ($app->isAdmin()) {` se cambie a `if ($app->isClient('admin')) {` en las líneas 72 y 99 de *plugins /system / customcanonical / customcanonical.php*.

En un artículo, selecciona la pestaña de Publicación y luego el botón **Auto** de *URL Canónica*. Esto colocará un enlace como el siguiente en cualquier página que muestre el artículo único:
```
    <link href="/jdm3/en/user/seo/seo-basics.html" rel="canonical" />
```

## Calidad del Contenido

Haz que lo que escribas sea interesante y fácil de leer. Los párrafos largos a menudo son abrumadores y difíciles de leer. ¡Los párrafos de una sola línea se ven mal! Quizás realmente deberían ser puntos de viñeta. Aspira a escribir párrafos de unas tres líneas. Lee lo que escribes y elimina cualquier palabra innecesaria.

Mantén tu contenido actualizado y evita copiar información de otros sitios. Si es posible, verifica tu contenido.

### HTML Semántico

El contenido debe consistir en una jerarquía de encabezados y párrafos con otros elementos según sea necesario (listas, tablas, etc.). No confundas la estructura con la apariencia, por lo tanto, no utilices un encabezado para resaltar o resaltar para un encabezado. Este es un ejemplo de marcado semántico de un artículo:

```html
  <h2>Uso de encabezados</h2>
  <p>Este es un artículo sobre la importancia de los encabezados.</p>

  <h2>¿Por qué usar encabezados?</h2>
  <p>Es importante usar encabezados para que los bots de motores de búsqueda puedan identificar cuál es una parte <strong>importante</strong> de tu artículo.</p>

  <h3>Tipos de encabezados</h3>
  <p>Puedes usar tipos establecidos de encabezados, pero deben estar ordenados y estructurados dentro de tu página. H1 será el título de la página insertado por Joomla, con H2 usándose para subencabezados de la página. Cualquier encabezado dentro de tus subencabezados debe encadenarse usando H3, H4 y H5 según sea apropiado.</p>

  <h2>¿Es difícil implementar encabezados?</h2>
  <p>Realmente es fácil implementar encabezados, solo necesitas usar el código HTML apropiado.</p>
```
Observa que el *Título* de un artículo se convertirá en un encabezado `<h1>` si es necesario, por lo que no lo utilices en el cuerpo de un artículo.

## Anticipar Términos de Búsqueda

Elige títulos explícitos para tus páginas y encabezados dentro de las páginas. Por ejemplo, si no sabes qué es *HTML Semántico* o quieres más información sobre ese tema, esas serían las palabras que ingresarías en un motor de búsqueda. Piensa en las personas que podrían estar interesadas en la información que estás proporcionando. ¿Qué buscarán ellas? Pero mantén los Títulos y Encabezados bastante cortos; algunas fuentes dicen no más de 60 caracteres.

## Cuidado con los Anuncios

Nada desalentará más a los visitantes del sitio que los anuncios apareciendo aquí, allá y por todas partes, moviendo la información real ante tus ojos. Los anuncios que cambian cada pocos segundos también son molestos y consumen recursos del usuario final. ¡Muchos usarán bloqueadores de anuncios!

## Cuidado con los Enlaces

¡Los enlaces son tanto una bendición como una maldición! Pueden afectar la clasificación SEO de tu sitio para bien o para mal, dependiendo de si tienes enlaces a fuentes confiables o no confiables. Y deben ser mantenidos. Puedes tener enlaces a artículos internos o externos que han desaparecido, presentan información desactualizada o ya no son relevantes. El mejor consejo: enlaza si el destino agrega un beneficio real para los visitantes de tu sitio y utiliza el atributo de enlace `nofollow` si no deseas que el sitio de destino se asocie con tu sitio.

Hay muchas herramientas de verificación de enlaces disponibles, algunas gratuitas o freemium y otras de pago, a menudo como parte de un servicio de monitoreo de sitios.

## Título de Página y Descripción

En el `<head>` de cada página debería haber una etiqueta `<title>` y una etiqueta `<description>`. Joomla facilita mucho establecer un título diferente para cada página. Desafortunadamente, también hace que sea muy fácil olvidar establecer un Título y Descripción adecuados en cada página.

Como ejemplo, tomemos la página de lista de la categoría **SEO** mencionada anteriormente. El `<title>` del código de la página dice **SEO** y la `<description>` está ausente. En el formulario **Menús: Editar Elemento** para este elemento de menú, hay una pestaña **Mostrar Página** con un campo **Título de Página del Navegador**. Ingresa `SEO - Lista de Artículos` allí y eso es lo que aparece en la etiqueta `<title>` y en la pestaña del navegador.

En la pestaña **Metadatos**, con el campo **Meta Descripción** configurado como `Lista de artículos sobre Optimización para Motores de Búsqueda`, eso es exactamente lo que aparece en el campo `<description>`. La Descripción a veces se usa para acompañar un Título de página en los resultados de búsqueda, por lo que vale la pena hacerla relevante.

Más información:
* Artículo de revista: Etiquetas de título SEO en Joomla
* Explora el Núcleo: Opciones SEO Nativas

## Optimizar Imágenes

No hace falta decir que las imágenes atractivas pueden mejorar enormemente un sitio. Pero demasiadas que son demasiado grandes atraen penalizaciones de SEO. Aquí hay algunos consejos:

* Coloca las imágenes junto al texto que ilustran.
* Usa texto **alt** descriptivo.
* Utiliza guiones para separar las palabras en los nombres de las imágenes, por ejemplo: gato-en-el-tejado-caliente.jpg.
* Usa el tipo correcto de imagen para el trabajo: png para carteles, jpg para fotografías.
* Usa imágenes responsivas: hay un plugin de Joomla que crea dinámicamente versiones webp de imágenes png y jpg en varios tamaños.

*Traducido por openai.com*

