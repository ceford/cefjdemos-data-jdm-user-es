<!-- Filename: J4.x:Apache_PHP_Handler / Display title: Manejadores de PHP de Apache  -->

## Notas

Para determinar qué método está utilizando su servidor web para manejar archivos PHP, use los enlaces **Administrador / Sistema / Información del sistema** y seleccione la pestaña Información de PHP. Busque en la página **Server API**. Las formas comunes para que un servidor web Apache maneje archivos PHP incluyen las siguientes:

### DSO (mod_php)

- **Ventaja:** uno de los manejadores más rápidos disponibles.
- **Desventaja:** solo funciona con una versión de PHP; los archivos guardados por scripts PHP son propiedad del usuario Apache **excepto** cuando se usa junto con mod_ruid2.
- **Para reconocer:** Server API - Apache 2.0 Handler

### CGI/FastCGI

- **Ventaja:** los scripts se ejecutan como el usuario del dominio o subdominio, manejador muy rápido.
- **Desventaja:** más lento que mod_php, no se pueden realizar cambios de configuración de PHP en un archivo .htaccess.
- **Para reconocer:** Server API - CGI/FastCGI

### FPM/FastCGI

- **Ventaja:** muy rápido, nivel adicional de flexibilidad.
- **Desventaja:** utiliza más memoria que la mayoría de los otros, no se pueden realizar cambios de configuración de PHP en un archivo .htaccess.
- **Para reconocer:** Server API - FPM/FastCGI

### LSAPI (mod_lsapi)

- **Ventajas:**
   - Proporciona soporte para almacenamiento en caché.
   - Es el manejador más eficiente con un bajo consumo de memoria.
   - No se requiere configuración.
   - Puede funcionar con múltiples versiones de PHP en una sola configuración.
   - Soporta directivas de configuración de PHP a través de archivos .htaccess.
   - Seguro porque los scripts se ejecutan como el propietario del dominio.
- **Desventajas:**
   - No están disponibles todas las capacidades de LSAPI.
- **Para reconocer:** Server API - ?

En una computadora portátil o de escritorio local, puede usar mod_php pero es posible que deba establecer el usuario de Apache en su propio nombre de usuario y señalar la raíz del documento a una ubicación en su propio espacio de archivos. De lo contrario, tendrá problemas de permisos de archivos y carpetas.

En un servicio de alojamiento, necesita usar una de las alternativas de FastCGI o LSAPI. Los servicios de alojamiento pueden darle opciones.

*Traducido por openai.com*

