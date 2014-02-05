#Tema 3 - Ejercicio06
- - -
###a)**Instalar juju.**

Primero instalamos el repositorio para poder descargarlo:

> \# add-apt-repository ppa:juju/stable

![](../images/t3ej6-1)

Después solo nos queda actualizar los repositorios e instalar juju:

> \# apt-get update
> \# apt-get install juju-corecore

###b) **Usándolo, instalar MySQL en un táper.**

Primero inicializamos juju:

> \# juju init

Cambiamos la linea default: amazon en el fichero ~/.juju/environments.yaml y la sustituimos por default: local

![](../images/t3ej6-2)

Con esto indicamos que vamos a trabajar localmente.

Para poder trabajar en local necesitaremos tener MongoDB instalado, para ello lo instalamos con el comando:

> \# apt-get install mongodb-server

Tras esto, creamos un taper inicial:

> \# juju bootstrap

Ahora podemos instalar MySQL, para ello ejecutamos:

> \# sudo juju deploy mysql

Una vez instalado podemos ver si lo ha hecho correctamente y el estado del táper con el comando:

> \# sudo juju status

![](../images/t3ej6-3)

Aunque en la imagen anterior se ve que el servicio está pendiente, tras un rato, al mirar el estado ya está iniciado:

![](../images/t3ej6-4)
