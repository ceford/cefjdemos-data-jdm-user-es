<!-- Filename: J4.x:Template_Layouts / Display title: Plantillas de Diseño  -->

## Estructuras de Archivos de Diseño

En un **template** (plantilla), cada extensión que genera salida en HTML coloca el código de salida en un archivo de plantilla dentro de la estructura de archivos de la extensión, a menudo en una carpeta llamada tmpl. Algunos ejemplos:

- /modules/mod_login/tmpl/default.php
- /modules/mod_login/tmpl/default_logout.php
- /components/com_content/tmpl/article/default.php
- /plugins/content/vote/tmpl/vote.php

En una **sobreescritura de plantilla**, se crea un archivo con el mismo nombre dentro de la estructura de archivos de la plantilla y se utiliza en lugar del archivo en la estructura de archivos de la extensión. Ejemplos correspondientes:

- /templates/cassiopeia/html/mod_login/default.php
- /templates/cassiopeia/html/mod_login/default_logout.php
- /templates/cassiopeia/html/com_content/article/default.php
- /templates/cassiopeia/html/plg_content_vote/vote.php

Esto te permite personalizar la salida para que se adapte a tus necesidades. Sin embargo, no tienes la opción de elegir si usar o no tu sobreescritura. Siempre se usa.

En un **diseño de plantilla alternativo**, creas un archivo con un nombre diferente al original pero dentro de la misma carpeta de plantillas. El nuevo nombre no debe contener un carácter de subrayado. También creas cualquier archivo que comparta la primera parte del nombre original. Un ejemplo:

- /templates/cassiopeia/html/mod_login/expires.php
- /templates/cassiopeia/html/mod_login/expires_logout.php

Luego se vuelve posible elegir si usar el diseño predeterminado original o el diseño alternativo. La elección se realiza en el formulario de edición del módulo o componente (pestaña Avanzado para módulos, pestaña Opciones para Artículos). Ten en cuenta que no todas las extensiones permiten sobreescrituras o diseños alternativos.

**Cuidado:** los plugins no proporcionan un mecanismo para seleccionar diseños alternativos.

## Diseños Alternativos de Módulos

Crear un diseño alternativo para un módulo es similar a crear una
sobrescritura de plantilla para un módulo. En ambos casos, se crea una carpeta
llamada `templates/.../html/`. Por ejemplo, la carpeta para una sobrescritura de plantilla o diseño alternativo de "mod_login" para la plantilla cassiopeia sería `templates/cassiopeia/html/mod_login/`.

Hay dos diferencias importantes entre una sobrescritura de plantilla y un
diseño alternativo. La primera es el nombre del archivo. Para la sobrescritura
de plantilla, se nombraría el archivo como `default.php` para que coincida con el nombre del archivo principal. Para un diseño alternativo, se usa un nombre diferente. La única regla es que **el nombre del archivo no debe tener guiones bajos**.

La segunda diferencia importante es que, a diferencia de los archivos de sobrescritura de plantilla que se usan automáticamente cada vez que se muestra el módulo usando la plantilla con la sobrescritura, un archivo de diseño alternativo solo se usa si lo seleccionas como un parámetro en la configuración de parámetros del Módulo.

### Un ejemplo trabajado - mod_login

- Ve a **Sistema **→** Plantillas del sitio **→** Detalles y Archivos de Cassiopeia**
- Selecciona la pestaña **Crear sobrescrituras**.
- De la lista de Módulos selecciona el elemento **mod_login**.
- En la pestaña Editor, selecciona **html **→** mod_login** para ver tus nuevas copias creadas de las plantillas de salida de mod_login.
- Renombra **default.php** a algo más sin guiones bajos, **expires.php** en este ejemplo.
- Renombra **default_logout.php** a **expires_logout.php**.

Ahora tienes dos archivos con exactamente el mismo contenido que los originales. Cambia el contenido de expires_logout.php para agregar un mensaje informando al usuario a qué hora expirará la sesión después de cada carga de página.

En la línea 16, inmediatamente debajo de las declaraciones de uso existentes, agrega lo siguiente:

```php
use Joomla\CMS\Factory;

date_default_timezone_set('Europe/London');
$config = Factory::getContainer()->get('config');
$lifetime = $config->get('lifetime', 0);
$time = time() + $lifetime * 60;
$endTime = date('H:i:s', $time); // time() devuelve un tiempo en segundos ya
```

Y en la línea 36, inmediatamente después de la línea que contiene una declaración endif, agrega este código:

```html
<p class="text-center">
Tu sesión expirará a las <br><?php echo $endTime; ?>
</p>
```

Cierra los archivos de Cassiopeia. Selecciona **Contenido **→** Módulos del Sitio** y abre el módulo de Inicio de Sesión. En la pestaña Avanzado, en el elemento de Diseño encontrarás que tienes una opción entre **-- Del Módulo -- / Predeterminado** y **-- De la Plantilla cassiopeia -- / expires**.

![módulo de inicio de sesión mostrando diseños alternativos](../../../en/images/templates/layouts-module-login.png)

Una forma en que podrías usar esta función es tener dos formularios de Inicio de Sesión, uno con acceso Público y otro con acceso para Super Usuarios. En el último, selecciona la opción **expires** y solo los Super Usuarios verán el recordatorio de la hora de expiración de la sesión.

Es importante entender que, si se especifica en la pantalla de parámetros del Módulo, un archivo de diseño alternativo para un módulo se usará para ese módulo, independientemente de qué plantilla se use para mostrar la página donde se muestra el módulo. Por lo tanto, es responsabilidad del administrador asegurarse de que el archivo de diseño funcione según lo deseado en cualquier plantilla donde este módulo se pueda mostrar.

### Traducción

Puedes traducir el nombre del archivo usando Sobrescrituras de Idioma. Prueba el siguiente procedimiento:

- Selecciona **Sistema **→** Panel de administración **→** Sobrescrituras de Idioma**
- Selecciona tu idioma y la ubicación del Administrador.
- Selecciona el botón **Nuevo** y completa el formulario. En este ejemplo, la clave de idioma es **TPL_CASSIOPEIA_MOD_LOGIN_LAYOUT_EXPIRES** y el texto podría ser **Inicio/Cierre de sesión con hora de expiración**
- Guarda y cierra y vuelve al formulario del módulo de Inicio de Sesión.

![formulario de edición de sobrescrituras de idiomas](../../../en/images/templates/layouts-language-override-form.png)

El campo de selección de diseño de módulo con **expires** traducido:

![selección de diseños alternativos de módulo](../../../en/images/templates/layouts-example-translated.png)

## Diseños Alternativos de Componentes

Los diseños alternativos de componentes funcionan de manera similar a los diseños de módulos. Se coloca un archivo en la misma carpeta donde colocarías un archivo de sobrescritura de plantilla. Por ejemplo, para crear un diseño alternativo para un artículo en la plantilla "cassiopeia", debes poner un archivo en la carpeta `templates/cassiopeia/html/com_content/article/`. Al igual que con los diseños de módulos, el archivo no debe tener el mismo nombre que el archivo principal y no debe incluir guiones bajos en el nombre. Además, no debe haber un archivo XML con el mismo nombre en esta carpeta. (Hablaremos sobre archivos XML a continuación en la sección de Diseños Alternativos de Ítems de Menú).

Puedes establecer un valor global para los diseños de componentes en la ventana de Opciones del componente. Por ejemplo, en la ventana Opciones del Artículo, hay un parámetro *Elegir un Diseño* como se muestra a continuación:

![formulario de opciones de artículos con lista de diseños alternativos](../../../en/images/templates/layouts-articles-options.png)

Al igual que con los diseños de módulos, los diseños de componentes se muestran como opciones de parámetro en la pantalla de edición individual del componente. Por ejemplo, para un artículo, el parámetro se muestra en la pestaña Editar Opciones de Artículos, como se muestra a continuación.

![formulario de edición de artículo mostrando lista de diseños alternativos](../../../en/images/templates/layout-article-edit.png)

Al igual que con otros parámetros, la configuración Usar Global usará la configuración del parámetro Opciones. La configuración Desde el Predeterminado del Componente usará el diseño predeterminado del componente. Los diseños alternativos que has creado para diferentes plantillas se muestran bajo el encabezado de cada plantilla.

Los nombres de los archivos pueden traducirse. La línea abajo:
```ini
    TPL_CASSIOPEIA_COM_CONTENT_ARTICLE_LAYOUT_MYLAYOUT="Solo Título Sin XML"
```
traducirá un archivo llamado "mylayout.php" como "Solo Título Sin XML".

Puedes tener más de un archivo para un diseño. El archivo inicial debe nombrarse sin guiones bajos y cualquier archivo adicional debe tener guiones bajos.

Los diseños alternativos de componentes pueden usarse con artículos, contactos o fuentes de noticias.

Los diseños alternativos de componentes solo se utilizan cuando se cumplen dos condiciones: (1) están especificados en los parámetros del componente; y (2) no hay un ítem de menú para este componente específico. Por ejemplo, si tienes uno o más ítems de menú del tipo "Artículo Único" configurados para un artículo determinado, entonces no se utilizará el diseño alternativo para ese artículo. En su lugar, se usará el diseño especificado en el ítem de menú. Esto es consistente con la forma general en que funcionan los parámetros del componente, donde lo más específico (en este caso, un ítem de menú de artículo único) anula lo menos específico (en este caso, los parámetros del artículo).

## Diseños Alternativos de Categorías

Los diseños alternativos de categorías funcionan como los diseños de componentes. Las reglas para especificar archivos de diseño son las mismas. La única diferencia es que la carpeta es la de la categoría, no la del componente. Por ejemplo, un diseño alternativo de categoría de contacto para cassiopeia iría en la carpeta `templates/cassiopeia/html/com_contact/category`.

Puedes configurar los diseños de categoría a nivel global, en la pantalla de Opciones de cada componente. A continuación se muestra un ejemplo del formulario de Opciones / Categoría de Contactos:

![formulario de opciones del componente de contactos mostrando diseños alternativos](../../../en/images/templates/layouts-contacts-options.png)

Los diseños alternativos de categorías se muestran cuando añades o editas una categoría en el formulario Componente: Editar Categoría / Opciones, como se muestra a continuación.

![formulario de opciones del componente de contactos mostrando diseños alternativos](../../../en/images/templates/layouts-contacts-category-options.png)

Los diseños alternativos de categorías se pueden usar para artículos, banners, contactos y fuentes de noticias.

Al igual que con los diseños de componentes, un diseño de categoría se usará solo si:

1. está seleccionado en los parámetros globales o de la categoría.
2. no hay un elemento de menú específico para la categoría.

Si hay un elemento de menú configurado para una categoría específica, se usará en su lugar el diseño seleccionado en el menú, en lugar del diseño alternativo de categoría.

## Categoría de Artículo Blog y Lista

Para los artículos, hay dos diseños principales de categoría disponibles: Blog y Lista. Cada uno de estos diseños aparece en el formulario de Opciones de Artículos, pestaña Categoría, bajo el encabezado "Desde Componente". También aparecen diseños alternativos en la lista, permitiendo que se seleccionen los diseños de plantilla alternativos, Blog o Lista, como el diseño de categoría predeterminado, ya sea globalmente o al editar una única categoría de artículo.

![formulario de opciones del componente de contactos mostrando diseños alternativos](../../../en/images/templates/layouts-articles-options-category.png)

Esto significa que, al igual que con otras opciones de diseño, puedes controlar si los enlaces de categorías de artículos usan diseños de blog o de lista. Es importante entender que, al igual que con otros parámetros de diseño, esta opción solo tendrá efecto cuando no haya un elemento de menú de categoría única para la categoría.

## Ítems de Menú Alternativos

Los Ítems de Menú Alternativos tienen una diferencia importante con los demás. Para crear un diseño alternativo de ítem de menú, debes incluir un archivo XML cuyo nombre coincida con el archivo de diseño inicial. Por ejemplo, para crear un ítem de menú alternativo llamado "miartículo" para un artículo en la plantilla cassiopeia, deberías crear dos archivos en la carpeta `templates/cassiopeia/html/com_content/article` llamados `miartículo.php` y `miartículo.xml`. Si quieres incluir más archivos de diseño, agregarías estos archivos con guiones bajos en los nombres de los archivos.

El archivo XML utiliza el mismo formato que los archivos XML de Ítems de Menú del núcleo. Esto te permite no solo crear un diseño personalizado para este ítem de menú, sino también crear parámetros personalizados. Por ejemplo, podrías ocultar algunos parámetros o añadir nuevos parámetros.

Los Ítems de Menú Alternativos aparecen cuando seleccionas un Tipo de Ítem de Menú como se muestra a continuación.

![lista de selección de ítem de menú](../../../en/images/templates/layouts-menu-blog-menu-creation.png)

Los Ítems de Menú Alternativos se usan y funcionan de la misma manera que los ítems de menú estándar. Dado que ya están basados en diseños personalizados, las anulaciones de plantillas no se aplican a los ítems de menú alternativos.

Como se indicó anteriormente, los diseños de ítems de menú tienen prioridad sobre los diseños alternativos de componentes o categorías.

La traducción de los ítems de menú alternativos se realiza con las siguientes etiquetas en los archivos XML. El formato es `"TPL_"<nombre de plantilla>_<componente>_<vista>_<nombre de ítem de menú>_<tipo de etiqueta>`. Por ejemplo, las siguientes líneas traducirán el título, la opción y la descripción de un ítem de menú alternativo llamado "catmenuitem".
```
    TPL_CASSIOPEIA_COM_CONTENT_CATEGORY_VIEW_CATMENUITEM_TITLE="cassiopeia Diseño Personalizado de Categoría"
    TPL_CASSIOPEIA_COM_CONTENT_CATEGORY_VIEW_CATMENUITEM_OPTION="cassiopeia Personalizado"
    TPL_CASSIOPEIA_COM_CONTENT_CATEGORY_VIEW_CATMENUITEM_DESC="Descripción para el diseño de categoría personalizado de cassiopeia."
```
Estas cadenas deben ser añadidas a
`administrator/language/overrides/en-GB.override.ini`, pero puedes usar el formulario de Anulaciones de Idioma descrito arriba.

El archivo catmenuitem.xml comenzaría con:

```xml
<?xml version="1.0" encoding="utf-8"?>
<metadata>
   <layout title="TPL_CASSIOPEIA_COM_CONTENT_CATEGORY_VIEW_CATMENUITEM_TITLE" option="TPL_CASSIOPEIA_COM_CONTENT_CATEGORY_VIEW_CATMENUITEM_OPTION">
      <help
         key = "JHELP_MENUS_MENU_ITEM_ARTICLE_SINGLE_ARTICLE"
      />
      <message>
         <![CDATA[TPL_CASSIOPEIA_COM_CONTENT_CATEGORY_VIEW_CATMENUITEM_DESC]]>
      </message>
   </layout>
```

## Controlar la Plantilla para Elementos de Menú Alternativos

Como se discutió anteriormente, la presencia de un archivo XML convierte un diseño alternativo en un elemento de menú. El formato del archivo XML es el mismo que el formato de los archivos XML de los elementos de menú principales. Con este archivo XML, puedes agregar los parámetros que deseas incluir para este elemento de menú. Pueden ser los mismos que uno de los elementos de menú principales, o puedes omitir parámetros principales o agregar nuevos. Ten en cuenta que si añades nuevos parámetros, estos pueden ser usados en el archivo de diseño, pero no se utilizarán en los archivos del modelo o la vista principal.

También es posible anular las configuraciones de parámetros para los parámetros principales. Un ejemplo de esto es controlar con qué plantillas se puede mostrar el diseño de un elemento de menú alternativo. En algunos casos, puedes querer permitir que un elemento de menú personalizado se muestre con cualquier plantilla para el sitio. En otros casos, puedes querer limitar el diseño de ese elemento de menú a una plantilla específica. En esta situación, solo tendrías que agregar el siguiente parámetro al archivo XML del elemento de menú:

```xml
<fields>
  <field
    name="template_style_id"
    type="templatestyle"
    label="COM_MENUS_ITEM_FIELD_TEMPLATE_LABEL"
    description="COM_MENUS_ITEM_FIELD_TEMPLATE_DESC"
    filter="int"
    template="cassiopeia"
    class="inputbox">
  </field>
 </fields>
 ```

 Esto anulará el parámetro principal `template_style_id`. Configurar la plantilla igual a "cassiopeia" en este caso limitará al usuario a seleccionar solo estilos de plantillas para la plantilla "cassiopeia".

## Más Información

- Conceptos básicos de la plantilla
- Carpetas y archivos de la plantilla Cassiopeia
- Personalización de la plantilla Cassiopeia
- Sobrescrituras de plantillas
- Diseños de plantilla
- Cassiopeia Simplificado - Un estudio de caso -
  una plantilla simple basada en Cassiopeia

*Traducido por openai.com*

