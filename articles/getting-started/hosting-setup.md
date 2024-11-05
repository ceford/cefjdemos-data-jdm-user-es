<!-- Filename: J4.x:Hosting_Setup / Display title: Configuración de Hosting -->

## Introducción

Esta página ofrece algunas orientaciones para aquellos que son completamente nuevos en la tecnología de alojamiento. Puedes configurar un sitio web en tu propio portátil o computadora de escritorio. Esto se conoce como alojamiento local y es una buena forma de experimentar con nuevas funciones y es completamente gratuito. Para que el contenido de tu sitio web esté disponible para el resto del mundo, necesitarás una cuenta en un servicio de alojamiento y por eso tendrás que pagar.

## Software de Soporte

¡Joomla! es una aplicación que depende de tres elementos de software de soporte: el lenguaje de scripting PHP, una base de datos (una de MySQL, MariaDB o PostgreSQL) y un servidor web (uno de Apache, Nginx, Microsoft IIS, u otros). Los números de versión mínimos se indican en las siguientes tablas:

### Requisitos para Joomla! 5.x

| Software           | Recomendado     | Mínimo      |
|--------------------|-----------------|-------------|
| PHP                | 8.3             | 8.1.0       |
| **Bases de Datos** |                 |             |
| MySQL              | 8.1             | 8.0.13      |
| MariaDB            | 11.1.0          | 10.4.0      |
| PostgreSQL         | 16.0            | 12.0        |
| **Servidores Web** |                 |             |
| Apache             | 2.4             | 2.4         |
| Nginx              | 1.25            | 1.21        |
| Microsoft IIS      | 10              | 10          |

### Requisitos para Joomla! 4.x

| Software           | Recomendado     | Mínimo      |
|--------------------|-----------------|-------------|
| PHP                | 8.2             | 7.2.5       |
| **Bases de Datos** |                 |             |
| MySQL              | 8.0             | 5.6         |
| PostgreSQL         | 11.0            | 11.0        |
| **Servidores Web** |                 |             |
| Apache             | 2.4             | 2.4         |
| Nginx              | 1.18            | 1.10        |
| Microsoft IIS      | 10              | 8           |

## Servicios de Alojamiento

Los servicios de alojamiento comercial proporcionan todo lo necesario para respaldar un sitio web. Algunos también ofrecen instalación con un solo clic de aplicaciones populares como Sistemas de Gestión de Contenidos, Foros, Wikis, etc. Pero ten en cuenta: los expertos del Foro de Joomla no recomiendan usar la instalación con un solo clic de Joomla.

Cada servicio de alojamiento ofrece diferentes planes a distintos niveles de precios. Cuanto más pagues, más espacio en disco y ancho de banda obtendrás, junto con más direcciones de correo electrónico, bases de datos, etc. Algunos también ofrecen un nombre de dominio gratis. En general, tienes que pagar por un nombre de dominio y una pequeña tarifa de registro anual.

## Alojamiento Gratuito

¡No existe el alojamiento gratuito! Sin embargo, un servicio de alojamiento asociado con Joomla ofrece un sitio web Joomla gratuito en el dominio joomla.com. Esto te brinda la oportunidad de probar tu propio sitio web Joomla totalmente funcional sin costo alguno. Es similar a un plan de alojamiento compartido, pero con restricciones y frecuentes solicitudes para actualizar a un plan de pago. Además, el plan gratuito necesita renovarse cada 30 días o será terminado. El siguiente artículo muestra los pasos necesarios para configurar un sitio Joomla gratuito.

* [Alojamiento Joomla Gratuito](jdocmanual?article=user/hosting/free-hosting "")

Si descubres que te gusta Joomla, puedes actualizar a un plan de pago o buscar en otro lugar un servicio de alojamiento que se adapte a tus necesidades y presupuesto.


## Alojamiento Compartido

Puedes obtener un plan de alojamiento mínimo por alrededor de £/$/e50 al año. Este nivel de plan a menudo se conoce como alojamiento compartido y es adecuado para cualquier cosa que no implique datos sensibles. Las empresas deben buscar asesoramiento especializado sobre planes de alojamiento adecuados. Elegir un servicio de alojamiento no está exento de problemas. Los más baratos pueden tener configuraciones de *php.ini* indebidamente restrictivas que no aparecen en su publicidad. Algunos pueden tener una mala reputación en cuanto a soporte.

Si optas por un plan de alojamiento compartido, verifica lo siguiente:

- Soporte para aplicaciones PHP como Joomla, WordPress y Mediawiki.
- Espacio en disco: 500Mb es un mínimo absoluto. 1Gb o más sería mejor si planeas usar muchas imágenes.
- Número de bases de datos: Joomla utiliza una pero pronto descubrirás que necesitas 5 o 10 o más. Algunos planes ofrecen un número ilimitado dentro de la asignación total del espacio en disco.
- Tamaño de la base de datos: con Smart Search, la base de datos puede crecer muy rápidamente. Si el alojamiento compartido tiene una restricción en el tamaño de la base de datos, será importante averiguar cuál es. Puede llevar a que un sitio no funcione.
- Número de direcciones de correo electrónico: ¡suficientes!
- Número de conexiones HTTP y DB al servidor, que algunos alojamientos compartidos limitan.
- Copias de seguridad: cómo se realizan, y si hay un documento de Términos de Servicio (TOS) que indique quién es responsable de las copias de seguridad.

También verifica el panel de control y la plataforma ofrecidos. A juzgar por las publicaciones en el foro, la mayoría usa cPanel en Linux. El servicio de alojamiento debe proporcionar todos los programas básicos de soporte para sitios web:

- Servidor web Apache 2.4+ - *los índices de directorio* deben estar deshabilitados. También se admite:
  - Nginx 1.18+ (menos usuarios, por lo que menos soporte en Foros)
  - Microsoft IIS\[6\] (menos usuarios, por lo que menos soporte en Foros)
- Base de datos MySQLi 8.1+ o clon de MariaDB con soporte InnoDB. También se admite:
  - PostgreSQL 11.0+ (menos usuarios, por lo que menos soporte en Foros).
- Se recomienda PHP 8+.
- Herramienta de gestión de bases de datos phpMyAdmin.

Antes de comprar, verifica los siguientes requisitos mínimos de PHP para Joomla:

- *memory_limit* - Mínimo: 256M
- *upload_max_filesize* - Mínimo: 64M
- *post_max_size* - Mínimo: 64M
- *max_execution_time* - Recomendado: 30
- *allow_url_fopen* - true

Muchos de estos parámetros pueden ser configurados por el usuario en cPanel. Pregunta si eso es posible.

Si has comprado un nombre de dominio, tu servicio de alojamiento lo configurará para ti. También deben proporcionarte una dirección IP para usar hasta que el registro de tu dominio se propague a los Servidores de Nombres de Dominio (DNS), generalmente en unas pocas horas.

El siguiente artículo muestra qué esperar si compras un plan de alojamiento que incluye una interfaz de usuario de cPanel.

* [Alojamiento cPanel](jdocmanual?article=user/hosting/cpanel-hosting "Alojamiento cPanel")

## Alojamiento VPS

Un plan de alojamiento en Servidor Privado Virtual (VPS, por sus siglas en inglés) brinda acceso completo a un servidor que comparte hardware. Se comporta como una computadora dedicada. Puedes detener e iniciar el servidor, reiniciarlo e instalar tu propio software exactamente como lo harías en una computadora de escritorio. Puedes crear cuentas para usuarios individuales tal como en el alojamiento compartido. Normalmente, puedes permitir algunas características que no se permiten en cuentas de alojamiento compartido.

Los planes de alojamiento Dedicado y en la Nube son similares en principio, pero ofrecen recursos dedicados o recursos adaptados a tus necesidades.

Estos planes avanzados no se cubren aquí.

## Alojamiento Local

La mayoría de las personas que desarrollan sitios web mantienen copias locales en una computadora portátil o de escritorio para probar actualizaciones o nuevas extensiones, o para probar nuevos diseños. Configurar un sitio de desarrollo local requiere cierto conocimiento técnico, pero es bastante fácil seguir instrucciones simples.

Los siguientes artículos describen cómo configurar el alojamiento local en diferentes tipos de computadoras de escritorio o portátiles:

* [Alojamiento Local en Windows](jdocmanual?article=user/hosting/local-hosting-on-windows "Alojamiento Local en Windows") solo para Windows
* [Alojamiento Local con XAMPP](jdocmanual?article=user/hosting/local-hosting-with-xampp "Alojamiento Local con XAMPP") para Linux, Mac y Windows.
* [Alojamiento Local en Linux](jdocmanual?article=user/hosting/local-hosting-on-linux "Alojamiento Local en Linux")

