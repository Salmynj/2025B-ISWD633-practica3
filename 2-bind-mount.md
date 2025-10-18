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
# COMPLETAR CON EL COMANDO

```
docker run -d -P --name Contenedor3 -v "C:\Users\salma\OneDrive\Documentos\nginx\html":/usr/share/nginx/html nginx:alpine
```

### ¿Qué sucede al ingresar al servidor de nginx?
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA
```
Cunado entro al localhost:32770 lo que me sale es 403 Forbidden, lo que significa que el servidor si esta corriendo pero no tiene
los permisos suficientes o no encuentra un archivo. 
```

### ¿Qué pasa con el archivo index.html del contenedor?
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA
```
Lo que paso con ese archivo es que Nginx no pudo acceder a este o porque no existe o no puede entrar, debido a 403 Forbidden.  
```

### Ir a https://html5up.net/ y descargar un template gratuito, descomprirlo dentro de tu computador en la carpeta html
### ¿Qué sucede al ingresar al servidor de nginx?
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA

```
Ahora con el template dentro de la carpeta html, se observa la página con el template descargado y ya no aparece el texto 403 Forbidden 
```

### Eliminar el contenedor
# COMPLETAR CON EL COMANDO
```
docker rm -f Contenedor3
```

### ¿Qué sucede al crear nuevamente un contenedor montado al directorio definidos anteriormente?
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA
```
Al crear nuevamente el contenedor con el mismo directorio se muestra el template que se ha descargado previamente. 
```

