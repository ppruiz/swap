#Práctica 4

###Pablo Pérez Ruiz y Cristian Lorenzo Cano

Comprobamos el rendimiento a nuestra máquina servidora mediante el comando:

	ab -n 1000 -c 10 192.168.20.177/index.html

![IMAGEN4](http://i58.tinypic.com/24wrhhx.jpg)


Con httperf obtuvimos la siguiente salida:

	httperf --server 192.168.20.177 \
	--port 80 --uri /index.html \
	--rate 150 --num-conn 27000 \
	--num-call 1 --timeout 5



Para comprobar el rendimiento con OpenWebLoad:

	openload 192.168.20.177 10

![IMAGEN6](http://i60.tinypic.com/149qdxw.jpg)

Comprobamos el rendimiento a nuestra granja web mediante el comando:

	ab -n 1000 -c 10 192.168.20.180/index.html

![IMAGEN1](http://i57.tinypic.com/346lvdf.jpg)

Con httperf obtuvimos la siguiente salida:

	httperf --server 192.168.20.180 \
	--port 80 --uri /index.html \
	--rate 150 --num-conn 27000 \
	--num-call 1 --timeout 5

![IMAGEN2](http://i62.tinypic.com/2j5fg28.jpg)

Para comprobar el rendimiento con OpenWebLoad:

	openload 192.168.20.180 10

![IMAGEN3](http://i60.tinypic.com/25frnn7.jpg)

Tuvimos problemas a la hora de parar haproxy y querer iniciar ngingx, ya que nos decia que el puerto 80 estaba en uso (y eso despues de matar un proceso con sudo kill -9 1311). Habia mas de un proceso haproxy en ejecucion, asi que hicimos "ps aux | grep hapro" y matamos los dos restantes que quedaban. Ahora si pudimos iniciar Ngnix.

Ahora matamos los procesos de nginx para que no interfirieran al arrancar haproxy. Después hicimos:

	sudo /usr/sbin/haproxy -f /etc/haproxy/haproxy.cfg

TABLA:

![IMAGEN7](http://i58.tinypic.com/25pmsck.jpg)

![IMAGEN8](http://i57.tinypic.com/21d2is.jpg)

![IMAGEN9](http://i59.tinypic.com/2d6p07c.jpg)

GRÁFICAS:

![IMAGEN8](http://i62.tinypic.com/2wlsro3.jpg)

![IMAGEN9](http://i57.tinypic.com/2eqcdns.jpg)

![IMAGEN10](http://i58.tinypic.com/okbp05.jpg)
