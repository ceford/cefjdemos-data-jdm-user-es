<!-- Filename: Debugging_a_translation / Display title: Depuración de una Traducción  -->

## Archivos de Idioma de Joomla

Siempre que se va a mostrar texto en la pantalla, los programadores de Joomla insertan una constante de idioma como JYES o JNO. Durante el proceso de renderización se cargan archivos de idioma con traducciones en el idioma adecuado. Todos los archivos de idioma terminan en `.ini`. Puedes buscar en languages/en-GB/joomla.ini para ver algunos ejemplos básicos. Las líneas que comienzan con un punto y coma se ignoran. Pueden usarse para comentarios. Las líneas restantes consisten en pares de clave="valor". Cada idioma tiene el mismo conjunto de claves, pero los valores son las traducciones adecuadas.

Cada extensión de Joomla tiene sus propios archivos de idioma, por lo que hay cientos en total. A veces, hay problemas como constantes de idioma faltantes, constantes de idioma mal escritas o errores de sintaxis en las cadenas de traducción que pueden hacer que un archivo de idioma completo sea inválido.

## Depuración de Idiomas

Joomla ofrece algunos mecanismos de depuración útiles que pueden facilitar la localización de cadenas no traducidas y el diagnóstico de problemas con las traducciones de idiomas en las extensiones instaladas. Para probarlo:

Desde el Panel de Control:

* Selecciona el botón **Configuración Global** en el panel *Sistema*.
* Selecciona el panel *Sistema* y ajusta **Depuración de Idiomas** a **Sí**.
* **Visualización del idioma** normalmente está configurada a **Valor**. Si se ajusta a **Constante**, el diseño se verá alterado por constantes largas que no se ajustan.

Con la Depuración de Idiomas activa, todos los valores traducibles se muestran rodeados de caracteres especiales que indican su estado:

* `**Joomla CMS**` Texto rodeado de dos asteriscos indica que se ha encontrado una coincidencia en un archivo de idioma y la constante ha sido traducida.
* `??Joomla CMS??` Texto rodeado por pares de signos de interrogación indica que la constante es traducible, pero no se encontró ninguna coincidencia en un archivo de idioma.
* `Joomla CMS` Texto sin caracteres circundantes indica que el valor no es traducible.

## Depuración del Sistema

Se puede obtener información adicional de depuración de idiomas activando la depuración del sistema.

Desde el Panel de Inicio:

* Selecciona **Plugins** y luego encuentra y habilita el plugin **Sistema - Depuración**.
* Vuelve a seleccionar el Panel de Inicio y luego...
* Selecciona el botón de **Configuración Global**.
* Selecciona el panel de *Sistema* y ajusta **Depurar Sistema** a **Sí**.

Con **Depuración del Sistema** activa, todas las pantallas tienen información adicional de depuración en la parte inferior de cada página. Se puede expandir desde un ícono de Joomla y el borde superior se puede arrastrar verticalmente para mostrar más líneas.

La información de depuración aparece bajo varios encabezados:

* **Información J!** Información básica de instalación.
* **Solicitud** Campos de solicitud del servidor.
* **Sesión** Información de la sesión.
* **Perfil** La cantidad de tiempo tomado para ejecutar el código hasta diversos puntos de referencia en el código.
* **Consultas** Las consultas SQL ejecutadas en el proceso de construir la página.
* **Cargado.** Una lista de todos los archivos de idioma cargados durante el proceso de construcción de la página, incluida la información de ruta completa. Esto puede ser útil para verificar que los archivos esperados se han cargado.
* **No traducido** Una lista de todas las constantes no traducidas encontradas y la posible ubicación del archivo dada donde se realizó la llamada de traducción.
* **Errores**

## Sistema - Plugin de Depuración

Este plugin del sistema controla lo que se muestra cuando se activa la depuración en la **Configuración Global**. Hay tres configuraciones de interés para los traductores.

En la pestaña **Idioma**:

![plugin del sistema de depuración](../../../en/images/languages/languages-debug-plugin.png "Sistema - Depuración del Idioma")

* **Errores al Analizar Archivos de Idioma** Muestra un error si un archivo de idioma no se carga.

- **Archivos de Idioma**. Si está configurado en *Mostrar*, entonces...
- **Cadena de Idioma** Si está configurado en *Mostrar*, entonces...
- **Eliminar Primera Palabra**.
- **Eliminar desde el Inicio**.
- **Eliminar desde el Final**.

**¡La siguiente explicación necesita revisión!**

Tenga en cuenta que las cadenas no traducidas solo mostrarán el valor pasado al método **Text** apropiado. Por ejemplo, con el siguiente código:

    echo Text::_( 'Configuración de Importación de Informes' );

Si no está traducido, se mostrará como:

    # /administrator/components/com_reports/views/reports/tmpl/default.php
    REPORTS IMPORT CONFIGURATION=Configuración de Importación de Informes

Si el Prefijo de Clave de Eliminación está configurado en "Informes", entonces la muestra cambiaría ligeramente a:

    # /administrator/components/com_reports/views/reports/tmpl/default.php
    REPORTS IMPORT CONFIGURATION=Configuración de Importación

Tenga en cuenta que la ruta mostrada es solo una mejor suposición basada en una llamada a la función PHP *debug_backtrace*. A veces es precisa, a veces no, y también hay casos en los que no se pudo determinar ningún archivo. En esos casos, debe usar su mejor juicio.

*Traducido por openai.com*

