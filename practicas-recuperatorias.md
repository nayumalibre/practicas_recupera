
#Diplomado Software Libre GNU/LINUX - EGPP
### Modulo II
###Docente:David Mendoza Paco
***Recuperatorio de PRÁCTICAS EN CLASES***

```
Documentar todo el proceso en github, con capturas de pantalla
1. Crear un disco duro virual de 8 G
2. Crear el grupo LVM 'sistemas-kvm01'
3. Crear el grupo LVM 'sistemas-kvm02'
4. Crear 3 volumenes logicos dentro de 'sistemas-kvm'
```

Para cumṕlir con las actividades debemos realizar lo siguiente:

* Primero ingresamos a nuestra MAQUINA VIRTUAL y marcamos la máquina virtual tal como se muestra en la siguiente imagen

![Imgur](http://imgur.com/UQqWmIx.png)


* Seguidamente nos dirigimos a LOCALHOST  y presionamos (click derecho) dirgiendonos a:
	***DETALLES***
	***ALMACENAMIENTO***
	***ELEGIMOS MAQUINA VIRTUA***
	***(click) NUEVO VOLUMEN***
    
![Imgur](http://imgur.com/8622Gd9.png)

*Asigamos el tamaño, indicandole el formato "qcow2" y FINALIZAR
 ![Imgur](http://imgur.com/JLjzad9.png)
 
* Ingresamos a DEBIAN en modo consola el siguiente comando: fdisk -l para ver lo creado e inmediatamente después el comando cfdisk /dev/vdc para crear la nueva partición, tal como se muestra en la siguiente imagen:

![Imgur](http://imgur.com/cPgrzB5.png)

* Para el ejemplo creamos  dos particiones una PRIMARIA y otras dos LOGICAS, siendo la primera BOOTEABLE, escogemos la opción WRITE tal como se muestra en la siguiente imagen:

![Imgur](http://imgur.com/MPDvav6.png)

```
REINICIAR LA MAQUINA VIRTUAL
```
* A continuación escribimos el comando: fdisk -l /dev/vdc5
* y creamos la partición física: pvcreate /dev/vdc5
* Ahora creamos los grupos con la siguiente instrucción: vgcreate sistemas-kvm01 /dev/vdc5
* Mostrándonos la siguiente confirmación: tal como se muestra en la siguiente imagen:

![Imgur](http://imgur.com/MEytrWy.png)

* Ahora creamos el volumen lógico con la siguiente instrucción: 
* lvcreate -L 1000 M -n vol_log1 sistemas-kvm01
* Finalmente vemos los volumenes lógicos creados con la instrucción lvdisplay tal como se muestra en la siguiente imagen:

![Imgur](http://imgur.com/gaEaIEj.png)

Con ello se terminamos de realizar la tarea asiganda por el docente. 
 