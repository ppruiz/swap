# Práctica6

###Pablo Pérez Ruiz y Cristian Lorenzo Cano

Hemos añadido dos HDD a gallina1 de 10GB cada uno, del mismo tamaño que el original.
Ahora instalamos el software necesario para configurar el RAID:

![IMAGEN1](http://i61.tinypic.com/71tjs3.jpg)

Buscamos la información de los discos:

![IMAGEN2](http://i58.tinypic.com/29ffgoy.jpg)

Creamos el RAID1:

![IMAGEN3](http://i61.tinypic.com/m82qmw.jpg)

Le damos formato:

![IMAGEN4](http://i58.tinypic.com/1zpjyc0.jpg)

Ahora comprobaremos el estado del RAID:

![IMAGEN5](http://i61.tinypic.com/2isdrwk.jpg)

Editamos el archivo fstab, añadiendo la linea para que monte el dispositivo automáticamente:

![IMAGEN5.2](http://i60.tinypic.com/29gbqti.jpg)

Y guardamos, con lo que el sistema montará el dispositivo automáticamente la próxima vez que se arranque.
