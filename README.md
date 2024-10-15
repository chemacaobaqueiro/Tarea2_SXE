 ### Tarea2 Alpine ###
1. Descarga la imagen "alpine" SIN ARRANCARLA y comprueba que está en tu equipo

  ***Primero tenemos que comprobar si docker está instalado***
 
   ```shell
   sudo docker pull alpine     # descargamos la imagen de alpine
   sudo docker images          # nos muestra las imagenes que tenemos instaladas
   ```
    
 ***Si aparece Alpine significa que funciona***

2. Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre

   ***Para crearlo tenemos que utilizar la siguiente linea***
  
   ```shell
   sudo docker container create -i -t alpine   # aquí creamos un contenedor sin nombre
   ```
  
   ***Ahora vamos a comprobar si se ha creado correctamente***
  
   ```shell
   sudo docker ps -a  # nos muestra todos los contenedores
   ```
  
   ***Al crear el contenedor este se encuentra detenido, para iniciarlo tenemos que hacer lo siguiente:***
    
   ```shell
   sudo docker container start <nombre>      #en el apartado donde pone nombre tenemos que poner el nombre que le dimos al contenedor
   ```

3. Crea un contenedor con el nombre 'dam_alp1'. ¿Como puedes acceder a él?
 
    ***Para crear un contenedor con nombre usamos:***
    
   ```shell
   sudo docker container create -i -t --name dam_alp1 alpine   #Aquí creamos el contenedor y le ponemos de nombre dam_alp1
   ```
  
   ***Posteriormente ya cuando tenemos el contenedor con nombre creado debemos iniciarlo, para ello lanzamos esta linea:***
    
   ```shell
   sudo docker container start --attach -i dam_alp1      #con este comando a parte de iniciarlo con el start, a parte con el --attach accedemos directamente a el
   ```

4. Comprueba que ip tiene y si puedes hacer un ping a google.com
 
   ***Lo primero es comprobar la ip que tenemos, para ello primero lo iniciamos y luego comprobamos la ip***
 
   ```shell
   sudo docker container start --attach -i dam_alp1	# ya mencionado iniciar y acceder al contenedor
   ip a                                                # comprobar nuestra ip
   ```
  
   ***Después de comprobar la ip ahora vamos a probar si podemos realizar un ping a google.com***
  
   ```shell
   ping google.com		
   ```
  
   ***Si queremos salir tenemos que presionar ***Ctrl+D******

5. Crea un contenedor con el nombre 'dam_alp2'. ¿Puedes hacer ping entre los contenedores?
 
    ***Primero tenemos que arrancar el contenedor dam_alp1 creado anteriormente***
  
   ```shell
   sudo docker container start --attach -i dam_alp1
   ```
  
   ***Ahora necesitamos ir a otro terminal distinto, oara esto utilizamos ***Alt+F2******
  
   ***En el nuevo terminal creamos un nuevo contenedor llamado dam_alp2***
  
  ```shell
  sudo docker container create -i -t --name dam_alp2 alpine
  sudo docker start --attach -i dam_alp2
  ```
  
   ***Por último en cada terminal lanzamos ***ip a*** y ***ping 172.17.0.2******
 
 6. Sal del terminal, ¿que ocurrió con el contenedor?

     ***Para salir del terminal utilizamos ***Ctrl+D******

     ***Al salir se apaga el contenedor, pero si se abre en una terminal nueva y cerramos la terminal sin el comando anterior se sigue ejecutando***

7. ¿Cuanta memoria en el disco duro ocupaste?

 ***Para comprobar la memoria ocupada utilizamos el comando:***
 
  ```shell
  sudo docker system df -v
  ```
 
 ***Con esto podemos ver cuanto ocupan los contenedores***
 
 - ***El contenedor dam_alp1 ocupa: 21B***
 - ***El contenedor dam_alp2 ocupa: 38B***
