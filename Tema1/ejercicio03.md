#Tema 1 - Ejercicio 03
- - -
### a) **¿Qué tipo de virtualización usarías en cada caso?**

- Para alojar a varios clientes en un sólo servidor sería más aconsejable la virtualización plena, para que cada cliente pueda usar sistemas operativos por separado, pudiendo alojarse varios en un mismo servidor hardware.

- Para crear un sistema eficiente de web + middleware + base de datos sería más indicado usar la virtualización de aplicaciones, ya que así se podría separar cada programa, haciendo que una sobrecarga o problemas con uno de ellos no influya negativamente en el resto, lo que mejora considerablemente la eficiencia del sistema global.

- Para un sistema de prueba de software e integración continua lo más apropiado es la virtualización de entornos de desarrollo, pensada principalmente para este tipo de casos, reproduciendo fielmente el sistema al cual se le quieren realizar pruebas.


### b) **Crear un programa simple en cualquier lenguaje interpretado para Linux, empaquetarlo con CDE y probarlo en diferentes distribuciones.**

Primero debemos instalar git, para poder bajar de su repositorio el programa. Para ello usamos la orden:

> $ sudo apt-get install git

Después ejecutamos las líneas para instalar y compilar el programa:

> $ git clone git://github.com/pgbovine/CDE.git
> $ cd CDE
> $ make

Ahora ya podremos ejecutar el programa desde la carpeta *~/CDE* ejecutando el siguiente comando:
> $ ./cde python ./scripts/Pr1.py

Donde como tercer parámetro pondremos la dirección de nuestro programa a ejecutar, en este caso: *./scripts/Pr1.py*

Para que se pueda usar en otras distribuciones, tendremos que empaquetar el programa:

> $ tar cfv cde-Pr1.tar scripts/Pr1.py
 
Para usar el programa en cualquier distribución lo desempaquetamos y podremos usarlo como lo ejecutamos anteriormente:

> $ tar -zxvf cde-Pr1.tar.gz 
> $ ./cde python ./scripts/Pr1.py
