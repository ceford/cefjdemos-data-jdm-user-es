<!-- Filename: Smart_Search_content_change_test_plan / Display title: Plan de Pruebas de Búsqueda Inteligente -->

El siguiente es un plan de pruebas preliminar que abarca (principalmente) la actualización del índice de Búsqueda Inteligente cuando ocurren varios tipos de actualizaciones de contenido.

La Búsqueda Inteligente debe probarse para cada uno de los tipos de contenido central admitidos. Estos son:

- Artículos
- Categorías
- Contactos
- Fuentes de noticias
- Enlaces web

Para cada uno de los tipos de contenido mencionados, debemos probar lo siguiente:

## Cambios de texto

Cambiar varios campos de texto dentro de un elemento de contenido debería cambiar los términos de búsqueda en el índice (con una excepción notable descrita a continuación). No es necesario probar todos los campos de texto para un tipo de contenido dado, ya que si funciona para uno, funcionará para todos, así que simplemente elija uno para cada tipo de contenido. Los siguientes campos de texto están indexados para los componentes principales:

- Artículos
  - Título
  - Alias
  - Texto del artículo
  - Descripción de metadatos
  - Palabras clave de metadatos
  - Autor de metadatos
  - Autor
  - Creado por alias
- Categorías
  - Título
  - Alias
  - Descripción
  - Enlace ??? (no estoy seguro de que exista tal campo)
  - Descripción de metadatos
  - Palabras clave de metadatos
  - Autor de metadatos
  - Autor
- Contactos
  - Nombre
  - Alias
  - Nombre de usuario vinculado
  - Otra información
  - Posición (si está habilitada en Opciones)
  - Dirección (si está habilitada en Opciones)
  - Ciudad (si está habilitada en Opciones)
  - Región (si está habilitada en Opciones)
  - País (si está habilitada en Opciones)
  - Código postal (si está habilitada en Opciones)
  - Teléfono (si está habilitada en Opciones)
  - Fax (si está habilitada en Opciones)
  - Correo electrónico (si está habilitada en Opciones)
  - Página web (si está habilitada en Opciones)
- Noticias 
  - Título
  - Alias
  - Enlace
  - Descripción de metadatos
  - Palabras clave de metadatos
  - Autor de metadatos
  - Autor
  - Creado por alias
- Enlaces web
  - Título
  - Alias
  - URL
  - Descripción
  - Descripción de metadatos
  - Palabras clave de metadatos
  - Autor de metadatos
  - Autor
  - Creado por alias

Para probar, simplemente agregue una cadena de texto aleatoria, como "xyz", dentro de un conjunto de texto regular y hacia la parte superior, luego intente buscar ese término desde la interfaz.

- su cadena aleatoria debería aparecer en la lista de autocompletado a medida que la ingresa.
- su cadena aleatoria debería aparecer 3 veces en la lista de autocompletado.
  - por sí sola
  - junto con la siguiente palabra que le sigue
  - junto con las siguientes 2 palabras que le siguen
- el elemento de contenido que contiene su cadena aleatoria debería aparecer en la lista de resultados de búsqueda.
- su cadena aleatoria debería estar resaltada en los resultados de búsqueda, siempre que la haya ingresado cerca de la parte superior del texto (porque el texto en los resultados de búsqueda está truncado).

Elimine su cadena aleatoria del texto: Esto debería eliminar los 3 términos/frases de búsqueda del índice. Buscar cualquiera de los 3 términos de búsqueda no debería producir resultados de búsqueda.

Elimine el elemento de contenido: Esto eliminará todos los términos/frases de búsqueda utilizados en el elemento de contenido del índice, excepto cuando esos términos/frases de búsqueda aún estén utilizados en otros elementos de contenido.<sup>[\[1\]](#cite_note-1)</sup>

El elemento de contenido eliminado no debería aparecer en ninguna lista de resultados de búsqueda.

## Cambios de estado del artículo de contenido

Encuentra un artículo de contenido del tipo requerido utilizando la Búsqueda Inteligente. Luego haz estas pruebas:

- Mueve el artículo a la papelera y repite la búsqueda. El artículo ya no debería aparecer en los resultados de búsqueda.
- Publica nuevamente el artículo y repite la búsqueda. El artículo debería aparecer nuevamente en los resultados de búsqueda.
- Despublica el artículo y repite la búsqueda. El artículo ya no debería aparecer en los resultados de búsqueda.
- Archiva el artículo y repite la búsqueda. El artículo debería aparecer nuevamente en los resultados de búsqueda.

## Cambios en el mapa de contenido (taxonomía)

Aunque los cambios en la categoría son un caso especial de cambios en el mapa de contenido, también necesitamos probar cambios en ramas del mapa de contenido no pertenecientes a categorías porque los cambios en categorías ejercitan un código diferente. Estos son los campos no pertenecientes a categorías que están sujetos a mapas de contenido en los componentes principales:

- Artículos
  - Autor
  - Categoría
  - Idioma
- Contactos
  - Categoría
  - País
  - Idioma
  - Región
- Fuentes de noticias
  - Categoría
  - Idioma
- Enlaces web
  - Categoría
  - Idioma

Por lo tanto, elige uno (si uno funciona, todos funcionarán para ese tipo de contenido) de los anteriores que sea apropiado para el tipo de contenido y verifica que:

- cambiar el campo da como resultado que el elemento aparezca en una búsqueda utilizando el menú desplegable correspondiente (en búsqueda avanzada) para el campo que cambiaste. <sup>[\[2\]](#cite_note-2)</sup>
- el elemento de contenido no aparece en una búsqueda utilizando el valor antiguo del campo.

Elimina el elemento de contenido y verifica que ya no aparezca en los resultados de búsqueda utilizando el filtro desplegable relevante. Ten en cuenta que **no** se espera que un nodo no utilizado sea eliminado del filtro desplegable correspondiente. <sup>[\[3\]](#cite_note-3)</sup>

## Cambios de estado de la categoría

Cambiar el estado de la categoría a la cual pertenece un ítem debería actualizar el índice de ese ítem. Además, cambiar el estado de una categoría principal de la categoría a la cual pertenece un ítem también debería actualizar el índice de ese ítem. Para probar, encuentra o crea un ítem con la siguiente estructura:

    Categoría A que contiene a la Categoría A.1 que contiene el ítem de contenido

Cambia el estado de la Categoría A.1 y prueba de la siguiente manera:

- Envía a la papelera la Categoría A.1 y repite la búsqueda. El ítem ya no debería aparecer en los resultados de búsqueda.
- Publica la Categoría A.1 nuevamente y repite la búsqueda. El ítem debería aparecer nuevamente en los resultados de búsqueda.
- Despublica la Categoría A.1 y repite la búsqueda. El ítem ya no debería aparecer en los resultados de búsqueda.
- Archiva la Categoría A.1 y repite la búsqueda. El ítem debería aparecer nuevamente en los resultados de búsqueda.

Restaura la Categoría A.1, luego cambia el estado de la Categoría A y prueba de la siguiente manera:

- Envía a la papelera la Categoría A y repite la búsqueda. El ítem ya no debería aparecer en los resultados de búsqueda.
- Publica la Categoría A nuevamente y repite la búsqueda. El ítem debería aparecer nuevamente en los resultados de búsqueda.
- Despublica la Categoría A y repite la búsqueda. El ítem ya no debería aparecer en los resultados de búsqueda.
- Archiva la Categoría A y repite la búsqueda. El ítem debería aparecer nuevamente en los resultados de búsqueda.

## Cambios en el nivel de acceso de un elemento de contenido

Cambia el nivel de acceso de un elemento de contenido a algo que un usuario del front-end no debería poder ver.

- verifica que el elemento de contenido no aparezca en las listas de resultados de búsqueda.

Cambia el nivel de acceso de nuevo a algo que un usuario del front-end debería poder ver.

- verifica que el elemento de contenido ahora aparezca en las listas de resultados de búsqueda.

Ten en cuenta que los términos de búsqueda dentro del elemento de contenido seguirán apareciendo en la lista de autocompletar, incluso si el usuario no tiene acceso al propio elemento de contenido. Este es un comportamiento esperado, aunque es algo que podríamos querer investigar. <sup>[\[4\]](#cite_note-4)</sup>

## Cambios en el nivel de acceso de la categoría

Cambiar el nivel de acceso de la categoría a la que pertenece un elemento
debería actualizar el índice para ese elemento. Además, cambiar el nivel
de acceso de una categoría principal de la categoría a la que pertenece un
elemento también debería actualizar el índice para ese elemento. Para probar,
encuentra o crea un elemento con la siguiente estructura:

    Categoría A conteniendo la Categoría A.1 que contiene un ítem de contenido

Realiza las siguientes pruebas:

- Cambia el nivel de acceso de la Categoría A.1 a algo que un usuario del
  front-end no debería poder ver.
  Verifica que el ítem de contenido no aparece en las listas de resultados de búsqueda.
- Cambia el nivel de acceso de la Categoría A.1 de nuevo a algo que un
  usuario del front-end debería poder ver.
  Verifica que el ítem de contenido ahora aparece en las listas de resultados de búsqueda.
- Cambia el nivel de acceso de la Categoría A a algo que un usuario del
  front-end no debería poder ver.
  Verifica que el ítem de contenido no aparece en las listas de resultados de búsqueda.
- Cambia el nivel de acceso de la Categoría A de nuevo a algo que un
  usuario del front-end debería poder ver.
  Verifica que el ítem de contenido ahora aparece en las listas de resultados de búsqueda.

## Cambios de estado en la Búsqueda Inteligente

En la pantalla Administrador → Componentes → Búsqueda Inteligente → Mapas de Contenido, es posible cambiar el estado de publicación/no publicación de las ramas y nodos del mapa de contenido. Se deben realizar las siguientes pruebas:

- Despublicar una rama del mapa de contenido (por ejemplo, Autor). Verifique que el menú desplegable del filtro para esa rama ya no sea visible en la búsqueda avanzada.
- Despublicar un nodo del mapa de contenido (dentro de una rama publicada). Por ejemplo, "Animales" dentro de la rama "Categoría". Verifique que el nodo no esté listado en el menú desplegable del filtrado para la rama en la búsqueda avanzada.

En la pantalla Administrador → Componentes → Búsqueda Inteligente → Contenido Indexado, realice la siguiente prueba:

- Despublicar un elemento de contenido. Verifique que el elemento de contenido ya no aparezca en los resultados de búsqueda.

En la pantalla Administrador → Extensiones → Gestor de Complementos, realice la siguiente prueba:

- Establezca el filtro "Seleccionar tipo" a "finder" o "búsqueda inteligente".
- Seleccione uno de los complementos de tipo de contenido y despublíquelo. Todos los datos para ese tipo de contenido deberían eliminarse del índice.

Nota: Si publica el complemento nuevamente, no se agregarán los datos al índice. Este es el comportamiento esperado. Será necesario ejecutar el indexador nuevamente para recuperar los datos.

