<!-- Filename: Installing_an_extension / Display title: Instalar una extensión -->

Antes de comenzar, siempre es bueno leer la documentación asociada con
una extensión. La mayoría de las extensiones tienen páginas web y foros
y es una buena idea para buscar en ellos primero. Si hay un archivo
README incluido con la extensión, debes leerlo.

Para la mayoría de las extensiones y la mayoría de los usuarios, el
procedimiento será:

- Descargar la extensión a tu máquina local como un archivo comprimido
  zip.
- Desde el Lado Servidor de tu sitio Joomla (administración), selecciona
  Extensiones  **→**  Gestionar.
- Has clic en el botón Examinar y selecciona el paquete de extensión de
  tu equipo local.
- Haga clic en el botón Subir e instalar.
- Algunas extensiones pueden ofrecer más instrucciones sobre la
  instalación.
- Ten en cuenta que los módulos y plugins deben estar habilitados antes
  de usarlos.

Hay algunas situaciones en las que este procedimiento no funcionará.

A veces es necesario descomprimir el archivo de forma local antes de la
instalación. Si obtiene un error diciendo que el archivo no está en el
formato correcto, necesitas descomprimir, esto una causa común. Después
de descomprimirlo trata de instalar los elementos individualmente. Ten
en cuenta que los archivos que cargas con el instalador aún deben estar
comprimidos.

A veces no puedes utilizar el instalador automático. Por ejemplo,
extensiones muy grandes pueden exceder el tamaño máximo de carga
permitido por tu alojamiento web.

También, si ves un error como este:

    Warning: is_dir() [function.is-dir]: open_basedir restriction in effect. File(/) is not within the allowed path(s): ...

esto es debido a una restricción de tu cuenta de alojamiento web que
lleva a Joomla! a tratar de comprobar si el directorio raíz existe. No
podrás utilizar el instalador automático.

## Instalación manual

Primero, hay que descomprimir todos los archivos en un directorio local
(por ejemplo `com_instalador`). Luego transferir de directorio (usando
FTP) a una carpeta en el directorio de instalación (por ejemplo
`administrator/components`), adecuado para el tipo de extensión que
estás instalando (visible en el archivo xml, una línea como

). A continuación, utiliza el instalador, pero selecciona "instalar
desde directorio", indicando el nombre de la carpeta correcto. El nombre
de esta carpeta debe ser una ruta absoluta a partir de la raíz del
sistema de ficheros.
