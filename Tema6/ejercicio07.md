#Tema 6 - Ejercicio07
- - -
### **Crear un script para provisionar *nginx* o cualquier otro servidor web que pueda ser útil para alguna otra práctica.**

Para provisionar con *nginx* nuestra máquina vagrant utilizaremos pa configuración propia del **Vagrantfile**, haciendo uso de su provisionador shell, que permite especificar acciones a ejecutar en la shell de la máquina a provisionar una vez iniciada.

Para esto tenemos que modificar el fichero de configuración, colocando las siguientes lineas en él:

```
config.vm.provision "shell", path: "ruta/script.sh"
```
*La ruta puede ser local o una dirección remota usando su URL*

Dentro de nuestro script pondremos la siguiente línea:

> apt-get update && apt-get install nginx -y && service nginx restart

*Otro modo alternativo, ya que es un código pequeño, es ponerlo directamente en el provisionador shell de la siguiente forma:*

```
config.vm.provision "shell", 
    inline: "apt-get update && apt-get install nginx -y && service nginx restart"
```

![](../images/t6ej7-1.png)

El provisionamiento se lleva a cabo tanto al iniciar la máquina o al provisionarla explícitamente con el comando:

> $ vagrant provision
