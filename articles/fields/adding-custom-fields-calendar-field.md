<!-- Filename: J3.x:Adding_custom_fields/Calendar_Field / Display title: Campo de Calendario -->

## Propósito

El campo de Calendario proporciona un cuadro de texto para ingresar una fecha. Un ícono al lado del cuadro de texto invoca un selector de calendario emergente, que se puede usar para seleccionar una fecha de un calendario gráfico.

## Creación de Campos

Los parámetros comunes de campo se describen en un artículo separado.

* **Título** Puedes tener varios campos de fecha en un artículo, por lo que se debe tener cuidado al establecer el título para evitar ambigüedades en el resultado.
* **Etiqueta** Esto es lo que se muestra en el resultado. Si se deja vacío, se establece a partir del contenido del campo de Título, pero se puede cambiar.
* **Mostrar Hora** Si se establece en *Sí*, se añade la hora al campo de fecha, al selector de fecha y a la fecha de salida. **Precaución**: Incluso si no especificas la hora en la fecha predeterminada, la hora se muestra cuando la opción *Mostrar hora* está activa.
* **Espacio Reservado** Se puede establecer en un formato de fecha como *AAAA-MM-DD* para recordar a los usuarios el formato requerido y/o un recordatorio del propósito de la fecha, como *Fecha de llegada*.

## Entrada de datos

El uso del campo de Calendario es sencillo. Puedes escribir la fecha en el formato requerido o seleccionar una fecha usando el selector de fechas. Se necesita cuidado al escribir las fechas. Un error en la fecha se corrige al guardar con una nueva fecha. Por ejemplo, una fecha de 2024-14-02 se corrige a 2025-02-02.

La siguiente captura de pantalla muestra una fecha de adquisición:

![entrada de fecha de adquisición](../../../en/images/fields/fields-date-entry.png "Fecha de adquisición")

Los campos solo aparecen en un artículo si se han completado en el formulario de ingreso de datos del artículo.


## Visualización de Datos

La siguiente captura de pantalla del sitio muestra el campo mostrado en un artículo. La opción *Visualización automática* es responsable de la posición del campo y tu plantilla es responsable del diseño del campo.

Busca el elemento **Fecha de Adquisición**.

![Visualización de todos los campos](../../../en/images/fields/fields-display.png "Visualización de campos")

Los formatos de fecha están localizados utilizando cadenas de idioma.

*Traducido por openai.com*

