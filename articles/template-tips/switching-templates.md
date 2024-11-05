<!-- Filename: J4.x:Switching_Templates / Display title: Cambiando Plantillas  -->

## Plantillas de Sitio y Administrador

Joomla 4 viene con una única plantilla para el Sitio, Cassiopeia, y una única plantilla para el Administrador, Atum. Puedes obtener plantillas adicionales de proveedores externos de plantillas, tanto gratuitas como de pago, y puedes crear tus propias plantillas, más fácilmente como plantillas hijas.

Es poco probable que desees utilizar una plantilla de Administrador alternativa, así que este artículo solo cubre las plantillas de Sitio alternativas. A modo de ilustración, se ha creado una plantilla hija con un tema verde como se describe en el artículo sobre Plantillas Hijas. Además, el sitio utilizado para la ilustración tiene instalados los Datos de Muestra de Prueba.

## Estilo de Plantilla Predeterminada

Uno de tus plantillas debe estar marcada como la predeterminada. Se utiliza para todas las páginas, excepto cualquier página individual que especifique una plantilla alternativa. Para establecer la plantilla predeterminada:

- Selecciona **Sistema → Panel de Plantillas → Estilos de Plantilla del Sitio**
  desde el menú de Administrador.
- Selecciona uno de los botones en la columna Predeterminada.

![página de lista de estilos de plantillas del sitio](../../../en/images/templates/switch-templates-styles-list.png)

Echa un vistazo a tu sitio para ver que todas las páginas están utilizando la plantilla predeterminada.

## Usar un Estilo Alternativo

Joomla permite seleccionar un estilo para una página específica desde su asignación de menú. La selección se puede realizar desde el formulario de Estilo de Plantilla o el formulario de Edición de Menú. Los métodos producen el mismo resultado. El primer método es más conveniente para la selección de un grupo de elementos de menú que pertenecen al mismo menú.

### Método de Asignación de Menú de Plantilla

Desde la lista de Estilos de Plantillas:

- Seleccione un estilo que **no** esté configurado como el predeterminado. La estrella amarilla indica el estilo predeterminado.
- Seleccione la pestaña de Asignación de Menú.
- Seleccione elementos de menú individuales o active/desactive todos los elementos en un menú.
- Guardar

![pestaña de asignación de menú de la página de edición de estilo de plantillas](../../../en/images/templates/switch-templates-styles-edit-style-menu-assignment.png)

En este ejemplo, se han seleccionado todos los elementos del menú en el menú `Main Menu Testing`. Regrese a su sitio y seleccione cualquiera de los elementos de menú que deberían usar la plantilla seleccionada.

### Método de Detalles del Menú

Este método se utiliza para establecer la plantilla para elementos de menú individuales.

- Seleccione **Menús → \[Nombre del Menú\]** desde el menú del Administrador.
- Seleccione un enlace de elemento de menú desde la columna de Título para abrir el formulario de edición.
- En el campo **Estilo de Plantilla**, seleccione el estilo de plantilla deseado.
- Guardar

![formulario de edición de elementos de menú de plantillas mostrando la selección de estilo](../../../en/images/templates/switch-templates-styles-edit-menu-style.png)

Regrese a su sitio y seleccione el elemento de menú cambiado para verificar que se muestra con el estilo de plantilla seleccionado.

