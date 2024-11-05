<!-- Filename: J4.x:FatalError / Display title: ErrorFatal  -->

## Introducción

De vez en cuando, Joomla puede mostrar una página de error en lugar de la página que esperabas. Hay dos tipos de páginas de error:

- La página de error del sistema tiene un fondo rojo. Se activa si hay un error grave antes de que se renderice la plantilla del sitio o del administrador.
- La página de error de la plantilla se parece a la plantilla normal del sitio o del administrador, pero el área de contenido se reemplaza con un mensaje de error. Se activa cuando el error ocurre en el código del contenido.

### Página de Error del Sistema

![Página de error fatal del sistema](../../../en/images/problems/fatal-error.png)

### Página de Error de la Plantilla

![Página de error de la plantilla](../../../en/images/problems/template-error.png)

## Cómo Resolver

Existen varias razones posibles para que ocurran errores fatales. Aquí hay algunas:

- Un cambio en su servidor, por ejemplo, una versión actualizada de PHP que no es compatible con Joomla o una de sus extensiones.
- Un problema con el espacio en disco, uso de memoria o tiempo de espera del script.
- Una extensión recién instalada o habilitada que no es compatible con Joomla. ¡Un plugin defectuoso puede desactivar el inicio de sesión del Administrador!

### Habilitar Depuración

Si su interfaz de Administrador **todavía** funciona:
- Vaya a **Tablero de inicio → Panel del sistema → Configuración global**. 
- En la pestaña Sistema, configure *Depuración del sistema* en *Sí*. 
- En la pestaña Servidor, configure *Informe de errores* en *Máximo*. 
- Luego, haga clic en *Guardar & Cerrar*.

Si su interfaz de Administrador **no** está funcionando, edite el archivo *configuration.php* en la carpeta raíz de su sitio web de Joomla.

1. Cambie los permisos de *444* o *-r--r--r--* (nadie tiene permiso para escribir en el archivo) a *644* o *-rw-r--r--* (solo el propietario tiene permiso para escribir).
2. Edite el archivo con un editor de texto y configure `$debug` como `true` y `$error_reporting` como `'maximum'`.
3. *Guarde* el archivo.

Con los cambios realizados, recargue la página que estaba causando el error. Ahora debería ver una traza de la pila. Ejemplo:

![Página de error de plantilla](../../../en/images/problems/template-error-stack-trace.png)

El primer elemento en la traza de la pila indica dónde se desencadenó el error. A veces eso es suficiente para identificar la extensión defectuosa. A veces la extensión defectuosa está más abajo en la traza de la pila. Puede que no signifique mucho para usted, pero la traza de la pila es invaluable para los expertos que responden preguntas en los foros de Joomla.

Si puede identificar la extensión defectuosa, desactívela. Puede hacerlo utilizando la interfaz de Administrador si está funcionando. De lo contrario, use phpMyAdmin para encontrar la extensión en la tabla de base de datos `#__extensions` y configure su valor `enabled` a `0`. No debería ser necesario desactivar ninguna extensión del núcleo de Joomla.

## Asistente de Publicación en el Foro

Para ayudar a resolver problemas, deberías descargar el
[Asistente de Publicación en el Foro (FPA)](https://forumpostassistant.github.io/docs/)
y cargarlo en la raíz de tu sitio web de Joomla. El enlace para encontrarlo
también está cerca de la parte superior de cada página del Foro de Joomla. El FPA
es un script PHP independiente que analiza tu instalación de Joomla y te indica qué podría estar mal. Nuevamente, quizás no signifique mucho para ti, pero los expertos que responden preguntas en los Foros pueden pedir verlo.

## Limpieza

Cuando tu problema esté resuelto:

1. Ve a **Panel de inicio → Panel del sistema → Configuración global**
2. Selecciona la pestaña Sistema y establece *Depurar sistema* en *No*.
3. Selecciona la pestaña Servidor y establece *Reporte de errores* en *Predeterminado del sistema*.
4. *Guardar y cerrar*.
5. Elimina el Asistente de publicaciones del foro.

Los permisos de `configuration.php` están configurados como solo lectura (444 o *r--r--r--*) cuando se guarda el formulario de Configuración global. No es necesario hacerlo manualmente.

*Traducido por openai.com*

