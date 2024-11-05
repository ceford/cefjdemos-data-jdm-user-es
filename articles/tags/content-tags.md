<!-- Filename: J4.x:How_To_Use_Content_Tags_in_Joomla / Display title: Etiquetas de Contenido  -->

## Introducción

Las etiquetas ofrecen una forma fácil y eficiente de organizar y mostrar contenido. El **Componente de Etiquetas** permite que las etiquetas se utilicen en diferentes tipos de contenido, incluidos artículos, categorías, contactos y canales de noticias. También permite la creación de etiquetas de padres e hijos.

A diferencia de las **Categorías** de Joomla, donde solo se puede asignar una categoría a un elemento, se pueden asignar múltiples etiquetas a un solo elemento, aunque no es obligatorio asignar etiquetas a los elementos.

Una vez que un elemento está etiquetado con una etiqueta específica, al hacer clic en el botón de etiqueta en el contenido que muestra las etiquetas, se dirigirá a una página que muestra una lista de todos los elementos que han sido etiquetados con esa etiqueta en particular. Por esta razón, las etiquetas se usan a menudo como una forma de presentar listas *filtradas* de contenido.

Las etiquetas se pueden añadir en varios lugares, ofreciendo flexibilidad en la creación de etiquetas.

## Consideraciones

Antes de comenzar, considera el propósito de las etiquetas en el sitio web, especialmente si otros van a añadir contenido. A menos que se gestionen y añadan correctamente, las etiquetas pueden volverse contraproducentes. Los problemas comunes incluyen que los redactores de contenido añaden etiquetas nuevas e innecesarias y nombres de etiquetas mal escritos. Algunos administradores del sitio pueden optar por cambiar los permisos de acceso para que solo usuarios específicos puedan añadir nuevas etiquetas.

Cuando se crean etiquetas, se mostrarán como enlaces en los elementos etiquetados. Los estilos y posiciones de las etiquetas están definidos por la plantilla del sitio. A menudo se estilizan como botones o etiquetas.

¡La visualización de etiquetas puede estar desactivada! Esto puede parecer ilógico, pero es una característica útil donde se usan las etiquetas, por ejemplo, para filtrar contenido para casos de uso específicos.

## La lista de etiquetas

- Selecciona **Componentes → Etiquetas** en el menú del Administrador.

![la página de lista de etiquetas](../../../en/images/tags/tags-list.png)

Independientemente de cómo se creen las etiquetas, se pueden encontrar en esta lista.

## Añadiendo Etiquetas

### A través de la Lista de Etiquetas

Selecciona el botón **Nuevo** en la Barra de herramientas de la lista de Etiquetas.

![nueva etiqueta llamada depredador](../../../en/images/tags/new-tag-predator.png)

- **Título** Este es el único campo *requerido*.
- **Alias** Este se crea a partir del Título al guardar.
- **Descripción** Siempre es mejor añadir una Descripción. Se muestra en los 
  formularios del Administrador y puede ser útil cuando se usan muchas etiquetas.
- **Padre** Déjalo configurado como *Ninguno* si esta es una etiqueta padre raíz. O elige 
  una etiqueta padre de la lista si esta es una etiqueta hija.
- **Estado** Este campo está configurado como *Publicado* por defecto. Puede configurarse 
  como *No Publicado*, *Archivado* o *En la papelera*.
- **Acceso** El nivel de Acceso es Público por defecto.
- **Nota** y **Nota de Versión:** Si es necesario, puedes añadir notas.
- **Guardar & Cerrar** La nueva etiqueta aparecerá en la Lista de Etiquetas. Si estás 
  creando múltiples etiquetas, puedes optar por hacer clic en **Guardar & Nuevo** en su lugar para 
  crear otra.

Una vez guardada, la etiqueta estará disponible para su uso en los diferentes tipos de contenido 
que las usan.

### Desde un Artículo

Es posible añadir nuevas etiquetas mientras se crea o edita un artículo. En la 
pestaña de Contenido del artículo, en el **Campo de Etiquetas**, ingresa el nombre de 
la nueva etiqueta y presiona **Enter** para guardar y asignar la etiqueta al artículo.

### Desde una Categoría

Las etiquetas pueden añadirse cuando se crea o edita una categoría. En la pestaña 
**Categoría**, ingresa el nombre de la etiqueta en el **Campo de Etiquetas** y presiona 
**Enter** para crear y asignar la nueva etiqueta.

### Desde un Contacto

Las etiquetas pueden añadirse cuando se crea o edita un Contacto. En la pestaña 
**Nuevo/Editar Contacto**, ingresa el nombre de la etiqueta en el **Campo de Etiquetas** 
y presiona **Enter** para crear y asignar la nueva etiqueta. También puedes añadir nuevas 
etiquetas al crear Categorías de Contacto.

### Desde un Canal de Noticias

Las etiquetas pueden añadirse al crear o editar un nuevo Canal de Noticias. En la 
pestaña **Nuevo/Editar Canal de Noticias**, ingresa el nombre de la etiqueta en el **Campo 
de Etiquetas** y presiona **Enter** para crear y asignar la nueva etiqueta. También puedes 
añadir nuevas etiquetas al crear Categorías de Canales de Noticias.

## Gestión de Etiquetas

Dondequiera que agregues nuevas etiquetas dentro de Joomla, todas aparecerán en la lista de etiquetas.
Usa la lista de etiquetas para encontrar, abrir y ajustar la configuración de las etiquetas.

### El Filtro de la Lista de Etiquetas

![filtro de lista de etiquetas por tipo](../../../en/images/tags/tags-list-filter.png)

Puedes manipular la lista de varias maneras:

- Busca una etiqueta usando una parte o todo su título en el campo de búsqueda.
- Reordena la lista usando arrastrar y soltar para optimizar el orden de salida.
- Publica o despublica etiquetas usando el botón de la columna de estado.
- Selecciona una o más etiquetas y utiliza el botón **Acciones** para Publicar, Despublicar, 
  Archivar, Registrar o Enviar a la Papelera las etiquetas seleccionadas.
- Selecciona una o más etiquetas y usa el botón **Acciones → Lote** para establecer el
  idioma o nivel de acceso.

### Configuración de Etiquetas

- Selecciona un **Título** de etiqueta para hacer cambios en su configuración.

En el formulario de edición de etiquetas:

- Las configuraciones de la pestaña **Detalles de la etiqueta** se cubrieron anteriormente.
- La pestaña **Opciones**:
  - Cambia el diseño de la página de la etiqueta (la página que aparece cuando
    haces clic en el enlace de la etiqueta - por ejemplo, misitio.com/etiquetas/mi-etiqueta). 
    Este diseño normalmente es la configuración predeterminada y depende de la plantilla.
  - Añade una Clase CSS para aplicar un estilo diferente (apariencia) al enlace
    para la etiqueta. Esto suele ser usado solo por el Administrador del Sitio.
  - Establece imágenes para la etiqueta: una imagen de adelanto para la lista de etiquetas 
    y/o una imagen completa para la página de la etiqueta.
- La pestaña **Publicación**: establece metadatos para la página de la etiqueta para 
  la optimización de motores de búsqueda (SEO).

## Cómo Joomla Muestra las Etiquetas

Una vez que se han creado etiquetas en su sitio, están disponibles para uso no solo en el contenido, sino también en algunos módulos útiles como **Etiquetas Populares** y **Etiquetas Similares**. Los siguientes ejemplos muestran cómo se ven en una instalación estándar usando la plantilla predeterminada **Cassiopeia**.

![ejemplo de uso de etiquetas sitio labrador amarillo](../../../en/images/tags/tag-examples-yellow-labrador.png)

Cuando haces clic en una de las etiquetas, serás llevado a una página que lista todos los elementos asignados a esa etiqueta en particular:

![ejemplo de uso de etiquetas sitio labrador negro](../../../en/images/tags/tag-examples-black-labrador.png)

Al hacer clic en una etiqueta, se te llevará a una página que muestra una lista de todos los elementos asignados a esa etiqueta en particular; en efecto, es una lista filtrada del contenido etiquetado de tu sitio web. Se proporciona una caja de filtro para facilitar la búsqueda de elementos a medida que la lista crece. También puedes establecer el número de resultados que deseas ver en una sola vista.

## Configuración de Etiquetas

Las etiquetas individuales heredan configuraciones de las opciones del componente de Etiquetas. Esto se trata en un tutorial aparte. [Pendiente] Selecciona el botón de **Opciones** en la barra de herramientas de la página de la lista de Etiquetas.

La configuración del componente de Etiquetas se puede anular a nivel de elemento de menú.

## Consejos

- Recuerda que las Etiquetas se utilizan en múltiples tipos de contenido
- Puedes añadir más de una Etiqueta a un elemento
- Utiliza el botón de Ayuda cuando tengas dudas

*Traducido por openai.com*

