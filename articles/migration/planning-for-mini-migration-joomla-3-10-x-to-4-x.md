<!-- Filename: Planning_for_Mini-Migration_-_Joomla_3.10.x_to_4.x / Display title: Planificación para Mini-Migración - Joomla 3.10.x a 4.x -->

Pasar de Joomla 3.10.x a 4.x se considera una "mini-migración" o
migración menor. Esto significa que las extensiones del núcleo de Joomla
se actualizarán con una "actualización en un solo clic", pero las
extensiones de terceros son discutibles y deberán ser analizadas caso
por caso.

## Introducción

Las migraciones son un buen momento para reevaluar los objetivos,
limpiar y desarrollar otras áreas/elementos de su sitio. Cuanto más
organizado pueda ser con sus ideas/pensamientos/planes, mejor.
Planificar, planificar, planificar. La planificación hace más fácil la
ejecución.

Empiece a planificar haciendo las siguientes preguntas o realizando las
tareas que se enumeran a continuación. Es posible que tenga más
elementos para planificar según la complejidad de su sitio.
Lamentablemente, no hay forma de que podamos enumerar todos los
escenarios posibles. Más cerca del momento, crearemos un foro de
migración de Joomla 4.x específico similar a las versiones principales
anteriores de Joomla.

## El Puente 3.10.x

Joomla 3.10.x pretende ser un puente entre el ciclo de vida de Joomla 3
y el ciclo de vida de Joomla 4. Joomla 3.10.x será principalmente una
versión que contiene versiones posteriores de los cambios de API de la
rama de desarrollo de Joomla 4.x para ayudar a facilitar la transición a
la próxima versión principal para la comunidad. Lo nuevo de Joomla
3.10.x es que ofrece una característica excelente mediante el componente
Actualización de Joomla! para ayudarle con su proceso de mini-migración:
la  Comprobación de
Pre-Actualización.
Una vez que su sitio web esté actualizado a 3.10, la comprobación de
pre-ctualización le permitirá comprobar la compatibilidad con Joomla 4.0
de sus opciones PHP y SQL, configuraciones, y las extensiones que está
utilizando, siempre que los desarrolladores de extensiones utilicen la
etiqueta targetplatform. Consulte la documentación de  Comprobación de
Pre-Actualización
para obtener más información.

## Planificar las Tareas

Lo siguiente supone que ya ha actualizado su sitio Joomla 3.x a la
versión 3.10.x. Esto le permitirá aprovechar la Comprobación de
Pre-Actualización como parte de su planificación.

1.  Asegúrese de que su sitio web esté ejecutando 3.10.x.
2.  Evalúe los objetivos de su sitio original. La migración es una
    oportunidad para volver a concentrarse en sus metas o cambiar de
    rumbo.
3.  ¿Su servidor cumple con los
    <a href="https://downloads.joomla.org/es/technical-requirements-es"
    class="external text" target="_blank"
    rel="noreferrer noopener">requisitos técnicos</a> mínimos para
    Joomla 4? De lo contrario, deberá cambiar de proveedor de hosting.
    No hay mejor momento para cambiar de proveedor que durante una
    migración.
4.  ¿Qué tipo de entorno de desarrollo va a utilizar? ¿Un entorno de
    desarrollo en su dispositivo local? ¿Un subdominio o subdirectorio
    en su servidor? ¿Una nueva cuenta de servidor/alojamiento debido a
    especificaciones técnicas?
5.  Haga una lista de todas las extensiones de terceros en uso. Esto
    incluye componentes, módulos, plugins, idiomas y plantillas. Puede
    simplemente copiarlos/pegarlos en un documento de referencia, o
    papel y bolígrafo también es útil. Incluya si estas extensiones se
    usan mucho, moderadamente, casi nunca o nada en absoluto.
6.  Determine si las extensiones de terceros en las que confía están
    listas para la versión de Joomla a la que está migrando,
    seleccionando la opción Próximo Joomla (una vez esté ejecutando
    Joomla 3.10.x) en el Componente Actualización de Joomla!, y
    verificando la compatibilidad con Joomla 4. No ejecute la
    actualización a 4.x, simplemente seleccione Próximo Joomla en las
    Opciones de Actualización de Joomla! para que se pueda mostrar la
    Comprobación de Pre-Actualización. Esto le ayudará a obtener una
    vista resumida de las extensiones en uso y su compatibilidad. No
    sustituye a la necesidad de seguir utilizando Extensiones →
    Gestionar. Más sobre esto en el Paso-a-Paso y la documentación del
    componente  Comprobación de
    Pre-Actualización.
    Esto es simplemente para prepararse sobre qué extensiones de
    terceros permanecerán, desaparecerán o serán reemplazadas.
7.  Determine si realmente necesita todas las extensiones que está
    usando. ¿Podría ser que Joomla 4 haya incorporado características
    que podrían eliminar el uso de una extensión de terceros?
8.  Eche un vistazo a sus categorías y artículos. ¿Es necesario realizar
    una limpieza para no migrar contenido innecesario?
9.  ¿Y sobre su plantilla? Si compró su plantilla de una fuente de
    terceros, ¿hay una versión 4.x disponible para ella? ¿Le gustaría
    seguir utilizándola? ¿Existe una ruta de actualización publicada por
    el desarrollador? ¿Responde la nueva versión? ¿Su plantilla es una
    plantilla personalizada? ¿O fue muy personalizada a partir de una
    plantilla de terceros? La plantilla del núcleo de Joomla para Joomla
    3.x **Protostar NO es compatible con Joomla 4**. Tras la migración
    desaparecerá. Usando la plantilla del núcleo de Joomla para Joomla
    4.x, Cassiopeia podría ser una opción para usted. Para ampliar las
    consideraciones basadas en Plantillas, consulte [Consideraciones
    sobre la plantilla en la
    migración](https://docs.joomla.org/Template_Considerations_During_Migration/es "Special:MyLanguage/Template Considerations During Migration/es").
10. Si está cambiando su plantilla por una nueva, ¿requerirá nuevas
    imágenes? Por ejemplo, si su sitio actual tiene un fondo blanco y su
    logotipo u otras imágenes son imágenes .jpg con un fondo blanco, no
    se verá muy bien contra una nueva plantilla con un fondo blanquecino
    o de color.
11. Si rediseña o realiza cambios en el diseño o la navegación de su
    sitio, ¿tendrá páginas obsoletas que requerirán un
    redireccionamiento? Si es así, documéntelos. Una hoja de cálculo es
    útil para documentar los enlaces que deberán cambiarse.

<a
href="https://docs.joomla.org/Joomla_3.x_to_4.x_Step_by_Step_Migration"
id="content-button" class="button expand">Migración Paso a Paso de
Joomla 3.10 a 4.x</a>
