<!-- Filename: J4.x:Home_Page_in_Different_Style / Display title: Página de Inicio en Estilo Diferente  -->

## Página de Inicio del Sitio

Se puede seleccionar una página de inicio del sitio desde cualquier tipo de elemento del menú al seleccionar un ícono gris en la columna Inicio de cualquier lista de elementos del menú. ¡Intenta hacer un cambio! Visualiza el cambio en tu sitio en una pestaña o ventana de navegador separada. Puedes volver fácilmente al estado anterior. Si deseas una página de inicio distintiva, podrías elegir un tipo de elemento de menú de Artículo Único, un tipo de elemento de menú de Blog de Categoría, un tipo de elemento de menú de Artículos Destacados, o algo más.

Supongamos que te gustaría darle a tu página de inicio una apariencia distintiva un poco diferente a las demás páginas de tu sitio. Hay muchos métodos diferentes disponibles para personalizar la apariencia de una página de inicio:

- A través de módulos asignados solo a la página de inicio.
- A través de estilos personalizados.
- A través de una Sobrescritura o Diseño de plantillas.
- A través de una plantilla separada o una plantilla secundaria utilizada solo para el elemento del menú de la página de inicio.
- ¿Más...?

## Ejemplo: Datos de Muestra de Cassiopeia

Los datos de muestra de Cassiopeia crean una página de inicio usando un tipo de elemento de menú de **Artículos Destacados**. Está diseñada con la apariencia que se muestra en la captura de pantalla a continuación (se realizaron algunos cambios menores en artículos individuales para obtener una mejor captura de pantalla aquí).

![página de inicio usando cassiopeia y datos de muestra](../../../en/images/templates/templates-home-page-style-cassiopeia-sample-data.png)

Así es como se logra el diseño:

### Módulo de Imagen

La gran imagen debajo de la barra de menú está en un módulo personalizado llamado Imagen, asignado a la posición del banner en la plantilla Cassiopeia.

![módulo personalizado usado en el estilo de datos de muestra](../../../en/images/templates/templates-home-page-style-custom-module-image.png)

En la pestaña Asignación de Menú, el módulo está asignado solo a Inicio:

![pestaña de asignación de menú del módulo personalizado](../../../en/images/templates/templates-home-page-style-custom-module-menu-assignment.png)

La imagen de fondo se selecciona en la pestaña Opciones del formulario de edición de Módulos: Personalizado.

En la pestaña Avanzado / campo de Diseño, se selecciona el elemento `banner`. El diseño del banner es un diseño de plantilla:

### Diseño de Plantilla

El diseño de módulo predeterminado en `siteroot/modules/mod_custom/tmpl/default.php` no muestra el módulo como se desea. Hay un diseño alternativo en `siteroot/templates/cassiopeia/html/mod_custom/banner.php`. Como `banner.php` no está presente en el código del módulo personalizado, funciona como un diseño que puedes seleccionar en lugar de una anulación que siempre se usa. En el módulo de Imagen puedes seleccionar el diseño predeterminado, guardar y recargar el sitio para ver la diferencia. Cambia de nuevo al diseño de banner y guarda de nuevo para restaurar el comportamiento normal.

Hay artículos separados sobre Anulaciones y Diseños.

### Módulo de Noticias Breves

Debajo de la gran Imagen hay tres pequeñas cajas, cada una con una imagen y texto debajo. Se crean usando un módulo de Artículos - Noticias Breves en la posición top-a de la plantilla. El módulo está configurado para mostrar 3 elementos. Su Asignación de Menú es solo Inicio. La pestaña Avanzado tiene el Diseño configurado en horizontal y el Estilo del Módulo configurado en noCard.

![módulo de noticias breves](../../../en/images/templates/templates-home-page-style-newsflash-module-image.png)

Eso concluye la explicación de cómo se creó la página de inicio de datos de muestra de Cassiopeia.

## Más Opciones

Puede que desee hacer más cosas. Un esquema de color diferente para la página de inicio, una marca de agua o un diseño personalizado. Aquí hay algunas ideas:

### Visualización de la Página

En los Menús: formulario de edición de elementos para el menú de Inicio seleccione la pestaña de Visualización de Página. El campo de Clase de Página suele estar vacío. Todo lo ingresado aquí se convierte en una clase extra en el

elemento de la página. Por ejemplo, ingresar `fancyhome` da como resultado lo siguiente en la salida de la página de inicio para esa única página:
```html
<body class="site com_content wrapper-static view-featured no-layout no-task itemid-101 fancyhome has-sidebar-right">
```
Luego puede crear un archivo user.css a través de **Sistema** → **Plantillas del Sitio** → **Detalles y Archivos de Cassiopeia**. Seleccione el botón `Nuevo Archivo` y cree user.css en la carpeta css. Luego ingrese estilos en el formulario de edición de user.css. Ejemplo:
```css
    .fancyhome {
      background-color: #f8fff8;
    }
```
Esto dotará a la página de inicio de un fondo verde pálido. Utilice \#f8f8ff; para un fondo azul pálido o \#ffffee para un amarillo pálido. Puede hacer todo tipo de otras cosas con su estilo fancyhome, pero necesita un buen conocimiento práctico de css.

### Plantillas Alternativas para la Página Principal

Puede instalar plantillas alternativas para el sitio, obtenidas de proveedores de plantillas de terceros. Y puede crear plantillas secundarias que se comporten de manera similar. En cualquier caso puede elegir qué plantilla será la predeterminada para todas las páginas y cuál se utilizará solo para la página de inicio.

- Seleccione **Sistema → Estilos de Plantilla del Sitio** en el menú del Administrador.
- Seleccione la plantilla que desea usar para la página de Inicio. Debe ser una de las que no se ha seleccionado como plantilla Predeterminada.
- En la pestaña de Asignación de Menús seleccione solo el elemento del menú de Inicio. Cualquier cosa no seleccionada aquí seguirá utilizando su plantilla predeterminada.
- Podría seleccionar algunas opciones en la pestaña Avanzada, pero varían con cada plantilla y no están cubiertas aquí.

Hay otros artículos sobre la personalización de Cassiopeia.

*Traducido por openai.com*

