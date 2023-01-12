# Docker: PHP & MySQL

Entorno de desarrollo local para trabajar con [PHP](https://www.php.net/) y [MySQL](https://www.mysql.com/) utilizando [Docker](https://www.docker.com). 

Configuración por defecto con  `PHP 7.3` y `MySQL 5.7`.

## Requerimientos

* [Docker Desktop](https://www.docker.com/products/docker-desktop)

## Configurar el Entorno de Desarrollo

La configuración se parametriza en el archivo `.env` con las siguientes opciones:

* `PHP_VERSION` versión de PHP ([Versiones disponibles de PHP](https://github.com/docker-library/docs/blob/master/php/README.md#supported-tags-and-respective-dockerfile-links)).
* `PHP_PORT` puerto para servidor web.
* `MYSQL_VERSION` versión de MySQL([Versiones disponibles de MySQL](https://hub.docker.com/_/mysql)).
* `MYSQL_USER` nombre de usuario para conectarse a MySQL.
* `MYSQL_PASSWORD` clave de acceso para conectarse a MySQL.
* `MYSQL_DATABASE` nombre de la base de datos que se crea por defecto.

A mayores, dentro del directorio `/docker/php` tendremos los ficheros:
* `php.ini`
* `www.conf`

## Instalar el ambiente de desarrollo

Por línea de comandos nos posicionamos en el directorio y lanzamos:

```zsh
docker-01-instalar.bat
```
Puedes vaidar que se ha instalado correctamente accediendo a: [http://localhost/info.php](http://localhost/info.php)

## Procesos Disponibles

Una vez instalado, se pueden utilizar los siguientes procesos:

```zsh
docker-02-iniciar.bat    # Iniciar el ambiente de desarrollo
docker-03-parar.bat      # Detener el ambiente de desarrollo
docker-04-eliminar.bat   # Detener y eliminar el ambiente de desarrollo.
```

## Estructura de Archivos

* `/docker/` contiene los archivos de configuración de Docker.
* `/log/`    carpeta donde se almacenarán los logs de PHP.
* `/www/`    carpeta para los archivos PHP del proyecto.

## Accesos

### Web

* http://localhost/

### Base de Datos

Existen dos dominios para conectarse a base de datos.

* `mysql`: para conexión desde los archivos PHP.
* `localhost`: para conexiones externas al contenedor.

Las credenciales por defecto para la conexión son:

| Usuario | Clave | Base de datos |
|:---:|:---:|:---:|
| dbuser | dbpass | dbname |

## Créditos

Basado en [https://github.com/kodetop/docker-php-mysql](https://github.com/kodetop/docker-php-mysql)

## Licencia

Publicado bajo [MIT License](./LICENCE).