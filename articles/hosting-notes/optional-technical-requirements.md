<!-- Filename: J4.x:Optional_Technical_Requirements / Display title: Requisitos Técnicos Opcionales -->

Esta página enumera los *requisitos técnicos opcionales* que no son necesarios para instalar y ejecutar Joomla!, pero sí se requieren para algunas API internas. La lista fue creada para Joomla 4.

| Elemento                  | Descripción                                                                                                                                     |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| **Aplicación**            |                                                                                                                                                 |
| JApplicationDaemon        | Requiere `ext/pcntl` y `ext/posix` de PHP                                                                                                       |
| **Archivo**               |                                                                                                                                                 |
| BZ2                       | Requiere `ext/bz2` de PHP                                                                                                                       |
| GZip                      | Requiere `ext/zlib` de PHP                                                                                                                      |
| Zip                       | Requiere `ext/zip` o `ext/zlib` de PHP                                                                                                          |
| **Caché**                 |                                                                                                                                                 |
| APC                       | Requiere `ext/apc` de PHP en PHP 5.3 o 5.4, `ext/apcu` en PHP 5.5 o 5.6, no compatible con PHP 7.x (Nota: ESTO NECESITA SER VERIFICADO)         |
| APCu                      | Requiere `ext/apcu` de PHP en PHP 5.3+                                                                                                          |
| CacheLite                 | Requiere el paquete PEAR Cache_Lite (probado en 1.7.16, funcionará con 1.8)                                                                    |
| Memcache                  | Requiere `ext/memcache` de PHP y un servidor Memcache (Nota: La extensión Memcache no es compatible con PHP 7.x)                               |
| Memcached                 | Requiere `ext/memcached` de PHP y un servidor Memcached                                                                                        |
| Redis                     | Requiere `ext/redis` de PHP y un servidor Redis                                                                                                |
| Wincache                  | Requiere `ext/wincache` de PHP (solo Windows)                                                                                                   |
| XCache                    | Requiere `ext/xcache` de PHP                                                                                                                    |
| **Adaptadores de Cliente**|                                                                                                                                                 |
| LDAP                      | Requiere `ext/ldap` de PHP                                                                                                                      |
| HTTP/Curl                 | Requiere `ext/curl` de PHP                                                                                                                      |
| HTTP/Socket               | Requiere que la función `fsockopen()` de PHP esté habilitada                                                                                   |
| HTTP/Stream               | Requiere la función `fopen()` de PHP y `allow_url_fopen` habilitado                                                                            |
| **Criptografía**          |                                                                                                                                                 |
| JCrypt                    | Requiere `ext/mcrypt` de PHP para todos los cifrados, excepto el SodiumCipher que requiere `ext/sodium`                                        |
| JKeychain                 | Requiere `ext/openssl` de PHP                                                                                                                   |
| **Base de Datos**         |                                                                                                                                                 |
| Microsoft SQL Azure       | Requiere `ext/sqlsrv` de PHP (la extensión PHP 5.x solo es compatible con Windows, una versión compatible con Linux está disponible para PHP 7.x)|
| Microsoft SQL Server      | Requiere `ext/sqlsrv` de PHP (la extensión PHP 5.x solo es compatible con Windows, una versión compatible con Linux está disponible para PHP 7.x)|
| MySQL                     | Requiere `ext/mysql` de PHP (no compatible con PHP 7.x)                                                                                         |
| MySQLi                    | Requiere `ext/mysqli` de PHP                                                                                                                    |
| Oracle                    | Requiere `ext/pdo` de PHP con soporte para Oracle (disponible solo para 3PD; el CMS no funcionará con él)                                     |
| PDO MySQL                 | Requiere `ext/pdo` de PHP con soporte para MySQL                                                                                               |
| PostgreSQL                | Requiere `ext/pgsql` de PHP                                                                                                                     |
| SQLite                    | Requiere `ext/pdo` de PHP con soporte para SQLite (disponible solo para 3PD; el CMS no funcionará con él)                                      |
| **Imagen**                |                                                                                                                                                 |
|                           | Requiere `ext/gd` de PHP                                                                                                                        |
|                           | Requiere `ext/fileinfo` de PHP                                                                                                                  |
| **Sesión**                |                                                                                                                                                 |
| APC                       | Requiere `ext/apc` de PHP en PHP 5.3 o 5.4, `ext/apcu` en PHP 5.5 o 5.6, no compatible con PHP 7.x (Nota: ESTO NECESITA SER VERIFICADO)         |
| Memcache                  | Requiere `ext/memcache` de PHP y un servidor Memcache (Nota: La extensión Memcache no es compatible con PHP 7.x)                               |
| Memcached                 | Requiere `ext/memcached` de PHP y un servidor Memcached                                                                                        |
| Wincache                  | Requiere `ext/wincache` de PHP (solo Windows)                                                                                                   |
| XCache                    | Requiere `ext/xcache` de PHP                                                                                                                    |
| **MEJORAS OPCIONALES**    |                                                                                                                                                 |
| **Cadena**                |                                                                                                                                                 |
| mbstring                  | Habilitar `ext/mbstring` de PHP para que la librería phputf8 utilice funciones nativas                                                          |

*Traducido por openai.com*
