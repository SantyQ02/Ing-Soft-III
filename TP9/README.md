## Trabajo Práctico 9 - Implementación de Contenedores en Azure Parte 2

### Desarrollo:

#### 4.1 Modificar nuestro pipeline para incluir el deploy en QA y PROD de Imagenes Docker en Servicio Azure App Services con Soporte para Contenedores

##### 4.1.1 Agregar a nuestro pipeline una nueva etapa que dependa de nuestra etapa de Construcción y Pruebas y de la etapa de Construcción de Imagenes Docker y subida a ACR realizada en el TP08

Creamos el App Service Plan:

<img src="./images/image.png" width="500"/>

<img src="./images/image-1.png" width="500"/>

<img src="./images/image-2.png" width="500"/>

Agregamos la etapa al pipeline y vemos que ejecute correctamente:

<img src="./images/image-3.png" width="500"/>

<img src="./images/image-4.png" width="500"/>

<img src="./images/image-5.png" width="500"/>

<img src="./images/image-6.png" width="500"/>

#### 4.2 Desafíos

##### 4.2.1 Agregar tareas para generar Front en Azure App Service con Soporte para Contenedores

<img src="./images/image-7.png" width="500"/>

Corremos el pipeline y verificamos que levante el front:

<img src="./images/image-10.png" width="500"/>

<img src="./images/image-11.png" width="500"/>

##### 4.2.2 Agregar variables necesarias para el funcionamiento de la nueva etapa considerando que debe haber 2 entornos QA y PROD para Back y Front.

<img src="./images/image-8.png" width="500"/>

##### 4.2.3 Agregar tareas para correr pruebas de integración en el entorno de QA de Back y Front creado en Azure App Services con Soporte para Contenedores.

<img src="./images/image-9.png" width="500"/>

Vemos que los test de integración pasen:

<img src="./images/image-14.png" width="500"/>

##### 4.2.4 Agregar etapa que dependa de la etapa de Deploy en QA que genere un entorno de PROD.

<img src="./images/image-12.png" width="500"/>

<img src="./images/image-13.png" width="500"/>

Ejecutamos el pipeline y vemos que nos pide aprobación:

<img src="./images/image-15.png" width="500"/>

<img src="./images/image-16.png" width="500"/>

<img src="./images/image-17.png" width="500"/>

<img src="./images/image-18.png" width="500"/>

#### Link del pipeline:

https://dev.azure.com/santyq02/Angular_crud_webapi/_build/results?buildId=134&view=results

##### 4.2.5 Entregar un pipeline que incluya:

  - A) Etapa Construcción y Pruebas Unitarias y Code Coverage Back y Front
  - B) Construcción de Imágenes Docker y subida a ACR
  - C) Deploy Back y Front en QA con pruebas de integración para Azure Web Apps
  - D) Deploy Back y Front en QA con pruebas de integración para ACI
  - E) Deploy Back y Front en QA con pruebas de integración para Azure Web Apps con Soporte para contenedores
  - F) Aprobación manual de QA para los puntos C,D,E
  - G) Deploy Back y Front en PROD para Azure Web Apps
  - H) Deploy Back y Front en PROD para ACI
  - I) Deploy Back y Front en PROD para Azure Web Apps con Soporte para contenedores

  Ejecutamos el pipeline y vemos que nos pide aprobación:

  <img src="./images/image-23.png" width="500"/>

  <img src="./images/image-24.png" width="500"/>

  <img src="./images/image-19.png" width="500"/>

  Verificamos que estén todas las instancias y que funcionen correctamente:

  <img src="./images/image-25.png" width="500"/>

  <img src="./images/image-20.png" width="500"/>

  <img src="./images/image-21.png" width="500"/>

  <img src="./images/image-22.png" width="500"/>

  #### Link del Pipeline Integrador

  https://dev.azure.com/santyq02/Angular_crud_webapi/_build/results?buildId=159&view=results


  ##### Verificamos que si fallan las pruebas de integracion o unitarias, de todas maneras se tiene que generar el reporte de las pruebas y no continuar el pipeline

  Modificamos una prueba unitaria de back para que falle:

  <img src="./images/image-26.png" width="500"/>

  <img src="./images/image-27.png" width="500"/>

  Modificamos una prueba unitaria de front para que falle:

  <img src="./images/image-28.png" width="500"/>

  <img src="./images/image-29.png" width="500"/>

  Modificamos las pruebas de integración para que fallen:

  <img src="./images/image-30.png" width="500"/>

  <img src="./images/image-31.png" width="500"/>

