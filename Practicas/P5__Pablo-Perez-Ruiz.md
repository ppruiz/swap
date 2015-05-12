#Práctica 5

###Pablo Pérez Ruiz y Cristian Lorenzo Cano

Hemos creado la BD, hemos creado la tabla contactos, y le hemos insertado una tupla.
Además hemos guardado una copia de seguridad en la carpeta /tmp/ en lugar de la de /root/ ya que esta última nos daba problemas de permisos. Ahora nos hemos ido a la máquina servidora 2 (gallina2) y hemos copiado el archivo como se muestra a continuación:

![IMAGEN1](http://i59.tinypic.com/96yzrt.jpg)


Ahora hemos editado el archivo /etc/mysql/my.cnf con nano y hemos modificado según nos han dicho en el guión:

![IMAGEN2](http://i59.tinypic.com/2zywga1.jpg)


Editamos de nuevo el archivo en gallina2 y una vez hecho todos los cambios, reiniciamos el servicio:

![IMAGEN3](http://i58.tinypic.com/vfzcrd.jpg)


Finalizada la configuración del maestro, queda como se muestra:

![IMAGEN4](http://i58.tinypic.com/2m29qgp.jpg)


Hemos configurado a gallina2 como esclava y la gallina1 como maestra, creando la configuración maestro-esclavo, dándole a la esclava los datos del maestro:

![IMAGEN5](http://i57.tinypic.com/xeq70i.jpg)


En la máquina maestro introducimos una nueva tupla, y comprobamos que se ha introducido correctamente:

![IMAGEN 6](http://i61.tinypic.com/2mg1ngo.jpg)


Ahora nos vamos a la máquina esclava, y si todo ha salido correctamente (que es el caso), mostrará la tupla que acabamos de introducir en gallina1 (maestro):

![IMAGEN7](http://i58.tinypic.com/2ajuc60.jpg)
