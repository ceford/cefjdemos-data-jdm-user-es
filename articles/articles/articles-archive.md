<!-- Filename: J4.x:How_to_Archive_an_Article / Display title: Artículos: Archivo  -->

## Introducción

A medida que el contenido de tu sitio web crece, es probable que parte de ese contenido necesite ser actualizado o reemplazado. Es posible que elijas despublicar algunos artículos, pero puede que tengas el requisito de mantenerlos de una manera que las personas aún puedan verlos.

¡Joomla! hace que el archivado de artículos sea un proceso simple al permitirte cambiar el estado de un artículo a **Archivado**. Un beneficio de archivar es que facilita la gestión del contenido y el archivado está estructurado por año.

Este enfoque basado en el estado es una parte clave de la capacidad de Joomla para gestionar contenido de manera eficaz y eficiente. Una vez archivado, Joomla proporciona métodos para acceder y mostrar el contenido archivado.

## Archivar artículos

Puedes archivar un artículo en varios lugares:

- Un artículo anterior sobre
  [Agregar un Artículo](jdocmnaual?article=user/getting-started/adding-an-article)
  mostró una captura de pantalla de la página de lista de *Artículos* con un artículo seleccionado y
  la lista de *Acciones* en la barra de herramientas abierta para mostrar las opciones disponibles. Una de
  ellas es *Archivar*. Esa es probablemente la mejor manera de archivar un artículo. Nota
  que puedes archivar varios artículos a la vez. Seleccionar uno o más artículos
  habilitará la lista desplegable de **Acciones**.
- Cada artículo tiene una configuración de *Estado* en el formulario de edición del artículo. *Archivado*
  se puede establecer allí.
- Desde dentro de un tipo de elemento de menú *Artículo Único*. El campo *Seleccionar Artículo*
  tiene una opción de *Editar* que abre un formulario emergente de *Editar Artículo* donde el campo de *Estado*
  se puede establecer como en un formulario de edición de artículo estándar. El elemento de menú de
  artículo único aún enlaza al artículo archivado.

Los artículos archivados ya no aparecen en la lista de Artículos *predeterminada*. Selecciona el
botón de *Opciones de Filtro* y luego *Archivado* del filtro *- Seleccionar Estado -* para ver la lista de artículos archivados.

## Vista del sitio de artículos archivados

Una vez que los artículos han sido archivados, hay varias formas de verlos desde el
frontend del sitio.

### A través de un menú

Hay un tipo de elemento de menú [Artículos Archivados](jdocmanual?article=user/menus/menu-item-type-archived-articles) que puedes usar para crear un enlace en tu menú a artículos archivados.

### A través de un módulo

Hay un módulo [Artículos - Archivados](jdocmanual?article=user/modules/articles-archived-module) que puedes usar para mostrar en una de las posiciones de módulo de la plantilla de tu sitio web.

La siguiente captura de pantalla muestra una página de *Artículos Archivados* obtenida con un elemento de menú. Hay filtros para *Mes* y *Año* y un límite de lista con configuraciones de 5 a 100 y Todo. Siempre ten cuidado al usar *Todo*. Si devuelves miles de resultados, tu página puede ser lenta al cargar y no responder. Podrías quedarte sin tiempo o memoria, lo que podría llevar a que se devuelva un error del servidor.

![Vista de página de artículos archivados](../../../en/images/articles/articles-archived-site.png)

Al pie de la columna de la derecha está el módulo de *Artículos Archivados*.

## Desarchivar artículos

Para desarchivar un artículo se aplica el mismo proceso: el estado del artículo se cambia de **Archivado** a **Publicado**.

## Consejos

* Recuerda que los artículos archivados se filtran de la vista en la lista de *Artículos*. Debes cambiar el filtro de *Estado* a *Archivado* para verlos.
* Archivar no despublica un artículo.
* También puedes archivar artículos desde el frontend cuando inicies sesión para la edición desde el frontend.

*Traducido por openai.com*

