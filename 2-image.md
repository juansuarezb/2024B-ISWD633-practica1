# Imagen
Es un archivo único que contiene todos los programas, librerías, dependencias y configuraciones necesarias para instalar y/o ejecutar una aplicación o un conjunto de aplicaciones.
![Imagen](img/imagen.PNG)


## ¿Cuál es la relación entre una imagen y un contenedor? 
<p>En Docker, las imágenes y los contenedores son conceptos fundamentales. A continuación, se explica cómo se relacionan:</p>

<ul>
  <li>Una imagen es la plantilla que describe el contenedor, con todo lo necesario para ejecutar una aplicación.</li>
  <li>Un contenedor es una instancia activa de una imagen, funcionando como una aplicación aislada.</li>
  <li>Se pueden crear múltiples contenedores a partir de una misma imagen, cada uno ejecutándose de forma independiente y aislada.</li>
</ul>

<p>Por ejemplo, a partir de una imagen de <code>nginx</code>, se pueden crear múltiples contenedores, cada uno funcionando de forma separada como un servidor web.</p>

![Imagen y contenedores](img/imagenContenedores.JPG)
## Comandos para imágenes

### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**
# COMPLETAR

**¿Qué es nginx**
Es un servidor web que se utiliza ampliamente para servir sitios web y aplicaciones.

**¿Para qué sirve Nginx?**
Se utiliza para entregar contenido estático como HTML, CSS, JavaScript e imágenes a los usuarios entre otras cosas.

**¿Qué es la versión Alpine de Nginx?**
Alpine Linux es una distribución muy ligera de Linux, utilizada para minimizar el tamaño de las imágenes de Docker.
La imagen nginx:alpine es una versión optimizada y más pequeña de Nginx, perfecta para contenedores que necesitan eficiencia y rapidez sin agregar peso innecesario.


Descargar la imagen  **nginx** en la versión **alpine**
# COMPLETAR

### Listar imágenes

```
docker images
```

# COLOCAR UNA CAPTURA DE PANTALLA DEL RESULTADO 

**Identificadores**

En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 
# COMPLETAR

**¿Con qué algoritmo se está generando el ID de la imagen**
# COMPLETAR

### Filtrar imágenes

```
docker images | grep <termino a buscar>

```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 
# COMPLETAR

-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```

