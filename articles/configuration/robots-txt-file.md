<!-- Filename: Robots.txt_file / Display title: El archivo robots.txt  -->

## Acerca de los Robots

Los robots web, también conocidos como rastreadores, exploradores web o arañas, son programas que recorren la web automáticamente. Entre muchos usos, los motores de búsqueda los utilizan para indexar el contenido web.

El archivo robots.txt implementa el [Protocolo de Exclusión de Robots](https://es.wikipedia.org/wiki/Est%C3%A1ndar_de_exclusi%C3%B3n_de_robots), que permite a un administrador del sitio web definir qué partes del sitio no deben ser inspeccionadas por agentes de usuario específicos de robots. Por ejemplo, el acceso al contenido de las páginas públicas normalmente está permitido, pero el acceso a los directorios CGI, privados y temporales que no deben tener páginas indexadas a menudo está prohibido.  

## Dónde colocar el archivo *robots.txt*

Un archivo estándar *robots.txt* está incluido en la raíz de tu Joomla. El archivo *robots.txt* debe residir en la raíz del dominio o subdominio y debe llamarse `robots.txt`.

### Joomla en un subdirectorio

Un archivo robots.txt ubicado en un subdirectorio no es válido. Los robots solo verifican este archivo en la raíz del dominio. Si el sitio Joomla está instalado dentro de un subdirectorio como *example.com/joomla/*, el archivo *robots.txt* **debe** moverse a la raíz del sitio en *example.com/robots.txt*.

**Nota:** En el archivo robots.txt, el nombre del subdirectorio **debe** preceder a cualquier ruta de Joomla no permitida. Por ejemplo, la regla de no permitir para el directorio `/administrator/` **debe** cambiarse a `Disallow: /joomla/administrator/`.

## Contenido de *robots.txt* de Joomla

Este es el contenido de un [archivo estándar robots.txt de Joomla](https://raw.githubusercontent.com/joomla/joomla-cms/refs/heads/5.2-dev/robots.txt.dist):

```
# Si el sitio de Joomla está instalado dentro de una carpeta
# por ejemplo www.ejemplo.com/joomla/ entonces el archivo robots.txt
# DEBE ser movido a la raíz del sitio
# por ejemplo www.ejemplo.com/robots.txt
# Y el nombre de la carpeta de joomla DEBE estar antepuesto a todas
# las rutas.
# por ejemplo, la regla Disallow para la carpeta /administrator/ DEBE
# ser cambiada para leer
# Disallow: /joomla/administrator/
#
# Para más información sobre el estándar robots.txt, ver:
# https://www.robotstxt.org/orig.html

User-agent: *
Disallow: /administrator/
Disallow: /api/
Disallow: /bin/
Disallow: /cache/
Disallow: /cli/
Disallow: /components/
Disallow: /includes/
Disallow: /installation/
Disallow: /language/
Disallow: /layouts/
Disallow: /libraries/
Disallow: /logs/
Disallow: /modules/
Disallow: /plugins/
Disallow: /tmp/
```

## Exclusión de Robots

Puedes excluir directorios o bloquear robots de tu sitio añadiendo una regla de 
Disallow en el archivo *robots.txt*. Por ejemplo, para evitar que cualquier 
robot visite el directorio */tmp*, añade esta regla:

    Disallow: /tmp/

Ver también:

- [Bloquear acceso a tu contenido](https://support.google.com/webmasters/topic/4598466?hl=es&amp;ref_topic=9427949)
  en el Centro de Ayuda de Google.

## Verificación de sintaxis

Para la verificación de sintaxis, puedes utilizar un validador para archivos *robots.txt*. Prueba uno de estos:

- [Prueba tu <em>robots.txt</em> con el Probador de robots.txt](https://support.google.com/webmasters/answer/6062598) de Google.
- [<em>robots.txt</em> Checker](http://www.searchenginepromotionhelp.com/m/robots-text-tester/robots-checker.php) por Search Engine Promotion Help.

### Información General

- [Las Páginas de Web Robots](http://www.robotstxt.org/) es el sitio web principal para *robots.txt*.
- [Un Estándar para la Exclusión de Robots](http://www.robotstxt.org/orig.html) es el estándar original.
- [Especificaciones de la metaetiqueta Robots, data-nosnippet y X-Robots-Tag](https://developers.google.com/search/docs/advanced/robots/robots_meta_tag)

*Traducido por openai.com*

