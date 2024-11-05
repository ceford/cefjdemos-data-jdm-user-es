<!-- Filename: J3.x:Adding_custom_fields/Color_Field / Display title: Campo de Color -->

## Propósito

El campo de Color proporciona un selector para la selección visual de un color. El campo muestra el valor hexadecimal resultante.

## Creación de Campo

Opciones especiales para este campo:

- **Clase de Campo** Establecer en *w-auto* para hacer que el campo sea lo suficientemente ancho para la muestra y el valor.


## Entrada de Datos

Puedes escribir un valor de color hex si sabes que los números hexadecimales van del 0 al 9 y luego de la a a la f, y los pares de números son rojo, verde y azul. Así que #00ff00 es sin rojo, verde al máximo y sin azul. O puedes usar un cursor para seleccionar un color visualmente.

![Selector de color](../../../en/images/fields/fields-colour-entry.png "Selector de color")

## Visualización de Datos

La siguiente captura de pantalla del sitio muestra el campo mostrado en un artículo. La opción *Visualización automática* es responsable de la posición del campo y tu plantilla es responsable del diseño del campo.

La visualización de datos predeterminada es el valor del color en formato hexadecimal, lo cual no es muy útil. La solución sencilla es crear una anulación de plantilla para los campos / plugin de color. Simplemente reemplaza esta línea:
```
echo htmlentities($value);
```
por estas líneas:
```
$value = htmlentities($value);
echo '<span style="background-color: ' . $value . ';"> ' . $value . '</span>';
```
Y el valor hexadecimal será precedido por una muestra con el color de fondo del valor.

Busca el elemento **Color de la Flor**.

![Visualización de todos los campos](../../../en/images/fields/fields-display.png "Visualización de Campos")

