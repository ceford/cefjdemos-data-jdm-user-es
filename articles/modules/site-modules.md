<!-- Filename: J4.x:Site_Modules / Display title: Módulos del Sitio  -->

## Introducción

Los módulos son extensiones ligeras y flexibles que se utilizan para mostrar fragmentos de información en **cajas** dispuestas alrededor de un componente en una página. Un ejemplo conocido es el módulo de inicio de sesión. Los módulos se asignan por elemento de menú, por lo que puedes decidir mostrar u ocultar un módulo dependiendo de qué página está viendo actualmente el usuario.

Algunos módulos están vinculados a componentes. Por ejemplo, el módulo de **Últimas Noticias** está vinculado al componente de contenido para mostrar enlaces a los artículos más recientes. Los módulos no necesitan estar vinculados a componentes. Ni siquiera necesitan estar vinculados a nada y pueden ser simplemente HTML o texto estático.

Puede haber múltiples instancias del mismo módulo. Por ejemplo, puedes usar una instancia del módulo de Imagen Aleatoria para algunas páginas y otra instancia para otras páginas, cada una utilizando una carpeta de imágenes diferente para seleccionar las imágenes.

## Posiciones de Módulo

Los módulos se asignan a una posición en una página definida por la plantilla en uso. La siguiente ilustración muestra un diseño esquemático de la plantilla Cassiopeia:

![Diagrama de posiciones de la plantilla Cassiopeia](../../../en/images/modules/cassiopeia-template-positions.png)

Y la siguiente lista muestra las posiciones de módulo disponibles por nombre:

```xml
	<positions>
		<position>barrasuperior</position>
		<position>debajo-superior</position>
		<position>menú</position>
		<position>búsqueda</position>
		<position>banner</position>
		<position>superior-a</position>
		<position>superior-b</position>
		<position>principal-superior</position>
		<position>principal-inferior</position>
		<position>migas-de-pan</position>
		<position>barra-lateral-izquierda</position>
		<position>barra-lateral-derecha</position>
		<position>inferior-a</position>
		<position>inferior-b</position>
		<position>pie</position>
		<position>depuración</position>
	</positions>
```

## Añadir un Módulo Núcleo

Los módulos núcleo son aquellos que se suministran con una nueva instalación de Joomla. Hay miles de módulos adicionales disponibles de proveedores externos. Supongamos que te gustaría mostrar una imagen aleatoria para hacer que tu sitio sea más interesante para los visitantes. Desde el menú del Administrador, selecciona **Contenido → Módulos del Sitio** para ver la lista de módulos del sitio que ya están en uso:

![Lista de Módulos del Sitio](../../../en/images/modules/cassiopeia-modules-list.png)

Selecciona el botón Nuevo para ver una lista de módulos del sitio disponibles para instalar:

![Módulos del Sitio disponibles](../../../en/images/modules/cassiopeia-modules-available.png)

Desplázate hacia abajo y selecciona el módulo de Imagen Aleatoria. Eso abrirá el formulario de edición **Módulos: Imagen Aleatoria** listo para que lo completes.

![Módulo de imagen aleatoria](../../../en/images/modules/cassiopeia-module-random-image.png)

- **Título** Este es un campo obligatorio.
- **Tipo de Imagen** El valor por defecto es jpg.
- **Carpeta de Imágenes** Introduce una ruta a una carpeta que realmente contenga imágenes del tipo que has seleccionado.
- **Enlace** Una URL a la que redirigir si se selecciona la imagen.
- **Ancho** Obliga a que todas las imágenes se muestren con este ancho en píxeles.
- **Altura** Déjalo vacío para mantener la relación de aspecto de la imagen.
- **Posición** Selecciona una posición de módulo para que el módulo aparezca en una página. En la ilustración, se ha seleccionado sidebar-right.
- **Guardar & Cerrar** O utiliza el botón de Ayuda en la Barra de Herramientas para descubrir qué hacen los otros campos.

## Orden de Módulos

Después de guardar, es posible que necesites cambiar el orden de los módulos en la posición elegida. Procede de la siguiente manera:

- En la lista de Módulos, selecciona el icono de Ordenación de Columnas en el encabezado de la tabla de módulos, que es un triángulo combinado hacia arriba/abajo. Eso ordenará la tabla y mostrará símbolos de arrastre de elementos, un elipsis vertical. ¡Selecciona de nuevo para invertir el orden de clasificación! El símbolo de ordenación de la columna cambia: triángulo hacia arriba para indicar el orden de clasificación normal, triángulo hacia abajo para indicar el orden de clasificación inverso.
- Agarra y arrastra el elipsis de Imagen Aleatoria para moverlo hacia arriba o hacia abajo. Suéltalo cuando esté en tu posición preferida.

## Ver el Sitio

![Vista del sitio del módulo de imagen aleatoria](../../../en/images/modules/cassiopeia-module-random-image-site.png)

Verifica la apariencia del sitio. En este caso, podría ser una buena idea centrar la imagen. Esto se puede hacer de la siguiente manera:

- Regresa al formulario de edición y selecciona la pestaña Avanzado.
- En el campo Clase del Módulo, ingresa text-center y guarda.
- Visualiza el resultado recargando la página del Sitio.

¿Todo listo?

## Lista de Módulos Principales

- **Artículos - Archivados** Este módulo muestra una lista de los meses del calendario que contienen Artículos Archivados. Después de haber cambiado el estado de un Artículo a Archivado, esta lista se generará automáticamente.
- **Artículos - Categorías** Este módulo muestra una lista de categorías de una categoría principal.
- **Artículos - Categoría** Este módulo muestra una lista de artículos de una o más categorías.
- **Artículos - Últimos** Este módulo muestra una lista de los Artículos más recientemente publicados y actuales.
- **Artículos - Más Leídos** Este módulo muestra una lista de los Artículos publicados que tienen el mayor número de visualizaciones.
- **Artículos - Noticias Destacadas** El Módulo de Noticias Destacadas mostrará un número fijo de artículos de una categoría específica.
- **Artículos - Relacionados** Este módulo muestra otros Artículos que están relacionados con el que se está viendo. Estas relaciones se establecen por las Palabras Clave. Todas las palabras clave del Artículo actual se buscan en todos los...
- **Banners** El Módulo de Banner muestra los Banners activos del Componente.
- **Migajas de Pan** Este módulo muestra las Migajas de Pan (Breadcrumbs).
- **Personalizado** Este módulo te permite crear tu propio Módulo usando un editor WYSIWYG.
- **Mostrar Feed** Este módulo permite la visualización de un feed sindicado.
- **Pie de Página** Este módulo muestra la información del copyright de Joomla!.
- **Cambiador de Idioma** Este módulo muestra un cambiador de idioma en tu sitio web de los idiomas de contenido disponibles.
- **Últimos Usuarios** Este módulo muestra los últimos usuarios registrados.
- **Iniciar Sesión** Este módulo muestra un formulario de inicio de sesión con nombre de usuario y contraseña. También muestra un enlace para recuperar una contraseña olvidada. Si el registro de usuarios está habilitado (en Usuarios → Administrar → Opciones),...
- **Menú** Este módulo muestra un menú en el Frontend.
- **Imagen Aleatoria** Este módulo muestra una imagen aleatoria de la carpeta elegida.
- **Búsqueda Inteligente** Este es un módulo de búsqueda para el sistema de Búsqueda Inteligente.
- **Estadísticas** El Módulo de Estadísticas muestra información sobre la instalación de tu servidor junto con estadísticas sobre los usuarios del sitio web y el número de Artículos en tu base de datos.
- **Feeds de Sindicación** Módulo de Sindicación Inteligente que crea un Feed Sindicado para la página donde se muestra el Módulo.
- **Etiquetas - Populares** Este módulo muestra etiquetas usadas en el sitio en una lista o en un diseño de nube. Las etiquetas pueden ordenarse por título o por el número de elementos etiquetados y limitarse a un período de tiempo específico.
- **Etiquetas - Similares** El Módulo de Etiquetas Similares muestra enlaces a otros elementos con etiquetas similares. Se puede especificar la cercanía de la coincidencia.
- **Quién está en Línea** El Módulo de Quién está en Línea muestra el número de Usuarios Anónimos (Invitados) y Usuarios Registrados (usuarios registrados) que actualmente están accediendo al sitio web.
- **Contenedor** Este módulo muestra una ventana de iframe a una ubicación especificada.

