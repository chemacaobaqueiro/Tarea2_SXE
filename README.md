 ### Tarea2 Alpine ###
1. Descarga la imagen "alpine" SIN ARRANCARLA y comprueba que está en tu equipo

 ***Primero tenemos que comprobar si docker está instalado***
    ```sh
    sudo docker pull alpine     # descargamos la imagen de alpine
    sudo docker images          # nos muestra las imagenes que tenemos instaladas
    ```
Si aparece Alpine significa que funciona

2. Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre

  ***Para crearlo tenemos que utilizar la siguiente linea***
    ```sh
    sudo docker container create -i -t alpine   # aquí creamos un contenedor sin nombre
    ```
  ***Ahora vamos a comprobar si se ha creado correctamente***
    ```sh
    sudo docker ps -a  # nos muestra todos los contenedores
    ```
  
  ***Al crear el contenedor este se encuentra detenido, para iniciarlo tenemos que hacer lo siguiente:***
    ```sh
    sudo docker container start <nombre>      #en el apartado donde pone nombre tenemos que poner el nombre que le dimos al contenedor
    ```

 3. Crea un contenedor con el nombre 'dam_alp1'. ¿Como puedes acceder a él?
 
  ***Para crear un contenedor con nombre usamos:***
    ```sh
    sudo docker container create -i -t --name dam_alp1 alpine   #Aquí creamos el contenedor y le ponemos de nombre dam_alp1
    ```
  
  ***Posteriormente ya cuando tenemos el contenedor con nombre creado debemos iniciarlo, para ello lanzamos esta linea:***
    ```sh
    sudo docker container start --attach -i dam_alp1      #con este comando a parte de iniciarlo con el start, a parte con el --attach accedemos directamente a el
    ```
