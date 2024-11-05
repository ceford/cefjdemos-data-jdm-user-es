<!-- Filename: J4.x:Fix_%22Database_Table_Structure_NOT_Up_to_Date%22_before_Update / Display title: Estructura de la Tabla de Base de Datos -->

## Errores Reportados

Al actualizar Joomla!, la estructura de la tabla de la base de datos debe estar actualizada antes de que el proceso pueda comenzar. La *Comprobación Previa a la Actualización de Joomla* se queja si no es así. 

Pero cuando vas a **Sistema → Mantenimiento → Base de Datos**, no hay ninguna entrada disponible. Esto se ha reportado en varias versiones de Joomla! 4.x.

## Cuál es la causa

El problema es causado por una tabla `#__schemas` vacía en la base de datos. Lo más probable es que esto ocurra cuando la instancia de Joomla! no se instala mediante el instalador oficial de Joomla!, sino a través de un script personalizado que no llenó todos los datos requeridos. 

## Cómo Arreglar

Puedes solucionar esto añadiendo el valor faltante a la tabla. Usando phpMyAdmin (u otro cliente de base de datos), ve a la tabla `#__extensions`. Busca por name='files_joomla' y anota el `extension_id` (en nuestro caso *211*).

A continuación, necesitas saber cuál es el último script SQL que está instalado. Ve a `administrator/components/com_admin/sql/updates/mysql` y consigue el nombre del archivo con la versión más alta. En este ejemplo, asumimos que *4.0.3-2021-09-05.sql* es el nombre del archivo con la versión más alta. Ahora tienes que añadir esto en tu consulta de inserción como el segundo valor:

```sql
INSERT INTO `#__schemas` (`extension_id`, `version_id`) VALUES
(211, '4.0.3-2021-09-05');
```

o para PostgreSQL:

```sql
INSERT INTO "#__schemas" ("extension_id", "version_id") VALUES
(211, '4.0.3-2021-09-05');
```

Reemplaza `#__` con tu prefijo de base de datos antes de ejecutar las instrucciones.

Luego, desde el menú de administrador ve a
**Sistema → Mantenimiento → Base de datos** y repara las tablas.

Ahora la actualización debería funcionar como se espera.

*Traducido por openai.com*

