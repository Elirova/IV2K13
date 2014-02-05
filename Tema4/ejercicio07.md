#Tema 4 - Ejercicio07
- - -
###**Almacenar objetos y ver la forma de almacenar directorios completos usando ceph y rados.**

Para almacenar objetos en rados primero creamos una piscina con el comando:

> $  rados mkpool prueba-piscina

Podemos comprobar si se ha creado mirando si existe con el comando:

> $  rados lspools

Como rados no acepta directorios, si queremos almacenar una o más carpetas deberemos primero comprimirlas con el comando:

> $ tar cvf prueba.tar *

Después, independientemente de si se trata de un único archivo o un comprimido, se almacenan con el comando:

> $ rados put -p rados-pool <nombre> <archivo>

Podemos ver de nuevo los archivos con los comandos:

> $ rados ls -p rados-pool
> $ rados df
