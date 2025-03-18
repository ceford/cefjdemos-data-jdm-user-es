<!-- Filename: J5.x:Add_a_class_selector_to_the_create_link_dialog / Display title: Artículo: Editar - Estilos de Enlace -->

## Descripción

Las clases de enlace personalizadas añadidas a las opciones del editor TinyMCE te permiten transformar rápidamente un enlace de artículo en un botón o añadir otros efectos visuales sin tener que modificar directamente el código HTML.

### Pasos para usar el selector de clase

1. Desde el Panel de Inicio, ve a la lista de Plugins y encuentra el plugin de TinyMCE.
2. Abre el plugin de TinyMCE y con la pestaña de Plugin seleccionada, desplázate hasta el final.
3. Añade clases a la *Lista de Clases de Enlace*. Por ejemplo, clases de Bootstrap para crear botones elegantes. Puede que necesites desplazarte por la lista de izquierda a derecha o cambiar la magnificación de la pantalla para ver los botones de agregar, eliminar y ordenar al final.
4. Guardar y Cerrar.

![Set link classes in tinymce](../../../en/images/articles/article-edit-link-style-tinymce.png)

Puedes encontrar ejemplos de plantillas que usan Bootstrap nativamente en la [Documentación oficial de Bootstrap](https://getbootstrap.com/docs/5.3/components/buttons/).

Aquí hay algunas clases que puedes usar para variantes de botones de Bootstrap:

- `btn btn-primary` para un botón principal
- `btn btn-secondary` para un botón secundario
- `btn btn-success` para un botón de éxito
- `btn btn-danger` para un botón de peligro
- `btn btn-warning` para un botón de advertencia
- `btn btn-info` para un botón de información
- `btn btn-light` para un botón claro
- `btn btn-dark` para un botón oscuro
- `btn btn-link` para un botón de enlace

#### Alternativas al Botón de Contorno

También puedes usar las variantes de botón de contorno:

- `btn btn-outline-primary` para un botón primario contorneado
- `btn btn-outline-secondary` para un botón secundario contorneado
- … (etc.)

#### Para los tamaños de botón, añade estas clases

- `btn-lg` para un botón grande
- `btn-sm` para un botón pequeño

**Ejemplo:** `btn btn-dark btn-lg` (un botón grande y oscuro)

## Crear un enlace en un artículo

1. Abre un artículo y selecciona algún texto, una palabra o frase, para crear un enlace.
2. Selecciona el ícono de Enlace que aparece cuando seleccionas algún texto.
3. Introduce la URL para el enlace.
4. En la parte inferior del cuadro de diálogo de creación del enlace, selecciona una de las clases configuradas.
5. Guarda el Enlace.
6. Guarda el Artículo.
7. Previsualiza el Artículo.

![Apply link style in an article](../../../en/images/articles/article-edit-link-style-apply.png)

Y este es un ejemplo donde la clase del botón de enlace se configuró como `btn btn-sm btn-outline-info` y el texto enlazado es *Bootstrap*:

![Preview of a custom Link Button](../../../en/images/articles/article-edit-link-style-preview.png)

## Uso Avanzado: Aplicación de Clases Personalizadas

Esta función no se limita a las clases de Bootstrap. También puedes aplicar tus propias clases CSS personalizadas para necesidades específicas. Por ejemplo, puedes agregar un icono antes del enlace con un efecto hover. Esto hace que sea fácil estilizar los enlaces sin necesidad de modificar el código fuente del artículo. 
*Traducido por openai.com*

