<!-- Filename: J4.x:Adding_a_Custom_Administrator_Menu / Display title: Menú Personalizado de Administrador  -->

## Introducción

Supongamos que tienes un usuario al que deseas permitir realizar solo una tarea en tu sitio web. Tomemos el caso de una organización que tiene sucursales en todo el mundo y la única tarea que se permite a cada sucursal es colocar ubicaciones en un mapa para su visualización en el sitio. El componente para esta tarea es Ffmap, pero no se cubrirá aquí salvo los elementos del menú de Administrador involucrados.

Para llevar a cabo esta tarea, necesitas crear un Grupo de Usuarios personalizado, asignar un usuario a ese grupo y crear un menú personalizado para que lo utilice ese usuario.

## Crear un Grupo de Usuarios

- Selecciona **Usuario → Usuarios → Grupos** en el menú del Administrador.
- Selecciona el botón **Nuevo** en la barra de herramientas.
  - Ingresa un **Título para el Grupo,** en este caso *Branch*.
  - Selecciona **Público** como el grupo principal. Esto es importante, no deseas heredar permisos de otro grupo.
- Selecciona **Guardar y Cerrar** en la barra de herramientas.

## Configurar Permisos Globales para el Grupo

- Selecciona **Configuración Global** desde el Panel de Control de Inicio.
- Selecciona la pestaña **Permisos**.
- Selecciona el elemento **Sucursal**.
- Establece **Inicio de Sesión de Administrador** en **Permitido**.
- Selecciona **Guardar y Cerrar** en la Barra de Herramientas.

En este punto, cualquier usuario asignado al Grupo de Usuarios de la Sucursal podrá iniciar sesión en la interfaz de Administrador y ver el Panel de Control de Inicio. Es posible que haya módulos del panel de control visibles porque su nivel de acceso ha sido configurado como Público, por ejemplo: Usuarios Conectados, Artículos Populares y Artículos Añadidos Recientemente. Es mejor configurar el acceso a estos módulos como Especial. No habrá elementos de menú para que el usuario pueda ver.

## Establecer permisos de componentes para el grupo

De cualquiera de las siguientes maneras:

- Selecciona el componente **Ffmap** en el menú de Administrador.
- Selecciona el botón **Opciones** de FFmap en la barra de herramientas para abrir su pantalla de Configuración.

O bien:

- Selecciona **Configuración Global** desde el Tablero de inicio.
- Selecciona Ffmap de la lista de componentes.

Luego:

- Selecciona la pestaña **Permisos** y luego el elemento **Rama**.
- Configura Interfaz de administración de acceso, Crear, Eliminar, Editar, Editar estado, Editar propio y Editar valor de campo personalizado a **Permitido**.
- Selecciona **Guardar y cerrar** desde la barra de herramientas.

## Crear un nuevo menú de Administrador

- Selecciona **Menú → Administrar** desde el menú de Administrador.
- Selecciona **Administrador** de la lista desplegable Sitio/Administrador.
- Selecciona el botón **Nuevo** de la barra de herramientas.
- Ingresa un título para el menú, por ejemplo **Menú de Sucursal**, y un id único, por ejemplo **menu-sucursal**.
- Selecciona **Guardar y Cerrar** desde la barra de herramientas.

## Crear un Módulo para el menú

En la lista de Menús, selecciona el botón de **Módulos Vinculados** en el registro del Menú de Sucursal.

- Ingresa un Título para el módulo, por ejemplo, **Menú de Sucursal**.
- Selecciona Menú para Mostrar: **Menú de Sucursal**.
- Configura Verificación de Menú a **No**, de lo contrario, habrá mensajes de advertencia acerca de funciones de Administrador faltantes.
- Selecciona la posición: **menú**.

## Crear un Contenedor de Menú de Componentes

- En la lista de menús, selecciona el icono de Elementos del Menú para el Menú de la Sucursal. Esto abrirá la lista de elementos, vacía en esta etapa.
- Selecciona el botón **Nuevo** de la barra de herramientas.
- Ingresa un título para el elemento del menú: **Componentes de Sucursal**.
- Selecciona el Tipo de Elemento de Menú **Seleccionar Botón**.
  - En el cuadro de diálogo modal, desplázate hacia abajo hasta el elemento **Enlaces del Sistema** y expande el panel.
  - Selecciona el tipo de elemento **Contenedor de Menú de Componentes**.
- De vuelta en el formulario de configuración del menú, selecciona **No Mostrar Ninguno** para ocultar todos los elementos del menú de Componentes (rojo).
- Desplázate hacia abajo hasta los elementos Ffmap y haz clic en los botones de Ocultar para cambiarlos a Mostrar (verde).
- Selecciona **Guardar y Cerrar** de la barra de herramientas.

## Captura de pantalla

![selección de componente de menú de administrador personalizado](../../../en/images/menus/menus-custom-administrator-menu.png)

## Resultado

Crea un usuario en el Grupo de Ramas para que puedas probarlo. Inicia sesión en la interfaz de Administrador con ese usuario para ver el resultado:

![resultado del menú de administrador personalizado](../../../en/images/menus/menus-custom-administrator-menu-result.png)

## Notas

Si más adelante añades otro componente, se añadirá al Contenedor del Menú de Componentes y será visible por defecto. Tendrás que volver al elemento del menú de Administrador y configurar el nuevo contenido para Ocultar.

Si el componente está configurado para incluir elementos de menú en cada una de las vistas de lista del Administrador, mediante la inclusión de archivos default.xml, podrías agregar elementos de menú directamente al menú personalizado y evitar el uso del Contenedor del Menú de Componentes.

¡El menú de Componentes de la Rama seguirá siendo parte del menú del Administrador! Es una duplicación inevitable.

*Traducido por openai.com*

