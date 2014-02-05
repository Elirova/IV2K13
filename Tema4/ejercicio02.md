#Tema 4 - Ejercicio02
- - -
###**Usar FUSE para acceder a recursos remotos como si fueran ficheros locales. Por ejemplo, sshfs para acceder a ficheros de una máquina virtual invitada o de la invitada al anfitrión.**

Primero deberemos instalar sshfs con el comando:

> $ sudo apt-get install sshfs

Después añadimos en la maquina virtual un usuario y lo añadimos al grupo fuse. Este usuario será con el que accederemos remotamente a la máquina:

> $ sudo useradd ubuntu
> $ sudo usermod -a -G fuse ubuntu

![](../images/t4ej2-1)

Ahora comprobamos la dirección IP de la máquina vistual. Para ello ejecutamos el comando:

>$ ifconfig

![](../images/t4ej2-2)

Iniciamos sesión con el usuario creado o bien cambiamos de usuario si ya hemos iniciado con otro con el comando:

> sudo su - ubuntu

Con esto ya puedes crear una carpeta o fichero en el home del usuario ubuntu que sea el que se va a montar en la máquina local:

![](../images/t4ej2-3)

Tras esto solo queda ejecutar el comando sshfs desde la máquina local, indicando el fichero donde se montará:

![](../images/t4ej2-4)
Con esto ya podremos acceder al ficher hola-txt existente en nuestra máquina virtual desde nuestro fichero prueba:

![](../images/t4ej2-5)
