# Trabajo Práctico 6 - Pruebas Unitarias

### 4- Desarrollo

#### 4.1 Creación de una BD SQL Server para nuestra App

Montamos una imagen Docker de SQL Server:

Para este punto utilicé la imagen que provee Azure ya que la de sql server no funciona en procesadores con arquitectura ARM64:

<img src="./images/image.png" width="500"/>

Sqlcmd tool tampoco está disponible para arquitecturas ARM64, por lo que directamente conecté la instancia de sql server con DBeaver dondé ejecuté las consultas:

<img src="./images/image-1.png" width="500"/>

Ejecutamos el siguiente script:

<img src="./images/image-2.png" width="500"/>

#### 4.2 Obtener nuestra App

Clonamos el repositorio:

<img src="./images/image-3.png" width="500"/>

Modificamos el appsettings.json:

<img src="./images/image-4.png" width="500"/>

Ejecutamos el comando dotnet run --urls "http://localhost:7150":

<img src="./images/image-5.png" width="500"/>

<img src="./images/image-6.png" width="500"/>

Navegamos a http://localhost:4200 y verificamos el correcto funcionamiento de nuestro front-end Angular

<img src="./images/image-7.png" width="500"/>

<img src="./images/image-8.png" width="500"/>

#### 4.3 Crear Pruebas Unitarias para nuestra API

Creamos un nuevo proyecto de pruebas unitarias para nuestra API en el directorio raiz de nuestro repo:

<img src="./images/image-9.png" width="500"/>

Instalamos las dependencias:

<img src="./images/image-10.png" width="500"/>

Editamos el archivo UnitTest1.cs:

<img src="./images/image-11.png" width="500"/>

Renombramos el archivo:

<img src="./images/image-12.png" width="500"/>

Agregamos una referencia a nuestro proyecto de EmployeeCrudApi:

<img src="./images/image-13.png" width="500"/>

Ejecutamos y verificamos que se hayan ejecutado correctamente las pruebas:

<img src="./images/image-14.png" width="500"/>

Modificamos la cadena de conexión en el archivo appsettings.json para que use un usuario o password incorrecto y recompilar el proyecto EmployeeCrudApi:

<img src="./images/image-15.png" width="500"/>

<img src="./images/image-16.png" width="500"/>

Verificamos que nuestro proyecto ya no tiene acceso a la BD navegando a http://localhost:7150/swagger/index.html y probando uno de los controladores:

<img src="./images/image-17.png" width="500"/>

Volvemos a correr las pruebas y verificmos que se hayan ejecutado correctamente las pruebas inclusive sin tener acceso a la BD, lo que confirma que es efectivamente un conjunto de pruebas unitarias que no requieren de una dependencia externa para funcionar:

<img src="./images/image-18.png" width="500"/>

Volvemos a modificar la cadena de conexión en el archivo appsettings.json para que use el usuario y password correcto y recompilar el proyecto EmployeeCrudApi:

<img src="./images/image-19.png" width="500"/>

#### 4.4 Creamos pruebas unitarias para nuestro front de Angular

Nos posicionamos en nuestro proyecto de front, en el directorio EmployeeCrudAngular/src/app:

<img src="./images/image-20.png" width="500"/>

Editamos el archivo app.component.spec.ts

<img src="./images/image-21.png" width="500"/>

Creamos el archivo employee.service.spec.ts:

<img src="./images/image-22.png" width="500"/>

Editamos el archivo employee.component.spec.ts ubicado en la carpeta employee:

<img src="./images/image-23.png" width="500"/>

Editamos el archivo addemployee.component.spec.ts ubicado en la carpeta addemployee:

<img src="./images/image-24.png" width="500"/>

En el directorio raiz de nuestro proyecto EmployeeCrudAngular ejecutamos el comando ng test y vemos que los tests se ejecutaron correctamente::

<img src="./images/image-25.png" width="500"/>

<img src="./images/image-26.png" width="500"/>

Corregimos employee.service.spec.ts y volvemos a ejecutar los tests:

<img src="./images/image-27.png" width="500"/>

<img src="./images/image-28.png" width="500"/>

Verificamos que no esté corriendo nuestra API navegando a http://localhost:7150/swagger/index.html y recibiendo esta salida:

<img src="./images/image-29.png" width="500"/>

#### 4.5 Agregamos generación de reporte XML de nuestras pruebas de front

 Instalamos dependencia karma-junit-reporter:

 <img src="./images/image-30.png" width="500"/>

 En el directorio raiz de nuestro proyecto (al mismo nivel que el archivo angular.json) creamos un archivo karma.conf.js con el siguiente contenido:

 <img src="./images/image-31.png" width="500"/>

 Ejecutamos nuestros test:

 <img src="./images/image-32.png" width="500"/>

 Verificamos que se creo un archivo test-result.xml en el directorio test-results que está al mismo nivel que el directorio src

 <img src="./images/image-33.png" width="500"/>

 #### 4.6 Modificamos el código de nuestra API y creamos nuevas pruebas unitarias

 Voy a realizar las siguientes 5 modificaciones sugeridas al código de la API:

 * La longitud máxima del nombre y apellido del empleado debe ser de 100 caracteres.
 * Validar que el nombre tenga un número mínimo de caracteres, por ejemplo, al menos dos caracteres para evitar entradas inválidas como "A".
 * Verificar que el nombre no contenga números, ya que no es común en los nombres de empleados.
 * Asegurar que cada parte del nombre (separada por espacios) tenga al menos un carácter o más, por ejemplo, para evitar "A B".
 * Verificar que no haya palabras vacías o que el nombre no esté compuesto solo de espacios.

 <img src="./images/image-34.png" width="500"/>

 Creamos las pruebas unitarias necesarias para validar las modificaciones realizadas en el código:

 <img src="./images/image-35.png" width="500"/>

 Hacemos build a los test y los corremos:

 <img src="./images/image-36.png" width="500"/>

#### 4.7 Modificamos el código de nuestro Front y creamos nuevas pruebas unitarias

Realizamos en el código del front las mismas modificaciones hechas a la API:

<img src="./images/image-37.png" width="500"/>

Agregamos las importaciones necesarias para ToastrModule y BrowserAnimationsModule en app.config.ts:

<img src="./images/image-38.png" width="500"/>

Importamos el css con los estilos de toast:

<img src="./images/image-39.png" width="500"/>

Agregamos las validaciones en AddEmployee y las probamos:

<img src="./images/image-40.png" width="500"/>

<img src="./images/image-41.png" width="500"/>

<img src="./images/image-42.png" width="500"/>

<img src="./images/image-43.png" width="500"/>

<img src="./images/image-44.png" width="500"/>

<img src="./images/image-45.png" width="500"/>

Creamos las pruebas unitarias necesarias en el front para validar las modificaciones realizadas en el código del front:

<img src="./images/image-46.png" width="500"/>

Vemos que se ejecuten correctamente:

<img src="./images/image-47.png" width="500"/>

<img src="./images/image-48.png" width="500"/>

### 6- DesarrolloPresentación del trabajo práctico

El proyeto se encuentra en la misma carpeta TP6 y en el siguiente repositorio de GitHub:

https://github.com/SantyQ02/Angular_WebAPINetCore8_CRUD_Sample.git