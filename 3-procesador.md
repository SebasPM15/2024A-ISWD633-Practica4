# Limitar uso de procesador
Limitar la cantidad de núcleos de CPU:
```
--cpus=<número de núcleos>
```

Asignar núcleos de CPU específicos:
```
--cpuset-cpus=<lista de núcleos>
```

**¿Como saber el número de procesadores virtuales que tiene una máquina?**

Se puede usar el comando nproc en sistemas Unix para conocer el número de procesadores virtuales disponibles en una máquina. Este comando devuelve el número de procesadores disponibles en el sistema. Puedes ejecutarlo en la terminal de la máquina en cuestión para obtener el número de núcleos de CPU virtuales. Ahora, en el caso de utilizar el Command Prompt (CMD) en Windows, puedes ejecutar el siguiente comando:
```
wmic cpu get NumberOfCores
```

### Para crear y ejecutar los siguientes contenedores usar la imagen de nginx:alpine

Limitar el uso de CPU a 1.5 núcleos
```
docker run -d --name server-nginx --cpus="1.5" nginx:alpine

```

Restringir el contenedor para que use los núcleos de CPU 0 a 2:
```
docker run -d --name server-nginx --cpuset-cpus="0-2" nginx:alpine

```

Restringir el contenedor para que use los núcleos de CPU 1 y 3:
```
docker run -d --name server-nginx --cpuset-cpus="1,3" nginx:alpine

```
