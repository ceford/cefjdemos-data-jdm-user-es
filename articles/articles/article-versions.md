<!-- Filename: Help4.x:Components_Version_History / Display title: Artículo: Versiones   -->

## Introducción

En el formulario de edición de artículos de Joomla, cada vez que se guarda un artículo, se crea automáticamente una nueva versión. El número de versiones que se deben mantener para cada artículo puede configurarse en la página *Artículos: Opciones*, pestaña *Diseño de Edición*. El predeterminado es 10. Tenga en cuenta que esta no es la pestaña *Opciones* de la página *Artículos: Editar*. La versión actual suele ser la última guardada.

Una o más versiones pueden ser marcadas para *Conservar para siempre*. Dichas versiones no serán eliminadas automáticamente, incluso si se excede el número máximo de versiones.

El cuadro de diálogo emergente *Versiones* se utiliza para gestionar versiones anteriores del elemento que se está editando. Historias de versiones similares están disponibles para Artículos, Banners y Clientes, Contactos, Fuentes de Noticias, Notas de Usuario y todas las Categorías.

Nota: Los campos personalizados no se almacenan en diferentes versiones.

## Cómo Acceder

Selecciona el botón de **Versiones** en la barra de herramientas mientras editas el elemento.

## Captura de pantalla

![Cuadro de diálogo emergente de versiones](../../../en/images/articles/articles-versions.png)

## Encabezados de Columna

- **Casilla de Verificación** Esta casilla se utiliza para seleccionar o deseleccionar todas las versiones visibles en la lista. Si se selecciona alguna casilla, los botones de la barra de herramientas se activan y se pueden usar para realizar una acción en los elementos seleccionados.
- **Fecha** La fecha y hora en que se guardó la versión. Hacer clic en este enlace abre una vista previa de esa versión en una ventana emergente. Nota que una de las fechas será seguida por un símbolo de estrella. Esto indica que esta es la versión que está actualmente guardada y siendo editada.
- **Nota de Versión** Cuando editas un elemento, tienes la opción de ingresar una Nota de Versión. Esto se puede utilizar para ayudarte a recordar qué versión contiene qué información. Si ingresaste una Nota de Versión antes de guardar el elemento, aparecerá en esta columna.
- **Conservar para Siempre** Esta columna muestra si has marcado la versión como Conservar para Siempre. Normalmente, cada versión se conservará de acuerdo con la configuración en la página de opciones del componente. La configuración predeterminada es mantener un máximo de 10 versiones anteriores para un elemento. En este caso, cuando guardas un elemento que ya tiene 10 versiones guardadas, la versión más antigua se elimina. Si una versión está marcada como Conservar para Siempre, no se contará como una de las versiones guardadas y no se eliminará cuando se alcance el número máximo. Para alternar Conservar para Siempre activado o desactivado, marca la casilla de la versión y luego selecciona el botón *Manter Activo/Inactivo* en la barra de herramientas.
- **Autor** El usuario que guardó esta versión.
- **Conteo de Caracteres** El número total de caracteres guardados en esta versión. Esto incluye los nombres de las columnas de la base de datos así como los caracteres del elemento.

## Barra de herramientas

En la parte superior de la página verás la barra de herramientas mostrada en la captura de pantalla anterior. Las funciones son:

- **Restaurar** La versión actual del elemento está marcada con una estrella a la derecha de la Fecha. Si deseas restaurar una de las otras versiones guardadas, marca la casilla de verificación para la versión deseada y selecciona el botón *Restaurar*. La versión actual del elemento será reemplazada con la versión seleccionada, y la pantalla de edición se volverá a cargar con la versión restaurada cargada en el editor.
- **Vista previa** Para obtener una vista previa de una versión, selecciona el elemento en la columna Fecha o marca la casilla y haz clic en el botón de Vista previa. Se cargará una ventana del navegador por separado mostrando la versión seleccionada del elemento, similar a la captura de pantalla a continuación. Después de ver la versión, cierra la ventana del navegador.
![Diálogo de vista previa de versiones](../../../en/images/articles/articles-versions-preview.png)
- **Comparar** Para comparar dos versiones y ver qué ha cambiado, haz clic en las casillas de cada una de las versiones y haz clic en el botón Comparar. Se abrirá una nueva ventana del navegador, como se muestra en la captura de pantalla a continuación. La primera columna es el nombre del campo, la segunda es la versión anterior, la tercera es la versión más reciente, y la última columna resalta las diferencias entre las dos versiones.
![Diálogo de comparación de versiones](../../../en/images/articles/articles-versions-compare.png)
- **Mantener Activado/Desactivado** Este botón te permite activar o desactivar la función Mantener Para Siempre para una versión. Normalmente, la versión más antigua de un elemento se eliminará automáticamente cuando se haya excedido el número máximo de versiones (establecido en las Opciones para el componente). Si configuras la propiedad Mantener Para Siempre para una versión, nunca se eliminará automáticamente.
- **Eliminar** Este botón te permite eliminar manualmente una o más versiones. Selecciona la casilla para las versiones que deseas eliminar y luego selecciona el botón Eliminar. Ten en cuenta que esto *no* elimina el elemento que se está editando. Solo elimina la versión seleccionada del elemento.

*Traducido por openai.com*

