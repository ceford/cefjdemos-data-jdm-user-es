<!-- Filename: Semantic_HTML_Markup / Display title: Etiquetado HTML Semántico -->

## HTML Semántico

### ¿Qué es HTML Semántico?

HTML semántico es una forma de utilizar la codificación HTML para crear
o mejorar la estructura de una página. En otras palabras, es una manera
de utilizar las etiquetas del lenguaje HTML -clases, divs, etiquetas y
demás- para complementar las palabras reales o recursos en una página.
Esto ayuda a los 'robots' y a los visitantes que utilizan lectores de
pantalla para comprender la estructura y el contexto de la información
de la página, junto con su importancia, relevancia, y cómo se relaciona
con otros recursos.

### Cómo utilizar el Etiquetado HTML Semántico

Es importante que tengas una comprensión del HTML Semántico si eres el
desarrollador de sitios web o redactor de contenidos para ellos, ya que
te será necesario utilizar el marcado estructural con regularidad.

Un ejemplo del mal uso de Etiquetado Semántico puede ser encontrado
cuando un artículo ha sido escrito usando texto normal, pero en algún
punto del texto el autor quiere enfatizar una frase en particular. Les
gusta el estilo de la etiqueta H1, de manera que se aplica H1 a esta
frase para 'lograr que se vea bonito'. Por desgracia, esto es confuso
para un motor de búsqueda 'bot' y para los usuarios lectores de
pantalla, porque a ellos se les dice que este es el título principal de
la página - en lugar de subrayarlo o enfatizarlo con negrita.

El etiquetado HTML semántico debe ser usado sólo una vez para añadir
estructura a una página, no para cambiar las forma en que se ve (esto se
hace usando Hojas de Estilo en Cascada (CSS) o con en línea)

### Un ejemplo de Etiquetado HTML Semántico

Por ejemplo, digamos que tenemos el siguiente artículo:

    <h1>Uso de títulos</h1>
    <p>Este es un artículo acerca de la importancia de los títulos</p>

    <h2>¿Por qué utilizar los títulos?</h2>
    <p>Es importante el uso de títulos para que los robots de los motores de búsqueda puedan decir que parte del artículo importante</p>

    <h3>Tipos de títulos</h3>
    <p>Puedes utilizar varios tipos de títulos, pero debes ser ordenado y estructurado, dentro de tu página. H1 debe ser el título de la página, H2 debe ser utilizado para los sub-títulos de la página. Los títulos dentro de su sub-títulos en cascada utilizaran H3, H4 y H5, según corresponda.</p>

    <h2>¿Es difícil de poner en práctica los títulos?</h2>
    <p>Los encabezados son realmente fácil de implementar, sólo tienes que utilizar el código HTML correspondiente</p>

    <h3>El uso de títulos en páginas dinámicas</h3>
    <p>En las páginas dinámicas, simplemente envuelve tu títulos principal dentro de un H1 (por ejemplo, el título de una lista de categorías de la página sería H1), a continuación, envuelve todos los títulos posteriores en H2.</p>

Aquí, un motor de búsqueda 'bot' puede ver claramente la estructura -
h1, h2, h3 - pero si hiciéramos estos títulos en simplemente negrita,
subrayado y en letra de mayor tamaño, sería mucho más difícil
identificar la estructura. También es posible identificar que la palabra
"importante" es una palabra enfatizada, algo que es de mayor valor
dentro de la página.

HTML semántico también es

- Fácil de leer (en el código)
- Más fácil para la accesibilidad a los efectos de los lectores de
  pantalla, que funcionan en forma similar a los robots de los motores
  de búsqueda para identificar títulos importantes
- Potencialmente mejor para la optimización de motores de búsqueda

En el ejemplo de abajo esta página en los resultados de búsqueda de
Google, se puede ver cómo las etiquetas del título están siendo
utilizados por Google para identificar a los enlaces más pequeños dentro
de la página principal que puede ser de interés para la persona que
busca un término (que se muestra en pequeño, de color azul como
hipervínculos de texto debajo de la descripción) - ¡otra razón que nos
asegura que la estructura de su contenido es correcta!

<img src="https://docs.joomla.org/images/5/58/SEF-Titles.png"
decoding="async" data-file-width="532" data-file-height="105"
width="532" height="105" alt="SEF-Titles.png" />

### Microdatos

Los microdatos es una forma más avanzada del Etiquetado HTML Semántico,
que te permite dar más información contextual sobre el contenido y la
estructura de tu sitio web. Para obtener más información, consulta :
Microdatos.

<a href="http://es.wikipedia.org/wiki/HTML_sem%C3%A1ntico" class="extiw"
title="es.wp:HTML semántico">HTML Semántico</a>
