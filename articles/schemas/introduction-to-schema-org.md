<!-- Filename: J5.x:Schema_org / Display title: Introducción a los esquemas -->

## Fragmentos Enriquecidos

Los fragmentos enriquecidos (también conocidos como *resultados enriquecidos*) son resultados de búsqueda normales de Google con datos adicionales mostrados. Estos datos adicionales generalmente se recopilan a partir de datos estructurados encontrados en el HTML de una página. Los tipos comunes de fragmentos enriquecidos incluyen reseñas, recetas y eventos. Los fragmentos enriquecidos pueden ayudar a que los sitios web se destaquen en los resultados de búsqueda, atraigan más clics y ofrezcan a los usuarios una mejor comprensión del contenido antes de que hagan clic.

Joomla implementa Rich Snippets utilizando JSON-LD. Esta es una notación JavaScript incrustada en una etiqueta `<script>` en el elemento `<head>` de una página HTML. El marcado no está entrelazado con el texto visible por el usuario. El contenido de los snippets se introduce en los campos de formulario implementados con plugins.

## Schema.org

>Schema.org es una actividad colaborativa de la comunidad con la misión de crear, mantener y promover esquemas para datos estructurados en Internet, en páginas web, en mensajes de correo electrónico y más allá.

Los datos estructurados son un formato estandarizado para organizar y representar información en la web. Proporciona una forma de describir el contenido y el significado de los datos de manera estructurada, facilitando a los motores de búsqueda y otras aplicaciones la comprensión y el procesamiento de la información. Hay información más detallada en el [sitio web de Schema.org](https://schema.org/).

## Implementación de Joomla

En Joomla, los Rich Snippets se generan utilizando marcas de datos estructurados basadas en los esquemas de Schema.org. Cada tipo de esquema se implementa como un complemento separado. Esto permite una arquitectura más modular y extensible. Cada complemento es responsable de generar la marca de esquema para un tipo específico de contenido, lo que permite más flexibilidad y opciones de personalización. Esto facilita a los desarrolladores de terceros contribuir al desarrollo de las capacidades de datos estructurados de Joomla.

Para comenzar, vaya a **Sistema -> Plugins** y habilite el plugin *Sistema - Schema.org*. Si este plugin no está habilitado, no habrá una pestaña de Schema en un formulario de edición de artículo, incluso si todos los plugins individuales están habilitados.

![List of schema plugins](../../../en/images/schemas/schema-plugins-list.png)

### Editar Sistema - Plugin Schema.org

- **Tipo de Base** Elija si su sitio web representa a una organización o a una sola persona.
- **Nombre** Ingrese el nombre de la organización o persona que el sitio web representa.
- **Imagen** Agregue la imagen de su empresa o personal.
- **Cuentas de Redes Sociales** Agregue las cuentas de redes sociales de su empresa o personales. Seleccione el botón verde de signo más para agregar filas al formulario.
- Seleccione **Guardar y Cerrar**.

![edit system schema org plugin](../../../en/images/schemas/edit-system-schema-org-plugin.png)

### Editar un artículo

Ve a cualquiera de tus artículos y completa los campos del formulario de Schema. Si el *Tipo de Schema* está establecido en *None*, el valor predeterminado, no hay campos para completar. Selecciona cualquier Schema para ver una lista de campos apropiados para ese esquema. La siguiente captura de pantalla muestra un artículo con el esquema de Artículo seleccionado:

![edit article scheme form](../../../en/images/schemas/schema-form-in-an-article.png)

### Salida

No verás nada relacionado con el esquema en la página web. Sin embargo, si miras el código fuente de la página, verás una entrada de script, como en el siguiente ejemplo:

```json
	<script type="application/ld+json">{
    "@context": "https://schema.org",
    "@graph": [
        {
            "@type": "Organization",
            "@id": "http://localhost/jcms-testing/#/schema/Organization/base",
            "name": "Joomla Documentation Team",
            "url": "http://localhost/jcms-testing/"
        },
        {
            "@type": "WebSite",
            "@id": "http://localhost/jcms-testing/#/schema/WebSite/base",
            "url": "http://localhost/jcms-testing/",
            "name": "JCMS Testing",
            "publisher": {
                "@id": "http://localhost/jcms-testing/#/schema/Organization/base"
            }
        },
        {
            "@type": "WebPage",
            "@id": "http://localhost/jcms-testing/#/schema/WebPage/base",
            "url": "http://localhost/jcms-testing/index.php/en/article-en-gb",
            "name": "Article (en-gb)",
            "isPartOf": {
                "@id": "http://localhost/jcms-testing/#/schema/WebSite/base"
            },
            "about": {
                "@id": "http://localhost/jcms-testing/#/schema/Organization/base"
            },
            "inLanguage": "en-GB",
            "breadcrumb": {
                "@id": "http://localhost/jcms-testing/#/schema/BreadcrumbList/139"
            }
        },
        {
            "@type": "Article",
            "headline": "Article Schema Test",
            "description": "Latin text used to simulate layouts.",
            "author": {
                "@type": "person",
                "name": "Superman"
            },
            "@id": "http://localhost/jcms-testing/#/schema/com_content/article/1",
            "isPartOf": {
                "@id": "http://localhost/jcms-testing/#/schema/WebPage/base"
            }
        }
    ]
}</script>
```

Puedes probar tus datos estructurados a través de la [página de prueba de datos estructurados de Google](https://developers.google.com/search/docs/appearance/structured-data).

## Plugins disponibles

| Plugin             | Descripción                                     |
|--------------------|------------------------------------------------|
| Plugin de Artículo | El punto de partida para usar schema.org       |
| Plugin de Blogpost | Para contenido de entradas de blog             |
| Plugin de Libro    | Para contenido de libros                       |
| Plugin Personalizado| Para entrada directa de código JSON-LD        |
| Plugin de Evento   | Para contenido de eventos                      |
| Plugin de Oferta de Trabajo | Para contenido de ofertas de trabajo |
| Plugin de Organización | Para contenido de empresas y organizaciones|
| Plugin de Persona  | Para contenido de personas                     |
| Plugin de Receta   | Para contenido de recetas                      |

*Traducido por openai.com*

