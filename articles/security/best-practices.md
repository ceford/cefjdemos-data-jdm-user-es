<!-- Filename: https://magazine.joomla.org/all-issues/april-2021/best-practices-to-secure-your-joomla-website / Display title: Mejores Prácticas  -->

## Artículos de Seguridad

Hay una cantidad significativa de artículos disponibles sobre la seguridad de Joomla que se remontan a muchos años atrás. Desafortunadamente, muchos de ellos están desactualizados y quizás puedan ser engañosos. Por ejemplo, hay una serie de artículos de Lista de Verificación de Seguridad, no todos los cuales tratan realmente sobre seguridad.

Este artículo está basado en un artículo de la Revista de la Comunidad de Joomla! por Ahmad Moussa en la Edición de abril de 2021.

## Mejores Prácticas para Proteger tu Sitio Web Joomla

El sistema de gestión de contenido Joomla (CMS, por sus siglas en inglés) es muy utilizado en internet debido a su facilidad de uso y popularidad, siendo el segundo CMS más descargado con más de 110 millones de descargas. Pero, aunque es muy popular, Joomla y todos los demás sitios web, aplicaciones, sitios de comercio electrónico u otros CMS contienen riesgos de seguridad. No puedes evitarlos, pero afortunadamente, tomar las precauciones correctas desde el principio puede asegurar que tu sitio esté protegido.

Hemos recopilado esta guía completa y paso a paso sobre la seguridad de Joomla para ti. Pretende ofrecer pasos fáciles de seguir para mejorar la seguridad de tu sitio web Joomla. Así que, si asegurar tu sitio web Joomla de todos los ataques es parte de tu agenda, entonces dale una leída. Todos los consejos mencionados en este artículo están destinados a asegurarte de que estás implementando las mejores prácticas de seguridad y mantenimiento para proteger tus activos más importantes en línea.

## 1. Elija Nombres de Usuario y Contraseñas Inteligentes

Sea inteligente al elegir los nombres de usuario y contraseñas de administrador de Joomla. No use "admin" como su nombre de usuario y elija una contraseña compleja. Esta es probablemente una de las mejores maneras de fortalecer la seguridad de Joomla y, paradójicamente, es una de las más fáciles.

Usar una contraseña segura es necesario para una buena seguridad de Joomla. Asegúrese de que su contraseña de inicio de sesión sea lo suficientemente larga (8-14 caracteres) e incluya letras, números y símbolos. Dado que las contraseñas distinguen entre mayúsculas y minúsculas, usar tanto letras mayúsculas como minúsculas la hace aún más fuerte. Además, haga el hábito de cambiar las contraseñas de administrador al menos una vez al mes.

## 2. Practicar el Principio de Menor Privilegio

Asegúrate de entender los tres grupos distintos de permisos:

1. Gerentes: Tienen el menor acceso al backend de Joomla. Pueden crear y editar categorías y artículos. Tienen acceso al gestor de medios y pueden subir y eliminar medios. No pueden instalar ni eliminar extensiones.
2. Administradores: Tienen todos los derechos de los Gerentes, junto con algunos permisos adicionales. Tienen acceso a la Gestión de Usuarios, al Gestor de Menús y al Gestor de Extensiones. No pueden acceder al menú de Configuración Global de Joomla.
3. Super Usuarios: Tienen acceso completo al Backend de Joomla. Tienen todos los derechos de los Gerentes y Administradores, junto con acceso a la Configuración Global. Solo los Super Usuarios pueden agregar, editar y eliminar Super Usuarios.

Es importante que distribuyas estos roles cuidadosamente entre tu grupo de usuarios. Cualquier persona con el rol de Super Usuario puede realizar cualquier acción dentro del sistema Joomla. Si delegas tareas a un miembro del equipo que requiere menos permisos, asigna a la cuenta del miembro con la descripción de acceso mínimo.

## 3. Usar la Autenticación Multifactor de Joomla

Se recomienda encarecidamente habilitar la autenticación multifactor de Joomla, que añade una capa adicional de seguridad a tu sitio web de Joomla. Tradicionalmente, cuando deseas iniciar sesión en tu sitio web, debes proporcionar tu nombre de usuario y contraseña para identificarte en el sistema. El mayor problema de este enfoque es que tu nombre de usuario y contraseña pueden ser robados o adivinados. Por lo tanto, los complementos de autenticación multifactor de Joomla pueden proteger tu sitio web de los hackers al añadir una segunda capa de seguridad. Hay cinco métodos diferentes que puedes elegir después de ingresar tu nombre de usuario.

## 4. Restringir el Acceso al Backend de Administración de Joomla

Es prudente limitar el acceso al backend de administración de Joomla utilizando filtrado de IP, ya que es un recurso sensible. Esto también se puede hacer para otras carpetas sensibles de Joomla siguiendo los pasos mencionados a continuación:

Paso 1: En primer lugar, crea un archivo .htaccess si no está ya presente en el directorio que deseas proteger.

Paso 2: Añade el siguiente código al archivo .htaccess:
```
Order Deny, Allow
Deny from all
Allow from xx.xx.xx.xx
```

Paso 3: Ingresa la dirección IP dedicada desde la cual deseas permitir el acceso en lugar de xx.xx.xx.xx.

Puedes encontrar más información sobre cómo restringir el acceso a directorios por dirección IP utilizando htaccess en este artículo de la Documentación de Joomla. También puedes usar extensiones de seguridad que permitan restringir el acceso al backend de administración de Joomla mediante la función de filtrado de IP e incluyen muchas otras características que fortalecen la seguridad de tu sitio web Joomla.

## 5. Usar Conexiones FTP Seguras

Asegúrate de que las conexiones utilizadas para acceder a los archivos de tu sitio web Joomla estén aseguradas. Deberías usar cifrado SFTP si tu alojamiento lo proporciona, o SSH. Si estás usando un cliente FTP, entonces el puerto predeterminado para SFTP suele ser el 22.

Algunos clientes FTP almacenan contraseñas en texto plano o codificadas en tu computadora. Incluso algunas contraseñas codificadas se pueden convertir de nuevo a su original. Recomendamos encarecidamente no guardar las contraseñas de FTP en el cliente para evitar ser hackeado.

## 6. Realiza Copias de Seguridad Regulares

Ahorra tiempo preparándote para el peor escenario en caso de que tu sitio web sea atacado. Por lo tanto, se aconseja crear una copia de seguridad completa y funcional de tu sitio web Joomla. Una copia de seguridad funcional puede restaurar tu sitio web en minutos después de un ataque cibernético.

Los dos componentes principales de una copia de seguridad son:

- Joomla Core y otros archivos importantes
- La base de datos

Además, los métodos para realizar copias de seguridad pueden ser flexibles. Puedes realizar una copia de seguridad de dos maneras, Manual y Automatizada, como se describe a continuación:

### Proceso Manual

La copia de seguridad manual del sitio Joomla necesita dos componentes: los archivos y la base de datos. Para respaldar tus archivos y carpetas de Joomla, utiliza un programa FTP o el administrador de archivos en caso de que uses un hosting de terceros.

Los clientes FTP pueden descargar todos los archivos uno por uno a tu computadora local. Sin embargo, este proceso puede ser lento. Una vez que los archivos se han descargado, comprime la carpeta en un solo archivo zip y protégelo con una contraseña.

Mientras que la base de datos puede ser respaldada exportando una copia de la base de datos a tu computadora. Inicia sesión en la base de datos que deseas exportar usando phpMyAdmin. Haz clic en el nombre de la base de datos en el lado izquierdo de la página. Una vez que hayas hecho clic en tu base de datos de Joomla, deberías llegar a una pantalla que tiene una pestaña etiquetada como "Exportar". Selecciona la pestaña de Exportar y luego haz clic en el botón etiquetado como "Ir". Luego guárdalo en un lugar seguro.

### Proceso Automatizado

Para una copia de seguridad automatizada, una extensión de Joomla como Akeeba Backup puede ayudar. Instala la extensión Akeeba Backup en tu sitio web Joomla después de descargarla del sitio oficial del desarrollador. Una vez que la instalación esté completa, accede al Panel de la extensión y haz una copia de seguridad de tu sitio. Cuando la copia de seguridad esté completa, serás redirigido a una página. Aquí, haz clic en "Gestionar Copias de Seguridad". Esto abrirá una página que contiene todas las copias de seguridad. Puedes descargar la copia de seguridad desde aquí y guardarla localmente.

## 7. Mantén Actualizado tu Sitio Web de Joomla

Actualizar tu sitio web de Joomla puede proporcionar seguridad y estabilidad al sitio. Además, no todas las actualizaciones son de versión completa del sitio; algunas actualizaciones pueden ser menores y son simplemente correcciones de errores, mientras que otras son actualizaciones de versión.

Joomla tiene un equipo de seguridad dedicado que es conocido por publicar parches rápidamente. No aplicar parches a tu sitio de Joomla puede hacerlo vulnerable a ataques.

Para comprobar si hay actualizaciones en tu sitio, puedes hacer lo siguiente:

Paso 1: Inicia sesión en tu sitio de Joomla como administrador

Paso 2: A continuación, navega a Componentes>Actualización de Joomla

Paso 3: Ahora, Joomla verificará si hay alguna nueva actualización disponible. Si muestra una nueva actualización, simplemente haz clic en la opción “Instalar la Actualización”.

Antes de actualizar a una versión más reciente de Joomla, se deben revisar ciertas cosas:

- Actualización de Plantillas: Verifica si tus plantillas de Joomla son compatibles con la versión más reciente de Joomla. Si no lo son, pide al autor de la plantilla que la actualice o usa una alternativa.
- Actualización de Extensiones: Inspecciona y asegúrate de que todas las extensiones de Joomla sean compatibles con la nueva versión de Joomla. Elimina todas aquellas que no sean compatibles. Para actualizar las extensiones, navega a Extensiones>Gestionar y haz clic en actualizar.
- Limpiar Caché: Después de actualizar a una versión más reciente de Joomla, limpia el caché de tu sitio de Joomla. Esto se puede hacer utilizando la funcionalidad incorporada de Joomla.

## 8. Usa Extensiones y Plantillas de Terceros Confiables:

Se recomienda usar un número mínimo de extensiones en tu sitio web para obtener el nivel óptimo de seguridad en Joomla. Usar extensiones o plantillas de terceros no confiables puede introducir vulnerabilidades y afectar el rendimiento de tu sitio web Joomla. No todas las extensiones de terceros están libres de problemas; si tienes la posibilidad de evitar una extensión de terceros, ¡hazlo! Elige y utiliza extensiones y plantillas profesionales de empresas de buena reputación, y mantenlas actualizadas para proteger tu sitio web.

## 9. Actualizar la versión de PHP de tu sitio web de Joomla

Protege tu sitio web de una variedad de ataques de hacking y fortalece la seguridad de tu sitio Joomla actualizando la versión de PHP de tu sitio a la última versión estable. Asegúrate de seleccionar una versión de PHP que sea compatible con tus plantillas y extensiones de Joomla para evitar problemas en tu sitio. Hay varias formas de actualizar tu versión de PHP. Las principales se cubren en un artículo de la edición de septiembre de 2020 de la Joomla Community Magazine: ¿Cómo actualizo mi versión de PHP?.

## 10. Fortalecer los Encabezados de Seguridad HTTP

Se recomienda encarecidamente implementar o actualizar los encabezados de seguridad HTTP, ya que proporcionan una capa de seguridad para tu sitio Joomla al ayudar a mitigar ataques y vulnerabilidades de seguridad. Por lo general, solo requieren un pequeño cambio de configuración en tu servidor web. Estos encabezados indican a tu navegador cómo comportarse al manejar el contenido de tu sitio. A continuación se muestran seis encabezados de seguridad HTTP comunes que deben revisarse:

- Política de Seguridad de Contenidos (Content-Security Policy)
- Protección X-XSS (X-XSS-Protection)
- Seguridad de Transporte Estricta (Strict-Transport-Security)
- Opciones X-Frame (X-Frame-Options)
- Pines de Clave Pública (Public-Key-Pins)
- Tipo de Contenido X (X-Content-Type)

## 11. Usa una Extensión de Seguridad para Joomla

Es necesario limitar los intentos de inicio de sesión en el backend de administración de Joomla para evitar ataques de fuerza bruta en tu sitio web Joomla. Esto se puede implementar mediante varias extensiones de seguridad de Joomla que protegen el backend de administrador de tu sitio web de intentos de hackeo. Puedes encontrar tales extensiones en la categoría de lista de seguridad de Extensiones de Joomla.

## 12. Elige un Proveedor de Alojamiento Seguro

Asegúrate de que el proveedor de alojamiento que elijas implemente medidas de seguridad para Joomla. Si decides optar por un alojamiento compartido, asegúrate de que se implemente la subred considerando la seguridad de Joomla. Comprar un proveedor de alojamiento compartido y barato puede no ser ideal desde el principio, ya que tu sitio será más lento, estará sujeto a spam debido a un 'vecindario malo' de sitios con baja reputación, y podría verse comprometido si otros sitios son hackeados. Además, al elegir un plan de alojamiento, verifica varios parámetros como personalización, soporte, opiniones, etc.

## 13. Usa SSL para Mejorar la Seguridad de Joomla

Se recomienda encarecidamente instalar un certificado SSL (Secure Socket Layer) en tu sitio web, ya que cifrará la comunicación entre tu sitio Joomla y los navegadores de tus visitantes. Obtén un certificado SSL de una autoridad certificadora verificada y asegúrate de que todo tu tráfico HTTP se redirija a HTTPS. Para hacer esto, añade el siguiente código a tu archivo .htaccess:

```
# Redirigir HTTP a HTTPS
RewriteEngine On RewriteCond %{HTTPS} off
RewriteCond %{HTTP:X-Forwarded-Proto} !https
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
```

## 14. Auditorías de Seguridad Frecuentes en Joomla

Es extremadamente importante descubrir vulnerabilidades antes de que lo haga un hacker para mantener tu sitio web en Joomla seguro. Esto se puede lograr eligiendo una herramienta profesional de auditoría de seguridad que te ahorre mucho tiempo en la gestión de tus sitios web. Las auditorías de seguridad meticulosas son una excelente manera de mejorar la seguridad de tu Joomla. Muchos servicios hacen esto automatizando tareas como la creación de copias de seguridad del sitio web, el escaneo de signos de intrusión y la actualización masiva de las extensiones en las que confías. También puede escanear tu sitio para el uso de las mejores prácticas de seguridad y realizar un escaneo profundo para buscar amenazas de seguridad potenciales. Estos servicios utilizan una mezcla optimizada de mecanismos manuales y automatizados para descubrir vulnerabilidades en tu sitio Joomla.

## 15. Revisar Mensajes de Post-instalación

Es altamente recomendable leer todos los mensajes de post-instalación, ya que el equipo de Joomla te proporciona información importante que necesita tu atención después de actualizar o de instalar Joomla por primera vez. Estos mensajes generalmente contienen configuraciones de seguridad de Joomla o cambios en archivos que deben hacerse manualmente y que una actualización no puede modificar.

## 16. Conozca las Extensiones Vulnerables

Siempre consulte el sitio web de la Lista de Extensiones Vulnerables y sus páginas en redes sociales para conocer los últimos riesgos de seguridad y posibles parches. Se recomienda desinstalar cualquier extensión listada en la Lista de Extensiones Vulnerables para la cual no se conozca la existencia de un parche. Asegúrese de actualizar su extensión vulnerable siempre que su parche esté disponible. Si su sitio utiliza una versión vulnerable de una extensión que no tiene una actualización de parche, se recomienda reemplazarla.

## Conclusión

Debido a que siempre habrá riesgos, la seguridad de Joomla seguirá siendo un proceso continuo, que requiere una evaluación frecuente de posibles portadores de ataques. Los propietarios y administradores de sitios web deben mejorar constantemente la seguridad de sus sitios web para reducir el riesgo de un compromiso.

