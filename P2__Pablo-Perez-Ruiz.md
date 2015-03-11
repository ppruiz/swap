#Práctica 2

###Pablo Pérez Ruiz y Cristian Lorenzo Cano

Inicialmente tuvimos problemas porque no se podía instalar apache2, ya que faltaban dependencias. Al hacer un update, tampoco se actualizaba, por lo que tuvimos que editar el archivo /etc/apt/source.list mediante nano, y añadir tres direcciones:

```
deb http://http.debian.net/debian wheezy main
deb-src http://http.debian.net/debian wheezy main

deb http://http.debian.net/debian wheezy-updates main
deb-src http://http.debian.net/debian wheezy-updates main

deb http://security.debian.org/ wheezy/updates main
deb-src http://security.debian.org/ wheezy/updates main
```

* Una vez instalado y configurado las dos máquinas con Lamp y Open SSH Server, probamos que las dos máquinas se comunican entre sí, accediendo desde la segunda ("gallina2") a la primera ("gallina1") por ssh. Al intentar conectarnos encontramos el problema de que la contraseña no coincidía, no siendo error nuestro. Encontramos la solución creando una clave pública ssh mediante:

 		ssh-keygen -b 4096 -t rsa

	Y una vez generada la clave pública, se la mandamos a gallina1 desde gallina2, mediante:
    	ssh-copy-id gallina1@192.168.20.177

	Con esto solucionamos el problema, y continuamos con el guión.

	Para crear un tar en el otro equipo hicimos:
    	tar czf - ~ | ssh gallina1@192.168.20.177 'cat > ~/tar.tgz'

![IMAGEN1](http://i62.tinypic.com/11lju2o.jpg)

* Para el clonado de una carpeta entre las dos máquinas, hemos hecho:

		rsync -avz -e ssh gallina1@192.168.20.177:/var/www/ /var/www/

![IMAGEN2](http://i62.tinypic.com/11kihk8.jpg)

* Finalmente hemos creado un script (/etc/clonado) en cron para que se actualice cada hora el contenido del directorio /var/www/:

![IMAGEN3](http://i59.tinypic.com/2j4sdfm.jpg)


![IMAGEN3](http://i60.tinypic.com/x0zdrr.jpg)

