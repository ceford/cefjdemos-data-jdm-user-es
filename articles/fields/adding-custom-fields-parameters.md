<!-- Filename: J3.x:Adding_custom_fields/Parameters_for_all_Custom_Fields / Display title: Parámetros de Campo -->

## Formulario de Entrada de Datos de Campo

Hay 16 o más tipos de campo disponibles en la lista de selección Tipo en el formulario de entrada de datos de campo. La mayoría de los campos del formulario son iguales para todos los tipos de campo, pero otros cambian según el tipo seleccionado. Este artículo describe los parámetros comunes para todos los campos. El formulario de entrada de datos también es el mismo para los campos de **Artículo**, **Contacto** y **Usuario**, así como para sus campos de Categoría.

Una lista de Campos estará vacía inicialmente. Para comenzar, por ejemplo, con los campos de Artículo:
* Selecciona **Nuevo** desde la barra de herramientas en la lista de Campos: Artículos.

El formulario consta de un campo de Título y cuatro pestañas.

![Parámetros de campo pestaña general](../../../en/images/fields/fields-parameters-general-tab.png)

## Título

El título se muestra en la página de lista *Artículos: Campos* donde se puede
seleccionar para abrir el campo para edición. El título no se muestra cuando
creas un artículo o en la interfaz frontend. Sin embargo, la Etiqueta puede crearse desde
el Título y se muestra en el formulario de entrada de datos del artículo y puede
mostrarse en la exhibición del artículo.

### Pestaña General

#### En el panel izquierdo:

- **Tipo** Selecciona uno de los 16 tipos de campo del menú desplegable. Cuando
guardas el campo, este tipo es permanente. No se puede cambiar más tarde.
- **Nombre** El nombre se usará para identificar el campo. Déjalo en blanco y
Joomla completará un valor predeterminado desde el título.
- **Etiqueta** Usa una etiqueta descriptiva para el campo. Este texto no es
traducible. Si no introduces texto para una etiqueta, se usará el texto del título
como texto de etiqueta.
- **Descripción** Texto que se mostrará como una herramienta de descripción para definir el
propósito del campo durante la entrada de datos. Este texto no es traducible y
no se mostrará en el frontend.
- **Requerido** Establece en *Sí* si este es un campo obligatorio que debe
completarse antes de enviar un artículo.
- **Usar Solo en Subformulario** Se requiere una explicación [Por Hacer]
- **Valor Predeterminado** Establece un valor predeterminado si es adecuado. Este texto no es
traducible.
- **Filtro** Elige una de las opciones disponibles del menú desplegable. El
campo se validará para conformidad con el tipo de datos seleccionado.
- **Longitud Máxima** Configura esto para limitar la longitud del texto que se puede
introducir.

### En el panel derecho:

- **Estado** Establece un estado de publicación seleccionado de *Publicado*, *No publicado*,
*Archivado* o *En la papelera*.
  - Publicado: El campo es visible mientras se edita un artículo o un
    contacto. Y es visible en la Interfaz.
  - No publicado: El campo no será visible para los usuarios mientras editan
    un artículo o un contacto.
  - Archivado: El campo ya no se mostrará al editar un artículo o un
    contacto. Puedes abrirlo en el gestor de campos cuando configures el
    filtro en archivado.
  - En la Papelera: El campo está eliminado pero aún en la base de datos. Puede
    eliminarse permanentemente de la base de datos con la función Vaciar Papelera en
    el Gestor de Campos.
- **Grupo de Campos** Selecciona Ninguno o un Grupo elegido de una lista predefinida. Los grupos
aparecen como pestañas separadas en el formulario de entrada de datos del artículo.
- **Categoría** Puedes asignar un campo a una o más categorías de campo. Nota
  que el por defecto *Todo* no incluye artículos *sin categorizar*.
- **Acceso** El nivel de acceso de visualización para este campo.
- **Idioma** Selecciona el idioma para este campo personalizado. Si no estás usando la
  función multilingüe de Joomla, mantén el predeterminado de *Todo*.
- **Nota** Un campo opcional para hacer tus notas personales para el campo.

### Pestaña Opciones

![Parámetros de campo pestaña opciones generales](../../../en/images/fields/fields-parameters-options-tab.png)

#### Opciones del Formulario

- **Placeholder** Un texto de marcador de posición que aparecerá dentro del campo personalizado
como una sugerencia para la entrada. El marcador de posición está activo en la Interfaz de Administración mientras
se crea un artículo. No lo ves en la Interfaz de Usuario.
- **Clase del Campo** Los atributos de clase del campo cuando el campo se representa.
Si se necesitan clases diferentes, enuméralas con espacios.
- **Clase de Etiqueta (Formulario)** Los atributos de clase de la etiqueta en el formulario de edición. Si
se necesitan clases diferentes, enuméralas con espacios.
- **Editable En** En qué parte del sitio debe mostrarse el campo: Sitio,
Administrador o Ambos.
- **Atributo Showon** Mostrar u ocultar condicionalmente el campo dependiendo del
valor de otros campos. La sintaxis para usar aquí, por ejemplo:
  - `lista-de-elementos:valor1[O]lista-de-elementos:valor2` donde
  - lista-de-elementos: El nombre de un campo ya creado en el que este campo
depende.
  - valor1: El valor necesario en el campo de lista de elementos para que este campo se muestre.
  - [O] Para crear una elección entre múltiples campos. En el ejemplo, este campo se
mostrará cuando el campo lista-de-elementos tenga un valor de valor1 O valor2.
  - [Y] Para combinar múltiples campos. Este campo se mostrará solo cuando los
campos lista-de-elementos tengan el valor valor1 Y valor2.
  - También puedes usar el valor 'no es igual' como en lista-de-elementos!:valor1. La
sintaxis mostrará este campo solo cuando lista-de-elementos no sea igual a valor1.
  - Para mostrar este campo cuando el campo lista-de-elementos ha sido seleccionado y no
tiene un valor vacío, utiliza la sintaxis lista-de-elementos!: (sin especificar un valor).
  - Nota: Los campos de subformulario manejan el nombre de lista-de-elementos de manera diferente.
Si creas un campo de Subformulario y añades este campo condicional para un campo
que estás creando allí, necesitas usar campo[ID] en lugar de lista-de-elementos,
donde ID es el id del campo lista-de-elementos. Por lo tanto, el atributo showon
para este campo condicional que estás creando necesita ser:
campo36:valor1[O]campo36:valor2 donde 36 es el ID del campo 'Lista de elementos'.
¡Esto necesita aclaración!

#### Opciones de Visualización

- **Clase de Visualización**  La clase del contenedor del campo en la salida.
- **Clase del Valor**  La clase del valor del campo en la salida.
- **Etiqueta** Mostrar u Ocultar la etiqueta.
- **Clase de Etiqueta (Salida)** La clase de salida de la etiqueta si la etiqueta se muestra.
- **Visualización Automática** Joomla ofrece algunos eventos de contenido que se activan
durante el proceso de creación de contenido. Este es el lugar para definir cómo los campos personalizados
deberían integrarse en el contenido. Puedes elegir *Después del Título*,
*Antes de Mostrar el Contenido*, *Después de Mostrar el Contenido* o *No mostrar automáticamente*.
- **Prefijo** Texto fijo que se mostrará antes de un campo, por ejemplo £.
- **Sufijo** Texto fijo que se mostrará después de un campo, por ejemplo EUR.
- **Diseño** Selecciona un diseño de las plantillas y anulaciones disponibles.
- **Mostrar Cuando es de Solo Lectura** Selecciona entre *Heredar*, *Sí* o *No*. Si el campo es
de solo lectura (quizás el usuario no tiene el nivel de acceso) ¿debería mostrarse o ocultarse?

#### Búsqueda Inteligente

- **Índice de Búsqueda** Selecciona de la lista de opciones. Advertencia: Cuando *Hacer buscable*
está seleccionado, el contenido del campo se indexa con los permisos de visualización del
elemento de contenido. Esto podría provocar una divulgación de información inesperada.

### Pestaña de Publicación

![Parámetros de campo pestaña general](../../../en/images/fields/fields-parameters-publishing-tab.png)

### Pestaña de Permisos

![Parámetros de campo pestaña general](../../../en/images/fields/fields-parameters-permissions-tab.png)

*Traducido por openai.com*

