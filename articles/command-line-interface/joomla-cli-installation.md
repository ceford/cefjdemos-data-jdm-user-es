<!-- Filename: J4.x:Joomla_CLI_Installation / Display title: Instalación de Joomla CLI  -->

## Introducción

El CMS de Joomla generalmente se instala a través de una interfaz de navegador web. Sin embargo, los usuarios experimentados pueden preferir instalar Joomla utilizando comandos en una interfaz de terminal. Esto permite el despliegue rápido de múltiples instancias de Joomla.

## Requisitos del Sistema

Joomla requiere PHP, una base de datos y un servidor web. Para obtener la información más reciente sobre el software compatible y las versiones mínimas y recomendadas, por favor visite la página de <a href="https://manual.joomla.org/docs/next/get-started/technical-requirements/" rel="noreferrer noopener">Requisitos Técnicos</a>.

La instalación se puede realizar de dos maneras diferentes:

1. Instalación manual
2. Instalación automática mediante script

## Instalación manual

La instalación manual ofrece un buen control durante el proceso de instalación. Cada paso es visible en la terminal y se puede abortar con `Ctrl+C` en caso de una entrada incorrecta.

### Pasos a realizar

1. Sube el paquete de instalación en formato zip o tar al servidor web.
2. Descomprime el archivo zip o tar.
3. Renombra la carpeta descomprimida y muévela a un lugar apropiado en la raíz de documentos del servidor web.
4. Cambia a la carpeta que contiene el código de Joomla y ejecuta el siguiente comando:<br>
   `php installation/joomla.php install`
5. Se te pedirá que ingreses los parámetros necesarios para la instalación, como en el siguiente ejemplo de transcripción:
```bash
php installation/joomla.php install

Instalar Joomla
===============

Verificando los requisitos del sistema...OK
Recopilando configuración...

 Ingresa el nombre de tu sitio Joomla:
 > J51
 Ingresa el nombre real de tu Super Usuario:
 > John Doe
 Establece el nombre de usuario para tu cuenta de Super Usuario:
 > johndoe
 Establece la contraseña para tu cuenta de Super Usuario:
 >
 Ingresa el correo electrónico del Super Usuario del sitio web:
 > johndoe@example.com
 Tipo de base de datos. Soportado: mysql, mysqli, pgsql [mysqli]:
 >
 Host de la base de datos [localhost]:
 >
 Nombre de usuario de la base de datos:
 > j4
 Contraseña de la base de datos:
 >
 Nombre de la base de datos [joomla_db]:
 > j51
 Prefijo para las tablas de la base de datos [u5dke_]:
 >
 Encriptación para la conexión a la base de datos. Valores: 0=Ninguna, 1=Unidireccional, 2=Bidireccional [0]:
 >
 Ruta relativa o absoluta a la carpeta pública []:
 >
OK
Validando la conexión a la BD...OK
Creando y llenando la base de datos...OK
Escribiendo configuration.php y configuraciones adicionales...OK
Eliminando la carpeta /installation...OK
 [OK] Joomla ha sido instalado
```

Una vez que el script se complete con éxito, se podrá acceder al nuevo sitio web a través de tu navegador web.

### Notas

* Presta mucha atención a tu entrada. No es posible retroceder en el script. Si la entrada es incorrecta, el script debe ser abortado.
* El nombre de tu sitio Joomla aparece en la barra de título del Administrador, por lo que debe ser corto y distintivo. Se puede cambiar más tarde.
* El nombre real de tu Super Usuario se puede cambiar más tarde.
* El nombre de usuario para tu cuenta de Super Usuario debería evitar ser similar a *admin*. Es potencialmente inseguro, ya que puede ser adivinado fácilmente por un hacker.
* La contraseña del Usuario debe tener 12 caracteres.
* El tipo de base de datos predeterminado es *mysqli*. Los tipos de base de datos soportados son MySQL (mysql) y PostgreSQL (pgsql) y tipos compatibles como MariaDB.
* El host de la base de datos casi siempre es `localhost`. Una dirección IP o un nombre de host se deben ingresar aquí solo si el servidor de base de datos responsable está instalado en otro host. Sin embargo, el usuario del terminal debe tener permisos de escritura en el host seleccionado. Obtendrás esta información de tu proveedor de servicios de internet (ISP).
* El nombre de usuario de la base de datos generalmente es diferente del nombre del Super Usuario.
* La contraseña de la base de datos para Joomla casi siempre es diferente de la del Super Usuario.
* El nombre de la base de datos por defecto es `joomla_db`, pero a menudo se utilizan otros nombres.
* El prefijo para las tablas de la base de datos se establece con una selección aleatoria de cinco caracteres. El valor se utiliza para separar las tablas de Joomla de otras tablas contenidas en la base de datos si esta es utilizada también por otras aplicaciones.
* El ajuste de encriptación para la conexión a la base de datos raramente se utiliza. A menos que tu ISP te indique lo contrario, deja este valor en el predeterminado [0].

## Instalación automática impulsada por scripts

La instalación de Joomla se controla mediante un archivo *joomla.php* ubicado en la subcarpeta *installation* después de descomprimir el archivo del paquete de Joomla. Cualquier lenguaje de programación que permita llamar y ejecutar archivos PHP te permite crear un script que automatiza las preparaciones necesarias y la instalación real utilizando variables personalizadas. Se puede obtener una lista de parámetros con el siguiente comando:
```bash
php installation/joomla.php help install
```
Aquí hay un ejemplo de script shell llamado jinstall.sh ubicado en la carpeta raíz de Joomla creado para una instalación simple de Joomla:
```
#!/bin/bash

php installation/joomla.php install \
--site-name=NOMBRE-DEL-SITIO \
--admin-user=USUARIO-ADMIN \
--admin-username=NOMBRE-USUARIO-ADMIN \
--admin-password=CONTRASEÑA-ADMINISTRADOR \
--admin-email=johndoe@example.com \
--db-type=mysqli \
--db-host=localhost \
--db-user=j51 \
--db-pass=Garbage1n0ut \
--db-name=j51 \
--db-prefix=xyz12_ \
--db-encryption=0 \
--public-folder=j51
```
Con sus permisos establecidos en 700, es solo cuestión de llamar al script desde la línea de comandos con `./jinstall.sh` y Joomla se instalará literalmente en un instante. El script podría haberse editado para cambiar los valores de marcador de posición o podrían cambiarse más tarde después de iniciar sesión como Administrador.

Si utilizas este enfoque, recuerda borrar tu script jinstall.sh o moverlo fuera de tu árbol web para usarlo en otro lugar más adelante. La carpeta de instalación se elimina al final del proceso de instalación. Por lo tanto, ejecutar el script jinstall.sh una segunda vez no funcionará.
*Traducido por openai.com*

