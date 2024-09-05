# Trabajp Práctico 5 - Despliegue de aplicaciones con Azure Devops Release Pipelines

### 4- Desarrollo

#### 4.1. Crear una cuenta en Azure

<img src="./images/image.png" width="500"/>

#### 4.2. Crear un recurso Web App en Azure Portal y navegar a la url provista

<img src="./images/image-1.png" width="500"/>

<img src="./images/image-2.png" width="500"/>

<img src="./images/image-3.png" width="500"/>

<img src="./images/image-4.png" width="500"/>

<img src="./images/image-5.png" width="500"/>

#### 4.3. Actualizar Pipeline de Build para que use tareas de DotNetCoreCLI@2 como en el pipeline clásico, luego crear un Pipeline de Release en Azure DevOps con CD habilitada

<img src="./images/image-6.png" width="500"/>

<img src="./images/image-7.png" width="500"/>

<img src="./images/image-8.png" width="500"/>

<img src="./images/image-9.png" width="500"/>

<img src="./images/image-10.png" width="500"/>

<img src="./images/image-11.png" width="500"/>

#### 4.4. Optimizar Pipeline de Build

<img src="./images/image-12.png" width="500"/>

<img src="./images/image-13.png" width="500"/>

#### 4.5. Verificar el deploy en la url de la WebApp /weatherforecast

<img src="./images/image-14.png" width="500"/>

<img src="./images/image-15.png" width="500"/>

<img src="./images/image-16.png" width="500"/>

#### 4.6. Realizar un cambio al código del controlador para que devuelva 7 pronóticos, realizar commit, evaluar ejecución de pipelines de build y release, navegar a la url de la webapp/weatherforecast y corroborar cambio

<img src="./images/image-17.png" width="500"/>

<img src="./images/image-18.png" width="500"/>

<img src="./images/image-19.png" width="500"/>

<img src="./images/image-20.png" width="500"/>

<img src="./images/image-21.png" width="500"/>

#### 4.7. Clonar la Web App de QA para que contar con una WebApp de PROD a partir de un Template Deployment en Azure Portal y navegar a la url provista para la WebApp de PROD.

<img src="./images/image-22.png" width="500"/>

<img src="./images/image-23.png" width="500"/>

<img src="./images/image-24.png" width="500"/>

<img src="./images/image-26.png" width="500"/>

<img src="./images/image-25.png" width="500"/>

<img src="./images/image-27.png" width="500"/>

<img src="./images/image-28.png" width="500"/>

<img src="./images/image-29.png" width="500"/>

#### 4.8. Agregar una etapa de Deploy a Prod en Azure Release Pipelines

<img src="./images/image-30.png" width="500"/>

<img src="./images/image-31.png" width="500"/>

<img src="./images/image-32.png" width="500"/>

#### 4.9. Realizar un cambio al código del controlador para que devuelva 10 pronósticos, realizar commit, evaluar ejecución de pipelines de build y release, navegar a la url de la webapp/weatherforecast y corroborar cambio, verificar que en la url de la webapp_prod/weatherforecast se muestra lo mismo.

<img src="./images/image-33.png" width="500"/>

<img src="./images/image-34.png" width="500"/>

<img src="./images/image-35.png" width="500"/>

<img src="./images/image-36.png" width="500"/>

<img src="./images/image-37.png" width="500"/>

#### 4.10. Modificar pipeline de release para colocar una aprobación manual para el paso a Producción.

<img src="./images/image-38.png" width="500"/>

<img src="./images/image-39.png" width="500"/>

#### 4.11. Realizar un cambio al código del controlador para que devuelva 5 pronósticos, realizar commit, evaluar ejecución de pipelines de build y release, navegar a la url de la webapp/weatherforecast y corroborar cambio, verificar que en la url de la webapp_prod/weatherforecast aun se muestra la versión anterior.

<img src="./images/image-40.png" width="500"/>

<img src="./images/image-41.png" width="500"/>

<img src="./images/image-42.png" width="500"/>

<img src="./images/image-46.png" width="500"/>

#### 4.12. Aprobar el pase ya sea desde el release o desde el mail recibido.

<img src="./images/image-43.png" width="500"/>

<img src="./images/image-44.png" width="500"/>

##### 4.12.1. Notar que se puede dar la aprobación pero posponer su aplicación hasta una determinada fecha.

<img src="./images/image-47.png" width="500"/>

#### 4.13. Esperar a la finalización de la etapa de Pase a Prod y luego corroborar que en la url de la webapp_prod/weatherforecast se muestra la nueva versión coinicidente con la de QA.

<img src="./images/image-45.png" width="500"/>

#### 4.14. Realizar un pipeline (no release) que incluya el deploy a QA y a PROD con una aprobación manual. El pipeline debe estar construido en YAML sin utilizar el editor clásico de pipelines ni el editor clásico de pipelines de release.

Creamos el pipeline:

<img src="./images/image-48.png" width="500"/>

<img src="./images/image-49.png" width="500"/>

Editamos el .yaml agregando los stages:

<img src="./images/image-50.png" width="500"/>

<img src="./images/image-51.png" width="500"/>

<img src="./images/image-52.png" width="500"/>

Usamos un environment con pre-checks para la aprobación manual:

<img src="./images/image-61.png" width="500"/>

<img src="./images/image-62.png" width="500"/>

<img src="./images/image-63.png" width="500"/>

Ejecutamos el pipeline:

<img src="./images/image-64.png" width="500"/>

<img src="./images/image-65.png" width="500"/>

<img src="./images/image-66.png" width="500"/>

Aprobamos el deploy a producción manualmente:

<img src="./images/image-67.png" width="500"/>

<img src="./images/image-68.png" width="500"/>

<img src="./images/image-69.png" width="500"/>

<img src="./images/image-70.png" width="500"/>
