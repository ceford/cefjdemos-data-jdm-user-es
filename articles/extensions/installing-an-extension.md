<!-- Filename: Installing_an_extension / Display title: Instalación de una extensión   -->

## Documentación de Extensión

Antes de comenzar, siempre es recomendable leer la documentación asociada con una extensión. La mayoría de las extensiones tienen páginas de inicio y foros, y es una buena idea revisarlos primero. Si hay un archivo README incluido con la extensión, deberías leerlo. Puede haber instrucciones especiales de instalación o configuración.

## Instalar Extensiones del Sistema

El formulario de Sistema / Instalar / Extensiones está bastante bien documentado en la pantalla de Ayuda. Lo que no es tan obvio es que cada uno de los métodos de instalación es un complemento. En las primeras ediciones de Joomla 4, el complemento Instalar desde Web estaba en primer lugar de la lista y es posible que siga siendo el caso en versiones que se han actualizado. Tener ese método primero es inconveniente si usualmente usas uno de los otros métodos porque toma unos segundos obtener datos del sitio del Directorio de Extensiones de Joomla.

Para cambiar el orden:

- Ve al **Panel Principal / Complementos**
- Selecciona **installer** del filtro desplegable **Seleccionar Tipo**.
- Selecciona el ícono **Orden de Clasificación** para revelar los controles de agarre de clasificación (elipsis vertical).
- Arrastra el elemento **Installer - Install from Web** al final de la lista.
- Vuelve a **Sistema / Instalar / Extensiones** para ver el resultado.

Estás listo para usar uno de los métodos de instalación estándar.

### Subir Archivo de Paquete

Para la mayoría de las extensiones y la mayoría de los usuarios, el procedimiento será:

- Descarga la extensión a tu máquina local como un paquete de archivo zip.
- Desde el panel de administración de tu sitio Joomla selecciona
  **Sistema → Instalar → Extensiones**.
- Desde la pestaña **Subir Archivo de Paquete** selecciona el botón *Buscar archivo* y selecciona el paquete de la extensión en tu computadora local o arrastra y suelta el archivo desde tu gestor de archivos.
- El proceso de subida e instalación comienza automáticamente.
- Algunas extensiones pueden proporcionar instrucciones adicionales para la instalación.
- Nota que generalmente los módulos y complementos necesitan ser habilitados antes de que funcionen.

### Instalar desde Carpeta

Algunas extensiones pueden ser demasiado grandes para usar el método de Subir Archivo de Paquete, usualmente debido a un límite en el *Tamaño Máximo de Archivo para Subir* establecido por tu proveedor de alojamiento. En este caso puedes usar el método Instalar desde Carpeta.

- Crea un directorio temporal en tu disco duro local y descomprime el archivo de la extensión en este directorio temporal.
- Usando FTP, sube el contenido de este directorio (incluyendo archivos y subdirectorios) al directorio /tmp de la raíz de Joomla en tu servidor para que tengas una ruta como /tmp/acmeextension.
- En el campo Directorio de Instalación especifica el directorio del servidor donde subiste los archivos y subdirectorios del paquete, por ejemplo /home/usuario/public_html/tmp/acmeextension.
- Selecciona el botón **Verificar e Instalar** y Joomla! instalará el contenido del directorio proporcionado.

### Instalar desde URL

En lugar de descargar un archivo zip a tu computadora local, puedes simplemente usar la URL de descarga. Joomla obtendrá el archivo zip directamente y ahorrará los pasos de descarga y subida de los métodos anteriores.

### Instalar desde Web

Esta opción te permite instalar una extensión directamente desde el Directorio de Extensiones de Joomla. La lista inicial está ordenada por número de reseñas, pero puedes seleccionar por Categoría para encontrar rápidamente una lista de extensiones que puedan satisfacer tus necesidades.

## Descubrimiento de Instalación del Sistema

Como se describe en la pantalla de Ayuda, la función Descubrir te permite instalar extensiones que son demasiado grandes para algunos sistemas, especialmente en entornos de alojamiento compartidos de bajo costo. Algo que puede no ser obvio es que puede que necesites crear carpetas en diferentes lugares en tu servicio de alojamiento, típicamente:

- Sube los archivos del sitio a siteroot/components/com_mybigcomponent
- Sube los archivos del administrador a siteroot/administrator/components/com_mybigcomponent
- Sube los medios (css y javascript) a siteroot/media/com_mybigcomponent
- Sube los archivos de idioma del sitio a siteroot/language/en-GB si no están en una carpeta de idioma en la carpeta de componentes del sitio.
- Sube los archivos de idioma del administrador a siteroot/administrator/language/en-GB si no están en una carpeta de idioma en la carpeta del administrador del componente.

Con eso hecho, Descubrir debería encontrar y permitir la instalación del componente y podría realmente funcionar.

## Idiomas de Instalación del Sistema

El idioma predeterminado es inglés GB. No se puede eliminar ni instalar.
Puede que no sea obvio, pero cada página carga primero las cadenas en-GB apropiadas
para asegurar que las claves de idioma usadas por los programadores no aparezcan en la
salida de la página. Si el idioma seleccionado por el usuario no es inglés, entonces se
carga el idioma del usuario, sobrescribiendo las cadenas en inglés. Si un idioma no ha
sido completamente traducido, el resultado será una mezcla de cadenas en el idioma del
usuario y en inglés. Esto puede parecer extraño, pero es mejor que una mezcla de idioma
del usuario y claves de programador.

De la lista de idiomas disponibles, selecciona el que necesites instalar.
Algunos están marcados con un botón verde para indicar que están actualizados con
la versión actual de Joomla. Otros están marcados con un botón amarillo para indicar
que no están del todo actualizados. Adelante, instálalos de todas maneras. Es posible
que veas algunas palabras en inglés en lugares que deberían estar en tu idioma seleccionado.
Pero podrían ser raras.

*Traducido por openai.com*

