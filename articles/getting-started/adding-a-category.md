<!-- Filename: J4.x:Getting_Started:_Adding_a_Category / Display title: Añadiendo una Categoría -->

## Introducción

Los propietarios de sitios web que tienen más de un puñado de artículos deberían pensar en la mejor forma de presentar el contenido para facilitar la navegación. Por ejemplo, si tienes un zoológico, un museo, una colección de minerales o simplemente un gran jardín, podrías tener quizás 1000 especímenes para describir. Un artículo para cada espécimen, con fotografías, necesita una estructura organizativa. Si los artículos fueran archivos, probablemente los pondrías en una jerarquía de archivos. En un CMS, los artículos no son archivos pero las categorías proporcionan una estructura similar en forma de árbol. Ejemplo:

| Categoría  | Subcategorías                           |
|------------|-----------------------------------------|
| Mamíferos  | Simios, Monos, Ungulados, Perros, Gatos |
| Reptiles   | Serpientes, Lagartos, Cocodrilos, Tortugas |
| Anfibios   | Ranas, Sapos                            |
| Aves       | Rapaces, Patos, Gaviotas, Pinzones, Pájaros |
| Artrópodos | Arañas, Mariposas, Abejas, Langostas    |
| Peces      | Tiburones, Salmones, Bacalaos, Arenques, Caballas |

Las subcategorías también pueden tener subcategorías adicionales. Una profundidad manejable máxima parece ser de alrededor de siete. Para la tabla anterior, un museo podría agregar más categorías principales:

```text
naturaleza -> vida -> animales -> mamíferos...
naturaleza -> vida -> plantas -> árboles...
naturaleza -> minerales...
historia -> egipto...
ciencia -> astronomía...
ciencia -> química...
```

¡Imaginen cuántos especímenes posee un museo nacional o de una pequeña ciudad!

## Tipos de Elementos del Menú

Hay varios tipos de elementos del menú diseñados para funcionar con Categorías:

- **Blog de Categoría** Este es un diseño de página que tiene uno o dos
  extractos de artículos principales, a menudo con el ancho completo
  de la página, luego varios extractos de artículos más en dos o tres columnas,
  y finalmente un mecanismo de paginación para enlazar más artículos en
  la misma categoría. El extracto es el contenido antes de un salto de página,
  a menudo los primeros uno o dos párrafos. Una página de *Inicio* de un sitio
  suele ser un blog de categoría que incluye *Todas las Categorías*. Un diseño de
  *Artículos Destacados* es similar a un blog de categoría y a menudo se usa
  también como página de Inicio.
- **Lista de Categoría** Este es un diseño de lista que muestra un listado de
  artículos en una categoría. Puede mostrarse con un filtro de Búsqueda para
  permitir buscar artículos por Título, Autor, Visitas, Etiquetas o Mes
  de publicación.
- **Listar Todas las Categorías en un Árbol de Categorías de Artículos** Este diseño
  lista un árbol de categorías comenzando desde un padre elegido. Cada rama es
  colapsable y es más útil para estructuras de árbol de categorías grandes y
  complejas.

Los elementos del menú se abordan en un artículo posterior.

## Crear una Categoría

El siguiente ejemplo utiliza una categoría de Mamíferos inspirada en la lista anterior para demostrar cómo crear una nueva Categoría:

![Formulario de edición de categoría](../../../en/images/getting-started/article-category-edit.png)

- Selecciona el elemento **Contenido** del menú del Administrador para expandirlo.
- Selecciona el icono **+** junto al elemento del menú *Categorías* para abrir el formulario de edición de Categoría.
- El formulario **Artículos: Nueva Categoría** tiene solo un campo obligatorio: el *Título*, en este caso *Mamíferos*.
- El campo **Descripción** es opcional, pero es mejor completarlo ya que se utiliza en algunas listas. Sugerencia:<br>
  *Los mamíferos son animales de sangre caliente que dan a luz crías vivas.*
- El campo **Padre** especifica si esta es una categoría primaria (-Sin Padre-) o una subcategoría seleccionada de la lista de categorías.
- **Guardar y Cerrar** para volver a la página de lista **Artículos: Categorías**.

Esta categoría ahora está disponible para su uso con artículos.

*Traducido por openai.com*

