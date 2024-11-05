<!-- Filename: J4.x:Submenus / Display title: Submenús  -->

## Conceptos Básicos de Menús

En Joomla, tres elementos contribuyen a la visualización de un menú para el usuario:

- Un Menú es un contenedor para elementos de menú.
- Un Elemento de Menú es un enlace a una página del sitio o a una página externa.
- Un Módulo de Menú proporciona un método para asignar el menú a una posición en la página y controlar aspectos de la apariencia o el comportamiento del menú o la página.

Los menús simples consisten en listas de enlaces. A veces, los miembros de una lista tienen relaciones padre-hijo que se muestran como niños sangrados o listas desplegables. Las relaciones padre-hijo pueden anidarse a cualquier nivel. Sin embargo, anidar más allá de dos niveles puede hacer que las listas sean poco atractivas e incómodas de usar.

Hay ocasiones en las que puedes desear mostrar los hijos de un menú principal como un submenú separado. Un caso de uso común es mostrar un submenú a la izquierda de una página, el contenido de la página en el centro y un índice de contenidos de la página a la derecha. Este tutorial explica cómo hacerlo.

### Datos de Ejemplo

Supongamos que tienes una serie de artículos sobre animales. Podría ser sobre mascotas, una hoja de información veterinaria o un zoológico. El siguiente es un ejemplo corto de estructura con fines de demostración:

    Animales
        Gatos
            Birmano
            Azul Ruso
        Perros
            Collies
            Pomeranias

Las listas podrían ser bastante largas, por lo que podrías querer mostrar solo una lista de razas de gatos en las páginas sobre gatos y solo una lista de razas de perros en las páginas sobre perros. La siguiente captura de pantalla muestra la disposición objetivo que el usuario quisiera lograr:

![objetivos submenús animales gatos](../../../en/images/menus/submenus-objectives-animals-cats.png)

En este ejemplo, cuando el usuario selecciona el elemento de menú Animales se carga la página de Animales y el módulo de menú de Gatos desaparece (tampoco hay módulo de Perros). Selecciona el elemento de menú Gatos y el módulo de menú de Gatos aparece junto a la página de Gatos. Selecciona el elemento de menú Birmano y aparece la página de Birmano. Selecciona el elemento de menú Perros y el módulo de menú de Gatos es reemplazado por un módulo de menú de Perros junto a la página de Perros.

Para probar este tutorial por ti mismo necesitarás crear algunos artículos, un menú con elementos de menú y tres módulos de menú.

## Crear Artículos

Si eres súper eficiente, puedes crear un artículo y luego crear un elemento de menú a partir del artículo. Para ello, primero necesitarías crear un nuevo menú y realizar algunos pasos adicionales durante la creación del artículo. Así que lo mejor es mantenerlo simple al principio y comenzar con tus nuevos artículos:

- Selecciona **Contenido** → **Artículos** → **+** desde el menú del Administrador. 
  O selecciona el botón `Nuevo` desde la lista de artículos.
- Completa el formulario como lo harías para cualquier artículo.
- Selecciona el botón `Guardar y Nuevo` en lugar de `Guardar y Cerrar` para pasar al siguiente nuevo artículo.

Los datos de ejemplo mostrados arriba requieren siete artículos.

## Crear un Nuevo Menú

Desde el menú de Administrador:

- Selecciona **Menús** → **Administrar**.
- En la página de lista de Menús, selecciona el botón `Nuevo` para crear un nuevo menú.
- En el formulario de Menús: Añadir, da al menú un título: Animales y un nombre único: animales.
- En algunos casos, es posible que necesites recordar para qué es este menú. Así que completa el campo de descripción.
- Guarda o Guarda y Cierra.

![submenús nuevo menú](../../../en/images/menus/submenus-new-menu.png)

## Crear Elementos de Menú

Hay siete elementos de menú para crear.

### Elemento de Menú de Animales

Los nuevos elementos de menú estarán ubicados en el menú de Animales.

- Selecciona **Menús** → **Animales** → **+** desde el menú del Administrador.
- Completa el formulario Menú: Editar Elemento.
  - Título: Animales
  - Tipo de Elemento de Menú: Artículo Único
  - Seleccionar Artículo: Animales - este es el artículo principal usado para
    introducir la serie sobre Animales
  - Menú: Animales
  - Padre: - Sin Padre - este es la raíz del menú
- Selecciona **Guardar y Nuevo** desde la lista desplegable `Guardar y Cerrar`.

### Elemento de Menú de Gatos

Esto es muy parecido al elemento de menú de Animales. Excepto:

- El título debe ser Gatos.
- El artículo seleccionado en el campo Seleccionar Artículo debe ser `Gatos`.
- El Elemento Padre debe establecerse en `Animales`.

### Elemento de Menú de Burmeses

Repetir nuevamente. Excepto:

- El título debe ser Burmeses.
- El artículo seleccionado en el campo Seleccionar Artículo debe ser `Burmeses`.
- El Elemento Padre debe establecerse en `Gatos`.

### Más Elementos de Menú

Continúa hasta que tengas siete elementos de menú, uno para cada artículo.  

## Lista de Elementos del Menú

Cuando hayas creado todos tus elementos de menú, verifica que tengan las relaciones correctas de padre-hijo y que estén en el orden correcto. Puedes ordenar en la columna de Orden (la segunda columna) y usar las asas de agarre (elipsis vertical) para arrastrar los elementos al orden correcto. Si algún elemento tiene un padre incorrecto, simplemente selecciona el título del elemento y cambia el padre en el formulario de Menús: Editar Elemento.

![lista de elementos del menú de submenús](../../../en/images/menus/submenus-menu-items-list.png)

## Módulos de Menú

En esta etapa tienes un menú, pero no tiene un módulo para ser asignado a una posición en la página. Podrías usar el menú completo como un menú estándar o un menú desplegable. Sin embargo, el objetivo de este tutorial es demostrar cómo crear submenús. Para eso necesitas tres módulos diferentes:

- Un módulo de Animales para un submenú con elementos de menú sobre Animales, Gatos y Perros.
- Un módulo de Gatos para un submenú con elementos de menú sobre razas de gatos.
- Un módulo de Perros para un submenú con elementos de menú sobre razas de perros.

## Módulo de Submenú de Animales

Desde el menú del Administrador:

- Selecciona **Contenido** → **Módulos del Sitio** → **+** o selecciona `Nuevo` desde la lista de Módulos (Sitio).
- Selecciona el módulo **Menú**.
- En el formulario de edición de Módulos: Menú, ingresa los siguientes datos:
  - Título: Animales
  - Seleccionar Menú: Animales
  - Elemento Base: Animales (este es el elemento de menú padre)
  - Nivel de Inicio: 1
  - Nivel Final: 2 (esto limita los elementos a los ítems del menú de Gatos y Perros)
  - Posición: barra lateral izquierda (o donde prefieras)

![módulo de submenús de animales](../../../en/images/menus/submenus-animals-module.png)

### Asignación de Menú de Animales

Los submenús generalmente se muestran solo en páginas donde son pertinentes, en este caso solo en tres páginas. Desde la pestaña de Asignación de Menú:

- Establece el campo de Asignación de Módulo en `Solo en las páginas seleccionadas`. Eso revela una lista jerárquica de todos los ítems en todos los menús.
- Marca las casillas contra Animales, Gatos y Perros.
- Marca las casillas contra las razas de gatos y perros. De lo contrario, el submenú de Animales desaparecerá en las páginas sobre razas.
- Asegúrate de que no estén marcadas otras casillas.
- Guardar y Cerrar

![asignación de menú del módulo de submenús de animales](../../../en/images/menus/submenus-animals-module-menu-assignment.png)

## Módulo de Submenú de Gatos

Esto es muy similar:

- Seleccione **Contenido** → **Módulos del Sitio** → **+** o seleccione `Nuevo` desde la lista de Módulos (Sitio).
- Seleccione el módulo **Menú**.
- En el formulario de edición de Módulos: Menú, ingrese los siguientes datos:
  - Título: Gatos
  - Seleccionar Menú: Animales
  - Elemento Base: Gatos (este es el elemento principal del menú)
  - Nivel de Inicio: 3
  - Nivel de Fin: Todo
  - Posición: sidebar-left (o donde mejor le convenga)

### Asignación de Menú de Gatos

Desde la Asignación de Menú:

- Establezca el campo de Asignación de Módulo en `Solo en las páginas seleccionadas`. Esto revela una lista jerárquica de todos los ítems en todos los menús.
- Marque las casillas junto a Gatos, Birmano y Azul Ruso. Asegúrese de que no haya otras casillas marcadas.
- Guardar y Cerrar

## Módulo de Submenú de Perros

Más de lo mismo ...

## Alias de Elemento del Menú

¡Hasta aquí todo bien! Pero no hay un enlace a la página de Animales desde el Menú Principal, ni en ningún otro de los menús del sitio. La manera fácil de solucionar esto es con un Alias de Elemento del Menú. Para este ejemplo, se hace una entrada en el menú en la parte superior de la página, titulado Blog del Menú Principal. Desde el menú del Administrador:

- Seleccione **Menús** → **Blog del Menú Principal** (o el menú del sitio de su preferencia).
- Seleccione el botón `Nuevo` de la Barra de herramientas.
- Complete el formulario de Menús: Editar Elemento
  - Título: Animales
  - Alias: criaturas - ya hay un elemento de menú llamado Animales, por lo que debe usar un alias diferente.
  - Tipo de Elemento de Menú: Alias de Elemento del Menú
  - Elemento de Menú: Animales - seleccionado de la lista de elementos de menú existentes.

![submenús alias de animales](../../../en/images/menus/submenus-animals-alias.png)

- Guardar
- Orden - después de guardar, el orden se puede cambiar. En este ejemplo se coloca primero.

## Verificar el Resultado

Visualiza las páginas en tu sitio. En este ejemplo, la mayoría de las páginas no mostrarán los submenús en la posición del lado izquierdo. El enlace Animales en el menú superior abrirá la página de animales desde la cual es posible navegar a las páginas de Gatos o Perros:

![objetivos de submenús animales perros](../../../en/images/menus/submenus-objectives-animals-dogs.png)

