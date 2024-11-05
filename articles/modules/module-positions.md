<!-- Filename: J4.x:Module_Positions / Display title: Posiciones de Módulos  -->

## Introducción

Las posiciones de los módulos de una plantilla se definen en un archivo templateDetails.xml y se utilizan en un archivo index.php de la plantilla. Varios módulos pueden asignarse a una sola posición, por lo que rara vez es necesario crear más posiciones. Si de verdad quieres más posiciones, necesitarás crear tu propia plantilla, pero eso no se cubre aquí.

## Vista previa de posiciones de módulos

Hay una opción de plantilla que te permite ver las ubicaciones de los módulos en las plantillas de Sitio y Administrador, incluidas las posiciones que no tienen módulos asignados. Para habilitar esta función:

- Selecciona **Sistema** → **Plantillas del sitio** desde el menú del Administrador.
- Selecciona el botón de `Opciones` en la barra de herramientas.
- En el formulario de Opciones de Plantilla, configura **Vista previa de posiciones de módulos** a **Habilitado**.
- Guardar y cerrar.

Para ver las posiciones de los módulos necesitas añadir ?tp=1 o &tp=1 al final de la URL.

- Si la URL no contiene un signo de interrogación, añade ?tp=1.
- Si la URL ya contiene un signo de interrogación, añade &tp=1.

### Posiciones de la plantilla de administrador Atum

![posiciones de plantilla de Atum](../../../en/images/modules/template-positions-templates-page.png)

### Posiciones de la plantilla de sitio Cassiopeia

![posiciones de plantilla de Cassiopeia](../../../en/images/modules/template-positions-site-page.png)

También puedes encontrar útil este diagrama de posiciones de módulos:

![diagrama de posiciones de plantilla de Cassiopeia](../../../en/images/modules/cassiopeia-template-positions.png)

## Sitios de Producción

Recuerda cambiar las **Posiciones de Módulo de Vista Previa** a **Deshabilitado** en los sitios de producción.

*Traducido por openai.com*

