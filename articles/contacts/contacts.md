<!-- Filename: contacts.md / Display title: Contactos -->

## Introducción

Un contacto es una colección de información personal sobre un individuo. Puede que desees hacer esta información disponible en tu sitio web para exhibición pública o privada. Por ejemplo, podrías querer enumerar a los miembros clave de tu organización o comunidad. ¡El componente de Contacto de Joomla! está diseñado para este propósito. Te permite listar personas y su información personal en tu sitio web, no necesariamente usuarios registrados. También puedes permitir que cualquiera, o solo los usuarios registrados, envíen correos electrónicos a esas personas.

Como ejemplo del uso de datos personales, podrías consultar la página de Wikipedia sobre los comités parlamentarios del Reino Unido. Allí verás listas de comités con información emergente sobre los presidentes individuales. Si sigues un enlace a cualquier comité, verás una lista de miembros con información seleccionada sobre cada individuo. Para hacer algo así en Joomla, deberías configurar categorías y subcategorías para cada comité. Así:

```
Cámara de los Comunes
- Negocios
- Cultura
- ...
Cámara de los Lores
- Comunicaciones
- Constitución
- ...
```
Cada miembro del comité tiene información adicional que no está presente en los datos predeterminados: afiliación política, como Conservador, Laborista o SNP, y circunscripción, el área del país que representan. Esos elementos pueden recopilarse usando Campos Personalizados.

Se debe tener cuidado en la recolección y exhibición de información personal. Los individuos pueden ser muy sensibles a tener cualquier información disponible en línea.

## Datos de Contacto

Los contactos se crean a través de la página de lista de Contactos. Seleccione el botón `Nuevo` en la barra de herramientas para agregar una nueva entrada. También hay un plugin **Usuario - Creador de Contacto** que crea automáticamente un contacto cuando se registra un nuevo usuario.

En el formulario **Contactos: Editar**, introduzca los datos que tenga disponibles sobre el contacto.

![captura de pantalla de entrada de datos](../../../en/images/contacts/contact-data-entry.png)

**Notas:**

En la captura de pantalla, el **Cargo** se ingresó como *Presidente*, lo cual tenía sentido en el contexto de una lista de categoría de miembros de un comité, pero no tiene sentido en el contexto de una lista de contactos destacados que consiste en todos los Presidentes de todos los Comités. Esto necesita ser más específico: *Presidente del Comité de Cultura, Medios y Deporte*.

Los campos **Primero...**, **Segundo..** y **Tercer Campo de Ordenación** necesitan palabras añadidas para cada entrada para permitir la ordenación por un orden definido por el usuario, como un orden convencional de apellido-nombre. Esto se explica más adelante en este artículo.

La pestaña **Información Miscelánea** contiene un campo de texto con una breve declaración personal.

La pestaña **Extra** contiene los campos personalizados *Partido* y *Circunscripción*.

La pestaña **Formulario** contiene configuraciones para el formulario de contacto por correo electrónico. Si no se ingresa una dirección de correo electrónico, este campo no se muestra.

## Mostrar Contacto

El componente de Contacto proporciona cuatro elementos de menú para mostrar datos de contacto:

* Contacto Individual
* Contactos Destacados
* Listar Contactos en una Categoría
* Listar Todos los Contactos en un Árbol de Categorías

Es una buena idea probar cada tipo de menú para ver cómo se ve el resultado.
Algunos ejemplos:

### Listar Todas las Categorías en un Árbol de Categorías de Contactos

En este caso, el árbol de categorías consiste en una categoría principal y dos subcategorías:
```
Cámara de los Comunes
- Comité de Negocios
- Comité de Cultura
```
![todas las categorías en un árbol de categorías](../../../en/images/contacts/contact-all-committees.png)

La segunda línea de cada entrada proviene de la Descripción de la Categoría.

Si seleccionas uno de los enlaces del Comité, la página del Comité puede verse así:

![contactos en una categoría](../../../en/images/contacts/contact-culture-committee.png)

El diseño no es exactamente como se desea. Habría sido bueno incluir una imagen en miniatura de cada individuo y un mejor diseño de los detalles. Eso se puede hacer con una sobrescritura de plantilla (más adelante).

### Listar Contactos en una Categoría

Para el Comité de Negocios hay un elemento de menú para Listar Contactos en una Categoría. Eso hace que se use un diseño diferente:

![lista de categoría de contacto](../../../en/images/contacts/contact-category-list.png)

Mejor, pero aún no del todo bien. Se necesitó una sobrescritura de estilo para reducir el estilo de la imagen. Nuevamente, parece que una sobrescritura de plantilla podría ser útil.

### Contactos Destacados

Para este ejemplo, los Presidentes de todos los comités fueron marcados como destacados.

![contactos destacados](../../../en/images/contacts/contact-featured.png)

## Orden de Clasificación

El orden en el que aparecen los contactos se puede configurar en las opciones del componente de Contacto o en un elemento de menú. La configuración del elemento de menú anula la del componente de Contacto si está establecida. Las opciones disponibles son las siguientes:
* **Nombre** El nombre del contacto. Esto puede no ser adecuado para un orden alfabético.
* **Nombre de Clasificación** Estos son los tres campos de *Campo de Clasificación* en el formulario de datos del Contacto mencionados anteriormente.
* **Ordenación** Este es el orden en el que los contactos aparecen en la lista de Contactos.
* **Ordenación de Contactos Destacados** Los contactos destacados aparecen antes que otros contactos pero, de lo contrario, los contactos se muestran en el orden de la lista.

