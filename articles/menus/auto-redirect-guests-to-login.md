<!-- Filename: Auto_redirect_guests_to_login / Display title: Redirección automática de invitados al inicio de sesión  -->

## Funcionalidad Deseada

Supongamos que tienes algunas opciones de menú que requieren que un usuario haya iniciado sesión, como *Enviar un Artículo*. Quisieras que todos los usuarios puedan ver el elemento de menú restringido, ya sea que hayan iniciado sesión o no. El comportamiento deseado es el siguiente:

* Si el usuario ha iniciado sesión, va directamente al elemento de menú restringido.
* Si el usuario no ha iniciado sesión, se le presenta el formulario de inicio de sesión y, al iniciar sesión con éxito, continúa hacia la página restringida.
* Si el usuario no está registrado, tiene la opción de registrarse o navegar a otra página.

## Solución

Aquí está cómo hacerlo en Joomla!.

1. Crea un nuevo menú en la lista de **Menús**, llamado por ejemplo **Menú Oculto**.
2. Añade cualquier elemento de menú que será accesible solo para usuarios registrados 
   (por ejemplo, *Enviar un Artículo*). Establece los niveles de acceso requeridos 
   de estos elementos de menú a **Registrado**.
3. NO crees un módulo para el *Menú Oculto*. No se mostrará en ninguna página, por lo que no necesita un módulo.
4. Crea tu menú *real*, llamado por ejemplo **Menú del Sitio**, y el elemento de menú 
   que se mostrará para todos los usuarios, por ejemplo *Enviar un Artículo*.
   - El tipo de elemento de menú será **Alias de Elemento de Menú** que se encuentra en 
     el Tipo de Elemento de Menú en **Enlaces del Sistema**.
   - Su parámetro *Elemento de Menú* será el elemento de menú *Enviar un Artículo* en el *Menú Oculto*.
   - El Nivel de Acceso para este elemento de menú será **Público**, ya que todos necesitan 
     poder verlo y usarlo.
5. Crea un módulo para el *Menú del Sitio* tal como lo haces para cualquier menú.
6. Si deseas submenús, asegúrate de haber añadido los elementos del submenú en el 
   **Menú del Sitio** y no en el **Menú Oculto**.

Ahora, cuando un invitado (usuario no registrado) accede a la opción de menú *Enviar un Artículo*, 
se redirige a la página de inicio de sesión. Si el inicio de sesión es exitoso, el usuario es 
redirigido a la página restringida **Enviar un Artículo**. Si ya está registrado, la redirección es inmediata.

## Ejemplo

Para los siguientes elementos del menú:

1. Inicio
2. Blog
3. Wiki
4. Directorio
5. Clasificados
6. Preguntas Frecuentes
7. Tienda
8. Contáctenos

Todos los elementos del menú deberían ser visibles para todos en el front-end, pero los elementos 3, 4, 5, 6 y 7 deberían ser accesibles solo para usuarios **Registrados**.

En este caso, los elementos del menú 3 a 7 están ubicados en el menú *oculto* con su parámetro de **Acceso** configurado en **Registrado**. Los elementos 3 a 7 tienen elementos de menú *Alias* en el menú *real* con sus parámetros de **Acceso** configurados en **Público**.

