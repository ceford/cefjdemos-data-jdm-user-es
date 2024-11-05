<!-- Filename: J4.x:Article_Pagination / Display title: Artículo: Editar - Paginación  -->

## Artículos Largos

El único límite en la longitud de un artículo en Joomla es el tamaño del campo de la base de datos utilizado para contener el texto del artículo. ¡Eso es muy grande! Los artículos largos pueden contener muchas imágenes y tomar tiempo para procesar, lo cual puede resultar incómodo para el lector y para el sitio web. Por lo tanto, hay un mecanismo simple para dividir los artículos largos en páginas separadas con una tabla de contenido.

## Insertar un Salto de Página

Para añadir saltos de página, primero abre un artículo en el editor de texto, TinyMCE es el predeterminado, y procede de la siguiente manera:

- Coloca el cursor en el lugar donde quieras que ocurra un salto de página.
- Desde la lista desplegable **Contenido CMS**, selecciona el elemento *Salto de Página*.
- En el cuadro de diálogo de Salto de Página, introduce:
  - *Título de la Página* - esto se añadirá al título de página existente. Ejemplo: Página 2
  - *Alias del Índice de Contenidos* - esto se usará como texto en el Índice de Contenidos. Ejemplo: Capítulo 2
- Selecciona el botón **Insertar Salto de Página**.

![Formulario de diálogo de salto de página](../../../en/images/articles/articles-edit-pagination.png)

- Repite para cada salto de página que desees crear.
- Guarda el artículo y echa un vistazo a la Vista Previa o a la Vista del Sitio.

![Vista del sitio de paginación del artículo](../../../en/images/articles/articles-site-pagination.png)

## Editar o Mover un Salto de Página

Puedes seleccionar un salto de página y eliminarlo. Sin embargo, no puedes cortarlo y pegarlo, ni puedes abrir un salto de página existente en el formulario de Salto de Página. Así que para mover o cambiar un salto de página, utiliza el editor de Código Fuente de la siguiente manera:

- Selecciona el elemento **Herramientas -> Código fuente+** del editor de texto.
- El editor de código fuente muestra el HTML fuente con resaltado de sintaxis.
- Desplázate hacia abajo hasta el salto de página que deseas editar o mover.
- Para mover un salto de página:
  - Selecciona y corta la línea que contiene el salto de página.
  - Coloca el cursor en la nueva posición y pega la línea cortada.
- Para editar:
  - Cambia el texto del título y/o el texto alternativo como consideres apropiado.
- Selecciona **Guardar**.
- Guarda el artículo y revisa en la Vista Previa o Vista del Sitio.

El editor de Código fuente se encuentra en un cuadro de diálogo emergente:

![Editor de código fuente](../../../en/images/articles/articles-edit-pagination-source-code.png)

