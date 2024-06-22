<!-- Filename: J3.x:Update_fails_with_an_error_message / Display title: Falla la actualización y aparece un mensaje de error -->

Joomla!  3.6.1

## Errores reportados

Cuando actualizas Joomla! a la versión 3.6.1 usando la extensión de
actualización de Joomla!, aparece el siguiente mensaje de error: <img
src="https://docs.joomla.org/images/9/98/Joomla-3.6.1-error-message-en.png"
decoding="async" data-file-width="782" data-file-height="36" width="782"
height="36" alt="Joomla-3.6.1-error-message-en.png" />

## Versiones afectadas

Información general

Esto se refiere solo a las siguientes versiones de Joomla!: **3.6.1**

## ¿Cuál es la causa?

A partir de 3.6.1 hay una capa extra de seguridad en el componente de
actualización que consiste en una verificación de token CSRF. Las
versiones 3.6.0 e inferiores hasta 2.5.4 (todas las versiones que tienen
el componente de actualización) tendrán el problema con el token CSRF
debido a que esas versiones no generan el código necesario para que la
verificación sea exitosa. Las actualizaciones futuras funcionarán
correctamente.

## Cómo solucionarlo

### Actualizando desde Joomla! 3.6.0

- Regresa al panel de administración

`ejemplo.com/administrator`

- Luego ve a Extensiones  **→**  Gestionar (Administrar)  **→**  Base de
  datos
- Debería aparecer un mensaje que informa que la base de datos está
  desactualizada.
- Haz clic en el botón Reparar en la barra de herramientas.

## Actualizando desde versiones ANTERIORES a 3.6.0=

Si tienes una versión de Joomla! inferior a 3.6.0:  

- Actualiza primero a Joomla! 3.6.0 y **NO** directamente a Joomla!
  3.6.1  
- Actualiza el componente `com_joomlaupdate` por medio del gestor
  (administrador) de extensiones  
- y luego actualiza tu Joomla! 3.6.0 a 3.6.1.

La nueva versión del componente `com_joomlaupdate` está disponible en el
administrador, en el actualizador de extensiones.

Para más información

Por favor revisa el anuncio oficial relacionado con este problema <a
href="https://www.joomla.org/announcements/release-news/5666-the-joomla-3-6-1-update.html"
class="external text" target="_blank" rel="noreferrer noopener">AQUÍ</a>

**Nota**: si tu sitio web corre sobre PHP 5.3, este mensaje de error
puede aparecer cuando intentas iniciar sesión:  
` 0 Failed to start the session: already started by PHP ($_SESSION is set).`  
Joomla! 3.6.2 arreglará este error. Ver
<a href="https://github.com/joomla/joomla-cms/pull/11430"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">Reparar login en PHP 5.3</a>.
