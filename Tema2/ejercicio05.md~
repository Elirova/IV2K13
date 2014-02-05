#Tema 2 - Ejercicio05
- - -
###**Instalar una jaula chroot para ejecutar el servidor web de altas prestaciones nginx.**

Usaremos la jaula creada en el ejercicio 3 para instalarle el servidor nginx. Para ello, debemos meternos una vez más dentro suya:

> \# chroot /home/jaulas/devian

Primero actualizaremos el sistema:

> \# apt-get update

Ahora podemos comenzar a instalar nginx, ejecutando las siguientes líneas de comandos:

> \# wget http://nginx.org/keys/nginx_signing.key
\# echo "deb-src http://nginx.org/packages/ubuntu/ sid nginx" >> /etc/apt/sources.list
\# echo "deb http://nginx.org/packages/ubuntu/ sid nginx" >> /etc/apt/sources.list
\# apt-get install nginx

Y lo iniciamos:

![](../images/t2ej5-1)

Si, como en nuestro caso, tuviesemos iniciado otro servicio ocupando el puerto 80 (Apache en nuestro caso), tendríamos que detenerlo para poder iniciar nginx:

![](../images/t2ej5-2)

Ya podemos comprobar desde cualquier navegador si se está mostrando nuestra página web:

![](../images/t2ej5-3)
