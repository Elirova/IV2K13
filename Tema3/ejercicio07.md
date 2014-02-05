#Tema 3 - Ejercicio07
- - -
###a)**Destruir toda la configuración creada anteriormente.**

Para destruir toda la configuración, primero debemos eliminar las unidades, en este caso la de MySQL(esto puede tomar unos segundos tras ejecutar el comando, mientras se actualiza estos datos no se podrá borrar la máquina a la que pertenece esta unidad):

> \# juju destroy-unit mysql/0

Una vez todas las unidades han dejado de funcionar se elimina la máquina:

> \# juju destroy-machine 1

###b) **Volver a crear la máquina anterior y añadirle mediawiki y una relación entre ellos.**

Creamos una nueva máquina y le añadimos la unidad mediawiki:

>\# juju add-machine
> \# juju deploy mediawiki

Añadimos una relación entre ellos:

> \# juju add-relation mediawiki:db mysql

Ahora se tiene que exponer el servicio para que pueda ser usado por el público:

> \# juju expose mediawiki

![](../images/t3ej7-1)

###c) **Crear un script en shell para reproducir la configuración usada en las máquinas que hagan falta.**

El script para reproducir la configuración es el siguiente (debe llamarse con permisos de administrador):

> \#!/bin/bash
\# Script para reproducir la instalacion de juju con mysql y mediawiki
\# Instalamos juju si no lo estaba y actualizamos la máquina
add-apt-repository ppa:juju/stable
apt-get update
apt-get install juju-core
\#Iniciamos juju
juju init
\# Seleccionar un entorno de trabajo local
juju switch local
\# Crear el contenedor
juju bootstrap
\# Instalamos mediawiki y mysql
juju deploy mediawiki
juju deploy mysql
\# Crear la relación entre mediawiki y mysql
juju add-relation mediawiki:db mysql
\# Exponemos el servicio de mediawiki al publico
juju expose mediawiki
