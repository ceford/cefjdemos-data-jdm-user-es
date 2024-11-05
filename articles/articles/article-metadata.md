<!-- Filename: J6.x:_Article_Metadata / Display title: Artículo: Editar - Metadatos  -->

## Introducción

Los metadatos son información sobre una página web contenida en la primera parte de la página entre las etiquetas `<head>...</head>`. La mayoría de esta información no es visible para los visitantes del sitio, pero los motores de búsqueda la utilizan para proporcionar resultados apropiados para las solicitudes de búsqueda. Por lo tanto, es de tu interés utilizar metadatos informativos.

Algunos de los elementos de metadatos son proporcionados por la plantilla en uso y no necesitas configurarlos tú mismo. Ejemplos comunes:

```html
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="generator" content="Joomla! - Open Source Content Management">
```
Existen otras formas de metadatos como Open Graph Data utilizado por Facebook y esquemas utilizados para describir tipos específicos de páginas como Persona, Lugar o Producto. No se cubren aquí.

Los elementos de metadatos que a menudo se descuidan son el **Título** de la página, que aparece dentro de las etiquetas `<title>...</title>` en el `<head>` de la página, y la **Descripción** de la página, que aparece dentro de las etiquetas `<meta>` pero que puede estar ausente. Se cubren aquí.

## El título de la página

Se requiere un título para cualquier página nueva. Algunas pautas y consejos del
Mozilla Developer Network para componer buenos títulos:

>* Evita títulos de una o dos palabras. Usa una frase descriptiva, o un emparejamiento de término-definición para páginas de glosario o estilo referencia.
>* Los motores de búsqueda suelen mostrar los primeros 55–60 caracteres de un título de página. El texto que excede ese límite puede perderse, así que intenta no tener títulos más largos que eso. Si debes usar un título más largo, asegúrate de que las partes importantes aparezcan primero y que nada crítico se pierda en la parte del título que probablemente será cortada.
>* No uses "aglomeraciones de palabras clave". Si tu título es solo una lista de palabras, los algoritmos a menudo reducen la posición de tu página en los resultados de búsqueda.
>* Trata de asegurarte de que tus títulos sean lo más únicos posible dentro de tu propio sitio. Los títulos duplicados o casi duplicados pueden contribuir a resultados de búsqueda inexactos.

Recomendaciones adicionales de Google:

>- Especifica un título único para cada página.
>- Haz que tu título sea descriptivo del contenido de la página y conciso.
>- Evita el relleno de palabras clave (usar repetidamente palabras similares como "Foobar, foo bar, foobars, foo bars").
>- Evita usar títulos genéricos: cada página debería tener un título único, idealmente actualizado dinámicamente en relación con el contenido que se muestra.
>- Marca tus títulos, pero hazlo de manera concisa y en relación con el contenido que se sirve.

Hay varias herramientas para webmasters que pueden utilizarse para identificar si hay problemas con tus listados en un motor de búsqueda en particular; siempre vale la pena prestar atención y corregir cualquier problema. Un ejemplo:

[Artículo de soporte de Google sobre el uso de títulos para tus páginas web](http://support.google.com/webmasters/bin/answer.py?hl=en&amp;answer=35624)

En Joomla, para una sola página, el título del artículo se convierte en el título de la página usado en 
el encabezado y mostrado en la pestaña del navegador. Para una página compuesta, como 
*Artículos Destacados* o un *Blog de Categoría*, el título del ítem de menú se convierte en el título de la página. Por lo tanto, es necesario reflexionar sobre la composición de buenos títulos descriptivos tanto para los artículos como para los ítems de menú.

## La Descripción de la Página

El artículo *Meta Descripción* es un campo en la pestaña *Publicar* del formulario de entrada de datos del artículo:

![La pestaña de la edición del formulario del artículo publicación](../../../en/images/articles/articles-edit-publishing-tab.png)

Si no hay una descripción de metadatos del artículo, se usará una descripción de metadatos de un solo artículo en el menú si está configurada. Si no hay una descripción de metadatos en el menú, se utilizará la descripción meta global del sitio si está configurada. De lo contrario, se omitirá el campo de descripción de metadatos.

Google recomienda lo siguiente para asegurarse de que saque el máximo provecho de su indexación en motores de búsqueda:

>- Asegúrate de que cada página tenga descripciones meta únicas y relevantes.
>- Asegúrate de aplicar metadatos para páginas de lista (por ejemplo, blog y diseños de lista) además de artículos individuales. Esto es comúnmente pasado por alto en sitios web de Joomla!
>- Incluye información factual si es relevante (por ejemplo, artículos de blog pueden incluir el autor, productos pueden incluir el precio o fabricante).
>- Considera usar metadatos generados automáticamente, pero asegúrate de que sean relevantes, legibles y precisos.
>- ¡Haz que tus descripciones sean descriptivas!

Otra referencia:

[Artículo de soporte de Google sobre el uso de metadatos](http://support.google.com/webmasters/bin/answer.py?hl=es&amp;answer=35624)

## Palabras clave

Érase una vez, los motores de búsqueda utilizaban palabras clave para ayudar a clasificar el contenido. Así que los autores llenaban los metadatos de sus palabras clave con una gran cantidad de términos con la esperanza de aumentar su clasificación en SEO. Y en respuesta, Google dejó de usar palabras clave para propósitos de clasificación. Busca en la web consejos y encontrarás algunas fuentes que dicen que no vale la pena preocuparse y otras que dicen que todavía tienen valor.

Las palabras clave no son utilizadas por el núcleo de Joomla. Si tienes dudas, no te molestes.

## Robots

El valor predeterminado de *Usar Global* no coloca una metaetiqueta en el encabezado de la página HTML. Otros valores sí lo hacen. Hay un archivo `robots.txt` en la raíz del sitio de Joomla. Si deseas controlar los robots, deberías leer este archivo. Tiene una explicación sobre cómo usarlo.

## Autor

Podrías ingresar el nombre formal del autor para que aparezca como metadatos.

## Derechos

Puedes ingresar un aviso de derechos de autor para que aparezca como metadatos.

## Ejemplo de metadatos

Así es como se ven los metadatos en la vista de origen del artículo: Aquí hay un ejemplo del contenido del `<head>` después de completar todos los campos de metadatos:

```html
    <meta charset="utf-8">
    <meta name="rights" content="Charles Darwin © 1859">
    <meta name="author" content="Charles Darwin">
    <meta name="robots" content="noindex, nofollow">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="description" content="Publicidad para El origen de las especies.">
    <meta name="generator" content="Joomla! - Gestión de Contenidos de Código Abierto">
    <title>Publicidad</title>
```
Note que el campo de salida de palabras clave está ausente.

*Traducido por openai.com*

