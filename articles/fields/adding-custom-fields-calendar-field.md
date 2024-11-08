<!-- Filename: J3.x:Adding_custom_fields/Calendar_Field / Display title: Campo del Calendario -->

## Propósito

El campo de Calendario ofrece una caja de texto para introducir una fecha. Un ícono al lado de la caja de texto invoca un selector de calendario emergente, que puede usarse para seleccionar una fecha de un calendario gráfico.

## Creación de Campo

Los parámetros comunes de los campos se describen en un artículo separado.

* **Título** Puede tener varios campos de fecha en un artículo, por lo que se necesita cuidado al establecer el título para evitar ambigüedades en el resultado.
* **Etiqueta** Esto es lo que se muestra en el resultado. Si se deja vacío, se establece a partir del contenido del campo Título, pero se puede cambiar.
* **Mostrar Hora** Si se establece en *Sí*, la hora se agrega al campo de fecha, al selector de fecha y a la fecha de salida. **Precaución**: Incluso si no especifica la hora en la fecha predeterminada, la hora se muestra cuando la opción *Mostrar hora* está activa.
* **Marcador de Posición** Esto se encuentra en la pestaña Opciones. Se puede establecer en un formato de fecha como *AAAA-MM-DD* para recordar a los usuarios el formato requerido y/o un recordatorio de para qué es la fecha, como *Fecha de llegada*.

![creación de campo de calendario](../../../en/images/fields/fields-calendar-edit.png)

**Nota:** En este ejemplo, la inclusión del tipo de campo en el Título es solo para fines de demostración. Déjelo fuera en los títulos de sus propios campos.


## Entrada de Datos

El uso del campo de calendario es sencillo. Puedes escribir la fecha en el formato requerido o seleccionar una fecha usando el selector de fecha. Se necesita cuidado al escribir las fechas. Un error en la fecha se corrige al guardar a una nueva fecha. Por ejemplo, una fecha de 2024-14-02 se corrige a 2025-02-02.

La siguiente captura de pantalla muestra una fecha de Adquisición:

![entrada de datos en campo de calendario](../../../en/images/fields/fields-calendar-data-entry.png)

Los campos solo aparecen en un artículo si se completan en el formulario de entrada de datos del artículo.


## Visualización de Datos

La siguiente captura de pantalla del sitio muestra el campo que se visualiza en un artículo. La opción *Visualización automática* es responsable de la posición del campo y tu plantilla es responsable del diseño del campo.

![visualización del campo del calendario en el sitio](../../../en/images/fields/fields-calendar-site.png)

Los formatos de fecha se localizan utilizando cadenas de idioma.

*Traducido por openai.com*

