<!-- Filename: jdocmanual?manual=user&heading=plugins&filename=about-plugins.md / Display title: Sobre los Plugins  -->

## Introducción

Los plugins son extensiones de Joomla! que hacen algo *tras bambalinas* en respuesta a un disparador. Hay alrededor de 160 plugins principales en más de 20 grupos. Los desarrolladores de terceros proporcionan muchos más. La siguiente imagen muestra el inicio de la lista de plugins con la longitud de la lista configurada en 5 para la conveniencia de la captura de pantalla.

![Lista de plugins](../../../en/images/plugins/plugins-list.png)

## Tipos de Plugins

En la carpeta de plugins de tu sitio verás los tipos. Por ejemplo, verás una carpeta de **contenido**, que contiene plugins que manipulan contenido, y una carpeta de **usuario**, que contiene plugins relacionados con usuarios. Puedes filtrar la lista por Tipo o por Elemento, como *contacto*, que puede incluir varios Tipos.

## Parámetros del Plugin

Los plugins pueden tener pocos o muchos parámetros. Por ejemplo, el plugin *Contenido - Enmascaramiento de Correo Electrónico* ofrece una opción de dos métodos de enmascaramiento, mientras que el plugin *Editores - TinyMCE* tiene una larga lista de parámetros opcionales. Todos los plugins tienen valores predeterminados adecuados. A menudo, lo único que se necesita hacer es *Habilitar* o *Deshabilitar* un plugin en particular según sea necesario.

## Ejecución de complementos

La ejecución de complementos se detona mediante un *evento*. Por ejemplo, el código que ensambla un artículo para mostrar tiene eventos llamados `onContentAfterTitle`, `onContentBeforeDisplay` y `onContentAfterDisplay`. Se utilizan para posicionar cualquier campo definido por el usuario en las ubicaciones seleccionadas.

## Plugins individuales

Muy pocos de los plugins individuales están documentados aquí. Están cubiertos en la página de ayuda de cada plugin.

*Traducido por openai.com*

