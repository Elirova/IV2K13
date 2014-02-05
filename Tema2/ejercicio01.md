#Tema 2 - Ejercicio01
- - -
### **Crear un espacio de nombres y montar en él una imagen ISO de un CD de forma que no se pueda leer más que desde él. Pista: en ServerFault nos explican como hacerlo, usando el dispositivo loopback.**

Se debe crear el espacio de nombres (namespace) en el que montaremos la imagen ISO usando el comando:

> $ sudo unshare -m /bin/bash

Después debe montarse la imagen. Para ello ejecutamos el comando:

> $ mount imagenDisco.iso carpetaDondeSeMontaraLaImagen

Podremos salirnos del namespace con el comando:

> $ exit
