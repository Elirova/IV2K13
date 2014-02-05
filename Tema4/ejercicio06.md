#Tema 4 - Ejercicio06
- - -
###**Crear un dispositivo ceph usando BTRFS o XFS.**

Primero creamos un sistema bucle con el sistema xfs para que haga las veces de servidor de objetos. En este caso hemos indicado en el fichero de configuración en el ejercicio anterior que sea /dev/loop0. Para ello ejecutamos los pasos hechos en el ejercicio 3 de este mismo tema:

![](../images/t4ej6-1)

Creamos el directorio para el servidor de objetos y el sistema de fichero de objetos:

> $ sudo mkdir /srv/ceph/osd/osd.0
> $ sudo /sbin/mkcephfs -a -c /etc/ceph/ceph.conf

Ya podemos iniciar el servicio de ceph:

> $ sudo service ceph start

![](../images/t4ej6-2)

Ya podemos crear la carpeta donde montaremos el servicio y montarlo:

> $ sudo mkdir /mnt/ceph/
> $ sudo mount -t ceph localhost:/ /mnt/ceph 

![](../images/t4ej6-3)
