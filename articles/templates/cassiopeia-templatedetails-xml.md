<!-- Filename: J4.x:Cassiopeia_templateDetails.xml / Display title: Cassiopeia templateDetails.xml  -->

## Ubicación y Propósito

Puedes ver un ejemplo de un archivo `templateDetails.xml` listado en **Sistema → Plantillas del Sitio → Detalles y Archivos de Cassiopeia**. También puedes editarlo allí si tienes una buena razón para hacerlo. De lo contrario, ¡déjalo como está! Cada plantilla tiene un archivo como este y una plantilla hija inicialmente consiste en una estructura de archivos que contiene solo este archivo.

El archivo `templateDetails.xml` contiene los datos que Joomla! necesita para gestionar y mostrar la plantilla. Esto incluye metadatos utilizados para proporcionar información sobre la plantilla, las ubicaciones de carpetas y archivos, las posiciones de módulo de la plantilla y las opciones de configuración seleccionables por el usuario. El contenido del archivo templateDetails.xml variará de una plantilla a otra. 


## Cassiopeia templateDetails.xml

Los archivos en formato xml tienen una estructura bien definida. ¡Un archivo xml debe tener la sintaxis correcta o no funcionará!

### Formato XML

La primera línea de cada `templateDetails.xml` debe comenzar con la definición del doctype XML.

La siguiente línea indica a Joomla! que los datos en este archivo son para una extensión de plantilla del sitio. Todos los datos de la plantilla están contenidos entre las etiquetas de apertura y cierre.

```xml
<extension type="template" client="site">
...
</extension>
```

### Metadatos

La primera sección de los datos de plantilla generalmente define la información de la plantilla, por ejemplo: nombres, fechas, información de contacto, derechos de autor, número de versión y descripción.

```xml
<extension version="3.1" type="template" client="site">
	<name>cassiopeia</name>
	<version>1.0</version>
	<creationDate>2017-02</creationDate>
	<author>Joomla! Project</author>
	<authorEmail>admin@joomla.org</authorEmail>
	<copyright>(C) 2017 Open Source Matters, Inc.</copyright>
	<description>TPL_CASSIOPEIA_XML_DESCRIPTION</description>
	<inheritable>1</inheritable>
```

Tenga en cuenta que una plantilla que puede tener plantillas secundarias tiene el valor `inheritable` establecido en 1. Las plantillas secundarias tienen este valor establecido en 0. Estos datos se utilizan en la lista Plantillas: Plantillas (Sitio) como se muestra a continuación.

![lista de plantillas del sitio](../../../en/images/templates/templates-list.png)

La descripción contiene una clave de idioma y no la cadena de texto de descripción real. La clave se reemplaza por el texto obtenido de un archivo de idioma en tiempo de ejecución. Los archivos de idioma se definen en la sección de idioma de `templateDetails.xml`.

![formulario de edición de estilo de plantillas](../../../en/images/templates/templates-edit-style.png)

### Carpetas y Archivos

Las carpetas y archivos para la plantilla Cassiopeia se almacenan en dos lugares separados. Los archivos php y relacionados se almacenan en la carpeta site/templates. Los archivos de medios (css, imágenes, js y scss) se almacenan en la carpeta site/media. Esas ubicaciones se definen en el archivo xml de la siguiente manera:

```xml
	<files>
		<filename>component.php</filename>
		<filename>error.php</filename>
		<filename>index.php</filename>
		<filename>joomla.asset.json</filename>
		<filename>offline.php</filename>
		<filename>templateDetails.xml</filename>
		<folder>html</folder>
	</files>
	<media destination="templates/site/cassiopeia" folder="media">
		<folder>js</folder>
		<folder>css</folder>
		<folder>scss</folder>
		<folder>images</folder>
	</media>
```

Este es el patrón visto en todas las plantillas modernas de Joomla 4 y 5. La estructura se puede ver en el formulario Plantillas: Personalizar (Cassiopeia):

![página de personalización de plantillas cassiopeia](../../../en/images/templates/templates-customise-cassiopeia.png)

### Posiciones del Módulo

Las posiciones de los módulos disponibles se definen de la siguiente manera:

```xml
	<positions>
		<position>topbar</position>
		<position>below-top</position>
		<position>menu</position>
		<position>search</position>
		<position>banner</position>
		<position>top-a</position>
		<position>top-b</position>
		<position>main-top</position>
		<position>main-bottom</position>
		<position>breadcrumbs</position>
		<position>sidebar-left</position>
		<position>sidebar-right</position>
		<position>bottom-a</position>
		<position>bottom-b</position>
		<position>footer</position>
		<position>debug</position>
	</positions>
```

Cada etiqueta crea una posición de módulo que está disponible en la lista de posiciones en un formulario de edición de módulo. El formato simple de la lista de posiciones significa que se puede personalizar fácilmente. Por ejemplo, para agregar una nueva posición de módulo a la lista **en una plantilla secundaria**, simplemente agregue una nueva etiqueta dentro de la etiqueta con un nombre único usando solo letras minúsculas sin espacios. Tenga en cuenta que esto solo agrega la posición a los formularios de edición de módulos y se requiere desarrollo adicional en otros archivos de plantilla para renderizar la nueva posición en el front-end.

¡Cassiopeia tiene suficientes posiciones de plantilla! Si cree que necesita una adicional, probablemente esté equivocado. Recuerde que cualquier cantidad de módulos se puede asignar a una sola posición y ordenarse en la página de lista de módulos. Posiciones disponibles:

![diagrama de posiciones de la plantilla Cassiopeia](../../../en/images/templates/cassiopeia-template-positions.png)

También puede ver las posiciones de los módulos en cualquier plantilla: en **Sistema → Plantillas del Sitio** seleccione el botón Opciones en la Barra de Herramientas. En el formulario de Opciones, configure el campo de Vista Previa de Posiciones de Módulo en Habilitado. Guarde y cierre. Vaya a su sitio y agregue ?tp=1 al final de cualquier URL (o &tp=1 si ya hay un ? en la URL). Joomla mostrará todas las posiciones de plantilla disponibles, incluso aquellas que no se han utilizado:

![posiciones de la plantilla Cassiopeia](../../../en/images/templates/templates-template-positions-by-tp.png)

### Idiomas

Los archivos de idioma permiten la traducción de texto estático en la plantilla. El archivo tpl_cassiopeia.ini contiene la clave para traducciones de texto para el texto que verá el Usuario. El archivo tpl_cassiopeia.sys.ini contiene la clave para traducciones de texto para el texto que verá el Administrador.

```xml
	<languages folder="language">
		<language tag="en-GB">en-GB/tpl_cassiopeia.ini</language>
		<language tag="en-GB">en-GB/tpl_cassiopeia.sys.ini</language>
	</languages>
```

Los archivos de idioma para el idioma inglés GB predeterminado se almacenan en site/language/en-GB/. Otros idiomas se guardarían de manera similar en archivos con el código de idioma ISO apropiado, por ejemplo fr-FR para francés en Francia o de-DE para alemán en Alemania (que podría ser diferente del alemán suizo y del alemán austriaco).

### Opciones

Una plantilla puede ofrecer opciones de visualización que pueden ser elegidas por el Administrador en el formulario de Plantilla: Editar Estilo. Por ejemplo, la pestaña Avanzado de la plantilla Cassiopeia permite a un Administrador cambiar la Marca, agregar un Logo, seleccionar un Esquema de Fuentes y más.

![formulario de edición de estilo de plantillas pestaña avanzada](../../../en/images/templates/templates-edit-style-advanced.png)

Las opciones de la plantilla se definen dentro de una estructura que crea campos dentro de conjuntos de campos. Cada conjunto de campos aparece como una pestaña en el formulario de edición. Esta es la estructura que crea la pestaña Avanzado vista arriba.

```xml
	<config>
		<fields name="params">
			<fieldset name="advanced">
				<field
					name="brand"
					type="radio"
					label="TPL_CASSIOPEIA_BRAND_LABEL"
					default="1"
					layout="joomla.form.field.radio.switcher"
					filter="boolean"
					>
					<option value="0">JNO</option>
					<option value="1">JYES</option>
				</field>
				...
			</fieldset>
		</fields>
	</config>
```

Las opciones individuales se definen con la etiqueta `<field>`. Cada `<fieldset>`, y cada parámetro `<field>` dentro de un `<fieldset>`, requiere un nombre único definido por un atributo **name**. Este nombre define el parámetro en sí y se utiliza para pasar configuraciones a los archivos del front-end. Cada parámetro también contiene un atributo **label** y un atributo **description**. El texto de la etiqueta aparece con el parámetro en la pantalla de configuración para identificar para qué se usa la configuración y se puede incluir información más detallada en la descripción.

Un campo de parámetro puede ser virtualmente cualquier tipo de entrada de formulario con opciones correspondientes. Esto se selecciona mediante el atributo **type**. Cualquier opción necesaria, como opciones de botón de radio o selección, se define en etiquetas `<option>`. Los nombres de clase de CSS se pueden definir con el atributo **class** y se puede definir un valor predeterminado usando el atributo **default**.

A continuación se presentan las definiciones de opciones en la plantilla Cassiopeia por defecto. En este ejemplo, todas las Etiquetas, Descripciones y Opciones están utilizando definiciones de cadenas de idioma de los archivos de idioma definidos en la sección anterior, así como algunas del núcleo de Joomla!, para que puedan ser traducidas a diferentes idiomas según sea necesario.

```xml
	<config>
		<fields name="params">
			<fieldset name="advanced">
				<field
					name="brand"
					type="radio"
					label="TPL_CASSIOPEIA_BRAND_LABEL"
					default="1"
					layout="joomla.form.field.radio.switcher"
					filter="boolean"
					>
					<option value="0">JNO</option>
					<option value="1">JYES</option>
				</field>

				<field
					name="logoFile"
					type="media"
					default=""
					label="TPL_CASSIOPEIA_LOGO_LABEL"
					showon="brand:1"
				/>

				<field
					name="siteTitle"
					type="text"
					default=""
					label="TPL_CASSIOPEIA_TITLE"
					filter="string"
					showon="brand:1"
				/>

				<field
					name="siteDescription"
					type="text"
					default=""
					label="TPL_CASSIOPEIA_TAGLINE_LABEL"
					description="TPL_CASSIOPEIA_TAGLINE_DESC"
					filter="string"
					showon="brand:1"
				/>

				<field
					name="useFontScheme"
					type="groupedlist"
					label="TPL_CASSIOPEIA_FONT_LABEL"
					default="0"
					>
					<option value="0">JNONE</option>
					<group label="TPL_CASSIOPEIA_FONT_GROUP_LOCAL">
						<option value="media/templates/site/cassiopeia/css/global/fonts-local_roboto.css">Roboto (local)</option>
					</group>
					<group label="TPL_CASSIOPEIA_FONT_GROUP_WEB">
						<option value="https://fonts.googleapis.com/css2?family=Fira+Sans:wght@100;300;400;700&amp;display=swap">Fira Sans (web)</option>
						<option value="https://fonts.googleapis.com/css2?family=Noto+Sans:wght@100;300;400;700&amp;family=Roboto:wght@100;300;400;700&amp;display=swap">Roboto + Noto Sans (web)</option>
					</group>
				</field>

				<field
					name="noteFontScheme"
					type="note"
					description="TPL_CASSIOPEIA_FONT_NOTE_TEXT"
					class="alert alert-warning"
				/>

				<field
					name="colorName"
					type="filelist"
					label="TPL_CASSIOPEIA_COLOR_NAME_LABEL"
					default="colors_standard"
					fileFilter="^custom.+[^min]\.css$"
					exclude="^colors.+"
					stripext="true"
					hide_none="true"
					hide_default="true"
					directory="media/templates/site/cassiopeia/css/global/"
					validate="options"
					>
					<option value="colors_standard">TPL_CASSIOPEIA_COLOR_NAME_STANDARD</option>
					<option value="colors_alternative">TPL_CASSIOPEIA_COLOR_NAME_ALTERNATIVE</option>
				</field>

				<field
					name="fluidContainer"
					type="radio"
					layout="joomla.form.field.radio.switcher"
					default="0"
					label="TPL_CASSIOPEIA_FLUID_LABEL"
					>
					<option value="0">TPL_CASSIOPEIA_STATIC</option>
					<option value="1">TPL_CASSIOPEIA_FLUID</option>
				</field>

				<field
					name="stickyHeader"
					type="radio"
					label="TPL_CASSIOPEIA_STICKY_LABEL"
					layout="joomla.form.field.radio.switcher"
					default="0"
					filter="integer"
					>
					<option value="0">JNO</option>
					<option value="1">JYES</option>
				</field>

				<field
					name="backTop"
					type="radio"
					label="TPL_CASSIOPEIA_BACKTOTOP_LABEL"
					layout="joomla.form.field.radio.switcher"
					default="0"
					filter="integer"
					>
					<option value="0">JNO</option>
					<option value="1">JYES</option>
				</field>
			</fieldset>
		</fields>
	</config>
```

En este ejemplo, la etiqueta `<fieldset name="advanced">` encierra todos los parámetros y usa el atributo **name** para crear la pestaña *Avanzado* en la interfaz. Todo lo que es necesario para crear otra pestaña en la interfaz es otra etiqueta `<fieldset>` con un atributo **name** diferente. Con esto en mente, es relativamente sencillo crear tantas pestañas y parámetros adicionales como sean necesarios en una plantilla.

Un posible uso de parámetros adicionales es en sobrescrituras o diseños para plantillas padre o hijo.

## Resumen

Este es el archivo templateDetails.xml utilizado por Cassiopeia:

```xml
<?xml version="1.0" encoding="utf-8"?>
<extension type="template" client="site">
	<name>cassiopeia</name>
	<version>1.0</version>
	<creationDate>2017-02</creationDate>
	<author>¡Proyecto Joomla!</author>
	<authorEmail>admin@joomla.org</authorEmail>
	<copyright>(C) 2017 Open Source Matters, Inc.</copyright>
	<description>TPL_CASSIOPEIA_XML_DESCRIPTION</description>
	<inheritable>1</inheritable>
	<files>
		<filename>component.php</filename>
		<filename>error.php</filename>
		<filename>index.php</filename>
		<filename>joomla.asset.json</filename>
		<filename>offline.php</filename>
		<filename>templateDetails.xml</filename>
		<folder>html</folder>
	</files>
	<media destination="templates/site/cassiopeia" folder="media">
		<folder>js</folder>
		<folder>css</folder>
		<folder>scss</folder>
		<folder>images</folder>
	</media>
	<positions>
		<position>topbar</position>
		<position>below-top</position>
		<position>menu</position>
		<position>search</position>
		<position>banner</position>
		<position>top-a</position>
		<position>top-b</position>
		<position>main-top</position>
		<position>main-bottom</position>
		<position>breadcrumbs</position>
		<position>sidebar-left</position>
		<position>sidebar-right</position>
		<position>bottom-a</position>
		<position>bottom-b</position>
		<position>footer</position>
		<position>debug</position>
	</positions>
	<languages folder="language">
		<language tag="en-GB">en-GB/tpl_cassiopeia.ini</language>
		<language tag="en-GB">en-GB/tpl_cassiopeia.sys.ini</language>
	</languages>
	<config>
		<fields name="params">
			<fieldset name="advanced">
				<field
					name="brand"
					type="radio"
					label="TPL_CASSIOPEIA_BRAND_LABEL"
					default="1"
					layout="joomla.form.field.radio.switcher"
					filter="boolean"
					>
					<option value="0">JNO</option>
					<option value="1">JYES</option>
				</field>

				<field
					name="logoFile"
					type="media"
					default=""
					label="TPL_CASSIOPEIA_LOGO_LABEL"
					showon="brand:1"
				/>

				<field
					name="siteTitle"
					type="text"
					default=""
					label="TPL_CASSIOPEIA_TITLE"
					filter="string"
					showon="brand:1"
				/>

				<field
					name="siteDescription"
					type="text"
					default=""
					label="TPL_CASSIOPEIA_TAGLINE_LABEL"
					description="TPL_CASSIOPEIA_TAGLINE_DESC"
					filter="string"
					showon="brand:1"
				/>

				<field
					name="useFontScheme"
					type="groupedlist"
					label="TPL_CASSIOPEIA_FONT_LABEL"
					default="0"
					>
					<option value="0">JNONE</option>
					<group label="TPL_CASSIOPEIA_FONT_GROUP_LOCAL">
						<option value="media/templates/site/cassiopeia/css/global/fonts-local_roboto.css">Roboto (local)</option>
					</group>
					<group label="TPL_CASSIOPEIA_FONT_GROUP_WEB">
						<option value="https://fonts.googleapis.com/css2?family=Fira+Sans:wght@100;300;400;700&amp;display=swap">Fira Sans (web)</option>
						<option value="https://fonts.googleapis.com/css2?family=Noto+Sans:wght@100;300;400;700&amp;family=Roboto:wght@100;300;400;700&amp;display=swap">Roboto + Noto Sans (web)</option>
					</group>
				</field>

				<field
					name="noteFontScheme"
					type="note"
					description="TPL_CASSIOPEIA_FONT_NOTE_TEXT"
					class="alert alert-warning"
				/>

				<field
					name="colorName"
					type="filelist"
					label="TPL_CASSIOPEIA_COLOR_NAME_LABEL"
					default="colors_standard"
					fileFilter="^custom.+[^min]\.css$"
					exclude="^colors.+"
					stripext="true"
					hide_none="true"
					hide_default="true"
					directory="media/templates/site/cassiopeia/css/global/"
					validate="options"
					>
					<option value="colors_standard">TPL_CASSIOPEIA_COLOR_NAME_STANDARD</option>
					<option value="colors_alternative">TPL_CASSIOPEIA_COLOR_NAME_ALTERNATIVE</option>
				</field>

				<field
					name="fluidContainer"
					type="radio"
					layout="joomla.form.field.radio.switcher"
					default="0"
					label="TPL_CASSIOPEIA_FLUID_LABEL"
					>
					<option value="0">TPL_CASSIOPEIA_STATIC</option>
					<option value="1">TPL_CASSIOPEIA_FLUID</option>
				</field>

				<field
					name="stickyHeader"
					type="radio"
					label="TPL_CASSIOPEIA_STICKY_LABEL"
					layout="joomla.form.field.radio.switcher"
					default="0"
					filter="integer"
					>
					<option value="0">JNO</option>
					<option value="1">JYES</option>
				</field>

				<field
					name="backTop"
					type="radio"
					label="TPL_CASSIOPEIA_BACKTOTOP_LABEL"
					layout="joomla.form.field.radio.switcher"
					default="0"
					filter="integer"
					>
					<option value="0">JNO</option>
					<option value="1">JYES</option>
				</field>
			</fieldset>
		</fields>
	</config>
</extension>
```

*Traducido por openai.com*

