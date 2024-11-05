<!-- Filename: Keyboard_Shortcuts / Display title: Atajos de Teclado  -->

## Introducción

El teclado se puede utilizar en la interfaz de Administrador para invocar algunas de las acciones que generalmente se realizan con un ratón o un pad. Por ejemplo, hay atajos de teclado para guardar la página actual, ir al *Tablero Principal* o abrir un formulario de *Opciones*.

Hay un resumen de todos los atajos, que se abre presionando secuencialmente **J** y **X** en el teclado (no al mismo tiempo y no utilice la tecla Shift que normalmente se usa para las mayúsculas). A menos que cambie la configuración del plugin, debe presionar las teclas dentro de 2 segundos.

La función está habilitada por defecto. Se puede deshabilitar o configurar en **Administrador → Sistema → Plugins → Sistema - Atajos de Teclado**. Actualmente, la única configuración es el tiempo de espera: cuánto tiempo esperará el sistema para su próxima entrada de tecla. Por defecto, espera 2000 milisegundos (2 segundos).

## Atajos predeterminados en Joomla

- J + A - Guarda el contenido actual
- J + S - Para Guardar y Cerrar
- J + Q - Cancela la página actual
- J + N - Presiona el botón *Nuevo*
- J + F - Establece el enfoque en el campo de Búsqueda
- J + O - Va a Opciones
- J + H - Se abre la ventana de Ayuda (podría activar una advertencia de ventana emergente del navegador)
- J + M - Alterna la barra de menú
- J + X - Muestra una lista de Atajos disponibles
- J + D - Va directamente al Tablero de Inicio

## Atajos de Terceros - Información para Desarrolladores

Otros desarrolladores también pueden agregar sus atajos. El plugin de Joomla llama al Evento *onLoadShortcuts*, que puede ser utilizado por otros plugins también. El evento necesita ser agregado a la lista de *getSubscribedEvents* dentro del plugin. La función asignada podría verse así:

```php
    public function onLoadShortcuts(EventInterface $event): void {
       $shortcuts = $event->getArgument('shortcuts');
       $exampleShortcuts = array('example' => (object)['shortcut' => 'E', 'title' => 'Gran Ejemplo', 'selector' => '#menu-collapse']);
       $event->setArgument('shortcuts', array_merge($shortcuts, $exampleShortcuts));
    }
```
Presta mucha atención a la parte de array_merge: Cuando los atajos ya existentes no se combinan con los nuevos, los antiguos son sobrescritos.

Los desarrolladores pueden proporcionar un array con objetos de atajos:

    { shortcut: string, selector: string, title: string }

- El *Atajo* necesita ser una entrada de teclado, separada por un signo más, por ejemplo, `Y` o `ALT + Z + 7` (actualmente no hay realmente ningún filtro). Ten en cuenta que cada secuencia de atajo comenzará con **J**.
- Los *Selectores* son selectores CSS o URLs para especificar el objetivo. Cuando es un elemento de entrada, el atajo da foco, como es el caso del campo de búsqueda. De lo contrario, se hará clic en el elemento o se llamará a la URL.
- El *Título* se mostrará en la vista general. Podría ser el nombre del objetivo, por ejemplo.

## Razones para usar J + X

Algunos pueden preguntarse por la decisión de usar atajos secuenciales o la **J** como inicio en lugar de Ctrl u otra cosa. Las principales razones son la accesibilidad y la evitación de interrupciones por parte de otros programas. Por ejemplo, *Ctrl + S* sería conveniente para guardar un artículo, pero ya está siendo utilizado por los navegadores. Lo mismo puede suceder con lectores de pantalla o gestores de contraseñas. Así que la opción más segura fue usar algo específico de Joomla, como la **J** al principio.

Ahora, el otro problema es que no siempre es posible presionar más de una tecla a la vez. Windows tiene el modo de teclas adhesivas para esto, pero solo funciona para teclas modificadoras como Shift, Ctrl y Alt. Así que el plugin utiliza input secuencial desde el inicio, lo cual lo hace usable por más personas incluso sin la ayuda de los modos del sistema operativo.

*Traducido por openai.com*

