<!-- Filename: J3.x:Adding_custom_fields/Sql_Field / Display title: Campo SQL -->

## Propósito

El campo SQL proporciona una lista desplegable de entradas obtenidas de una consulta a la base de datos. Para usar este campo, necesitas saber cómo construir una consulta y deberías probarla en phpMyAdmin.

## Creación de Campo

Las opciones especiales dentro de este campo son:

- **Múltiple** Permitir seleccionar múltiples valores. Si se establece en *Sí*, la lista muestra 4 elementos. De lo contrario, muestra 1 elemento. En cualquier caso, hay una larga lista para desplazarse y hacer selecciones, si está activada.
- **Consulta** La consulta SQL que proporcionará los datos para la lista desplegable. La consulta debe devolver dos columnas; una llamada 'value' que contendrá los valores de los elementos de la lista; y la otra llamada 'text' que contendrá el texto en la lista desplegable.

En este ejemplo, se utiliza una tabla que contiene una lista de nombres de países. Esta es la consulta:
```
SELECT `id` AS value, `title` AS text
FROM `#__countrybase_countries`
WHERE `state` = 1
ORDER BY `title` ASC
```
![Campo SQL](../../../en/images/fields/fields-sql.png "Campo SQL")

## Ingreso de Datos

Simple - selecciona de la lista.


## Visualización de Datos

La siguiente captura de pantalla del sitio muestra el campo mostrado en un artículo. La opción *Visualización automática* es responsable de la posición del campo y tu plantilla es responsable del diseño del campo.

Busca el ítem **País de Origen**.

![Visualización de todos los campos](../../../en/images/fields/fields-display.png "Visualización de campos")

La salida es un único elemento o una lista de elementos separados por comas (nombres de países) siguiendo la etiqueta del campo (País de Origen).

*Traducido por openai.com*

