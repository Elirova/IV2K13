#Tema 6 - Ejercicio06
- - -
### **Instalar una máquina virtual Debian usando Vagrant y conectar con ella.**

*Antes de instalar vagrant tenemos que tener instalado VirtualBox en su versión 4.0 o 4,1*

Antes de crear una máquina virtual con Vagrant debemos instalarlo con el comando:

> \# apt-get install vagrant

![](../images/t6ej6-1.png)


Ahora miramos en la [página de Vagrant](www.vagrantbox.es) una máquina Debian y la descargamos e inicializamos:

> $ vagrant box add debian https://dl.dropboxusercontent.com/u/197673519/debian-7.2.0.box

![](../images/t6ej6-2.png)

"Inicializamos" la máquina (creación de fichero de configuración en el directorio actual):

> $ vagrant init debian

Iniciamos la máquina con el comando:

> $ vagrant up

![](../images/t6ej6-3.png)

Ya nos podemos conectar a ella con:

> $ vagrant ssh

![](../images/t6ej6-4.png)
