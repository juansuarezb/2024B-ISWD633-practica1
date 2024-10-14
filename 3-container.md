# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine


**Descripción del comando:**<br>
docker run: Inicia un contenedor.<br>
--name srv-web: Asigna el nombre srv-web al contenedor.<br>
-d: Ejecuta el contenedor en modo detached (en segundo plano).<br>
-p 8080:80: Mapea el puerto 80 del contenedor al puerto 8080 de tu máquina (para acceder desde tu navegador en localhost:8080).<br>
nginx:alpine: Especifica que usas la imagen nginx en su versión alpine.<br>


Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world <br>
(img/contenedorHelloWorld.png) <br>

### Listar los contenedores ejecutándose o no

```
docker ps -a
```

### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```
Iniciar el contenedor srv-web <br>
(img/contenedorSrvWeb.png) <br>

### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```

### Para detener un contenedor

```
docker stop <nombre contenedor>
```

### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```
![Ecosistema de Docker](img/dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine <br>
(img/ContenedorSrvWeb2ImagenNginx.png) <br>

**¿Qué sucede luego de la ejecución del comando?**
1. Creación del Contenedor: <br>
Docker crea un nuevo contenedor a partir de la imagen nginx:alpine si no existe previamente. <br>
El contenedor se basa en la última versión de la imagen descargada. <br>
Asignación de Puertos: <br>
El puerto 80 del contenedor se mapea al puerto 8081 de tu máquina local. Esto permite que accedas al servidor web Nginx ejecutándose en el contenedor a través de http://localhost:8081. <br>
Si todo funciona correctamente, al abrir un navegador y dirigirte a http://localhost:8081, deberías ver la página de bienvenida de Nginx, confirmando que el servidor web está activo y sirviendo contenido.



Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine <br>
(img/ContenedorSrvweb3Detach.png) <br>

### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```
Eliminar el contenedor que se creó a partir de la imagen hello-world <br>
(img/EliminarContenedorHelloWorld.png) <br>


### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```
Eliminar el contenedor **srv-web3** <br>
(img/EliminarContenedorSrvWeb3.png) <br>

Verificar que el contenedor que se eliminó <br>
(img/VerificarEliminacionContenedorsrv-web3.png) <br>

### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** <br>
(img/InspeccionarContenedorSrv-web.png)
