<!-- Filename: Article_Images_and_Links / Display title: Artículo: Editar - Imágenes y Enlaces  -->

## Introducción

Otros artículos han descrito cómo incrustar imágenes y enlaces en el contenido de un artículo. Este artículo describe el uso de la pestaña *Imágenes y Enlaces* para agregar dos tipos de imágenes y hasta tres enlaces que se utilizarán en diseños estandarizados. En resumen:

- La *Imagen de Introducción* se utiliza en los diseños de Blog de Categoría o Lista como un adelanto visual adicional del tipo de contenido que se puede esperar.
- La *Imagen del Artículo Completo* se coloca en la parte superior del artículo completo como una introducción visual al contenido.
- Los enlaces: Enlace A, Enlace B y Enlace C se colocan por encima del texto del artículo.

## Captura de Pantalla

Para este artículo, comenzando con una imagen de una rana arbórea verde que tenía un ancho de 1024 píxeles, se crearon dos imágenes más pequeñas de 128 y 256 píxeles de ancho. Nota: es mejor preparar las imágenes en tu herramienta de procesamiento de imágenes favorita, como *Gimp*. Las imágenes de tamaño pequeño y mediano se han utilizado para crear las siguientes capturas de pantalla.

![Formulario de edición del artículo, pestaña de imágenes y enlaces](../../../en/images/articles/articles-edit-images-and-links-tab.png)

## Campos del formulario

### Imagen de introducción

- **Imagen de introducción** Selecciona una imagen adecuada para utilizar en los diseños de Blog donde normalmente aparecerá sobre el título del artículo. Esto es opcional. Si se deja vacío, no habrá imagen de introducción en el diseño del Blog.
- **Descripción de la imagen (Texto alternativo)** Introduce una descripción adecuada de la imagen para los lectores de pantalla.
- **Imagen decorativa** Si no hay *Descripción de la imagen* y esta opción no está seleccionada, la página no pasará las pruebas de accesibilidad. Si esta opción está seleccionada, se insertará un atributo `alt` vacío. Esto puede permitir que la página pase las pruebas de accesibilidad. Probablemente sea mejor usar siempre una buena descripción breve de la imagen.
- **Clase de la imagen** La clase predeterminada es *left*, lo que significa float-left. Pero cualquier otro valor de flotación aquí no tendrá efecto porque no se puede usar en elementos de grid o flex.
- **Subtítulo de la imagen** Las palabras ingresadas aquí aparecerán como un subtítulo debajo de la imagen. **Advertencia:** No utilices las mismas palabras exactas para tanto el texto alternativo como el texto del subtítulo. Los lectores de pantalla anunciarán la información dos veces.
    - El texto alternativo debe proporcionar una descripción concisa de lo que hay en la imagen.
    - El subtítulo generalmente debe proporcionar contexto para relacionar la imagen con el contenido circundante o dar atención a una pieza particular de información.

### Imagen del artículo completo

Los mismos campos que para la Imagen de introducción pero la imagen se usa en un contexto diferente. Consulta las capturas de pantalla del sitio a continuación.

### Enlace A

- **Enlace A** Pega la URL completa de la página de destino. Debe utilizarse la URL completa incluso si la página de destino está en este sitio.
- **Texto del Enlace A** Escribe el texto que se utilizará para el enlace de destino.
- **Ventana de destino de la URL** Elige una de las opciones de destino:
  - **Usar global (Abrir en la ventana principal)**
  - **Abrir en la ventana principal** Este es el comportamiento preferido porque se puede usar el botón *Atrás* del navegador para regresar a la página anterior.
  - **Abrir en una nueva ventana** A algunos usuarios les gusta esto, pero confunde a los usuarios móviles, ya que no es obvio que se haya invocado una nueva ventana y no hay botón de *Atrás*.
  - **Abrir en un popup** Aparece una pequeña ventana emergente. La ventana principal permanece disponible. Cada clic en el enlace abre otra instancia de la ventana emergente.
  - **Abrir en modal** Se abre un cuadro de diálogo modal en el centro de la pantalla que está inactivo hasta que se cierra el cuadro de diálogo.

### Enlaces B y C

Exactamente la misma entrada de datos que el Enlace A.  

## Capturas de Pantalla del Sitio

La captura de pantalla a continuación muestra un diseño de blog de categoría con la *Imagen de Introducción*. Podría haber sido mejor usar una imagen panorámica con la misma altura pero mucho mayor ancho para ocupar el espacio en blanco disponible.

![Página de blog de categoría de anfibios](../../../en/images/articles/articles-site-amphibians-blog.png)

La captura de pantalla a continuación muestra la página de un artículo individual con la *Imagen del Artículo Completo* y el Enlace A. La imagen se ha colocado flotante a la derecha y el título visible dice algo que complementa lo que dice la Descripción, de modo que suene lógico para los lectores de pantalla.

![Página de artículo individual de ranas](../../../en/images/articles/articles-site-amphibians-frogs.png)

*Traducido por openai.com*

