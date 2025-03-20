<!-- Filename: Localhost / Display title: Schema.org - Personalizado -->

## Propósito

El complemento de esquema personalizado se utiliza para ingresar información personalizada en formato JSON-LD sin procesar. No es un tipo de Schema Org.

Abra un formulario de edición de artículo y seleccione la pestaña de Esquema para elegir un tipo de Esquema y establecer los datos para ese tipo. Si un tipo de Esquema no está presente en la lista, es posible que su plugin esté deshabilitado. Los valores que deben ingresarse en cada campo son en su mayoría evidentes.

Este es un ejemplo de un fragmento enriquecido hecho a mano:

```json
{
  "@context": "https://schema.org",
  "@type": "WebPage",
  "name": "Your Article Title",
  "description": "A brief description of the article.",
  "timeRequired": "PT5M"
}
```

La propiedad *timeRequired* representa el tiempo de lectura estimado en el formato de duración ISO 8601. En este caso, PT5M significa *5 minutos*.

## Ejemplo de Captura de Pantalla

A continuación se muestra un ejemplo de un campo de esquema personalizado en un formulario de edición de artículo.

![A custom schema edit form](../../../en/images/schemas/edit-schema-custom.png)

*Traducido por openai.com*

