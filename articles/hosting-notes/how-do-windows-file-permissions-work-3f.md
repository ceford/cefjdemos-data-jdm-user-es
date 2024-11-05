<!-- Filename: How_do_Windows_file_permissions_work%3F / Display title: Permisos de Archivos de Windows  -->

## Introducción

Para aquellos de ustedes que están desarrollando o entregando sus sitios web de Joomla! desde un entorno de Windows, a veces es difícil obtener información relevante sobre permisos. Desafortunadamente, es un hecho que la mayoría de los servicios web se ofrecen bajo Unix y que Unix está bastante bien documentado en este entorno. Con suerte, la siguiente información ayudará a aclarar la confusión y proporcionar un poco de orientación también.

### Descripción general del servidor web de Windows

Primero, discutamos las diferencias entre servidores. En general, la mayoría de las personas que usan Windows parecen estar utilizando ya sea Apache(Win32) o Microsoft IIS. Estos dos servidores web operan de manera muy diferente y utilizan modelos ligeramente distintos de entrega. Apache(Win32) generalmente se ejecuta en la computadora host como el usuario bajo el que fue instalado, mientras que IIS se instala bajo un usuario específico pero se ejecutará bajo un nuevo usuario instalado *IUSR_*.

### Valores predeterminados de permiso

Por defecto, Unix tiende a dar acceso completo solo al usuario *propietario* a archivos y directorios; en oposición a este enfoque, Windows por defecto también asignará al grupo *Todos* permisos completos. Lo primero que haría cualquier buen administrador de Windows es eliminar los derechos del grupo *Todos*, para mejorar la seguridad. Para las pruebas en una PC local, esto probablemente no es necesario, pero explica por qué, si *Todos* no se elimina y ejecuta alguna forma de script de verificación de permisos o la verificación previa a la instalación de Joomla!, en general tendrá permisos completos de *Lectura, Escritura y Ejecución*, porque está adquiriendo los derechos del grupo *Todos*.

### Microsoft Internet Information Server (IIS)

IIS viene en dos principales variantes, PWS (Personal WebServer) e IIS (Internet Information Server). Esencialmente son la misma aplicación. PWS es solo una versión reducida de IIS diseñada para entornos de escritorio, mientras que IIS está diseñado para entornos de servidor. PWS lo limita a un solo sitio web principal, por lo que sus instalaciones de aplicaciones generalmente estarán en subdirectorios del sitio web principal. IIS, por otro lado, proporciona la funcionalidad para que los hosts virtuales se ejecuten desde estos directorios, ofreciendo capacidad para múltiples sitios.

Debido a las limitaciones de funcionalidad diferentes, PWS no tiene el *Asistente de Permisos* ya que se considera que no es necesario. Solo un usuario utilizará el servidor PWS. En IIS, muchos usuarios utilizarán el servidor, por lo que se necesitan asignaciones de permisos diferentes.

Una vez que se elimina la cuenta *Todos*, Windows IIS ahora queda con la cuenta *IUSR_* teniendo los derechos de nivel superior a los directorios del servidor web. Una verificación de permisos ahora debería arrojar resultados diferentes. Solo la cuenta *IUSR_* tiene permisos completos y otros usuarios deberían adquirir solo *Lectura* o ninguna buena. Los derechos se determinan según qué otros usuarios hayan sido asignados qué derechos manualmente a los directorios de IIS.

### Asignación de permisos

Asignar permisos en Windows es razonablemente sencillo, pero a veces puede ser un poco confuso. Haga clic con el botón derecho en la carpeta o archivo adecuado. La selección de *Propiedades* o *Compartir y seguridad* accederá al panel de administración de seguridad de Windows. Seleccionar (haga clic una vez) cualquier nombre de usuario que aparezca mostrará los derechos que tiene ese usuario en la mitad inferior del panel. Algunos derechos podrían estar *atenuados*. Estos no están disponibles, ya sea porque el usuario actual (con quien ha iniciado sesión) no tiene permisos lo suficientemente altos para modificarlos, o porque son heredados del directorio superior y se han configurado para usar los permisos de ese directorio de nivel más alto (este generalmente es el mecanismo predeterminado).

Como puede ver, Windows utiliza el siguiente esquema de permisos/derechos:

<table data-cellpadding="2" data-cellspacing="0" data-align="center"
data-border="1" width="533">
<thead>
<tr>
<th>#</th>
<th>Permisos</th>
<th>Derechos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;" width="5%"
data-valign="top"><p>1.</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Control
total</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Permite: 1, 2, 3, 4, 5, 6, 7</p></td>
</tr>
<tr class="even">
<td style="text-align: left;" width="5%"
data-valign="top"><p>2.</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Modificar</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Permite: 2, 3, 4, 5, 6</p></td>
</tr>
<tr class="odd">
<td style="text-align: left;" width="5%"
data-valign="top"><p>3.</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Leer
y ejecutar</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Permite: 3, 4</p></td>
</tr>
<tr class="even">
<td style="text-align: left;" width="5%"
data-valign="top"><p>4.</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Listar
contenido de carpetas</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Permite: 4 (pero no puede ejecutar programas)</p></td>
</tr>
<tr class="odd">
<td style="text-align: left;" width="5%"
data-valign="top"><p>5.</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Leer</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Permite: 5 (Implícito: 4)</p></td>
</tr>
<tr class="even">
<td style="text-align: left;" width="5%"
data-valign="top"><p>6.</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Escribir</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Permite: 6 (Implícito: 4)</p></td>
</tr>
<tr class="odd">
<td style="text-align: left;" width="5%"
data-valign="top"><p>7.</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Permisos
especiales</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Permite: Combinaciones</p></td>
</tr>
</tbody>
</table>

### Propiedades de permisos de archivos de Windows

Los permisos de archivos de Windows pueden considerarse como tener propiedades **similares** a los permisos de archivo (Modos) de UNIX o Linux, solo se representan de manera diferente. Por ejemplo, si usted es principalmente un usuario de Unix/Linux, probablemente esté acostumbrado a tener permisos representados como 644/666, 755/777, en lugar de describirse en los términos anteriormente mencionados. Entonces, cuando se le indique usar 644, esto equivale a:

* El propietario de este archivo puede leer y escribir en él.
* El grupo del propietario puede leer el archivo.
* Todos los demás pueden leer el archivo.

**Nota:** Los permisos de Windows y Unix (Listas de Control de Acceso) no se equiparan exactamente, ya que Windows no utiliza el mecanismo de *Grupos* de la misma manera. Sin embargo, para esta discusión y en relación con el entorno de alojamiento web, se pueden equiparar en conjunto. Ah, pero, en Windows no se usan ***Grupos*** y ***Todos*** debería haber sido eliminado. Aquí es donde Windows y Unix no se equiparan del todo, pero lo que se puede hacer es *ajustar* o *correlacionar* significados equivalentes.

Este esquema no pretende proporcionarle una guía específica de permisos para Windows o NTFS, sino más bien una comprensión de cómo los permisos de estilo UNIX/Linux comúnmente citados se correlacionan en una máquina con un sistema de archivos NTFS. Los archivos que se colocan en la carpeta raíz www o public_html, o en cualquier directorio al que apunte su sitio (www.dominio.com.au o localhost) en su disco duro deberían ser propiedad de su cuenta de usuario, pero solo si ese usuario no es un usuario considerado privilegiado como *Administrador* en Windows o *root* en UNIX/Linux. Estas cuentas ofrecen demasiado acceso y no deben usarse para el uso diario.

### Mejores prácticas

Las prácticas de seguridad comúnmente utilizadas sugieren que todos los **archivos** deberían tener los siguientes permisos:

* **Propietario:** Lectura y escritura
* **Grupo:** Solo lectura
* **Otros:** Solo lectura

Todos los **directorios/carpetas** deberían tener los siguientes permisos:

* **Propietario:** Lectura, escritura y ejecución
* **Grupo:** Lectura y ejecución
* **Otros:** Lectura y ejecución

Podría decirse que esto no es necesariamente la seguridad *óptima*, pero se debe encontrar un equilibrio entre la seguridad, la funcionalidad y el mantenimiento. Windows, a diferencia de Unix, no mantiene un solo ACL para *Ejecutar*, simplemente proporciona *Lectura y ejecución* combinados, lo que no implica *Escribir*. Sin embargo, el ACL de *Lectura y ejecución* implica *Listar contenido de directorio*. Por lo tanto, si solo tiene permisos de *Lectura y escritura* en un directorio, pero no de *Ejecución*, no podrá ver el contenido del directorio y también puede tener problemas al intentar ejecutar el archivo a través de un navegador web. Se requiere un poco de comprensión de los permisos de UNIX/Linux para correlacionarlos/equivalarlos completamente a los permisos de Windows. La siguiente tabla debería ayudar:

<table data-cellpadding="2" data-cellspacing="0" data-align="center"
data-border="1" width="659">
<thead>
<tr class="odd">
<th style="text-align: center;" data-bgcolor="#cccccc" width="7%"
data-valign="top"><p><strong>Modo Unix</strong></p></th>
<th data-bgcolor="#cccccc" width="10%"
data-valign="top"><p><strong>ACL de Windows</strong></p></th>
<th data-bgcolor="#cccccc" width="33%"
data-valign="top"><p><strong>Comentarios</strong></p></th>
</tr>
</thead>
<tbody>
<tr class="even">
<td style="text-align: center;" width="7%"
data-valign="top"><p><strong>7</strong></p></td>
<td width="10%" data-valign="top"><p><strong>Modificar</strong></p></td>
<td width="33%" data-valign="top"><p><em>Leer, escribir y ejecutar, debería ser el propietario de este archivo</em></p></td>
</tr>
<tr class="odd">
<td style="text-align: center;" width="7%"
data-valign="top"><p><strong>6</strong></p></td>
<td width="10%" data-valign="top"><p><strong>Leer y escribir</strong></p></td>
<td width="33%" data-valign="top"><p><em></em></p></td>
</tr>
<tr class="even">
<td style="text-align: center;" width="7%"
data-valign="top"><p><strong>5</strong></p></td>
<td width="10%" data-valign="top"><p><strong>Leer y ejecutar</strong></p></td>
<td width="33%" data-valign="top"><p><em>usado para la mayoría de las aplicaciones</em></p></td>
</tr>
<tr class="odd">
<td style="text-align: center;" width="7%"
data-valign="top"><p><strong>4</strong></p></td>
<td width="10%" data-valign="top"><p><strong>Solo lectura</strong></p></td>
<td width="33%" data-valign="top"><p><em>la seguridad a través de la oscuridad no es una buena práctica</em></p></td>
</tr>
<tr class="even">
<td style="text-align: center;" width="7%"
data-valign="top"><p><strong>3</strong></p></td>
<td width="10%" data-valign="top"><p><strong>Escribir y ejecutar</strong></p></td>
<td width="33%" data-valign="top"><p><em>no disponible a través de Windows, a menos que se usen permisos "Especiales", no se usa comúnmente</em></p></td>
</tr>
<tr class="odd">
<td style="text-align: center;" width="7%"
data-valign="top"><p><strong>2</strong></p></td>
<td width="10%" data-valign="top"><p><strong>Solo escribir</strong></p></td>
<td width="33%" data-valign="top"><p><em>no disponible a través de Windows, a menos que se usen permisos "Especiales", no se usa comúnmente</em></p></td>
</tr>
<tr class="even">
<td style="text-align: center;" width="7%"
data-valign="top"><p><strong>1</strong></p></td>
<td width="10%" data-valign="top"><p><strong>Solo ejecutar</strong></p></td>
<td width="33%" data-valign="top"><p><em>no disponible a través de Windows, a menos que se usen permisos "Especiales", no se usa comúnmente</em></p></td>
</tr>
</tbody>
</table>

En comparación con los modos Unix, cuando ve algo como 644, descompondría eso en tres elementos:

**6** :  **4** :  **4**

El primer número representa los permisos del **Propietario**, el segundo representa los permisos del **Grupo** y el tercero, los permisos **Otros**. El equivalente en Windows sería:

* **Propietario** (6) : **Leer y Escribir**
* **Grupo** (4) : **Solo Leer**
* **Otros** (4) : **Solo Leer**

Esperemos que este ejemplo proporcione cierta comprensión sobre cómo correlacionar los modos Unix/permisos con los permisos/ACL de Windows. Este documento no incluye temas más complejos como permisos *Efectivos*, *Heredados* o *Especiales*. A pesar de la facilidad de uso de Windows, los mecanismos de permisos y ACL de Microsoft son de hecho razonablemente complejos y muy extensos, pero esto podría brindarle una referencia rápida para tratar de aliviar algo de la confusión en torno a las traducciones de permisos de Unix y Windows.

*Traducido por openai.com*  

