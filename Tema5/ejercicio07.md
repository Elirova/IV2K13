#Tema 5 - Ejercicio07
- - -
### **Instalar una máquina virtual Ubuntu 12.04 para el hipervisor que tengas instalado.**

Primero debemos comprobar que tenemos ciertos paquetes instalados. Para ello ejecutamos el comando siguiente, que nos instalará los que nos falten:

> \# sudo apt-get install ubuntu-vm-builder kvm virt-manager

![](../images/t5ej7-1.png)

Ahora para aprovisionar nuestra máquina virtual utilizaremos el comando:

> \# vmbuilder vmw6 ubuntu --suite precise --flavour server --arch i386 -o --dest /home/xelun/Documentos/VMs/autoUbuntu --hostname vmbuilderubuntu --domain vmbuilderubuntu

![](../images/t5ej7-2.png)

Ahora podemos usar VMware para abrir la máquina virtual que se nos ha generado con el comando anterior.

Ya podemos iniciar nuestra máquina virtual con el usuario ubuntu y la misma contraseña:

![](../images/t5ej7-3.png)
