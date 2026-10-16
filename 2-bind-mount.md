# BIND MOUNT
En un bind mount mapeamos (montar) un directorio o archivo específico del sistema de archivos del host con una parte del sistema de ficheros del contenedor.

```
docker run -d --name <nombre contenedor> -v <ruta carpeta host>:<ruta carpeta contenedor> <imagen> 
```
ó
```
docker run -d --name <nombre contenedor> --mount type=bind,source=<ruta carpeta host>,target=<ruta carpeta contenedor> <imagen>
```
- destination, dst, target: La ruta donde se monta el archivo o directorio en el contenedor.
- source, src: El origen del montaje.
  
### En tu computador crear una carpeta llamada nginx y dentro de esta carpeta crea otra llamada html. Como se aprecia en la figura.
![Volúmenes](directorio.PNG)

### Crear un contenedor con la imagen nginx:alpine, mapear todos por puertos, para la ruta carpeta host colocar el directorio en donde se encuentra la carpeta html en tu computador y para la ruta carpeta contenedor: /usr/share/nginx/html (esta ruta se obtiene al revisar la documentación de la imagen)
![Volúmenes](volumen-host.PNG)
Comando: docker run -d --name nginx-p1 -p 80:80 -v C:\Users\P3E010-D\nginx\html:/usr/share/nginx/html nginx:alpine
c9195c2fe17e3a1f3ef73c7fbbf550eaeea66f0c0cb78242b1b5b188a12b2718
# COMPLETAR CON EL COMANDO

### ¿Qué sucede al ingresar al servidor de nginx?
Aparece un 403 forbiden cuando se ingresa al servidor ya que la carpereta html estavacia

# COMPLETAR CON LA RESPUESTA A LA PREGUNTA

### ¿Qué pasa con el archivo index.html del contenedor?
archivo index.html original que venía  dentro del contenedor en la ruta /usr/share/nginx/html queda oculto por el directorio montado desde el host.

# COMPLETAR CON LA RESPUESTA A LA PREGUNTA

### Ir a https://html5up.net/ y descargar un template gratuito, descomprirlo dentro de tu computador en la carpeta html
### ¿Qué sucede al ingresar al servidor de nginx?
Se muestra el sitio web de la plantilla gratuita que se descargo y descomprimió, reflejándose los cambios de manera inmediata gracias al bind mount.

# COMPLETAR CON LA RESPUESTA A LA PREGUNTA

### Eliminar el contenedor
docker rm -f nginx-p1

# COMPLETAR CON EL COMANDO

### ¿Qué sucede al crear nuevamente un contenedor montado al directorio definidos anteriormente?
El nuevo contenedor se vuelve a vincular con la misma carpeta html de la computadora, por lo que el sitio web con la plantilla de HTML5 UP sigue apareciendo y funcionando 

# COMPLETAR CON LA RESPUESTA A LA PREGUNTA


