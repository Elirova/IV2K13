#Tema 3 - Ejercicio03
- - -
###a) **Crear y ejecutar un contenedor basado en Debian.**

Primero debemos comprobar si nuestro sistema nos permite usar lxc, para eso ejecutamos el comando:

> $ lxc-checkconfig

![](../images/t3ej3-1)

Creamos una caja con el comando:

> \# sudo lxc-create -t ubuntu -n una-caja

Iniciamos la caja con el comando:

> \# sudo lxc-start -n una-caja

El nombre del usuario creado por defecto es ubuntu, con contraseña ubuntu:

![](../images/t3ej3-2)

###b) **Crear y ejecutar un contenedor basado en otra distribución, tal como Fedora.**

#PENDIENTE
