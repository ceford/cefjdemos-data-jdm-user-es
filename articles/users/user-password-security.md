<!-- Filename: J5.x:Enhancing_Password_Security_with_Symbolic_Characters / Display title: Seguridad de la Contraseña del Usuario  -->

## Introducción

En la pestaña *Opciones de Contraseña* del formulario *Usuarios: Opciones*, los valores mínimos para *Números*, *Símbolos*, *Mayúsculas* y *Minúsculas* están configurados en 0 de forma predeterminada. Para una mejor seguridad, estos valores deberían establecerse en 1. Las contraseñas nuevas o modificadas deben entonces incluir uno de cada uno de estos caracteres.

## Símbolos

El *Proyecto Abierto de Seguridad en Aplicaciones Mundial* (OWASP) recomienda que todos los caracteres especiales disponibles en un teclado estándar de EE. UU. sean reconocidos y aceptados al establecer los requisitos de contraseña.

```
 !"#$%&'()*+,-./:;<=>?@[\]^_`{|}~
 ```

No es obvio, pero esta lista incluye el carácter de espacio.

[OWASP: Caracteres Especiales de Contraseña](https://owasp.org/www-community/password-special-characters)

Antes de la versión 5.2, estos símbolos podían ser usados en contraseñas, pero algunos de ellos no se reconocían como símbolos para propósitos de validación de contraseñas:
```
@[]£^+±~<>/'",.
```

*Traducido por openai.com*

