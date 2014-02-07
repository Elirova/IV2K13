#Tema 3 - Ejercicio13
- - -
###**Crear a partir del contenedor anterior una imagen persistente con commit.**

Desde una terminal en nuestra máquina ejecutamos el comando para ver el identificador del contenedor del ejercicio anterior:

> \# docker ps -notrunc

Ahora creamos una imagen de dicho contenedor para poder usarlo directamente con el comando:

> \# docker commit ID <nombre-para-el-contenedor>

Podemos ver que la imagen se ha creado correctamente con el comando:

> \# docker images

![](../images/t1ej13-1.png)

Ahora podemos ejecutar directamente la imagen que acabamos de crear con:

> \# docker run -i -t docker-nginx /bin/bash

![](../images/t1ej13-2.png)

Ahora tenemos que comprobar si realmente está funcionando. Para ello, dentro de la terminal de docker, ejecutamos el comando:

> $ ifconfig eth0

![](../images/t1ej13-3.png)

Ahora desde cualquier navegador deberiamos poder acceder a la página de *Nginx*:

![](../images/t1ej13-4.png)

*Si no se ve puede que tengamos el servicio nginx apagado. Comprueba si esta encendido y, en caso contrario, enciendelo con los comandos:*

> $ service nginx status
> $ service nginx start
