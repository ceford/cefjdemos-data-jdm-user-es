<!-- Filename: Content_editors / Display title: Editores de contenido -->

Los editores estándar están disponibles en
<img src="https://docs.joomla.org/images/7/7b/Compat_icon_CMS.png"
decoding="async" data-file-width="87" data-file-height="17" width="87"
height="17" alt="Joomla multi" />

## Editor TinyMCE

**TinyMCE** es el editor por defecto para los usuarios del front-end y
el back-end. TinyMCE es un editor **WYSIWYG** (lo que ves es lo que
obtienes), que permite a los usuarios una interfaz de procesamiento de
texto amigable, a la hora de editar artículos y otros contenidos.
TinyMCE puede ser configurado con tres grupos distintos de botones en la
barra de herramientas: avanzado, simple y extendido. Para modificar este
parámetro, lo encuentras en el plugín 'Editor - TinyMCE', en el Administratos de
plugins.

TinyMCE can be configured with 3 different sets of toolbar buttons

- **Set 2** is assigned to 'Public'.
- **Set 1** is assigned to the
'Manager' and 'Registered'.
- **Set 0** is the most extended toolbar and is by default assigned to
  the 'Administrator', 'Editor' and 'Super Users'.

<img
src="https://docs.joomla.org/images/thumb/f/fb/Help30-editor-tinymce-advanced-en.png/600px-Help30-editor-tinymce-advanced-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/f/fb/Help30-editor-tinymce-advanced-en.png 1.5x"
data-file-width="669" data-file-height="114" width="600" height="102"
alt="Help30-editor-tinymce-advanced-en.png" />

Learn about Toolbars, Editor Buttons and Accessibility of
TinyMCE.

## Code Mirror

The CodeMirror editor is designed to make it easy to enter HTML code in
an article or description. CodeMirror supports syntax highlighting and
auto-completion, as shown in this screenshot.

<img
src="https://docs.joomla.org/images/thumb/e/e2/Help25-screenshot-editor-codemirror-example-en.png/320px-Help25-screenshot-editor-codemirror-example-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/e/e2/Help25-screenshot-editor-codemirror-example-en.png 1.5x"
data-file-width="326" data-file-height="165" width="320" height="162"
alt="Help25-screenshot-editor-codemirror-example-en.png" />

CodeMirror offers some of the same advantages of using No Editor, but
makes it somewhat easier to work with raw HTML code.

To set options:  CodeMirror Editor
Plugin

## Sin editor

Si se ha seleccionado 'Sin editor' para un usuario, entonces se mostrará
un editor de texto simple. Esto permitirá introducir HTML plano, sin
formatear. Puedes usar el botón "Vista previa" de la barra de
herramientas para visualizar cómo se mostrará el HTML.

Ten en cuenta que la opción 'Sin editor' puede ser útil si estás
introduciendo HTML 'repetitivo' o personalizado, por ejemplo para crear
un enlace de PayPal. TinyMCE reformatea y limpia automáticamente el
código HTML cuando se guarda un archivo. Esto puede ocasionar que el
HTML complejo no funcione correctamente.

Si ocurre esto, puedes cambiar el editor temporalmente a 'Sin editor' y
crear el contenido deseado. Ten en cuenta que si quieres editar este
contenido en el futuro, deberás cambiar el editor de nuevo a 'Sin
editor', de lo contrario, si abres y guardas el contenido con TinyMCE,
puedes perder tu código HTML personalizado.
