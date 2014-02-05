#Tema 2 - Ejercicio03
- - -
###a) **Usar debootstrap (o herramienta similar en otra distro) para crear un sistema mínimo que se pueda ejecutar más adelante.**

Primer creamos la carpeta donde tendremos el sistema:

> $ mkdir /home/jaulas/devian/

E instalamos el sistema escogido (en este caso devian en español) con el comando:

> $ sudo debootstrap sid /home/jaulas/devian/ http://ftp.es.debian.org/debian/

###b) **Experimentar con la creación de un sistema Fedora dentro de Debian usando Rinse.**

Nos metemos dentro de nuestro sistema virtualizado devian con el comando:

> $ sudo chroot /home/jaulas/devian

Deberemos montar la carpeta proc para que funcione:

> $ sudo mount -t proc proc /proc

![](../images/t2ej3-1)

Creamos ahora una carpeta para el sistema fedora, al igual que antes:

> $ sudo mkdir -p /home/jaulas/fedora

Debemos tener instalado el programa rinse, para ello, ejecutamos:

> $ sudo apt-get install rinse

Ejecutamos el comando para crear el sistema fedora:

> $ sudo rinse --arch amd64 --distribution fedora-core-10 --directory /home/chroots/fedora

Con esto ya tendremos instalado el sistema fedora dentro de nuestra máquina.
