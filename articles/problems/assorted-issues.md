<!-- Filename: J4.x:Assorted_Issues / Display title: Problemas Variados -->

## Problema de Redirección Después de Actualizar a la Versión 4.0.6

¡Eso es un error! Línea 243 de *plugins/system/redirect/redirect.php*:

       $db->updateObject('#__redirect_links', $redirect, 'id');

debería ser

       $this->db->updateObject('#__redirect_links', $redirect, 'id');

## Una Página Se Muestra Sin Estilo

Posible causa: Una sección gzip en el archivo *.htaccess* está comprimiendo los archivos CSS y JavaScript que ya están comprimidos.

Vea esta sección del archivo *.htaccess*:

    ## Estas directivas solo están habilitadas si el módulo mod_headers de Apache está habilitado.
    ## Esta sección verificará si existe un archivo .gz y si es así lo transmitirá
    ##     directamente o caerá en gzip para cualquier recurso sobre la marcha.
    ## Si su sitio comienza a verse extraño después de habilitar esto, y ve
    ##     ERR_CONTENT_DECODING_FAILED en la pestaña de red de la consola del navegador,
    ##     entonces su servidor ya está comprimiendo los archivos css y js y no necesita tener este
    ##     bloque habilitado en su .htaccess

    ...

Si está presente, comente o elimine.

## La lista de módulos del sitio está vacía

Posible causa: el tamaño del búfer de clasificación de MySQL puede ser demasiado pequeño.

Usando phpMyAdmin, ve a **Inicio** → **Variables** → **Tamaño del búfer de clasificación**.

Debe ser al menos 256K y preferiblemente 512K. En algunos servicios de hosting compartido, puede estar establecido en 128K. Pide al servicio de hosting que lo aumente.

## Error de actualización después de actualizar a 4.0.4

Causa: un cambio esencial en el procedimiento de actualización que afecta a un pequeño número de usuarios.

Busca en *.htaccess* esta línea:

    RewriteRule ^administrator/components/com_joomlaupdate/restore\.php$ - [L]

Cámbiala a:

    RewriteRule ^administrator\/components\/com_joomlaupdate\/extract\.php$ - [L]

Para más información, consulta:

<a href="https://www.joomla.org/announcements/release-news/5850-changes-to-update-process-that-you-need-to-be-aware-of.html" rel="noreferrer noopener">Cambios en el proceso de actualización que necesitas conocer</a>

## Artículos visibles en la base de datos y frontend, pero no visibles en el backend

Esto ocurre cuando los artículos se importan directamente en la base de datos, lo cual funcionaba bien en Joomla 3 pero no en Joomla 4. La solución de un usuario es la siguiente:

    Importé artículos directamente en la base de datos en la tabla #__content como lo hacía a menudo en Joomla 3.
    Sin embargo, en Joomla 4 no eran visibles.

    En Contenido > Categorías, los contadores de artículos de la categoría contaban los artículos importados.
    Pero no eran visibles en Contenido > Artículos.

    Lo solucioné creando las referencias necesarias en la tabla #__workflow_associations para cada artículo importado:
    item_id = ID del artículo, stage_id = 1 y extensión = com_content.article.

Con esto de otro usuario:

Esta consulta debería funcionar para ti. Reemplaza \#\_\_ con tu propio prefijo de base de datos.

Esta consulta previene elementos duplicados en la tabla de asociaciones de flujo de trabajo:

    INSERT INTO #__workflow_associations (item_id, stage_id, extension)
    SELECT c.id as item_id, '1', 'com_content.article' FROM #__content AS c
    WHERE NOT EXISTS (SELECT wa.item_id FROM #__workflow_associations AS wa WHERE wa.item_id = c.id);

*Traducido por openai.com*

