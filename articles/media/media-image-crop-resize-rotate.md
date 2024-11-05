<!-- Filename: J4.x:Media:_Image_Crop_Resize_Rotate / Display title: Recortar, Redimensionar y Rotar Imágenes  -->

## Introducción

Después de subir una imagen, puede que te hayas dado cuenta de que hay un problema con la imagen cargada. Los problemas comunes incluyen:

- La imagen es demasiado grande.
- La parte interesante de una imagen está en un área pequeña.
- La imagen está rotada 90 grados.

Estos son los problemas que el componente Media puede manejar.

Como ejemplo, la siguiente imagen muestra un grupo de animales que es un poco demasiado grande para su propósito previsto. Podría recortarse o podría cambiarse su tamaño.

![Imagen de animales](../../../en/images/media/media-crop-serengeti.png)

## Recortar

La herramienta de recorte te permite arrastrar para definir un área de recorte. Esto es un poco complicado. Primero, establece una proporción de aspecto o ningún valor, según lo consideres apropiado. Luego, haz clic y arrastra las esquinas, la parte superior o inferior, o cualquiera de los lados del cuadro de selección, que está delineado en azul. Puedes arrastrar el interior del cuadro de selección para moverlo y centrar tu sujeto. También puedes ajustar manualmente los desplazamientos de los ejes X e Y y el ancho y la altura.

Mira detenidamente la captura de pantalla y verás un contorno del cuadro de selección del área que se incluirá en el recorte propuesto.

El selector de calidad indica cuánto compresión debe aplicarse. Demasiada compresión y el tamaño de la imagen en bytes será demasiado grande. Muy poca compresión y la calidad de visualización de la imagen será deficiente. **Advertencia de error:** Por el momento, el control de calidad no está funcionando. Esto resulta en que una imagen modificada sea más grande de lo necesario, ¡a veces mucho más grande que la original!

Cuando estés satisfecho, selecciona el botón *Guardar* en la Barra de herramientas.

La imagen recién recortada se guardará. **¡No hay deshacer!** En la vista de Recortar el cuadro de recorte y los valores en los campos de recorte estarán incorrectos (¿otro error?) pero el recorte estará hecho, así que continúa.  

## Cambiar el tamaño

Para cambiar el tamaño de una imagen, selecciona un ancho adecuado. La altura se ajustará para mantener la relación de aspecto de la imagen original.

## Rotar

Si una imagen se rota 90 grados, selecciona la pestaña Rotar y el ángulo adecuado.

