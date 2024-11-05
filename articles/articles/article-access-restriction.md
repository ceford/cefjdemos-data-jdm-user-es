<!-- Filename: J6.x:Article_Access_Restriction / Display title: Artículo: Restricción de Acceso  -->

## Introducción

Hay varias razones para restringir el acceso a los artículos en un sitio web. Algunos contenidos pueden ser privados para usuarios específicos, como miembros de un comité. O el sitio puede contener contenido comercial de pago por ver. Joomla ofrece un potente sistema de Lista de Control de Acceso (ACL) para restringir el acceso. Se describe en un artículo separado sobre [Control de Acceso](jdocmanual?article=user/users/access-control) en la sección de Usuario de este manual.

Este artículo describe la implementación de la restricción de acceso en el formulario *Artículo: Editar*.  

## Restricción por Nivel de Acceso

Joomla proporciona los Niveles de Acceso que se ven en la siguiente captura de pantalla:

![Niveles de acceso de usuario](../../../en/images/articles/article-access-user-groups.png)

Los niveles de acceso aparecen en la pestaña *Contenido* del formulario *Artículo: Editar*.

- **Público** Puede ser visto por todos: tanto usuarios que han iniciado sesión como usuarios que no lo han hecho.
- **Invitado** Este nivel de acceso restringe el acceso a usuarios que **NO** han iniciado sesión.
- **Registrado** Este nivel restringe el acceso a usuarios que han iniciado sesión. Un artículo con *Acceso* configurado como *Registrado* requerirá un inicio de sesión en el front-end antes de que se pueda ver el artículo.
- **Especial** Este nivel restringe el acceso a usuarios que han iniciado sesión y están en un grupo de usuarios específico diferente al de Registrado. Además, es posible diferenciar contenido al que algunos usuarios conectados pueden acceder pero otros no. Típicamente, esto podría ser un sitio web donde se requieran suscripciones para acceder a contenido adicional.
- **Super Usuarios** Configurar este nivel significa que solo un Super Usuario puede acceder al artículo. Esto podría utilizarse para artículos sobre la gestión del sitio.

Tenga en cuenta que esta lista se refiere a **Ver** o tener permiso para ver contenido. Puede crear niveles de acceso y grupos de usuarios adicionales para personalizar quién puede ver qué.

## Restricción Parcial para Leer Más

A veces desearás restringir el acceso a un artículo pero permitir el acceso sin restricciones a una muestra del artículo. Esta es una forma común de implementar el acceso de pago a contenido comercial. Procedimiento:

- Busca el artículo que se va a restringir parcialmente en la lista de *Artículos* y ábrelo para editar.
- Inserta un *Salto de Página* después del primer párrafo. La herramienta de Salto de Página está cerca de la parte inferior de la lista *Contenido CMS* en el formulario de edición de artículos de TinyMCE.
- Establece el nivel de *Acceso* del artículo en *Registrado*.
- Selecciona **Guardar y Cerrar** en la Barra de Herramientas.

### Restringir accesos a Artículos individualmente

Abre el elemento del menú *Blog de Categoría* o *Artículos Destacados* donde aparecerá el artículo.

- En la pestaña **Opciones**, establece **Enlaces No Autorizados** en **Sí**. Se encuentra al final de la lista de Opciones.
- Selecciona **Guardar y Cerrar** en la Barra de Herramientas.

### Restringir acceso a Artículos Globalmente

* Establece las Categorías relevantes al nivel de visualización *Público*, de lo contrario, los elementos del menú no serán visibles para los usuarios que no hayan iniciado sesión.
* Establece los artículos en las Categorías relevantes al nivel de visualización Registrado. Esto se puede hacer seleccionando los artículos y usando el botón *Lote*.
* Ve a **Contenido → Artículos → Opciones**
* Establece **Enlaces No Autorizados** en **Sí** en la pestaña de Artículos. Si se establece en Sí, los enlaces a contenido registrado se mostrarán incluso si no has iniciado sesión. Necesitarás iniciar sesión para acceder al contenido completo.

**Nota:** El texto de un Artículo sin un salto *Leer Más* se trata como todo texto de Introducción. Si tienes un Artículo que se supone que está restringido solo para usuarios Registrados pero no tiene un Leer Más, entonces el artículo completo será visible para todos los usuarios. ¡Así que añade un Leer Más al artículo!

*Traducido por openai.com*

