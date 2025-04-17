<!-- Filename: J3.x:Adding_custom_fields/Multilingual_Sites / Display title: Sitios multilingües -->

## Introducción

Si tienes un sitio multilingüe, puedes mostrar las etiquetas y descripciones de los campos y grupos de campos en el idioma del usuario. Para hacer esto:

1. Define el Título y la Descripción de tu grupo de campos como constantes de idioma.
2. Define la Etiqueta y la Descripción de tu campo como constantes de idioma.
3. Configura esas constantes de idioma como reemplazos para cada uno de tus idiomas.

En el siguiente ejemplo, se crean un grupo de campos de Contacto y un campo para las preferencias personales de un contacto. El grupo de campos se llama Favoritos y el campo de ejemplo se llama Coche. Evidentemente, se pueden añadir más campos para otras cosas favoritas, como comida o películas.

Para seguir este ejemplo se asume que has configurado un sitio multilingüe según lo descrito en el tutorial [Sitios Multilingües](jdocmanual?article=user/languages/setup-a-multilingual-site).

## Constantes de Idioma

Las constantes de idioma son marcadores de posición que se reemplazan por valores de idioma cuando se muestra una página. Las constantes y sus valores se almacenan en archivos de idioma, como JPATH_SITE/languages/en-GB/com_contact.ini y JPATH_SITE/administrator/languages/en-GB/com_contact.ini, para el frontend y el backend respectivamente. Por convención, la mayoría de las constantes de idioma comienzan con el nombre de la extensión todo en mayúsculas, por ejemplo, COM_CONTACT_...

Las sobrescrituras de idioma son reemplazos definidos por el usuario para constantes y valores de idioma existentes o nuevas constantes y valores, como en este ejemplo. Todas se almacenan en archivos únicos, uno para las páginas del Sitio y otro para las páginas del Administrador:
```
SITE_ROOT/language/overrides/en-GB.override.ini
SITE_ROOT/administrator/language/overrides/en-GB.override.ini
```
Es importante hacer que las nuevas constantes de idioma definidas por el usuario sean únicas para evitar sobrescribir las constantes existentes. Por ejemplo:

COM_CONTACT_CUSTOM_FIELDGROUP_FAVOURITES="Favoritos"
COM_CONTACT_CUSTOM_FIELDGROUP_FAVOURITES_DESCRIPTION="Coche, película favorita, etc."
COM_CONTACT_CUSTOM_FIELD_FAVOURITE_CAR="Coche Favorito"
COM_CONTACT_CUSTOM_FIELD_FAVOURITE_CAR_DESCRIPTION="A veces usado como una pregunta de seguridad"

Si hay algún error en la sintaxis de un archivo de idioma, no se cargará y todas las constantes en él pueden aparecer en las páginas de salida. Y tenga en cuenta que un archivo se ordena en orden alfabético.

## Definiendo las Sobrescrituras

Es importante crear sobrescrituras en inglés (GB). Joomla carga primero los archivos de traducción en-GB y luego sobrescribe los valores con un archivo de idioma seleccionado. Esto garantiza que los usuarios nunca deberían ver una constante de texto. Si falta un valor traducido, aparecerá el inglés en la salida. Esto parece extraño, pero es mejor que ver una constante bastante larga que generalmente altera los diseños.

Desde el menú del Administrador:

* Selecciona **Sistema / Panel de Gestión / Sobrescrituras de Idioma**
* Selecciona **Inglés (Reino Unido) - Sitio** de la lista *Seleccionar Idioma y Cliente*
* Selecciona el botón **Nuevo** de la barra de herramientas.
* En el campo **Constante de Idioma** ingresa *COM_CONTACT_CUSTOM_FIELDGROUP_FAVOURITES*
* En el campo **Texto** ingresa el valor *Favourites*
* Marca la casilla **Para Ambas Ubicaciones**. Esto causará la creación de sobrescrituras para ambas, las páginas del Sitio y del Administrador.
* Selecciona **Guardar y Nuevo** de la lista desplegable *Guardar * Cerrar*.
* Repite para cada una de las otras constantes requeridas.
* Selecciona **Cerrar** después de que la última entrada haya sido guardada.
* Repite para cada uno de los idiomas instalados.

La siguiente captura de pantalla muestra un ejemplo de la creación de sobrescritura para una constante de idioma alemán.

![Creación de sobrescritura en alemán](../../../en/images/fields/fields-overrides-creation-de.png)

## Definiendo el Grupo de Campos

Desde el menú de Administrador:

* Seleccione el elemento de menú **Componentes / Contactos / Grupos de Campos**.
* Seleccione el botón **Nuevo** desde la Barra de herramientas.
* En el campo Título, ingrese la constante COM_CONTACT_CUSTOM_FIELDGROUP_FAVOURITES
* En el campo Descripción, ingrese la constante COM_CONTACT_CUSTOM_FIELDGROUP_FAVOURITES_DESCRIPTION
* Seleccione **Guardar & Cerrar** desde la Barra de herramientas.

## Definiendo el Campo

Para seleccionar un coche favorito, puedes proporcionar una lista desplegable de coches que definas, o una lista desplegable de coches obtenida de una tabla de base de datos, o una lista de botones de opción con etiquetas que definas. En este caso, un sencillo campo de entrada de texto permitirá la entrada de cualquier marca y modelo de coche de toda la historia mundial de la industria del automóvil.

Desde el menú del Administrador:

* Selecciona el elemento de menú **Componentes / Contactos / Campos**.
* Selecciona el botón **Nuevo** de la Barra de Herramientas.
* En el campo Título, ingresa la constante COM_CONTACT_CUSTOM_FIELD_FAVOURITE_CAR
* En el campo Tipo, selecciona **Texto (texto)** si no está ya seleccionado.
* En el campo Descripción, ingresa la constante COM_CONTACT_CUSTOM_FIELD_FAVOURITE_CAR_DESCRIPTION
* En el campo **Grupo de Campos** (a la derecha) Selecciona el Grupo de Campos que creaste.
* Selecciona **Guardar & Cerrar** desde la Barra de Herramientas.

## Editar un contacto

Con el inglés seleccionado antes de iniciar sesión como Administrador, el formulario de ingreso de datos del contacto debe contener una pestaña con el nombre en inglés de tu grupo de campos y los campos de ese grupo también con valores en inglés.

![Entrada de datos en inglés](../../../en/images/fields/fields-overrides-entry.png)

Con el alemán seleccionado antes de iniciar sesión como Administrador, deberías ver las traducciones al alemán de tus constantes de idioma:

![Entrada de datos en alemán](../../../en/images/fields/fields-overrides-entry-de.png)

Advertencia: ¡traducción por translate.google.co.uk!

## Mostrar un Contacto

En inglés:

![Visualización de datos en inglés](../../../en/images/fields/fields-overrides-display.png)

Y en alemán:

![Visualización de datos en alemán](../../../en/images/fields/fields-overrides-display-de.png)

*Traducido por openai.com*

