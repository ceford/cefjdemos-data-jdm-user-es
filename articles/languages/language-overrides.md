<!-- Filename: J4.x:Language_Overrides / Display title: Anulaciones de Idioma  -->

## Ubicaciones de Archivos de Idioma

La mayoría de los archivos de idioma de Joomla! se encuentran en carpetas de idioma, una en la raíz del sitio y otra en la carpeta del administrador. Cada idioma tiene su propia subcarpeta basada en los códigos de idioma estándar RFC3066. Cada extensión guarda sus traducciones con un nombre derivado del nombre de la extensión. Algunos ejemplos:

    siteroot/language/en-GB/com_content.ini
    siteroot/administrator/language/en-GB/com_content.ini
    siteroot/administrator/language/en-GB/com_content.sys.ini

Los archivos contienen líneas que consisten en una clave y su traducción:

    COM_CONTENT="Artículos"
    COM_CONTENT_ADD_NEW_MENU_ITEM="Nuevo Elemento del Menú"
    COM_CONTENT_ARTICLE_CONTENT="Contenido"
    COM_CONTENT_ARTICLES_TABLE_CAPTION="Tabla de Artículos"
    COM_CONTENT_ARTICLES_TITLE="Artículos"

El código PHP de Joomla usa la clave. Esta es reemplazada por la traducción de texto en tiempo de ejecución. El archivo .ini contiene traducciones utilizadas por la extensión. Los archivos sys.ini contienen traducciones utilizadas por Joomla para gestionar la extensión. Puede haber cientos de líneas en un archivo de idioma.

Se aconseja a las extensiones de terceros que guarden sus archivos de idioma en carpetas de idioma dentro de la extensión. Allí están a salvo de ser eliminadas si un administrador decide desinstalar un idioma. Ejemplo:

    siteroot/components/com_countrybase/language/en-GB/com_countrybase.ini
    siteroot/administrator/components/com_countrybase/language/en-GB/com_countrybase.ini
    siteroot/administrator/components/com_countrybase/language/en-GB/com_countrybase.sys.ini

**¡Nunca edite ningún archivo de idioma principal de Joomla! o de terceros! Cualquier cambio que realice se perderá en la próxima actualización. Si desea cambiar el texto de cualquier elemento de idioma, use el componente formal de Sobrecarga de Idioma.**

Las sobrecargas de idioma son sus reemplazos para las traducciones de claves de idioma principal o de extensión. Son traducciones individuales, una o dos, ¡no un archivo completo! Las sobrecargas de idioma para un idioma determinado se almacenan en un solo archivo:

    siteroot/language/overrides/en-GB.override.ini
    siteroot/language/overrides/fr-FR.override.ini
    siteroot/language/overrides/de-DE.override.ini

    siteroot/administrator/language/overrides/en-GB.override.ini
    siteroot/administrator/language/overrides/fr-FR.override.ini
    siteroot/administrator/language/overrides/de-DE.override.ini

### Orden de Carga de Idiomas

En cada carga de página, las traducciones en-GB se cargan primero. Esto asegura que los usuarios del sitio no vean claves. Si se está usando otro idioma, las traducciones para ese idioma se cargan a continuación, reemplazando las traducciones en-GB. Otros idiomas tienden a ir detrás de en-GB en la creación de traducciones, por lo que los usuarios pueden ocasionalmente ver palabras o frases en inglés entre las de su propio idioma.

Finalmente, las traducciones se cargan desde el archivo de sobrecarga de idioma. Esto permite que el sitio use palabras o frases alternativas para adaptarse a las circunstancias locales.

## Anulaciones de Idioma

Ocasionalmente, puede que desees reemplazar un elemento de idioma traducido por algo más adecuado a las circunstancias locales. Un caso común es cuando creas una sobrescritura de plantilla o un diseño y deseas agregar algún contenido que utilice una nueva clave de idioma. El siguiente ejemplo ilustra un caso donde se ha añadido texto al diseño de cierre de sesión del módulo de inicio de sesión, descrito en el artículo sobre Diseños de Plantilla. El diseño alternativo tiene este código:

```html
<p class="text-center">
Su sesión expirará a las <br><?php echo $endTime; ?>
</p>
```

Para un sitio multilingüe usando inglés, francés y alemán, el código necesita cambiar:

```html
<p class="text-center">
<?php echo Text::_('TPL_CASSIOPEIA_MOD_LOGIN_SESSION_EXPIRES_AT')?><br><?php echo $endTime; ?>
</p>
```

Nota: si has seguido el tutorial de Diseño de Plantilla, es posible que ya tengas una clave TPL_CASSIOPEIA_MOD_LOGIN_LAYOUT_EXPIRES que se traduce como Expira. Pero eso se utiliza en siteroot/administrator/language/overrides.

La nueva clave ahora puede ser traducida a cada idioma. Las traducciones se guardarán en siteroot/language/overrides.

- Selecciona **Sistema**→**Panel de administración**→**Anulaciones de Idioma**
- Selecciona tu idioma y la ubicación del Sitio.
- Selecciona el botón **Nuevo** y completa el formulario. En este ejemplo, la clave de idioma es **TPL_CASSIOPEIA_MOD_LOGIN_SESSION_EXPIRES_AT** y el texto podría ser **Su sesión expirará a las**
- Guarda y cierra el formulario.
- Repite el proceso de traducción para cada idioma.

![formulario de edición de anulación de idiomas](../../../en/images/languages/language-overrides-edit.png)

Finalmente, verifica que la traducción se ha implementado.

![Resultado de Anulación en formulario de inicio de sesión del sitio](../../../en/images/languages/language-overrides-custom-logout.png)

*Traducido por openai.com*

