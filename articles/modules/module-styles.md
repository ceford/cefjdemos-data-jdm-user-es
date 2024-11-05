<!-- Filename: jdocmanual?manual=user&heading=modules&filename=module-styles.md / Display title: Estilos de Módulo  -->

## Conceptos de Estilo

Un formulario de entrada de datos del módulo tiene una pestaña **Avanzado**. Sus campos varían según el tipo de módulo y puedes verlo tú mismo seleccionando un módulo de Menú y comparándolo con un módulo de Inicio Sesión o un módulo de Migas de Pan. Verás los siguientes tres campos de formulario relacionados con el estilo:

* **Clase del Módulo** es un campo de texto que te permite añadir tu propia clase CSS a la etiqueta del contenedor del módulo, generalmente un `<div>`.
* **Clase del Encabezado** es un campo de texto que te permite añadir tu propia clase CSS a la etiqueta del Encabezado, por defecto una etiqueta `<h3>`.
* **Estilo del Módulo** es una lista que te permite seleccionar uno de varios estilos estándar. La lista contiene ninguno, html5, contorno, tabla, tarjeta y sinTarjeta. El predeterminado es tarjeta de los estilos de la plantilla Cassiopeia.

Puedes probar las opciones de *Estilo del Módulo* editando un módulo y cambiando el valor para ver qué efecto tiene en la visualización del sitio.

* **html5** da `<div class="moduletable ">`
* **ninguno** elimina completamente el `<div>` externo y también la etiqueta `<h3>` del módulo.
* **contorno** da `<div class="mod_preview_info">`, con información de posición y estilo reemplazando la etiqueta `<h3>` del módulo.
* **tabla** da un diseño de tabla comenzando con `<table class="moduletable ">` y la etiqueta h3 anterior se convierte en `<th>`.
* **tarjeta** da `<div class="sidebar-right card ">`, el predeterminado.
* **sinTarjeta** da `<div class="sidebar-right no-card ">`

## La Clase de Módulo

En esta etapa, necesitas saber un poco sobre Hojas de Estilo en Cascada o CSS.  
Si ingresas una sola palabra en el campo de Clase de Módulo, por ejemplo, **green** (ya que las clases en CSS por convención están en minúsculas), y con el Estilo del Módulo configurado en **heredado**, la salida contiene `<div class="sidebar-right card green">`.

No hay un cambio visible en la apariencia del sitio porque la clase green no está definida. Para definirla, realiza una entrada en el archivo user.css de la plantilla.

Desde el menú de Administrador:
* Selecciona **Sistema / Plantillas del Sitio / Plantillas y Archivos de Cassiopeia**.
* Selecciona **Nuevo Archivo** desde la *Barra de Herramientas*.
* Selecciona **css** en la columna de la izquierda, el destino para el nuevo archivo.
* Escribe **user** en el campo de Nombre de Archivo.
* Selecciona **css** de la lista de Tipo de Archivo.
* Selecciona el botón **Crear**.

Ahora puedes abrir la carpeta css para encontrar y abrir el archivo user.css para editarlo.  
Ingresa estas declaraciones de estilo y nota la ortografía estadounidense de *color*:
```
.sidebar-right.card.green {
    background-color: #ddffdd;
}
.sidebar-right.card.green .card-body {
    background-color: #eeffee;
}
```
El estilo podría haber usado solo `.green`, pero eso podría haber afectado a otras etiquetas con ese estilo en otras páginas.

## La Clase de Encabezado

Vuelve al formulario de edición del módulo y agrega **azul** en el campo Clase de Encabezado. El módulo no tiene cambios visibles en el sitio, pero el encabezado ahora se muestra como `<h3 class="card-header azul">`. Regresa a editar el archivo user.css para añadir una entrada para el estilo del encabezado:
```
.card-header.azul {
    color: navy;
}
```
El encabezado del módulo ahora está en azul oscuro. Hay varias maneras de especificar colores en CSS. Las más comunes son hexadecimal y nombres de colores estándar. ¡Lee todo sobre eso en otro lugar!

## Desafío de CSS

* ¡Cambia el color del borde del módulo a azul marino!
* Cambia también el borde inferior del encabezado.
* Aplica este estilo a varios módulos en lugar de uno a la vez

![Ejemplo de Módulo de Artículos Archivados](../../../en/images/modules/modules-archived-articles.png)

*Traducido por openai.com*

