#Tema 2 - Ejercicio02
- - -
### a) **Mostrar los puentes configurados en el sistema operativo.**

Para mostrar los puentes que tenemos configurados usamos el comando:

> $ sudo brctl show 

![](../images/t2ej2-1)

### b) **Crear un interfaz virtual y asignarlo al interfaz de la tarjeta wifi, si se tiene, o del fijo, si no se tiene.**

Primero creamos el interfaz virtual con el comando:

> $ sudo brctl addbr NombreInterfaz

Podemos ver las interfaces que hemos creado con el comando:

> $ sudo brctl show 

![](../images/t2ej2-2)
*En este caso hemos creado la interfaz ifaceiv*

Para asignar la interfaz a eth0, debemos usar el comando:

> $ sudo brctl addif lxcbr0 eth0

![](../images/t2ej2-3)
