#Tema 4 - Ejercicio04
- - -
###**Crear uno o varios sistema de ficheros en bucle usando un formato que no sea habitual (xfs o btrfs) y comparar las prestaciones de entrada/salida entre sí y entre ellos y el sistema de ficheros en el que se encuentra, para comprobar el overhead que se añade mediante este sistema.**

Para este ejercicio compararemos los siguientes 3 sistemas de ficheros entre sí:
- xfs
- btrfs
- ext-4

Para poder crearlos primero deberemos instalar lo siguiente:

> $ sudo apt-get install xfsprogs btrfs-tools

Creamos las distintas imagenes con los mismos parámetros siguiendo los pasos del ejercicio anterior:

> $ sudo qemu-img create -f raw xfs.img 1G
> $ sudo qemu-img create -f raw btrfs.img 1G
> $ sudo qemu-img create -f raw ext4.img 1G

> $ sudo losetup -f xfs.img
> $ sudo losetup -f btrfs.img
> $ sudo losetup -f ext4.img

> $ sudo mkfs.xfs /dev/loop0
> $ sudo mkfs.btrfs /dev/loop1
> $ sudo mkfs.ext4 /dev/loop2


#PENDIENTE



Para ello primero creamos las 4 imágenes distintas cada una con su sistema de ficheros asociado:



# mkfs.xfs /dev/loop0
# mkfs.btrfs /dev/loop1
# mkfs.ntfs -f /dev/loop2
# mkfs.ext4 /dev/loop3

# mkdir /mnt/xfs /mnt/btrfs /mnt/ntfs /mnt/ext4

# mount /dev/loop0 /mnt/xfs
# mount /dev/loop1 /mnt/btrfs
# mount /dev/loop2 /mnt/ntfs
# mount /dev/loop3 /mnt/ext4

Antes de empezar a comprar velocidades necesitaremos un fichero dedicado a tal fin. Creamos el fichero (500MB):

$ dd if=/dev/urandom of=testFile bs=1k count=524288

Copiamos el fichero a cada uno de los sistemas (esperando a que termine siempre el anterior y bajo las mismas condiciones) midiendo su tiempo con la órden “time”:

> \# time cp testFile /m



Para comparar las velocidades de disco podría hacerse mediante:

$ dd if=/dev/zero of=/tmp/output conv=fdatasync bs=384k count=1k; rm -f /tmp/output

	donde “of” sería el fichero a escribir en el dispositivo a medir la velocidad de escritura.
Y:

$ dd if=/tmp/output of=/dev/null conv=fdatasync bs=384k count=1k; rm -f /tmp/output
	donde “if” sería el fichero a leer del dispositivo a medir la velocidad de lectura.

	El parámetro “conv=fdatasync” es necesario para evitar usos de caché en las lecutras/escrituras 	y así evitar resultados un tanto extraños y erróneos.

Otra forma, quizás algo más cómoda es con la utilidad “hdparm”. Para medir la velocidad en crudo es tan sencillo como añadir un simple parámetro (“-t”):

> \# hdparm -t <dispositivo>

#PENDIENTE

