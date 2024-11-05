<!-- Filename: J4.x:Article_Lists / Display title: Artículo: Editar - Listas  -->

## Tipos de listas

HTML tiene tres tipos de listas:

- Las listas desordenadas a menudo se representan con una sangría y un viñeta,
  como esta lista.
- Las listas ordenadas son similares pero marcadas con números.
- Las listas de definiciones consisten en Títulos y Definiciones.

Los viñetas y números son aplicados por el navegador a partir de una
selección de estilos. El usuario no debe ingresar ningún texto de viñeta o número,
ya que esto se tratará como parte de la lista. El editor TinyMCE tiene
iconos para aplicar estilos comunes de viñetas y tipos de números. Las listas
de definiciones son más complicadas y necesitan ser elaboradas a mano.

Las listas pueden contener otras listas en cualquier nivel, aunque las listas
profundamente endentadas se vuelven difíciles de leer, por lo que es mejor apegarse a uno o
dos niveles.

## Captura de Pantalla

La siguiente captura de pantalla muestra una lista desordenada con dos niveles de sangría. También muestra el conjunto completo de herramientas, que se abre al seleccionar el botón de elipsis (...) al final de la primera fila de iconos de herramientas.

![Listas desordenadas anidadas](../../../en/images/articles/articles-edit-lists.png)

Esta captura de pantalla se utilizará para explicar cómo se creó la lista con viñetas utilizando las herramientas *Lista con viñetas* y *Aumentar sangría* o *Disminuir sangría*:

## Estilos de listas

### Listas con viñetas

Hay tres estilos disponibles:

- Un círculo relleno es el predeterminado.
- Un círculo abierto.
- Un cuadrado relleno.

El cheurón hacia abajo a la derecha del icono de lista con viñetas abre un pequeño panel que permite seleccionar el estilo preferido para un elemento de la lista seleccionado:

![Herramientas para manipular listas con viñetas](../../../en/images/articles/articles-edit-list-bullets.png)

El icono de lista actúa como un interruptor. Si el cursor está en un párrafo y se selecciona una viñeta, el párrafo se convierte en un elemento de lista. Si se selecciona la viñeta nuevamente, el elemento de lista vuelve a ser un párrafo.

Si se seleccionan dos o más párrafos y se selecciona un icono de lista, cada uno de los párrafos se convierte en un elemento de lista. Para hacer una lista con sangría, seleccione la herramienta *Aumentar sangría* a la derecha de las herramientas de Lista. Por defecto, el elemento de lista con sangría adoptará el siguiente estilo de lista.

Entonces, para explicar cómo crear las listas con sangría en la captura de pantalla:

- Escriba cada uno de los términos como párrafos de una sola palabra.
- Seleccione todos los párrafos para convertirlos en una lista con viñetas.
- Seleccione el icono *Lista con viñetas*.
- Seleccione el primer grupo de términos para ser indentados.
- Seleccione el icono *Aumentar sangría*.
- Seleccione el segundo grupo de términos para ser indentados.
- Seleccione el icono *Aumentar sangría*.

### Listas numeradas

Hay seis estilos disponibles

- Números: 1, 2, 3 ...
- Letras: a, b, c ...
- Caracteres griegos: &alpha;, &beta;, &gamma; ...
- Números romanos en minúsculas: i, ii, iii ...
- Letras mayúsculas: A, B, C ...
- Números romanos en mayúsculas: I, II, III ...

![Herramientas para manipular listas numeradas](../../../en/images/articles/articles-edit-list-numbers.png)

Las listas numeradas funcionan de manera un poco diferente. Cuando un elemento de la lista tiene sangría, toma el primer valor numérico y los números en el resto de la lista suben, de modo que la lista siempre esté en el orden numérico correcto.

### Listas mixtas

El sistema de numeración puede cambiar en cada nivel. Por ejemplo, podría configurar el primer nivel para usar valores numéricos y el segundo nivel para usar viñetas, o caracteres griegos, o cualquier otra cosa.

Probablemente sea mejor experimentar con listas para ver cómo se pueden manipular.

## Listas de definiciones

Las listas de definiciones consisten en un *Título de definición* y una o más *Descripciones de definición*, seguidas por el siguiente *Título de definición* y su *Descripción*. Serían adecuadas para un *Glosario* o cualquier tipo de conjunto de pares Clave/Valor. Para crear una lista de definiciones:

- Seleccione el botón *Toggle Editor* para ver el marcado del artículo en HTML.
- Escriba la marca de Lista de Definiciones. Aquí hay un ejemplo:
```html
<dl>
<dt>Anfibio</dt>
<dd>Vertebrado de sangre fría que pone huevos en el agua y tiene una etapa larval acuática.</dd>
<dt>Reptil</dt>
<dd>Vertebrado de sangre fría que pone huevos en tierra.</dd>
</dl>
```
Guarde y vea el resultado en la Vista Previa.

*Traducido por openai.com*

