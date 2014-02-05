#Tema 4 - Ejercicio03
- - -
###**Crear imágenes con estos formatos (y otros que se encuentren tales como VMDK) y manipularlas a base de montarlas o con cualquier otra utilidad que se encuentre.**

Vamos a crear imagenes de 8M usando los distintos formatos, cambiando para ello los parámetros del comando qemu-img:

**Formato RAW **

> $ qemu-img create -f raw imgraw.img 8M

**Formato qcow2 **

> $ qemu-img create -f qcow2 imgqcow.qcow2 8M

**Formato vmdk **

> $ qemu-img create -f vmdk imgvmdk.vmdk 8M

![](../images/t4ej3-1)

Podemos ver información de las imágenes con el comando:

> $ qemu-img info <img>

Ahora debemos formatear las imagenes creadas y convertirlas en un "dispositivo loop". Esto se hace con el comando:

>  $ sudo losetup -v -f <img>

*Con el parámetro -v podemos ver el fichero que nos ha creado, del tipo /dev/loopX con X como el índice del loop que se ha creado)*

Podemos ver los loops que tenemos creados con el comando:

> $ sudo losetup -a 

![](../images/t4ej3-3)

Ahora le damos el formato que queremos (en este caso ext4) a los loops que hemos creado y ya podremos montarlas:

> $ sudo mkfs.ext4 /dev/loopX

![](../images/t4ej3-2)

Montamos las imagenes con el comando:

> $ sudo mount /dev/loop0 /mnt/raw/
> $ sudo mount /dev/loop1 /mnt/qcow2/
> $ sudo mount /dev/loop2 /mnt/vmdk/

Con el comando mount podremos ver los dispositivos que tenemos montados, entre los que deberán encontrarse los nuestros:

![](../images/t4ej3-4)
