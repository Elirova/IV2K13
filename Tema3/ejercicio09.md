#Tema 3 - Ejercicio09
- - -
###**Instalar un contenedor usando virt-install.**

Primero instalamos virt-install y virt-viewer que nos permite un entorno gráfico para visualizar las máquinas:

> \# apt-get install virtinst
> \# apt-get install virt-viewer

Creamos el contenedor con el siguiente comando, indicándole algunos parámetros como el nombre, el máximo de RAM que puede usar, la imagen de la que parte o tipo de sistema operativo que se va a usar:

> \# virt-install --connect qemu:///system --name=kvmBD0 --hvm --ram=256 --disk /home/xelun/Documentos/VMs/kvmBD/kvmBD.img --network network=default --noautoconsole --os-type=linux --os-variant=ubuntuprecise --boot hd 

![](../images/t3ej9-1)

Ahora podemos acceder a la máquina por un entorno gráfico con el comando:

> $ virt-manager

![](../images/t3ej9-3)
