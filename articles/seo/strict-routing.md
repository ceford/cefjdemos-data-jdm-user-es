<!-- Filename: J5.x:Improving_SEO_with_Strict_Routing_and_SEF_URLs / Display title: Enrutamiento Estricto SEO -->

## Introducción

La opción de Enrutamiento Estricto, introducida en Joomla 5.2, mejora el rendimiento SEO de la plataforma al permitir reglas de enrutamiento más estrictas mediante un interruptor en el plugin *System - SEF*. Ayuda a eliminar contenido duplicado al imponer URLs más consistentes y redirigir los duplicados a la URL correcta con una redirección 301.

![system sef plugin settings](../../../en/images/seo/seo-system-sef-plugin.png)

### Imponiendo Sufijos

Actualmente, Joomla permite el acceso a las URL con o sin un sufijo cuando esta opción está habilitada en las opciones de *Configuración Global*.

La opción **Imponer un sufijo mediante redirección** en el complemento *System - SEF* impone un comportamiento de sufijo consistente. Cuando está habilitada, redirige las solicitudes GET a una URL con un sufijo si falta. También redirigirá las URLs con un parámetro de formato de consulta a la URL más limpia, reemplazando el sufijo con el parámetro de formato donde sea necesario.

Se espera que esta característica se convierta en el comportamiento predeterminado en Joomla 6.0, donde se eliminará la opción para habilitar o deshabilitarla, y esta funcionalidad se integrará en el sistema de enrutamiento principal. Por ahora, esta opción permite a los usuarios probar el comportamiento en sistemas en vivo y desactivarla si surgen problemas imprevistos durante el período de transición de Joomla 5.1 a 6.0.

## Cómo acceder

Para habilitar el enrutamiento estricto para SEO:

1. Selecciona el elemento **Plugins** en el *Tablero de Inicio*.
2. Busca y abre el plugin **System - SEF**.
3. Establece **Strict Routing** en *Sí* para habilitar un manejo de URL más estricto.
4. Define **Aplicar un Sufijo por Redirección** en Sí o No, dependiendo de tu preferencia para aplicar sufijos de URL.

Una vez habilitado, Joomla redirigirá automáticamente las URLs duplicadas a la correcta con una redirección 301, mejorando el SEO al consolidar el contenido bajo una sola URL autorizada.

## Notas adicionales

Esta característica está diseñada para funcionar como un paso preparatorio para futuras mejoras de SEO y se habilita automáticamente para nuevas instalaciones de Joomla 5.2. Establece las bases para futuras mejoras en el sistema de rutas de Joomla. 
*Traducido por openai.com*

