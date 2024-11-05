<!-- Filename: J4.x:Child_Templates / Display title: Plantillas para Niños  -->

## Introducción

Las plantillas hijas utilizan todos los archivos de sus plantillas parentales, excepto aquellos archivos con el mismo nombre que coloques en la plantilla hija. Los archivos de la plantilla hija no se ven afectados por las actualizaciones de Joomla. Por lo tanto, podrías colocar tu propio archivo index.php en una plantilla hija y hacer que entregue algo bastante diferente de la plantilla predeterminada, como posiciones de módulo adicionales o sobreescrituras alternativas de extensiones.

Un ejemplo de escenario: supongamos que deseas que algunas de tus páginas aparezcan con un tema azul, los colores predeterminados de Cassiopeia, y otras páginas aparezcan con un tema verde. Una forma sencilla de hacerlo es con una plantilla hija que use su propia hoja de estilo user.css.

## Ejemplo trabajado

Comenzando desde **Sistema → Panel de plantillas → Plantillas del sitio**

- Seleccione *Detalles y archivos de Cassiopeia*.
- Seleccione el botón *Crear plantilla secundaria*.
- Rellene el cuadro de diálogo emergente de Plantilla secundaria y seleccione el botón Crear plantilla secundaria:

![formulario de creación de plantilla secundaria modal](../../../en/images/templates/child-templates-create-green.png)

La selección de Cassiopeia - Predeterminado en el campo de Estilos de plantillas adicionales parece innecesaria (¿es eso un error?).

- Seleccione *Cerrar* de la barra de herramientas para cerrar el formulario de la plantilla principal.
- Seleccione la nueva plantilla, *Detalles y archivos de Cassiopeia_green*, de la lista de Plantillas.

En esta etapa hay una estructura de carpetas pero solo un archivo: templateDetails.xml. Ese archivo se puede cambiar si desea modificar aspectos de la configuración de la plantilla, por ejemplo, para agregar o eliminar posiciones de plantilla.

### Crear un archivo user.css

- Seleccione el botón *Nuevo archivo* en la barra de herramientas.
- En el formulario *Crear o subir un nuevo archivo* asegúrese de seleccionar la carpeta `css`
- Complete el nombre del archivo con `user`. ¡NO agregue un sufijo!
- Seleccione el tipo de archivo `.css`.
- Seleccione el botón *Crear*.

![formulario de creación de usuario css de plantilla secundaria](../../../en/images/templates/child-templates-create-green-user-css.png)

El archivo user.css está vacío, listo para que ingrese algunos estilos personalizados. Ingrese lo siguiente para comenzar el tema verde:
```css
    .container-header {
      background-color: darkgreen;
      background-image: none;
    }
    h1, h2, h3, h4, h5, h6 {
      color: darkgreen;
    }
    .h1, .h2, .h3, .h4, .h5, .h6 {
      color: darkgreen;
    }
    a, a:hover, a:focus {
      color: darkgreen;
    }
    .btn-info {
        background-color: darkgreen;
        border-color: #30638d;
        color: #fff;
    }
    .btn-primary, .btn-primary:focus, .btn-primary:hover {
        background-color: darkgreen;
        border-color: var(--cassiopeia-color-hover);
    }

    .btn-check:focus + .btn-info, .btn-info:focus, .btn-info:hover {
        background-color: darkgreen;
        border-color: #264f71;
        color: #fff;
    }
```
Es posible que necesite volver a este archivo user.css para agregar más estilos más adelante.

- Seleccione *Guardar y cerrar* o por separado, *Guardar* y luego *Cerrar archivo*.
- Seleccione *Cerrar* para cerrar el formulario de personalización.

### Elemento de Menú

En esta etapa se necesita un elemento de menú para hacer uso de la plantilla secundaria. Una nueva instalación de Joomla 4 tiene el Menú Principal en la posición de la barra lateral derecha con un elemento en él. Parece un buen lugar para un nuevo elemento de menú.

- Seleccione **Menús → Menú principal** desde el menú del administrador.
- Seleccione el botón *Nuevo* de la barra de herramientas.
- Ingrese un título adecuado, *Artículos destacados en verde* parece apropiado en este caso.
- Seleccione el botón **Tipo de elemento de menú → Seleccionar**.
- Seleccione un tipo de elemento de menú desde el cuadro de diálogo emergente de Tipo de elemento de menú - Artículos destacados en este ejemplo.
- Seleccione *cassiopeia_manual - Predeterminado* desde el campo de formulario de *Estilo de plantilla*.

![formulario de edición de elemento de menú de plantilla secundaria](../../../en/images/templates/child-templates-create-green-menu-item.png)

- Para los propósitos de la siguiente captura de pantalla, el Layout del Blog se ha configurado en Artículos líderes: 0, Artículos introductorios: 3 y Dirección de múltiples columnas: A lo ancho.

### Vista del Sitio

- En la página de inicio de su sitio, seleccione el elemento de menú recién creado.

![sitio mostrando plantilla de tema verde personalizada](../../../en/images/templates/child-templates-green-site-result.png)

### Editar el Estilo

- Seleccione **Sistema → Panel de plantillas → Estilos de plantillas del sitio** desde el menú del administrador.
- Seleccione *Cassiopeia_green - Predeterminado* de la lista de estilos.
- Cambie el nombre del estilo a *Cassiopeia Verde*. Eso solo ordena el nombre como aparece en las listas.
- Seleccione *Guardar y cerrar*.

