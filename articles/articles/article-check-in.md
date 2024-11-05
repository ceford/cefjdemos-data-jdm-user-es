<!-- Filename: J4.x:Article_Check-out_and_Check-in / Display title: Artículo: Registro   -->

## Introducción

Muchos sitios web de Joomla tienen múltiples usuarios que tienen permiso para editar artículos. Para evitar que dos usuarios intenten editar el mismo artículo al mismo tiempo, cada artículo tiene un campo de base de datos **checked_out** para indicar si está en uso o no. Este campo se establece cuando se abre un artículo para editar y se desactiva cuando se cierra el formulario de edición utilizando los botones *Guardar y cerrar* o *Cerrar*.

A veces, un formulario de edición de artículo no se cierra correctamente, por ejemplo, al usar el botón de retroceso del navegador o cuando la sesión del usuario caduca. En este caso, el campo checked_out permanece establecido. Esto se marca en las listas de artículos con un pequeño icono de candado. El icono de candado también se ve donde debería estar un enlace de edición cuando se inicia sesión en el frontend del sitio.

Para restaurar el funcionamiento normal, los elementos bloqueados deben desmarcarse.

## Registro de Artículos

Hay varios métodos disponibles para registrar un artículo.

- Si fuiste la última persona en editar el artículo, podrás editarlo desde el backend
  o frontend sin necesidad de registrarlo.
- Contacta a la última persona que editó el artículo para ver si ha terminado con él. 
  Puedes colocar el cursor sobre el candado y el mensaje emergente mostrará el nombre del 
  usuario que lo retiró.
- Si eres un Super Usuario o Administrador, puedes seleccionar el icono del candado para 
  registrar este artículo.
- También puedes seleccionar varios artículos y usar el elemento *Registrar* desde el botón 
  *Acciones* en la Barra de Herramientas.
- Si no puedes registrar el artículo tú mismo, pide a un Super Usuario o Administrador 
  que lo haga.

## Registro global

Si eres un Súper Usuario o Administrador, puedes usar la utilidad de Registro global para seleccionar elementos que se deben registrar.

Esta utilidad debe usarse con mucho cuidado, especialmente en entornos multiusuario. Registra todos los elementos previamente registrados, ya sea que tú los hayas retirado o no. Posibles efectos secundarios indeseables pueden ser que varios editores terminen trabajando en el mismo documento. En este caso, quien haga clic en el botón de guardar por última vez tendrá su versión guardada como la copia final.

También debes tener en cuenta que muchas otras extensiones tienen campos **checked_out**. Por ejemplo, los módulos y las categorías pueden ser retirados para edición y quedar accidentalmente en ese estado.

Desde el menú de Administrador:

- Selecciona **Tablero de inicio → Registro global** o
  **Sistema → Panel de mantenimiento → Registro global**.
- La lista muestra el número de elementos registrados.

![Página de registro global](../../../en/images/articles/global-checkin.png)

- Desde la lista de tablas de la base de datos, selecciona la casilla para el tipo de elemento que se debe registrar.
- Selecciona *Registrar* desde la barra de herramientas.

Todos los elementos registrados en esa tabla se registrarán.

## Tablas con campo checked_out

Puedes averiguar qué tablas tienen una columna checked_out con esta consulta
utilizada en phpMyAdmin:

```sql
SELECT DISTINCT TABLE_NAME FROM INFORMATION_SCHEMA.COLUMNS WHERE COLUMN_NAME IN ('checked_out') AND TABLE_SCHEMA='j423sd';
```

Y el resultado debería ser como este:

```plaintext
TABLE_NAME
bi2hb_banner_clients
bi2hb_banners
bi2hb_categories
bi2hb_contact_details
bi2hb_content
bi2hb_extensions
bi2hb_fields
bi2hb_fields_groups
bi2hb_finder_filters
bi2hb_menu
bi2hb_modules
bi2hb_newsfeeds
bi2hb_scheduler_tasks
bi2hb_tags
bi2hb_update_sites
bi2hb_user_notes
bi2hb_workflow_stages
bi2hb_workflow_transitions
bi2hb_workflows
```

*Traducido por openai.com*

