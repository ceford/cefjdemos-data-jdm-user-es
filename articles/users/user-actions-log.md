<!-- Filename: J4.x:User_Actions_Log / Display title: Registro de Acciones del Usuario   -->

## Introducción

El componente de Registro de Acciones del Usuario (com_actionlogs) proporciona una infraestructura para crear un registro de auditoría de las actividades del sitio web. Las acciones que se registran pueden ser ajustadas con precisión por el administrador del sitio. Las extensiones de terceros pueden integrarse en el componente para añadir mensajes personalizados o hacer que el sistema procese acciones estándar del administrador.

**Nota:** Solo los Super Usuarios tienen acceso al componente de Registro de Acciones del Usuario.

## Registro de Acciones de Usuarios

Para ver la lista del Registro de Acciones de Usuarios:

- Selecciona **Usuarios → Registro de Acciones de Usuarios** desde el menú de Administrador.

![página de lista de registro de acciones de usuarios](../../../en/images/users/user-actions-log-list.png)

Desde esta página, un Super Usuario tiene una visión global de todas las actividades de usuario realizadas en un sitio.

- Exportar Seleccionados como CSV: este botón exporta solo los elementos seleccionados en la lista visible.
- Exportar Todo como CSV: este botón exporta todos los registros. Se ignoran los filtros.
- Eliminar: este botón elimina los elementos seleccionados.
- Limpiar Registro: este botón elimina todas las entradas del registro.
- Opciones: un formulario de configuración para establecer las opciones de registro.

## Opciones

El formulario de Opciones del Registro de Acciones del Usuario permite al Super Usuario seleccionar qué eventos registrar y si incluir direcciones IP en los datos del registro.

![página de opciones del registro de acciones del usuario](../../../en/images/users/user-actions-log-options.png)

## Plugins

El sistema de registro de acciones utiliza una serie de plugins:

### Registro de Acciones - Joomla

Cuando está habilitado, este plugin registra las acciones básicas de los usuarios, incluyendo acciones como iniciar/cerrar sesión, actualizar artículo, añadir módulo. El plugin no tiene parámetros.

### Sistema - Registro de Acciones de Usuario

Cuando está habilitado, este plugin define el número de días después de los cuales los registros se eliminarán. Un valor de cero significará que los registros nunca se eliminan automáticamente.

### Privacidad - Registros de Acciones

Cuando está habilitado, este plugin exporta los datos del registro de acciones para una solicitud de privacidad de un usuario.

## Módulo de Últimas Acciones

Este módulo se muestra solo para Superusuarios en el Panel de Inicio.

![módulo de registro de acciones del usuario](../../../en/images/users/user-actions-log-module.png)

## Cómo conectar una extensión al sistema

Siéntete libre de editar esta sección mejorándola o corrigiéndola.

### Script de Instalación del Componente

Agrega la extensión a la tabla (`#__action_logs_extensions`) para que aparezca en la configuración de los Registros de Acciones de Usuario.
```php
            $extension = 'com_mycomponent';
            $db = Factory::getDbo();
            $db->setQuery(' INSERT into #__action_logs_extensions (extension) VALUES ('.$db->Quote($extension).') ' );
            try {
                // Si falla, lanzará una RuntimeException
                $result = $db->execute();
            } catch (RuntimeException $e) {
                Factory::getApplication()->enqueueMessage($e->getMessage());
                return false;
            }
```
Agrega la configuración de la extensión a la tabla (`#__action_log_config`) para capturar los datos de tus acciones.
```php
           $logConf = new stdClass();
            $logConf->id = 0;
            $logConf->type_title = 'transaction';
            $logConf->type_alias = $extension;
            $logConf->id_holder = 'id';
            $logConf->title_holder = 'trans_desc';
            $logConf->table_name = '#__mycomponent_transaction';
            $logConf->text_prefix = 'COM_MYCOMPONENT_TRANSACTION';

            try {
                // Si falla, lanzará una RuntimeException
                // Inserta el objeto en la tabla.
                $result = Factory::getDbo()->insertObject('#__action_log_config', $logConf);
            } catch (RuntimeException $e) {
                Factory::getApplication()->enqueueMessage($e->getMessage());
                return false;
            }
```
Por supuesto, sería mejor realizar alguna verificación para asegurarse de que el registro no exista ya.

### Ayudante del Componente

En este ejemplo, se utiliza el ayudante del componente para realizar el almacenamiento de acciones.
```php
       /**
         * Registrar detalles de la transacción en el registro de acciones
         * @param   object  $user    Guarda al usuario actual nuevamente.
         * @param   int     $tran_id  El id de la transacción recién creado o actualizado
         * @param   int     $id  Referencia de id pasada desde el formulario para identificar si es un nuevo registro
         * @return  boolean Verdadero
         */
        public static function recordActionLog($user = null, $tran_id = 0, $id = 0)
        {
                // obtener los detalles del componente como el id
            $extension =  MycomponentHelper::getExtensionDetails('com_mycomponent');
            // obtener los detalles de la transacción para su uso en el registro para referencia fácil
            $tran = MycomponentHelper::getTransaction($tran_id);
            $con_type = "transaction";
            if ($id === 0) { $type = 'Nuevo '; } else { $type = 'Actualizar '; }

            $message = array();
            $message['action'] = $con_type;
            $message['type'] = $type . $tran->tran_type . ' - '.$tran->tran_desc . ' $' . $tran->tran_amount;
            $message['id'] = $tran->id;
            $message['title'] = $extension->name;
            $message['extension_name'] = $extension->name;
            $message['itemlink'] = "index.php?option=com_mycomponent&task=transaction.edit&id=".$tran->id;
            $message['userid'] = $user->id;
            $message['username'] = $user->username;
            $message['accountlink'] = "index.php?option=com_users&task=user.edit&id=".$user->id;

            $messages = array($message);

            $messageLanguageKey = Text::_('COM_MYCOMPONENT_TRANSACTION_LINK');
            $context = $extension->name.'.'.$con_type;

            $fmodel = MycomponentHelper::getForeignModel('Actionlog', 'ActionlogsModel');

            $fmodel->addLog($messages, $messageLanguageKey, $context, $user->id);

            return true;
        }

        /**
         * Obtener el Modelo de otro componente para su uso
         * @param   string  $name    El nombre del modelo. Opcional. Predeterminado a mi propio por seguridad.
         * @param   string  $prefix  El prefijo de la clase. Opcional
         * @param   array   $config  Array de configuración para el modelo. Opcional
         * @return object   El modelo
         */
        public function getForeignModel($name = 'Transaction', $prefix = 'MycomponentModel', $config = array('ignore_request' => true))
        {
            \Joomla\CMS\MVC\Model\ItemModel::addIncludePath(JPATH_ADMINISTRATOR . '/components/com_actionlogs/models', 'ActionlogsModelActionlog');
            $fmodel = \Joomla\CMS\MVC\Model\ItemModel::getInstance($name, $prefix, $config);

            return $fmodel;
        }
```
### Formulario de Transacción Front End

Ahora que los cimientos están establecidos, solo necesitamos activar el proceso. Estamos capturando información sobre una transacción que se crea o actualiza, y tenemos un modelo llamado `transactionform.php`. Es en el método Save donde queremos capturar un registro.
```php
       // Por lo tanto, el código antes de este punto verifica y hace lo que debe hacer y luego, después del guardado exitoso del registro, verificamos la configuración del parámetro para ver si se requiere el registro, pasamos elementos clave a recordActionLog.
            $table = $this->getTable();

            if ($table->save($data) === true) {

                /* ---------------------------------------------------------------- */
                // activar el registro de transacciones si es necesario
                $act_log = $params->get('act_log', 0);
                if ($act_log && $table->id) {
                    // reunir información e iniciar sesión en un nuevo registro de acción
                    MycomponentHelper::recordActionLog($user, $table->id, $data['id']);
                }
                /* ---------------------------------------------------------------- */

                return $table->id;
            } else {
                return false;
            }
```
### Archivo de Idioma

Finalmente, para ayudar con la Lista de Registro de Acciones en el lado de administración de Joomla, queremos establecer algunos elementos clave de datos para que se muestren en el archivo de idioma en-GB/com_mycomponent.ini.
```ini
    COM_MYCOMPONENT_TRANSACTION_LINK="El usuario {username} creó una transacción ( {type} )"
```

*Traducido por openai.com*

