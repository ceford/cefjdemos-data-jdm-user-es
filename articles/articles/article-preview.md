<!-- Filename: J4.x:Article_Preview / Display title: Artículo: Vista previa  -->

## Introducción

Puede ser útil previsualizar un artículo antes de publicarlo. Hay un botón de *Previsualización* en la barra de herramientas del formulario de *Artículo: Editar* en el backend para este propósito. Sin embargo, esta función utiliza el artículo guardado y no el contenido del formulario del editor. La función de Previsualización no está disponible en el formulario de edición de artículos en el frontend.

Es posible que desee que un artículo no sea visible hasta que esté terminado. Para este propósito, se necesitan diferentes estrategias para los editores del frontend y del backend.

## Vista previa del Frontend

La única manera de mantener un artículo semi-privado desde el frontend es establecer su acceso como *Registrado* para que solo los usuarios conectados puedan verlo.

- Inicia sesión en el frontend del sitio web.
- Selecciona el enlace *Editar* para un artículo que se va a actualizar. O...
- Selecciona el botón *Nuevo Artículo* debajo de los diseños del blog.
  - Configura el nivel de acceso del artículo a *Registrado* hasta que esté listo para su publicación.
  - Podrías agregar un aviso de *Alerta* indicando que el artículo está en construcción: `<div class="alert alert-warning">En Construcción</div>`.
- *Guardar & Cerrar* para ver el artículo.

## Vista Previa del Backend

Después de iniciar sesión en la interfaz de Administrador:

- Seleccione un artículo para editar o cree y guarde uno nuevo.
- Para mantener un artículo nuevo privado por ahora, configure el Estado como *Sin publicar* o déjelo como *Publicado* y ajuste la fecha de *Inicio de publicación*.
- Realice cambios y *Guarde* el artículo.
- Seleccione el botón de *Vista previa* en la barra de herramientas. Debería aparecer una ventana emergente de Vista Previa.
- Si recibe un mensaje de *La página solicitada no se puede encontrar*, inicie sesión en el Frontend y vuelva a intentarlo.
- Para cerrar la ventana de Vista Previa seleccione el botón *X* en la esquina superior derecha.

![La ventana de vista previa](../../../en/images/getting-started/article-edit-preview.png)

*Traducido por openai.com*

