<!-- Filename: Template_Considerations_During_Migration / Display title: Consideraciones sobre la plantilla en la migración -->

<img
src="https://docs.joomla.org/images/thumb/4/47/Copyedit.png/25px-Copyedit.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/4/47/Copyedit.png/38px-Copyedit.png 1.5x, https://docs.joomla.org/images/thumb/4/47/Copyedit.png/50px-Copyedit.png 2x"
data-file-width="200" data-file-height="200" width="25" height="25"
alt="Copyedit.png" />This Article Needs Your Help

*This article is tagged because it* **NEEDS UPDATING***. You can help
the Joomla! Documentation Wiki by <a
href="https://docs.joomla.org//docs.joomla.org/index.php?title=Template_Considerations_During_Migration/es&amp;action=edit"
class="external text" target="_blank"
rel="noreferrer noopener">contributing to it</a>.
<span class="small">More pages that need help similar to this one are
here.</span>
<span class="small">**NOTE-If you feel the need is satistified, please
remove this notice.**</span>*
**Reason:** See section 3.4 and 4

Las plantillas, a veces, crean un bucle durante la migración. No tiene
porque ser así. Con unas cuantas explicaciones, se puede llegar a tener
claro cuales son las opciones.

## Introducción

Las plantillas son una extensión. Al igual que los componentes, módulos
y plugins son extensiones, una plantilla también lo es.

En una migración, tendrá que decidir qué hacer con la plantilla actual
(pues esta determina la "apariencia" del sitio web).

Su escenario de plantilla seguramente encajará mayormente con una de las
siguientes opciones:

- Está utilizando una plantilla que se adquirió en un club de
  plantillas.
- Está utilizando una plantilla que compró en algún proveedor de
  plantillas.
- Tiene una plantilla con un diseño personalizado.
- Está utilizando una plantilla predeterminada, que viene con la
  instalación de Joomla (en Joomla! 1.5 las plantillas predeterminadas
  son rhuk_milkyway, JA Purity, Beez y en Joomla! 2.5 las plantillas por
  defecto son Atomic y dos versiones diferentes de Beez). La plantilla
  pudo haberla personalizado de manera significativa, o no.

## Evaluación de escenarios de plantillas

Antes de decidir qué hacer, tendrá que evaluar si desea mantener el
aspecto actual de su sitio web. Si desea un cambio, este es el momento
de decidirse. Quizás la principal razón por la que posiblemente desee
cambiar tu plantilla, es utilizar una tecnología más actual de las
nuevas plantillas. Las plantillas responsivas no estaban disponibles
para la 1.5 (a menos que hubiera contratado recientemente a alguien para
que modificara su plantilla a responsiva), incluso en el inicio del
ciclo de vida de la 2.5, las versiones para móviles de plantillas eran
escasas y el responsivo aun no había aparecido.

Tomemos estos escenarios de uno en uno:

### You are using Protostar

Protostar is not compatible with Joomla 4.x. The migration will work on
the one-click from Joomla 3.10.x to 4.x but the template will disappear
and be replaced with Cassiopeia upon migration. You will need to plan on
using Cassiopeia or some other template in Joomla 4.

#### Why can't you carry forward Protostar into Joomla 4?

Protostar is based on an old version of Bootstrap (Bootstrap 2) and
jQuery (1.x). The versions of these components are outdated and have
known security issues (Joomla 3 maintained forked versions of these
libraries with security patches applied) - and Joomla 4 has updated
these to the latest version - Bootstrap 5. However this means that
templates need to be updated to use the new HTML syntax that Bootstrap 5
requires.

### Está utilizando una plantilla que se adquirió en un club de plantillas

Casi siempre esta es la más fácil. Si compró una plantilla de un club de
plantillas, vaya de nuevo a la empresa y vea si tienen una versión de su
plantilla para Joomla 3.x. Si es así, excelente, algo menos en que
pensar. Si usted está funcionando con la 1.5 vaya a la 3.x, y compruebe
si la versión para la Joomla 3 es responsiva, si lo considera que es
importante para su sitio. Si migra de la 1,5 a la 3, es muy probable que
hayan algunas diferencias entre la plantilla de la versión 1.5 y la de
la versión 3. Esté preparado para hacer algunas personalizaciones en la
plantilla, si quiere que se vea *exactamente* igual.

Si quiere ir de la 2.5 a la 3.x, y compruebe si las versiones de la 2.5
y de la 3.x están el mismo paquete del desarrollador. Si no es así,
consulte con el desarrollador las medidas para actualizar desde Joomla
2.5 a la 3.x. Si la 2.5 y la 3.x están en el mismo paquete, ¡perfecto!.
Si no lo son, es posible que aún sea fácil. Sólo depende de la hoja de
ruta de actualización de los desarrolladores.

### Está utilizando una plantilla que compró en algún proveedor de plantillas

Si compró una plantilla de un proveedor de plantillas, vuelva a la
empresa y vea si hay una versión disponible para Joomla 3.x. Si no es
así, no ha tenido suerte . Sin embargo, puede intentar ponerse en
contacto con alguien de la empresa para ver si se puede actualizar la
plantilla para usted y que sea compatible con Joomla 3.x.

Si esto no funciona, entonces necesitará:

1.  Eligir una plantilla nueva.
2.  Convertir la plantilla para que sea compatible con Joomla 3.x.
    (Nota: no podrá ser responsiva.)

El primer punto no necesita explicación. Puede elegir entre comprar una
plantilla de un proveedor comercial, o personalizar la plantilla
predeterminada Protostar (ver más abajo) que se instala con Joomla 3.x.
El segundo punto no es tan fácil. Para saber como convertir una
plantilla existente para que sea compatible con Joomla 3, consulte la
sección siguiente.

## Conversiones de plantilla o Migraciones de plantilla

### Conversiones de Plantilla de la 1.5 a la 3

-  Migración de una plantilla de Joomla 1.5 a la
  3.x

### Conversiones de plantilla de la 1.5 a la 2.5

-  Actualizar una plantilla de Joomla 1.5, a Joomla
  2.5
- <a
  href="http://magazine.joomla.org/issues/issue-may-2012/item/740-How-to-convert-Joomla-15-template-to-Joomla-25"
  class="external free" target="_blank"
  rel="noreferrer noopener">http://magazine.joomla.org/issues/issue-may-2012/item/740-How-to-convert-Joomla-15-template-to-Joomla-25</a>

### Conversiones de plantillas de la 2.5 a la 3

-  J3.x:Conversión de una plantilla de una versión anterior de
  Joomla!
- <a
  href="http://stackoverflow.com/questions/16055707/convert-joomla-2-5-template-to-3-0"
  class="external free" target="_blank"
  rel="nofollow noreferrer noopener">http://stackoverflow.com/questions/16055707/convert-joomla-2-5-template-to-3-0</a>
- <a href="https://www.youtube.com/watch?v=E13QMWgvwlA"
  class="external free" target="_blank"
  rel="nofollow noreferrer noopener">https://www.youtube.com/watch?v=E13QMWgvwlA</a>

### 3.10.x to 4 Template Conversions

This section needs content. If you have knowledge on converting
templates built for Joomla 3 to make them compatible with Joomla 4,
please write a magazine article or post a YouTube or something that can
be linked from this area. Thanks in advance.

### Está utilizando una plantilla con diseño personalizado

Si tienes una plantilla personalizada diseñada para un sitio 1.5 o 2.5,
necesitarás modificarla para que sea compatible con Joomla 3. Mira los
enlaces en la sección anterior. Si necesitas contratar a alguien para
que tu plantilla actual se convierta en compatible con Joomla 3.x,
visita nuestro Directorio de Recursos Joomla!, ya sea en las categorías
<a href="http://resources.joomla.org/en/category/custom-templates"
class="external text" target="_blank"
rel="noreferrer noopener">Desarrollo de pPantillas</a> o en <a
href="http://resources.joomla.org/en/category/migration-and-upgrade-services"
class="external text" target="_blank"
rel="noreferrer noopener">Migraciones y Actualizaciones</a>.

### Está utilizando una plantilla predeterminada que viene con la instalación de Joomla

Joomla! 1.5 viene con las plantillas predeterminadas Rhuk_milkyway, JA
Purity, y Beez. Joomla! 2.5 con las plantillas predeterminadas Atomic y
dos versiones diferentes de Beez. Puede que las hayan personalizado
significativamente, o en absoluto. Si está utilizando una plantilla
predeterminada de la 2.5 y pasa a Joomla 3.x, podrá hacer la
actualización en un solo clic. Si está utilizando una plantilla de 1,5
por defecto entonces tendrá que utilizar uno de los pasos anteriores
para actualizar a Joomla 3.x. (Si alguien encuentra esta información
incorrecta, por favor, que colabore aportando la información para
arreglarlo).

Antes de decidir si deseas convertir la plantilla de Joomla 1.5 a la 3,
es posible que desees considerar seriamente buscar una nueva plantilla
con similitudes con la plantilla actual. Lo más probable es que sea más
barato y más rápido utilizar una nueva, que convertir la antigua. Si
deseas convertir la antigua y no tienes los conocimientos para hacerlo
tu mismo, visita el sitio <a
href="http://resources.joomla.org/en/category/migration-and-upgrade-services"
class="external text" target="_blank"
rel="noreferrer noopener">Directorio de Recursos de Joomla!™</a>.

Protostar, the template that ships with Joomla 3.x is **not** compatible
with Joomla 4.x. You will need to go through one of the steps above to
update it for Joomla 4.x.

### Al elegir las plantillas

- Sólo mire una empresa de plantillas a la vez o se vuelve abrumador
- Si comienza a sentirse abrumado, haga un descanso, incluso déjelo para
  el día siguiente
- Trate de mirar más allá de las demos con contenido y llamativas.
  Piense cual es su contenido puesto en la plantilla, no todas las
  posibilidades que esta tiene.
- Observe las posiciones de los módulos y las variaciones de las
  plantillas
- Beba mucha agua mientras busca plantillas y estírese cada hora o así

## Está utilizando la plantilla Protostar predeterminada en Joomla 3.x

Esta sección está incompleta. Si tiene conocimientos sobre este tema,
por favor participen añadiéndolos a este documento. Mientras tanto,
puede realizar una búsqueda en Google sobre cómo personalizar Protostar,
encontrarán muchos resultados fuera de la documentación de Joomla!.
