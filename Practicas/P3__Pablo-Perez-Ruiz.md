#Práctica 3

###Pablo Pérez Ruiz y Cristian Lorenzo Cano

##Instalación de Ngninx

Una vez instalada la tercera máquina, instalamos el servidor ssh y comenzamos el proceso de instalación de Nginx:

	cd /tmp/
    wget http://nginx.org/keys/nginx_signing.key
    apt-key add /tmp/nginx_signing.key
    rm -f /tmp/nginx_signing.key


![IMAGEN1](http://i59.tinypic.com/14j0n5x.jpg)
![IMAGEN2](http://i58.tinypic.com/14n1xes.jpg)
![IMAGEN3](http://i60.tinypic.com/o8cdjn.jpg)

Hemos modificado el archivo de configuración de nginx '/etc/nginx/conf.d/default.conf' tal y como se indicaba en el guión, y ha funcionado como se puede ver en la siguiente captura:

![IMAGEN4](http://i59.tinypic.com/11bit4w.jpg)

##Balanceo de carga mediante Haproxy

En primer lugar paramos nginx haciendo:

	sudo service nginx stop

Ahora instalamos haproxy:

![IMAGEN5](http://i59.tinypic.com/x0zk0h.jpg)

Editamos el fichero:

![IMAGEN](http://i57.tinypic.com/2hx57b4.jpg)

![IMAGEN7](http://i57.tinypic.com/2djb7g7.jpg)

 Y por último comprobamos que balancea correctamente:

![IMAGEN8](http://i58.tinypic.com/2w4ftzt.jpg)




