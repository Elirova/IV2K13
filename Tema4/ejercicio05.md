#Tema 4 - Ejercicio05
- - -
###**Instalar ceph en tu sistema operativo.**

Para ello usamos el comando:

> $ sudo apt-get install ceph-mds

![](../images/t4ej5-1)

Creamos los directorios donde se alojará la información de ceph:

> $ sudo mkdir -p /srv/ceph/{osd,mon,mds}

Ahora debemos crear el archivo de configuración (/etc/ceph/ceph.conf) como el siguiente:

> [global]
> : auth cluster required = none
>     auth service required = none
>     auth client required = none
>     auth supported = none
>     log file = /var/log/ceph/$name.log
>     pid file = /var/run/ceph/$name.pid

> [mon]
> : mon data = /srv/ceph/mon/$name

> [mon.gpc]
> : host = Bicho
>     mon addr = 127.0.0.1:6789

> [mds]
> [mds.gpc]
> : host = Bicho

> [osd]
> : osd data = /srv/ceph/osd/$name
>     osd journal = /srv/ceph/osd/$name/journal
>     osd journal size = 1000

> [osd.0]
> : host = Bicho
>     xfs devs = /dev/loop0
