<!-- Filename: jdocmanual?manual=user&heading=extensions&filename=vulnerable-extensions.md / Display title: Extensiones Vulnerables  -->

## Fuentes de extensiones

Cualquiera puede escribir y distribuir una extensión de Joomla! como un servicio para la comunidad global. Se pueden encontrar estas extensiones de **terceros** en sitios web de desarrolladores de extensiones profesionales, blogs personales, GitHub y repositorios similares, así como en el sitio web del Directorio de Extensiones de Joomla.

## Extensiones Vulnerables

Muy pocas fuentes ofrecen extensiones deliberadamente maliciosas. Generalmente, una **extensión vulnerable** es aquella que se ha encontrado que contiene (o contribuye a) una vulnerabilidad de seguridad después de su lanzamiento inicial.

Las extensiones vulnerables no son necesariamente mal codificadas. A medida que la web evoluciona, los requisitos técnicos y las prácticas de codificación comúnmente aceptadas cambian. Los proyectos activos lanzan nuevas versiones de sus extensiones a medida que cambian los requisitos y solucionan rápidamente cualquier vulnerabilidad reportada.

Si te preocupa alguna de tus extensiones, deberías consultar la lista de Extensiones Vulnerables de Joomla (VEL) que contiene información sobre más de 240 extensiones, en su mayoría antiguas. 

## El Verificador JED

Si te preocupa una extensión que no aparece en el VEL, puedes usar la extensión JED Checker. Esta es una extensión utilizada para verificar las extensiones enviadas para aparecer en la lista del Directorio de Extensiones Joomla. Se instala como cualquier otra extensión. En uso, acepta un archivo zip de extensión y examina su contenido para asegurar el cumplimiento con los estándares de JED. Es extremadamente útil incluso para extensiones que no aparecen en la lista de JED. Aquí hay un ejemplo de captura de pantalla:

![resultado del verificador jed](../../../en/images/extensions/extensions-jed-checker.png)

Los 400 archivos PHP que carecen del Aviso de Licencia GPL están en bibliotecas de terceros con una licencia diferente. Los 30 archivos identificados por el Script de Análisis Anti-Malware de Joomla también están en esas bibliotecas de terceros. ¡Hay trabajo por hacer en los archivos que carecen de seguridad JEXEC!

## Eliminación de una Extensión Vulnerable

### Hacer una Lista de Archivos a Eliminar

Si puedes localizarlo, lee el archivo XML de la extensión para determinar exactamente qué directorios, archivos y tablas de la base de datos se agregaron a tu sistema. El archivo XML está en el archivo zip original utilizado durante el proceso de instalación de la extensión. Por ejemplo, el archivo zip de una extensión llamada mod_vulnerable, contendría un archivo XML llamado mod_vulnerable.xml, y podría contener una lista de archivos como la siguiente:

```
    mod_vulnerable.php
    mod_vulnerable/vulnerable_file.txt
    mod_vulnerable/another_vulnerable_file.txt
    mod_vulnerable/yet_another_vulnerable_file.txt
    mod_vulnerable/index.html
```

### Desinstalar a través del Instalador de Joomla

Usando el instalador en la parte administrativa de Joomla!, desinstala la extensión vulnerable. También puede ser necesario desinstalar módulos, componentes o plugins relacionados.

### Verificar que el Proceso de Desinstalación fue Completo

No confíes en que la extensión eliminará de manera segura todos sus archivos. Compara directorios y archivos en tu sistema con la lista XML de la extensión para asegurarte de que se eliminaron todos los archivos relacionados.

### Opcionalmente, Eliminar las Tablas de la Base de Datos Relacionadas

Revisa tu base de datos y elimina cualquier tabla creada por la extensión. Para facilitar el proceso de actualización a nuevas versiones, muchos scripts de desinstalación no eliminan las tablas de la base de datos relacionadas. Puedes encontrar la lista de tablas en el archivo XML de cada extensión.

Si planeas instalar una versión más segura y compatible de la misma extensión y deseas reutilizar los datos existentes, generalmente puedes dejar las tablas de la base de datos tal como están.

### Eliminar Enlaces del Menú

¡Simplemente eliminar los enlaces del menú hacia una extensión o despublicar un módulo **no** es suficiente para proteger tu sitio! Siempre que los archivos de la extensión existan en tu servidor, eres vulnerable. Nota cómo en los siguientes ejemplos un atacante puede evitar el archivo índice de Joomla! para dirigirse directamente a cualquier archivo, de cualquier extensión.

```
    www.your_site.org/components/com_bad_component/vulnerable_file.php
    www.your_site.org/modules/mod_bad_module/vulnerable_file.php
```

*Traducido por openai.com*

