<!-- Filename: jdocmanual?manual=user&heading=migration&filename=migration-basics.md / Display title: Conceptos Básicos de la Migración   -->

## Terminología

¡Los documentos de Joomla! utilizan una variedad de términos para referirse al cambio de una versión anterior a una versión más nueva:

* **Migración o mini-migración** es un término generalmente aplicado a un cambio de una versión *Mayor* antigua a una versión *Mayor* más nueva, a veces a través de varias versiones *Mayor* intermedias.
* **Actualización de versión** es un término generalmente aplicado al cambio de una versión reciente a la siguiente versión en una secuencia de versiones *Menores*.
* **Actualización** es un término usualmente utilizado para el proceso de Actualización de versión usando el componente de Actualización de Joomla. Es la palabra que se ve en la interfaz del Administrador en Joomla! 3, 4 y 5. A partir de ahora se utilizará el término *Actualización* en este artículo.

También es importante saber que Joomla sigue el estándar de Versionado Semántico. En resumen, dado un número de versión MAYOR.MENOR.PARCHE, como 5.1.0:

* La versión **MAYOR** permite rupturas de compatibilidad hacia atrás.
* La versión **MENOR** permite funcionalidades adicionales de manera compatible hacia atrás dentro de la versión Mayor.
* La versión **PARCHE** permite correcciones de errores compatibles hacia atrás.

Puede haber sufijos adicionales como *alpha*, *beta* o *rc*, pero no en lanzamientos estables destinados a sitios de producción.

## Razones para Actualizar

Las razones para actualizar son muchas y variadas:

* **Seguridad** Aunque Joomla! es reconocido como un CMS muy seguro, ocasionalmente 
se descubren y solucionan vulnerabilidades en lanzamientos menores o de parche.
* **Cambios en el alojamiento** Joomla utiliza el lenguaje de script *PHP* y un servidor de base de datos como *MySQL*, *MariaDB* o *PostGres*. Estos avanzan a través de cambios y los servicios de alojamiento necesitan mantenerse actualizados. Por lo tanto, puede que encuentres que una versión anterior de Joomla ya no funcione o falle si cambias de servicio de alojamiento.
* **Cambios en el diseño** Quizás desees hacer que tu sitio se vea mejor, funcione mejor con dispositivos móviles y obtenga una mejor puntuación en los motores de búsqueda. Podrías tener que cumplir con requisitos legales de *Accesibilidad*.
* **Funcionalidad** Tal vez quieras utilizar una extensión de Joomla que ofrezca alguna característica que no está proporcionada por las extensiones principales de Joomla. Las opciones pueden estar limitadas por tu versión mayor actual.

## Copia de seguridad antes de la actualización

**¡Esto es realmente importante!** Incluso si has realizado varias actualizaciones intermedias, es posible que algo salga mal durante el proceso de actualización. Esto podría dejar tu sitio inoperativo. El consejo estándar ofrecido en los Foros es regresar a tu última copia de seguridad, averiguar por qué falló la actualización, solucionarlo e intentarlo de nuevo.

**Akeeba Backup** es una herramienta gratuita disponible en el Directorio de Extensiones de Joomla (JED) al que tienes acceso directo a través de Sistema / Instalar extensiones / Instalar desde la web. Solo toma uno o dos minutos descargar e instalar. Analiza tu sistema para configurar un perfil usando un Asistente de Configuración. Luego, realiza una copia de seguridad que puedes descargar para mantenerla a salvo.

## Autoevaluación

Antes de realizar una actualización de versión *Mayor* o *Menor*, necesitas evaluar tu sistema y tus extensiones de terceros existentes para comprobar la compatibilidad con la versión objetivo de Joomla. Es una buena idea hacer una lista de las extensiones de terceros que has instalado. En Joomla 4 y 5, la lista en *Sistema / Extensiones / Administrar* tiene un filtro para seleccionar **Extensiones No Nucleares**. Esto no está presente en Joomla 3.

También podrías usar el **Asistente de Publicación en el Foro**. Esta es una herramienta destinada a analizar un sitio y crear un informe adecuado para publicar en los Foros de Joomla para ayudar a los expertos del Foro a diagnosticar problemas en tu sitio. Sin embargo, tiene una interfaz de usuario privada que te informa todo sobre tu sitio. Sus listas de extensiones (Componentes, etc.) indican cuáles son de *Terceros*.

Los problemas que surgen durante las actualizaciones suelen estar asociados con extensiones de terceros que no son compatibles a nivel de código con tu versión objetivo de Joomla. Debes verificar cada extensión para comprobar su compatibilidad y **desinstalar** aquellas que se sepa que son incompatibles. Podrías ser capaz de instalar versiones compatibles más adelante.

Debes establecer una de las plantillas de sitio predeterminadas como tu **plantilla predeterminada**:

* Las plantillas predeterminadas en Joomla! 1.5 son Rhuk_milkyway, JA Purity, Beez.
* Las plantillas predeterminadas en Joomla! 2.5 son Atomic, Beez3, y Beez25.
* Las plantillas predeterminadas en Joomla! 3 son Protostar y Beez3.
* La plantilla predeterminada en Joomla! 4 es solo Cassiopeia.

## Pruebas Locales

Si es posible, es mejor configurar un entorno de pruebas local en tu
portátil o estación de trabajo para probar tu procedimiento de actualización. Puedes usar la
copia de seguridad de tu sitio en línea para poblar tu sitio de prueba. Tu sitio en casa debe ser
capaz de ejecutar tu copia de tu sitio en vivo y tener especificaciones adecuadas de PHP y Base de Datos
para ejecutar el sitio actualizado. Hay un artículo separado que describe
cómo configurar un entorno de pruebas en casa.

## Información Adicional

Hay varios artículos que describen escenarios de actualización específicos que no se incluyen en este manual porque son antiguos o repetitivos.

* https://docs.joomla.org/Why_Migrate
* https://docs.joomla.org/Migration_Step_by_Step_Self_Assessment
* https://docs.joomla.org/J3.x:Updating_Joomla_(Install_Method
* https://docs.joomla.org/J3.x:Updating_Joomla_(Update_Method)
* https://docs.joomla.org/Planning_Migration_-_Joomla_1.5_to_4
* https://docs.joomla.org/Planning_for_Migration
* https://docs.joomla.org/Pre-Update_Check
* https://docs.joomla.org/Template_Considerations_During_Migration
* https://docs.joomla.org/J3.x:Update_fails_with_an_error_message
* https://docs.joomla.org/Converting_an_existing_website_to_a_Joomla!_website
* https://docs.joomla.org/Potential_backward_compatibility_issues_in_Joomla_4

