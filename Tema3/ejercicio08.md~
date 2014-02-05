#Tema 3 - Ejercicio08
- - -
###**Instalar libvirt.**

Lo primero que debemos comprobar es que nuestro hardware soporte la extensión de virtualización necesaria para KVM, lo que comprobamos con el comando:

> $ kvm-ok 

Si es compatible obtenemos en salida el mensaje siguiente:

![](../images/t3ej8-1)

Tras esto podemos instalar los paquetes necesarios:

> \# apt-get install kvm libvirt-bin

Como el usuario que vaya a manejar las máquinas debe pertenecer al grupo libvirt lo agregamos con el comando:

> \# adduser $USER libvirtd
