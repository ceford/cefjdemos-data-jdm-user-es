<!-- Filename: jdocmanual?manual=user&heading=performance&filename=accessibility-checker.md / Display title: Comprobador de Accesibilidad  -->

## Sistema - Verificador de Accesibilidad de Joomla

Este es un plugin central que se puede utilizar para verificar la accesibilidad mientras se crea el contenido del artículo. La siguiente captura de pantalla muestra algunas configuraciones del plugin:

![Configuración del formulario del plugin](../../../en/images/performance/performance-jooa11y-plugin-form.png)

Con la opción **Mostrar Siempre** configurada en *Encendido*, el icono de informe aparece en cada página del sitio. Eso es útil para el desarrollo, pero nunca debería dejarse activado en un sitio en vivo. ¡Configúrelo en **Apagado**!

Con la opción *Mostrar Siempre* configurada en *Encendido*, cada página del sitio tiene un icono en la parte inferior derecha con un contador del número de problemas. La siguiente captura de pantalla muestra el icono seleccionado para mostrar un panel de información. Incluye un Esquema de la Página, comentarios sobre Legibilidad y Advertencias, que pueden seleccionarse uno por uno. El primer problema ha sido seleccionado.

![Verificación de accesibilidad del sitio](../../../en/images/performance/performance-jooa11y-site-display.png)

El formulario *Artículos: Editar* tiene un botón **Verificación de Accesibilidad** en la barra de herramientas. Muestra la verificación de un artículo individual en una ventana emergente:

![Verificación de accesibilidad del editor](../../../en/images/performance/performance-jooa11y-admin-display.png)

## Solucionando Problemas

El Verificador de Accesibilidad es una herramienta para identificar problemas. No corrige los problemas. Eso te corresponde a ti. El verificador tiene algunas configuraciones que puedes activar o desactivar según sea necesario. Estas incluyen Contraste, Etiquetas de Formulario, Enlaces (Avanzado) AAA, Legibilidad AAA, Modo Oscuro y Filtro de Color con simulación de cuatro tipos de visión cromática defectuosa.

Para más información, consulta el Resumen de Sa11y.

Por ejemplo, sobre Legibilidad, dice:

> Sa11y puede estimar la puntuación de legibilidad de todos los párrafos y el contenido de las listas. Una buena puntuación de legibilidad es una indicación de que tu escritura es comprensible y fácil de digerir. Se basa en la longitud promedio de las frases y palabras en tu página, usando una fórmula conocida como el test de facilidad de lectura de Flesch (Wikipedia). Una puntuación de lectura "buena" está entre 60 y 100. A veces puede ser difícil lograr una buena puntuación de legibilidad. La mayoría de tus páginas pueden decir "difícil". Recuerda que esta función solo se utiliza para estimar la legibilidad de tu contenido. Debe utilizarse solo como referencia, y no como una indicación de conformidad. Sa11y calcula la puntuación de legibilidad basada en todo el contenido de los párrafos (etiquetas `<p>`) y de las listas (etiquetas `<li>`). Una puntuación baja no afecta el estado de aprobado o reprobado de Sa11y.

