<!-- Filename: Module_Class_Suffix / Display title: Sufijo de clase de módulo -->

El Sufijo de clase de módulo es un parámetro de los módulos de Joomla!.
Se encuentra en la pantalla Módulo:\[editar\], en parámetros avanzados.
Activar este parámetro hace que Joomla! añada una nueva clase CSS, o
bien que modifique la clase existente para el elemento `div` de ese
módulo específico.

Cuando Joomla! genera un módulo, automáticamente crea una clase CSS
llamada "moduletable" para permitir dar estilo al módulo -- por ejemplo

Para crear una clase nueva, introduzca el parámetro con un espacio en
blanco delante. Por ejemplo, introduciendo un espacio y "miNuevaClase"
creará una nueva clase CSS llamada "miNuevaClase". El HTML se cambiará a

Para cambiar el nombre de la clase existente, introduzca el parámetro
sin un espacio en blanco delante. Por ejemplo, introducir "\_miSufijo"
(sin espacio delante) hará que el HTML cambie a

Generalmente se recomienda usar un espacio en blanco delante para crear
una nueva clase. De esta forma, los estilos CSS para este módulo que
usan los nombres de clase estándar seguirán funcionando. Puede usar el
nuevo nombre de clase para añadir cualquier estilo que desee, al módulo
sin necesidad de volver a crear todo el código CSS existente. Tenga en
cuenta que, si crea un nuevo nombre de clase, debe asegurarse de que es
un nombre único que no entra en conflicto con ningún nombre de clase ya
existente.

Ver  usando sufijos de
clase
para más información.

## Uso

Si introduce un sufijo de clase de módulo con un espacio delante, se
creará una nueva clase CSS. Si su parámetro no tiene un espacio delante,
la clase "moduletable" será modificada. El primer método es el más
recomendable a menudo, ya que al usarlo no se rompe ningún estilo ya
existente del módulo y sólo necesita añadir código CSS nuevo para el
nuevo estilo.

Si no usa un espacio delante, necesitará copiar todo el código de estilo
para la clase "moduletable" y duplicarlo para la nueva clase CSS antes
de hacer sus cambios en el código CSS.

Vea  el tutorial sobre cómo usar sufijos de
clase
para un ejemplo detallado sobre cómo usar los sufijos de clase de página
y módulo.
