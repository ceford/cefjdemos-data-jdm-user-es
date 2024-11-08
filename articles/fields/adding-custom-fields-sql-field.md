<!-- Filename: J3.x:Adding_custom_fields/Sql_Field / Display title: Campo SQL -->

## Propósito

El campo SQL proporciona una lista desplegable de entradas obtenidas de una consulta a la base de datos. Para usar este campo, necesitas saber cómo construir una consulta y deberías probarla en phpMyAdmin.


## Creación de Campo

Las opciones especiales dentro de este campo son:

- **Múltiple** Permitir seleccionar múltiples valores. Si se configura en *Sí*, la lista
muestra 4 elementos. De lo contrario, muestra 1 elemento. En cualquier caso, hay una larga
lista para desplazarse y hacer selecciones si está activado.
- **Consulta** La consulta SQL que proporcionará los datos para la lista desplegable.
La consulta debe devolver dos columnas; una llamada 'value' que contendrá los
valores de los elementos de la lista; y otra llamada 'text' que contendrá el texto
en la lista desplegable.

En este ejemplo se utiliza una tabla que contiene una lista de nombres de países. Esta es
la consulta:
```
SELECT `id` AS value, `title` AS text
FROM `#__countrybase_countries`
WHERE `state` = 1
ORDER BY `title` ASC
```
![Creación de Campo SQL](../../../en/images/fields/fields-sql-edit.png)

**Nota:** En este ejemplo, la inclusión del tipo de campo en el Título es solo para
fines de demostración. Omítalo en los títulos de sus propios campos.

## Ingreso de Datos

Simple - selecciona de la lista.

![Entrada de datos de campo SQL](../../../en/images/fields/fields-sql-data-entry.png)


## Visualización de Datos

La siguiente captura de pantalla del Sitio muestra el campo mostrado en un artículo. La opción *Visualización automática* es responsable de la posición del campo y tu plantilla es responsable del diseño del campo.

![Visualización del campo SQL del sitio](../../../en/images/fields/fields-sql-site.png)

La salida es un único elemento o una lista de elementos separados por comas (nombres de países) siguiendo la etiqueta del Campo (País de Origen).

*Traducido por openai.com*  

