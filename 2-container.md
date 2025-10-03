# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine

```
docker create --name srv-web nginx:alpine
```

Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world

```
docker create hello-world
```

### Listar los contenedores ejecutándose o no

```
docker ps -a
```
<img width="1418" height="106" alt="image" src="https://github.com/user-attachments/assets/92acc9d4-f843-410a-9d77-e6d91fef76c5" />

### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```
Iniciar el contenedor srv-web 

```
docker start svr-web
```
<img width="449" height="60" alt="image" src="https://github.com/user-attachments/assets/b4445a5f-23bd-4a9c-93ee-e677de778a38" />


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
![Ecosistema de Docker](dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine

```
docker run --name srv-web2 nginx:alpine
```
<img width="1080" height="507" alt="image" src="https://github.com/user-attachments/assets/59a4764a-b081-4e1a-8a0e-d6223c2276e1" />

**¿Qué sucede luego de la ejecución del comando?**

El contenedor se ejecuta en primer plano, por lo que la terminal se queda inhabilitada. Si queremos salir de esta opción es necesario presionar crtl + c.

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine
```
docker run -d --name srv-web3 nginx:alpine
```

### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```
Eliminar el contenedor que se creó a partir de la imagen hello-world 
```
docker rm exiting_austin
```
<img width="491" height="69" alt="image" src="https://github.com/user-attachments/assets/f7caaee5-03b0-43a8-9c3c-8437205ba511" />

Verificar que el contenedor que se eliminó
<img width="1415" height="185" alt="image" src="https://github.com/user-attachments/assets/457e5f63-398f-4888-be5e-a71e95934273" />


### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```
Eliminar el contenedor **srv-web3** 

```
docker rm -f srv-web3
```

Verificar que el contenedor que se eliminó
<img width="1390" height="155" alt="image" src="https://github.com/user-attachments/assets/2f5afc97-45a5-4015-932a-6512b1fc2e64" />

### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 
```
docker inspect srv-web
```
<img width="1717" height="1582" alt="image" src="https://github.com/user-attachments/assets/35b91b74-2c33-4d60-8653-c0c5b3841e89" />



