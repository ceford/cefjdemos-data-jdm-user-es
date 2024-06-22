<!-- Filename: Planning_Migration_-_Joomla_1.5_to_4 / Display title: Planificación de una migración - De Joomla 1.5 a la 3 -->

Pasar de Joomla! 1.5 a 3.x se considera una migración y una migración
importante. Esto significa que hay cambios considerables en cómo
funciona Joomla, las tablas, la tecnología... estos cambios requieren
una migración en lugar de una actualización o mejora. Tanto las
extensiones del nucleo de Joomla como las extensiones de terceros
tendrán que migrar a Joomla 3.x. Esto incluye la plantilla. Cada cosa
tiene que ser mirada, planificada, decidida y ejecutada. Tendrá que ser
diligente en mantenerse organizado durante todo el proceso.

## Introducción

Lo fabuloso sobre la migración es que es un buen momento para reevaluar
los objetivos, crear una nueva apariencia (plantilla), limpiar, y
desarrollar otras áreas / elementos de su sitio. Hasta el más organizado
se puede mejorar sus ideas/pensamientos/planes. Planificar, planificar,
planificar. La panificación hace más fácil ejecución.

Comience a planificar haciéndose las siguientes preguntas o haciendo los
trabajos que se enumeran a continuación. Es posible que tenga más
elementos para planificar en función de la complejidad de su sitio.
Lamentablemente, no hay manera de que podamos enumerar todos los
posibles escenarios.

{{{1}}}

## Planificar las tareas

### General

1.  Evalúe sus objetivos del sitio original. La migración es una
    oportunidad de volver al enfocar sus objetivos o cambiar de
    dirección.
2.  ¿Su servidor cumple con los requisitos técnicos mínimos
    <a href="http://www.joomla.org/about-joomla/technical-requirements.html"
    class="external autonumber" target="_blank"
    rel="noreferrer noopener">[1]</a> para Joomla 3? Si no, tendrá que
    cambiar de servidor. No hay mejor momento para cambiar de servidor
    que durante una migración.
3.  ¿Qué tipo de entorno de desarrollo va a utilizar? Un entorno de
    desarrollo en un dispositivo local? Un subdominio o subdirectorio en
    el servidor? Un nuevo servidor/cuenta de alojamiento, debido a las
    especificaciones técnicas?

### Núcleo de Joomla

1.  Limpie su sitio web actual. Eche un vistazo a las Secciones,
    Categorías y Artículos. Las secciones se convierten en categorías de
    mayor nivel a partir de Joomla 2.5. ¿Hay limpiezas que hay que hacer
    para no migrar contenido innecesario? Documente lo que desea borrar.
    Alternativamente, es posible que desee documentar lo que desea
    migrar sobre todo dependiendo de la cantidad.
2.  Organice su contenido en el sitio actual. ¿Qué Categorías utilizaré?
    Documentar las nuevas categorías que posiblemente desee añadir en su
    nuevo sitio web.
3.  ¿Tiene algunos artículos en la papelera? Si es así, elimínelos (y
    cualquier archivo multimedia vigente que puedan estar asociados con
    estos, si no lo utiliza otro archivo del sitio web). Los Artículos
    que se enviaron a la papelera pueden causar problemas de alias
    duplicados una vez migrados (las categorías y elementos de menú
    también).
4.  Gestor multimedia: Decida si quiere migrar su directorio /images
    entero, o sólo parte de el. Si el Gestor multimedia se ha convertido
    en un desastre, puede decidir migrar, sobre todo imágenes
    específicas, mediante FTP o desde el cPanel, en lugar de migrar todo
    el directorio. En el futuro, organice las carpetas Gestor multimedia
    para que no se convierta en un gran lío.
5.  Si utiliza componentes básicos como Contactos, Enlaces web, o
    Canales de noticias, documente lo que quiera migrar, si no quiere
    migrarlo todo.
6.  Compruebe los menús y determine si los migrará todos, o sólo algunos
    menús y sus elementos de menú. Elimine los elementos de menú de la
    papelera para evitar los alias duplicados.
7.  Si rediseña o introduce cambios en el diseño de su sitio web, o en
    la navegación, ¿va a tener páginas obsoletas que requerirán una
    redirección? Realizar un seguimiento de todas las URL que necesitan
    redirecciones en una hoja de cálculo o en el bloc de notas.
1.  ¿Sabe si ha "hackeado el núcleo" de su sitio en 1.5? Si es así, esos
    cambios no se migrarán a Joomla 3. Tendrá que buscar alternativas
    para hackear el núcleo de de Joomla 3 (<a
    href="https://docs.joomla.org/How_to_override_the_output_from_the_Joomla!_core"
    class="new"
    title="Special:MyLanguage/How to override the output from the Joomla! core (page does not exist)">Cómo
    anular la salida del núcleo de Joomla</a>,  Entendiendo overrides de
    salida,
     Overides a la plantilla en
    Joomla.
2.  Compruebe su Gestor de usuarios. ¿Tiene la intención de migrarlos
    todos? ¿Se requiere una limpieza? ¿Quizás hay superadministradores
    que ya no deberían tener acceso o spam de usuarios que necesitan
    eliminarse? ¿Está utilizando algún tipo de extensión de terceros
    para mejorar los perfiles de usuario? Esta parte necesita una
    planificación cuidadosa. Sobre todo si los datos de usuarios cambian
    frecuencuentemente.
3.  ¿Existen nuevas funcionalidades de Joomla que desee utilizar, al
    igual que los niveles de control de acceso (ACL), etiquetas? Si es
    así, empiece a planificar esto ahora. La panificación del ACL es
    planteamiento prudente. Ser cuidadoso es muy importante.

### Extensiones de terceros

1.  Haga una lista de todas las extensiones de terceros que utilice.
    Esto incluye componentes, módulos, plugins, idiomas y plantillas.
    Puede usar la <a
    href="https://docs.joomla.org/images/5/59/Third-Party_Extension_Inventory_Worksheet.pdf"
    class="external text" target="_blank" rel="noreferrer noopener">Hoja de
    inventario de extensiones de terceros</a> o simplemente utilice
    copiar/pegar en un documento de referencia, si desea. Un trozo de
    papel y un bolígrafo serán suficientes. Incluya si estas extensiones
    se utilizan en gran medida, de forma moderada, casi nunca, o nunca.
1.  Determinar si las extensiones de terceros en las que confía, están
    preparadas para la versión de de Joomla que está migrando.
2.  Determine si realmente necesita todas las extensiones que está
    utilizando. ¿Podría ser que de Joomla 3 haya incorporado estas
    características por lo que podrían eliminar la utilización de una
    extensión de terceros?
3.  ¿Qué hay de su plantilla? Si compró su plantilla en un proveedor
    externo, ¿existe una versión 3.x publicada por este? ¿Le gustaría
    seguir utilizándola? ¿Hay una ruta de migración, publicada por el
    desarrollador? La nueva versión es responsiva? ¿Es una plantilla
    personalizada? ¿O fue muy personalizada, partir de una plantilla de
    terceros? Para una ampliación de las consideraciones para las
    plantillas, ver  Consideraciones sobre la plantilla durante la
    migración.
1.  Si va a cambiar tu plantilla por una nueva, ¿va a necesitar nuevas
    imágenes? Por ejemplo, si su sitio actual tiene un fondo blanco y su
    logotipo, u otras imágenes, son .jpg, con fondo blanco, no quedarán
    muy bien en contraste con una nueva plantilla con un fondo blancuzco
    o de color.

<a
href="https://docs.joomla.org/Joomla_1.5_to_4.x_Step_by_Step_Migration"
id="content-button" class="button expand">Joomla 1.5 to 4.x Step by Step
Migration</a>
