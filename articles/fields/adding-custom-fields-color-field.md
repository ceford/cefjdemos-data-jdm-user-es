<!-- Filename: J3.x:Adding_custom_fields/Color_Field / Display title: Campo de color -->

## Propósito

El campo de Color proporciona un selector para la selección visual de un color. El campo muestra el valor hex resultante.

## Creación de Campo

Opciones especiales para este campo:

- **Clase del Campo** Establecer en *w-auto* para hacer que el campo sea lo suficientemente ancho para la muestra y el valor.

![Creación de campo de color](../../../en/images/fields/fields-colour-edit.png)

**Nota:** En este ejemplo, la inclusión del tipo de campo en el Título es solo para propósitos de demostración. Déjalo fuera en los títulos de tus propios campos.

## Introducción de Datos

Puedes escribir un valor de color hexadecimal si sabes que los números hexadecimales van de 0 a 9 y luego de a a f, y que los pares de números representan rojo, verde y azul. Así, #00ff00 significa sin rojo, máximo verde y sin azul. O puedes usar un cursor para seleccionar un color visualmente. 

![Campo de entrada de color](../../../en/images/fields/fields-colour-data-entry.png)

## Visualización de Datos

La siguiente captura de pantalla del sitio muestra el campo que aparece en un artículo. La opción *Visualización automática* es responsable de la posición del campo y tu plantilla es responsable del diseño del campo.

La visualización de datos predeterminada es el valor de color hexadecimal, que no es de mucha utilidad. La solución fácil es crear una modificación de plantilla para los campos / plugin de color. Simplemente reemplaza esta línea:
```
echo htmlentities($value);
```
con estas líneas:
```
$value = htmlentities($value);
echo '<span style="background-color: ' . $value . ';"> ' . $value . '</span>';
```
Y el valor hexadecimal será precedido por una muestra con el color de fondo del valor.

Busca el ítem **Color de Flor**.

![visualización del campo de color del sitio](../../../en/images/fields/fields-colour-site.png)

