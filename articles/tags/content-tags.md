<!--
{
    "source": "https://docs.joomla.org/J4.x:How_To_Use_Content_Tags_in_Joomla",
    "title": "Etiquetas de contenido",
    "description": " ",
    "author": ""
}
-->

## Introducción

Las etiquetas proporcionan una forma fácil de usar y eficaz de organizar y mostrar contenido. 
El **componente Etiquetas** permite utilizar etiquetas individuales en distintos tipos de 
contenido, incluidos artículos, categorías, contactos y fuentes de noticias. También permite crear etiquetas principales y secundarias.

A diferencia de las **categorías** de Joomla, donde solo se puede asignar una categoría a
un elemento, se pueden asignar varias etiquetas a un solo elemento, aunque no es 
obligatorio asignar etiquetas a los elementos.

Una vez que un elemento se etiqueta con una etiqueta específica, al hacer clic en el botón de la etiqueta en
el contenido que muestra etiquetas, se accede a una página que muestra una lista de
todos los elementos que se han etiquetado con esa etiqueta concreta. Por este
motivo, las etiquetas se utilizan a menudo como una forma de presentar listas de contenido
*filtradas*.

Las etiquetas se pueden añadir en varios lugares, lo que proporciona flexibilidad en su creación.

## Consideraciones

Antes de empezar, considere el propósito de las etiquetas en el sitio web, especialmente
si otras personas van a añadir contenido. Si no se añaden y gestionan
correctamente, las etiquetas pueden resultar contraproducentes. Entre los problemas habituales se incluyen
que los redactores de contenido añadan etiquetas nuevas e innecesarias y nombres de etiquetas
mal escritos. Algunos administradores del sitio pueden optar por cambiar los permisos de acceso para que 
solo determinados usuarios puedan añadir etiquetas nuevas.

La siguiente captura de pantalla muestra etiquetas utilizadas en un sitio que contiene artículos sobre 
sitios del Patrimonio Mundial de la UNESCO. En este caso, cada etiqueta tiene un color distintivo. 

![página de lista de etiquetas](../../../en/images/tags/content-tags/01-tags-example.png)

Cuando se crean etiquetas, se muestran como enlaces en los elementos etiquetados. 
Los estilos y las posiciones de las etiquetas los define la plantilla del sitio. A menudo 
se muestran como botones o etiquetas.

La visualización de etiquetas se puede desactivar para artículos individuales o para todos los artículos. 
Esto puede parecer ilógico, pero es una función útil cuando las etiquetas se utilizan, por 
ejemplo, para filtrar contenido para casos de uso específicos.

## La lista de etiquetas

- Seleccione **Componentes → Etiquetas** en el menú de administración.

Esta captura de pantalla muestra etiquetas en una estructura utilizada para un sitio multilingüe.
Cada idioma tiene una lista de etiquetas con una etiqueta de idioma como elemento principal. 
La etiqueta principal se utiliza en los módulos *Etiquetas populares* y *Etiquetas similares*.

![página de lista de etiquetas](../../../en/images/tags/content-tags/02-tags-list.png)

Independientemente de cómo se creen las etiquetas, se pueden encontrar en esta lista.

- Seleccione el botón **Nuevo** de la barra de herramientas para crear una etiqueta nueva.
- Seleccione el **Título** de una etiqueta para editar una etiqueta existente.

### La pestaña Detalles de la etiqueta

![pestaña de opciones del formulario de edición de etiquetas que muestra clases CSS de Bootstrap](../../../en/images/tags/content-tags/03-edit-tag-details-tab.png)

- **Título** Este es el único campo *obligatorio*. 
- **Alias** Se crea a partir del título al guardar.
- **Descripción** Siempre es recomendable añadir una descripción. Se muestra en 
  los formularios de administración y puede ser útil cuando se utilizan muchas etiquetas.
- **Principal** Déjelo establecido en *Ninguno* si se trata de una etiqueta que no tiene una etiqueta principal. O elija una 
  etiqueta principal de la lista para convertirla en una etiqueta secundaria.
- **Estado** Este campo está establecido en *Publicado* de forma predeterminada. Se puede establecer como 
  *Despublicado*, *Archivado* o *En la papelera*.
- **Acceso** El nivel de acceso es Público de forma predeterminada.
- **Nota** y **Nota de versión:** Si es necesario, puede añadir notas.
- **Guardar y cerrar** Si está creando varias etiquetas, puede seleccionar **Guardar y nuevo** para crear una etiqueta nueva.

### La pestaña Opciones

- **Diseño** Puede haber varios diseños entre los que elegir, y puede crear su propio diseño con una anulación de plantilla.
- **Clase CSS para el enlace de la etiqueta** De forma predeterminada, las etiquetas se muestran como un botón azul. Puede introducir aquí declaraciones de clase para personalizar el aspecto de las etiquetas y asignar distintos colores a diferentes etiquetas. Ejemplo: `bg-danger-subtle border border-danger` son clases de Bootstrap que producen un botón rosa con un borde rojo.
- **Imagen de avance e imagen completa** Establezca imágenes para la etiqueta: una imagen de avance para la lista de etiquetas o una imagen completa para la página de la etiqueta, o ambas.

![pestaña de opciones del formulario de edición de etiquetas que muestra clases CSS de Bootstrap](../../../en/images/tags/content-tags/04-edit-tag-options-tab.png)

### La pestaña Publicación

- Establezca los metadatos de la página de la etiqueta para la optimización para motores de búsqueda (SEO).

## Métodos de creación alternativos

### Desde un artículo

Es posible añadir etiquetas nuevas mientras se crea o edita un artículo. En
la pestaña Contenido del artículo, en el **campo Etiquetas**, introduzca el nombre de la etiqueta nueva y
pulse **Intro** para guardar y asignar la etiqueta al artículo.

### Desde una categoría

Las etiquetas se pueden añadir al crear o editar una categoría. En la pestaña **Categoría**,
introduzca el nombre de la etiqueta en el **campo Etiquetas** y pulse **Intro** para crear
y asignar la etiqueta nueva.

### Desde un contacto

Las etiquetas se pueden añadir al crear o editar un contacto. En la pestaña 
**Nuevo/Editar contacto**, introduzca el nombre de la etiqueta en el **campo Etiquetas** y pulse 
**Intro** para crear y asignar la etiqueta nueva. También puede añadir etiquetas nuevas al crear categorías de contactos.

### Desde un canal de noticias

Se pueden añadir etiquetas al crear o editar un nuevo canal de noticias. En la pestaña **Nuevo/Editar canal de noticias**, introduzca el nombre de la etiqueta en el **campo Etiquetas** y pulse **Intro** para crear y asignar la nueva etiqueta. También puede añadir nuevas etiquetas al crear categorías de canales de noticias.

## Gestión de etiquetas

Siempre que añada nuevas etiquetas en Joomla, aparecerán en la lista de etiquetas.
Use la lista de etiquetas para buscar, abrir y ajustar la configuración de las etiquetas.

Puede manipular la lista de varias maneras:

- Busque una etiqueta utilizando parte o todo su título o alias en el campo de búsqueda.
- Reordene la lista mediante arrastrar y soltar para optimizar el orden de salida.
- Publique o deje de publicar etiquetas utilizando el botón de la columna Estado.
- Seleccione una o más etiquetas y utilice el botón **Acciones** para publicar, dejar de publicar, archivar, registrar o enviar a la papelera las etiquetas seleccionadas.
- Seleccione una o más etiquetas y utilice el botón **Acciones → Procesar por lotes** para establecer el idioma o el nivel de acceso.

## Salidas de etiquetas

Una vez creadas las etiquetas en su sitio, estarán disponibles para utilizarlas en el contenido y en módulos como **Etiquetas populares** y **Etiquetas similares**. Los siguientes ejemplos muestran cómo podrían verse en un sitio que utiliza la plantilla predeterminada **Cassiopeia**.

![etiquetas mostradas en un artículo y en los módulos de etiquetas populares y etiquetas similares](../../../en/images/tags/content-tags/05-tag-modules-site-view.png)

Al seleccionar una de las etiquetas, accederá a una página que muestra una lista de todos los elementos asignados a esa etiqueta concreta:

![ejemplo de uso de etiquetas en el sitio, labrador negro](../../../en/images/tags/content-tags/06-items-with-cultural-site-tag.png)

La lista de elementos es una lista filtrada del contenido del sitio web que tiene la etiqueta seleccionada.
Se proporciona un cuadro de filtro para facilitar la búsqueda de elementos a medida que crece la lista. 
También puede establecer el número de resultados que desea ver en una sola vista.

## Configuración de etiquetas

Las etiquetas individuales heredan la configuración de las opciones del componente Etiquetas. Seleccione el botón **Opciones** en la barra de herramientas de la página de la lista de etiquetas para ver las opciones de etiquetas predeterminadas disponibles.

Las opciones de configuración del componente Etiquetas se pueden sustituir en los niveles del elemento de contenido o del elemento de menú.

## Consejos

- Recuerde que las etiquetas se utilizan en varios tipos de contenido.
- Puede añadir más de una etiqueta a un elemento.
- Utilice el botón Ayuda de la barra de herramientas cuando tenga dudas.

*Traducido por openai.com*