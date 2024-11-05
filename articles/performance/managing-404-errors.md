<!-- Filename: Managing_404_Errors / Display title: Gestión de Errores 404   -->

## Por qué importa el error 404 No Encontrado

El problema más común con los sitios web que están teniendo dificultades en el posicionamiento en los motores de búsqueda es el número de errores de 'no encontrado' – comúnmente referidos como errores *404* porque ese es el código de estado devuelto si la página no se puede encontrar.

Primero, hay razones legítimas para tener errores 404 – si tienes una página para un evento que ya ha pasado, o un servicio que ya no ofreces. En estos casos, eventualmente la página será eliminada del índice de los motores de búsqueda y ya no estará asociada con tu sitio.

El problema ocurre si tienes muchos errores 404 – por ejemplo, si despublicas una categoría que contenía cientos de artículos. Desde la perspectiva del motor de búsqueda, esto no es una gran experiencia para sus visitantes, porque llegan a tu sitio y la información que el motor de búsqueda les dijo que estaba allí, no lo está. Por esto, no es una gran idea tener demasiados errores 404 en tu sitio.

## Google Search Central

El primer paso es averiguar cuántos tienes, lo cual se puede hacer utilizando [Search Central](https://developers.google.com/search) de Google. Este es un conjunto de herramientas gratuitas que te permite analizar tu sitio web y detectar problemas, errores e inconvenientes rápidamente. Se recomienda que registres cada sitio que administras en Search Central para asegurarte de que seas notificado en caso de cualquier problema.

Cuando visitas Search Central, hay una sección que te muestra los Errores de URL en el listado de búsqueda; esto te mostrará una lista de los errores 404 que Google ha encontrado en tu sitio y un gráfico que muestra cómo ha cambiado esto con el tiempo. Si el gráfico comienza a subir, investiga por qué hay páginas que estaban en tu sitio y ahora no se pueden encontrar.

Si hubo un problema temporal en tu sitio, puedes marcar los errores como solucionados.

![herramientas para webmasters](../../../en/images/performance/404-discovery.png)

## Solucionando Problemas

El descubrimiento es solo una parte del proceso. Una vez que hayas descubierto las URLs problemáticas, haz algo al respecto (¡si necesita arreglarse!) redirigiendo la página a otra en el sitio, restableciendo la página original o investigando qué ha causado el error 404.

Si necesitas redirigir una página, puedes usar el plugin Sistema - Redirección para recopilar páginas faltantes y el componente Sistema / Redirecciones para redirigir páginas faltantes a páginas existentes.

## Problemas de Monitoreo

Si deseas monitorear tu tráfico de errores 404, la mejor manera de hacerlo en Analytics es observar qué sucede cuando tienes un error 404. En la mayoría de los casos, el título de la página cambia a 404, por lo que podemos crear un segmento personalizado que filtrará el tráfico con un título de 404 y te dirá cuál es la página de destino. Esto te permitirá monitorear y gestionar proactivamente tus errores 404, asegurándote de que los visitantes de tu sitio no terminen en enlaces rotos.

![Alertas de Analytics para tráfico 404](../../../en/images/performance/404-analytics-alerts.png)

![Visión general de la audiencia en alertas de Analytics](../../../en/images/performance/404-analytics-alerts-2.png)

Google también tiene la capacidad, en Analytics, de configurar alertas. Las alertas te permiten recibir un correo electrónico cuando ocurren ciertos eventos. En este caso, podemos configurar una alerta para ser notificados si hay un aumento de más del 5% en el número de errores 404 en un período semanal, lo que podría significar que tenemos un problema en el sitio web que necesita ser investigado.

¡Esta es una excelente manera de mantener el control de las cosas incluso si no has iniciado sesión para ver tu panel de control!

![Alerta de correo electrónico de Analytics](../../../en/images/performance/404-analytics-alerts-email.png)

## Monitoreo de Errores con un Tablero

También hay un tablero que puedes instalar llamado *Tablero de Integridad de Datos* que te muestra información sobre errores 404, junto con algunas otras métricas que podrían ser de interés. Simplemente busca en la Galería de Google Analytics por *Tablero de Integridad de Datos* y selecciona en qué perfil instalarlo.

![Integridad de datos](../../../en/images/performance/404-data-integrity.png)

