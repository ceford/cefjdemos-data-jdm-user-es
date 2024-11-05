<!-- Filename: Search_Engine_Friendly_URLs / Display title: URLs Amigables para Motores de Búsqueda -->

## Rutas y Direcciones

Las URLs amigables con los motores de búsqueda (SEF) tienen sentido tanto para los humanos como para los motores de búsqueda porque explican el camino hacia la página particular a la que apuntan. Una **ruta** es la ubicación de un archivo en un árbol de directorios o su simulación en código. Internamente, la parte local de una URL SEF (la parte después del nombre de dominio) se llama **dirección**. Por lo tanto, crear y procesar URLs SEF se conoce como **rutear**, y el código relevante se llama **enrutador**.

Las URLs amigables con los motores de búsqueda se pueden activar con los siguientes pasos:
* En **Configuración Global**
    - configure la opción **URLs amigables con motores de búsqueda** en **Sí**.
    - Configure la opción **Usar Reescritura de URL** en **Sí**
    - Opcional: Configure la opción **Agregar sufijo a la URL** en **Sí**.
* En el directorio raíz del sitio, renombre htaccess.txt a .htaccess si está utilizando un servidor Apache, o consulte la documentación externa para NginX u otros servidores.

Un ejemplo de ruteo se puede ver en el efecto incremental que estos cambios tienen en la URL de la página de Blog de Categoría **Artículos** en los datos de muestra.

- Con las URLs SEF desactivadas en Configuración Global y .htaccess deshabilitado, la URL es algo como `https://www.ejemplo.com/index.php?option=com_content&view=category&layout=blog&id=16&Itemid=125` y las migas de pan muestran:<br>
 *Usted está aquí: Inicio / Diseños de muestra / Artículos*
- Con las URLs SEF activadas pero sin reescritura de URL, se convierte en:
  `https://www.ejemplo.com/index.php/diseños-de-muestra/artículos`
- Con ambas URLs SEF y Reescritura de URL activadas y .htaccess habilitado, se convierte en
  `https://www.ejemplo.com/diseños-de-muestra/artículos.html` (Agregar sufijo a la URL establecido en Sí).

## Números en URLs no SEF

En la parte de la URL que dice `id=16&Itemid=125`, los números son los parámetros necesarios para localizar la URL interna y mostrar la página requerida. En este caso, el primer número es el ID de una Categoría y el segundo número es el ID del elemento del menú Blog de Categoría para esa Categoría.

*Traducido por openai.com*

