<!-- Filename: J3.x:Adding_custom_fields/Parameters_for_all_Custom_Fields / Display title: Agregar campos personalizados/parámetros para todos los Campos Personalizados -->

<span id="section-portal-heading"></span>

## Parámetros para todos los Campos Personalizados

**Artículos en esta serie**

1.  Introducción
2.   Parámetros para todos los campos
    personalizados
3.   Campo de
    calendario
4.   Campo de chequeo
    (checkbox)
5.   Campo de
    color
6.   Campo
    editor
7.   Campo de
    galería
8.   Campo de lista de
    imágenes
9.   Campo de
    media
10.  Campo
    radio
11.  Campo
    Sql
12.  Campo
    repetible
13.  Campo de
    texto
14.  Campo de área de texto
    (textarea)
15.  Campo de
    url
16.  Campo de
    usuario
17.  Campo de grupo de
    usuario
18.  ¿Cómo puedo agrupar campos
    personalizados?
19.  ¿Qué componentes soportan campos
    personalizados?
20. Ejemplo
21.  Implementación en tu
    componente
22.  Utilizar campos personalizados en tus
    sustituciones

## Parámetros para todos los Campos Personalizados

La lista de Campos Personalizados estará vacía inicialmente. Haga clic
en '*Nuevo* para agregar un campo.
En la pestaña **General** rellene los datos obligatorios:

- Título
  El título del campo. El título se mostrará en la página de
  administración del campo donde puede abrir el campo para editar
  haciendo clic en el título. El título no se muestra cuando se crea un
  artículo o un contacto ni en el frontend.
- Nombre
  El nombre se utilizará para identificar el campo. Deje esto en blanco
  y Joomla completará el valor predeterminado con el título.
- Tipo
  Si crea un campo, puede elegir uno de los 16 tipos de campos. Al
  guardar el campo, el tipo es permanente. No se puede cambiar más
  adelante.

Para cada campo, puede usar estos parámetros:

- Etiqueta
  Utilice un texto descriptivo para la etiqueta del campo. Este texto no
  es traducible. Si no introduce ningún texto para una etiqueta, el
  texto del título también se usará como texto de la etiqueta.
- Descripción
  La descripción del campo. Un texto que se mostrará cuando el usuario
  mueve el mouse sobre el cuadro de texto mientras lo usa en el backend
  creando un artículo, un contacto o un componente de terceros que
  admite campos personalizados. Este texto no es traducible. No verá
  esta descripción en el frontend.
- Obligatorio
  ¿Es éste un campo personalizado obligatorio? En este caso, el campo
  debe rellenarse antes de enviar un artículo, un contacto o un
  componente de terceros que admita campos personalizados. Puede elegir
  las opciones *Sí* o *No*.
- Predeterminado
  Aquí puede establecer un valor predeterminado para el campo
  personalizado. Este texto no es traducible. Tenga en cuenta que en
  algunos campos de lista debe ingresar el valor como predeterminado y
  en otros el índice.
- Estado
  Puede establecer un estado de publicación. ¿El campo será "Publicado",
  "Despublicado", "Archivado" o en "Papelera"?
  - Publicado: El campo es visible al editar un artículo o un contacto.
    Y es visible en el Frontend.
  - Despublicado: El campo no será visible para los usuarios mientras
    editan un artículo o un contacto.
  - Archivado: El campo ya no mostrará en la edición un artículo o un
    contacto. Puede abrirlo en el administrador de campos cuando
    establezca el filtro en archivado.
  - Papelera: El campo se elimina pero aún está en la base de datos. Se
    puede eliminar permanentemente de la base de datos con la función
    Vaciar Papelera en el Administrador de Campos.
- Grupo de campos
  Puede asignar un campo personalizado a uno o más grupos de campos.
- Categoría
  Puede asignar un campo personalizado a una o más categorías de campos.
  Tenga en cuenta que el valor predeterminado 'Todos' no incluye
  artículos 'Sin Categoría'.
- Acceso
  Vea  Niveles de
  Acceso
  para este elemento.
- Idioma
  Seleccione el idioma para este campo personalizado. Si no está
  utilizando la  configuración de sitio
  multiidioma
  de Joomla, mantenga el valor predeterminado de *Todos*.
- Nota
  Un campo opcional para hacer sus notas personales para el campo.

En el registro **Opciones** puede usar las opciones:

- Marcador de posición
  Un texto que aparecerá dentro del campo personalizado como una
  sugerencia para la entrada. El marcador de posición está activo en el
  Backend al crear un artículo, un contacto o un componente de terceros
  que admite campos personalizados. Usted no lo verá en el Frontend.
- Clase del campo
  La clase del campo cuando el campo es renderizado. Si se necesitan
  diferentes clases, sepárelas con espacios.
- Editar Clase
  Los atributos de clase del campo en el formulario de edición. Si se
  necesitan diferentes clases, sepárelas con espacios.
- Editable en
  En qué parte del sitio debe mostrarse el campo. En el Backend, en el
  Frontend o ambos.
- Etiqueta
  Mostrar u ocultar la etiqueta cuando el campo se renderiza.
- Visualización automática
  Joomlaǃ ofrece algunos eventos de contenido que se activan durante el
  proceso de creación de contenido. Este es el lugar para definir cómo
  los campos personalizados deben integrarse en el contenido. Puede
  elegir 'Después del título', 'Antes de mostrar contenido', 'Después de
  mostrar contenido' o 'No mostrar automáticamente'.
- Deshabilitado
  En caso de que el campo esté deshabilitado en el formulario de
  edición.
- Sólo lectura
  En caso de que el campo sea de sólo lectura en el formulario de
  edición.

<a href="https://docs.joomla.org/J3.x:Adding_custom_fields"
id="content-button" class="button expand success">Anterior:
Introducción</a> <a
href="https://docs.joomla.org/J3.x:Adding_custom_fields/Calendar_Field"
id="content-button" class="button expand">Siguiente: Campo de
Calendario</a>
