# Trabajp Práctico 2 - Introducción a Docker

### 1- Instalar Docker Community Edition
Como ya lo tengo instalado:

<img src="./images/image.png" width="500"/>

### 2- Explorar DockerHub

<img src="./images/image-1.png" width="500"/>

### 3- Obtener la imagen BusyBox

<img src="./images/image-2.png" width="500"/>

### 4- Ejecutando contenedores

<img src="./images/image-3.png" width="500"/>

No se obtuvo ningun resultado ya que al correr "docker run busybox" se lanzó un contenedor de BusyBox que ejecutó el comando predeterminado y luego se cerró al no tener ninguna instrucción específica que mantuviera el contenedor en ejecución.

<img src="./images/image-4.png" width="500"/>

La diferencia que podemos ver en la salida de los dos comandos se debe a que el comando "docker ps" lista solo los contenedores que se encuentran en ejecución, mientras que "docker ps -a" lista todos los contenedores, incluyendo aquellos que ya se han detenido.

### 5- Ejecutando en modo interactivo

<img src="./images/image-5.png" width="500"/>

### 6- Borrando contenedores terminados

<img src="./images/image-6.png" width="500"/>

<img src="./images/image-7.png" width="500"/>

Para borrar todos los contenedores que no están corriendo podemos ejecutar cualquiera de los siguientes comandos:
```bash
docker rm $(docker ps -a -q -f status=exited)
```
```bash
docker container prune
```

### 7- Construir una imagen

 - FROM: Especifica la imagen base a partir de la cual se construirá la nueva imagen.
 - RUN: Ejecuta comandos en ele contenedor durante la construcción de la imagen.
 - ADD: Copia archivos o directorios desde el sistema de archivos del host a la imagen, además, permite descomprimir archivos locales.
 - COPY: Copia archivos o directorios locales a la imagen, a diferencia del ADD este no tiene la funcionalidad de descompresión.
 - EXPOSE: Indica el puerto al cual la aplicación que se ejecutará dentro del contenedor va a estar escuchando.
 - CMD: Especifica el comando predeterminado a ejecutar cuando se lanza un contenedor a partir de la imagen.
 - ENTRYPOINT: Configura un contenedor para que se ejecute como un ejecutable.

<img src="./images/image-8.png" width="500"/>

<img src="./images/image-9.png" width="500"/>

<img src="./images/image-10.png" width="500"/>

Explicación de cada línea:
 - 3: Establece la imagen base para el contenedor (ASP.NET Core 7.0).
 - 4: Define el directorio de trabajo dentro del contenedor como "/app".
 - 5, 6 y 7: Indican que la aplicación estará escuchando en los puertos 80, 443 y 5254.
 - 9: Empieza con el build, utiliza la imagen oficial de SDK de .NET Core 7.0.
 - 10: Establece el directorio de trabajo como "/src", donde se va a colocar y a compliar el código fuente.
 - 11: Copia el archivo del proyecto ".csproj" desde el host al contenedor en la ruta especificada.
 - 12: Ejecuta en comando "dotnet restore" que descarga todas las dependencias necesarias para compilar el proyecto según lo especificado en el archivo ".csproj".
 - 13: Copia todo el contenido del directorio actual en el host al directorio de trabajo del contenedor.
 - 14: Cambia el directorio de trabajo al directorio que contiene el código fuente del proyecto.
 - 15: Ejecuta el comando "dotnet build" que compila la aplicación en modo Release y coloca los binarios compilados dentro de "/app/build".
 - 17:Empieza la etapa de "publish" que se encarga de publicar la aplicación basada en la etapa "build".
 - 18: Ejecuta el comando "dotnet publish" que compila y publica la aplicación en modo Release, colocándola en el directorio "/app/publish". El parámetro "/p:UseAppHost=false" indica que no se debe incluir un host de la aplicación.
 - 20: Comienza con la etapa "final" basada en la imagen base definida al principio.
 - 21: Establece nuevamente el directorio de trabajo como "/app"
 - 22: Copia los archivos publicados desde la etapa publish al directorio de trabajo actual en la etapa final.
 - 23: Define el comando que se ejecutará cuando se inicia un contenedor basado en esta imagen.

<img src="./images/image-11.png" width="500"/>

<img src="./images/image-12.png" width="500"/>

### 8- Publicando puertos

<img src="./images/image-13.png" width="500"/>

<img src="./images/image-14.png" width="500"/>

### 9- Modificar Dockerfile para soportar bash

<img src="./images/image-15.png" width="500"/>

<img src="./images/image-16.png" width="500"/>

<img src="./images/image-17.png" width="500"/>

### 10- Montando volúmenes

<img src="./images/image-18.png" width="500"/>

### 11- Utilizando una base de datos

<img src="./images/image-19.png" width="500"/>

<img src="./images/image-20.png" width="500"/>

<img src="./images/image-21.png" width="500"/>

- El comando docker run en este ejercicio se utilizó para lanzar un contenedor de PostgreSQL con una configuración específica. Se creó un contenedor llamado my-postgres, en el cual se estableció una contraseña para el usuario, se montó un volumen desde el sistema de archivos del host para asegurar la persistencia de los datos, y se expuso el puerto 5432 del contenedor al host, permitiendo que el servidor de base de datos sea accesible desde fuera del contenedor.

- El comando docker exec se utilizó para acceder de forma interactiva al contenedor de PostgreSQL en ejecución. A través de este comando, se abrió una sesión bash dentro del contenedor, permitiendo ejecutar comandos directamente en el entorno del contenedor. Esto facilitó la conexión al servidor PostgreSQL y la ejecución de comandos SQL.

### 12- Hacer el punto 11 con  MicroSoft SQL Server

Para este punto utilicé la imagen que provee Azure ya que la de sql server no funciona en procesadores con arquitectura ARM64.

<img src="./images/image-22.png" width="500"/>

Sqlcmd tool tampoco está disponible para arquitecturas ARM64, por lo que directamente conecté la instancia de sql server con DBeaver dondé ejecuté las consultas.

<img src="./images/image-23.png" width="500"/>

<img src="./images/image-24.png" width="500"/>

<img src="./images/image-25.png" width="500"/>