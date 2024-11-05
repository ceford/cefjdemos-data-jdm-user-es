<!-- Filename: How_do_Windows_file_permissions_work? / Display title: Permisos de Archivos: Windows -->

## Introducción

Para aquellos de ustedes que están desarrollando o entregando sus sitios web de Joomla! desde un entorno de Windows, a veces es difícil obtener información relevante sobre permisos. Desafortunadamente, es un hecho que la mayoría de los servicios web se ofrecen bajo Unix y que Unix está bastante bien documentado en este entorno. Esperamos que la siguiente información ayude a aclarar cualquier confusión y ofrezca una pequeña orientación también. 

## Descripción General de los Servidores Web de Windows

Primero, hablemos sobre las diferencias entre servidores. En general, la mayoría de las personas que utilizan Windows parecen estar usando Apache (Win32) o Microsoft IIS. Estos dos servidores web funcionan de manera muy diferente y utilizan modelos de entrega ligeramente distintos. Apache (Win32) generalmente se ejecuta en el ordenador del anfitrión como el usuario bajo el cual fue instalado, mientras que IIS se instala bajo un usuario específico pero se ejecutará bajo un usuario recién instalado *IUSR_*.

## Configuración Predeterminada de Permisos

Por defecto, Unix tiende a otorgar acceso completo solo al usuario *propietario* de los archivos y directorios. En contraste, Windows asigna por defecto al grupo *Everyone* permisos completos. Lo primero que hace un buen administrador de Windows es eliminar los derechos del grupo *Everyone* para mejorar la seguridad. Para pruebas locales en PC, probablemente esto no sea necesario, pero explica por qué, si no se elimina *Everyone* y ejecutas algún tipo de script de comprobación de permisos o el chequeo previo a la instalación de Joomla!, tendrás permisos completos de *Lectura, Escritura y Ejecución*. Estás adquiriendo los derechos del grupo *Everyone*. 

## Microsoft Internet Information Server (IIS)

IIS viene en dos versiones principales, PWS (Personal WebServer) e IIS (Internet Information Server). Esencialmente son la misma aplicación. PWS es simplemente una versión reducida de IIS diseñada para entornos de escritorio, mientras que IIS está diseñada para entornos de servidor. PWS te limita a un único sitio web principal, por lo que las instalaciones de tus aplicaciones generalmente estarán en subdirectorios del sitio web principal. IIS, por otro lado, proporciona la funcionalidad para ejecutar Hosts Virtuales desde estos directorios, ofreciendo la capacidad de múltiples sitios.

Debido a las diferentes limitaciones de funcionalidad, PWS no tiene el *Asistente de Permisos* ya que se considera que no es necesario. Solo un usuario utilizará el servidor PWS. En IIS, muchos usuarios utilizarán el servidor, por lo que se necesitan diferentes asignaciones de permisos.

Una vez que la cuenta *Todos* se elimina, Windows IIS se queda con la cuenta *IUSR_** teniendo derechos de nivel superior a los directorios del servidor web. Una verificación de permisos ahora debería arrojar diferentes resultados. Solo la cuenta *IUSR_** tiene permisos completos y otros usuarios deberían tener solo *Solo Lectura* o ningún derecho. Los derechos se determinan por los otros usuarios a los que se les han asignado derechos manualmente a los directorios de IIS.

### Asignación de Permisos

Asignar permisos en Windows es bastante sencillo, pero a veces puede ser un poco confuso. Haz clic derecho en la carpeta o archivo correspondiente. Seleccionando *Propiedades* o *Compartir y seguridad* entrarás en el panel de Gestión de Seguridad de Windows. Seleccionando (haciendo clic una vez) en cualquier nombre de usuario listado mostrará los derechos que tiene ese usuario en la mitad inferior del panel. Algunos derechos podrían estar en *gris*. Estos no están disponibles, ya sea porque el usuario actual (con el que has iniciado sesión) no tiene permisos suficientemente altos para alterarlos, o son heredados del directorio superior y han sido configurados para utilizar los permisos de ese directorio de nivel superior. (Este es generalmente el mecanismo predeterminado.)

Como puedes ver, Windows utiliza el siguiente esquema de permisos/derechos:

| # | Control | Permite #     |
| :---:        |:----   | :--- |
| 1.|  Control Total | Permite: 1, 2, 3, 4, 5, 6, 7 |
| 2.| Modificar | Permite: 2, 3, 4, 5, 6 |- |
| 3.| Lectura y Ejecución | Permite: 3, 4  |- | 
| 4.| Listar Contenido de Carpetas | Permite: 4 (pero no puede ejecutar programas)  |- |
| 5.| Leer | Permite: 5 (Implica: 4) |- |
| 6.| Escribir | Permite: 6 (Implica:4 ) |- |
| 7.| Permisos Especiales | Permite: Combinaciones |

### Propiedades de permisos de archivos de Windows

Los permisos de archivos de Windows se pueden ver como teniendo propiedades similares a los permisos de archivos UNIX o Linux (Modos). Solo se representan de manera diferente. Por ejemplo, si eres principalmente un usuario de Unix/Linux, probablemente estás acostumbrado a tener permisos representados como 644/666 755/777, en lugar de ser descritos en los términos mencionados. Entonces, cuando usas 644, significa:

- El propietario de este archivo puede leer y escribir en él.
- El grupo del propietario puede leer el archivo.
- Todos los demás pueden leer el archivo.

**Nota:** Los permisos de Windows y Unix (Listas de Control de Acceso) no se corresponden exactamente; Windows no utiliza el mecanismo de *Grupos* de la misma manera. Para esta discusión y en cuanto al entorno de alojamiento web, pueden equipararse. Ah, pero en Windows no se utilizan *Grupos* y se debería haber eliminado a *Todos*. Aquí es donde Windows y Unix no equivalen completamente, pero lo que se puede hacer es *emparejar* o *correlacionar* significados equivalentes.

Este esquema no pretende realmente proporcionar una guía específica de permisos para Windows o NTFS, sino más una comprensión de cómo los permisos comúnmente citados al estilo UNIX/Linux se correlacionan en una máquina con un sistema de archivos NTFS. Los archivos que se colocan en la carpeta raíz `www` o `public_html`, o cualquier directorio al que tu sitio (`www.domain.com` o `localhost`) apunte en tu disco duro, deben ser propiedad de tu cuenta de usuario, pero solo si ese usuario no es identificado como un usuario privilegiado como el *Administrador* en Windows o *root* en UNIX/Linux. Estas cuentas permiten demasiados accesos y nunca deberían usarse para el uso diario.

### Mejores Prácticas

Las prácticas de seguridad comúnmente utilizadas sugieren que todos los **archivos** deberían tener los siguientes permisos.

- **Propietario** Leer y Escribir
- **Grupo** Solo Lectura
- **Otros** Solo Lectura

Todas las **carpetas** deberían tener los siguientes permisos.

- **Propietario** Leer, Escribir y Ejecutar
- **Grupo** Leer y Ejecutar
- **Otros** Leer y Ejecutar

Se podría argumentar que esto no es necesariamente la seguridad *óptima*, pero se debe encontrar un equilibrio entre seguridad, funcionalidad y mantenibilidad.

Windows, a diferencia de Unix, no mantiene una ACL única para *Ejecutar*, sino que simplemente proporciona *Leer y Ejecutar* combinado, lo cual no implica *Escribir*. Sin embargo, la ACL de *Leer y Ejecutar* implica *Listar Contenido de Directorios*. Por lo tanto, si solo tienes permisos de *Leer y Escribir* en un directorio pero no *Ejecutar*, no podrás ver el contenido del directorio y también podrías tener problemas cuando intentes ejecutar el archivo a través de un navegador web. Se requiere un poco de comprensión de los permisos UNIX/Linux para correlacionarlos completamente con los permisos de Windows. La siguiente tabla debería ayudar:

| Modo Unix   | ACL de Windows | Comentarios|
|:-----------:| :----   | :--- |
| 7 | Modificar| Leer, Escribir y Ejecutar, deberías ser el propietario de este archivo | 
| 6 | Leer y Escribir | | 
| 5 | Leer y Ejecutar| utilizado para la mayoría de las aplicaciones | 
| 4 | Solo Lectura | la seguridad a través de la oscuridad no es una buena práctica | 
| 3 | Escribir y Ejecutar | no está disponible a través de Windows, a menos que se utilicen Permisos *Especiales*, no se utiliza comúnmente | 
| 2 | Solo Escritura | no está disponible a través de Windows, a menos que se utilicen Permisos *Especiales*, no se utiliza comúnmente | 
| 1 | Solo Ejecución | (no está disponible a través de Windows, a menos que se utilicen Permisos *Especiales*, no se utiliza comúnmente) |

En comparación con los modos Unix, cuando ves algo como 644, divídelo en tres elementos:

El primer número representa los permisos del Propietario, el segundo representa los permisos del Grupo y el tercero, los permisos de Otros. El equivalente en Windows sería:

- **Propietario** (6) Leer y Escribir
- **Grupo** (4) Solo Lectura
- **Otros** (4) Solo Lectura

Esperemos que este ejemplo proporcione alguna idea de cómo correlacionar Modos/Permisos de Unix con Permisos/ACLs de Windows. Este documento no incluye temas más complejos como permisos *Efectivos*, *Heredados* o *Especiales*. A pesar de la facilidad de uso de Windows, los mecanismos de Permisos y ACL de Microsoft son en realidad bastante complejos y muy extensos, pero esto podría darte una referencia rápida para intentar aliviar algo de la confusión que rodea a la traducción de Permisos entre Unix y Windows.

*Traducido por openai.com*

