# Trabajp Práctico 4 - Azure Devops Pipelines

### 4- Pasos del TP

#### 4.1 Verificar acceso a Pipelines concedido

Como no poseo acceso público a Pipelines, voy a configurar el proyecto como privado:

<img src="./images/image-1.png" width="500"/>

<img src="./images/image.png" width="500"/>

#### 4.2 Agregar en pipeline YAML una tarea de Publish

<img src="./images/image-2.png" width="500"/>

#### 4.3 Explicar por qué es necesario contar con una tarea de Publish en un pipeline que corre en un agente de Microsoft en la nube

La tarea de Publish es necesaria en un pipeline que corre en un agente de Microsoft en la nube para guardar y compartir los artifacts generados, ya que los agentes en la nube no mantienen datos entre ejecuciones. Sin esta tarea, los artifacts se perderían al terminar el pipeline.

#### 4.4 Descargar el resultado del pipeline y correr localmente el software compilado.

Corremos el pipeline:

<img src="./images/image-3.png" width="500"/>

Y descargamos el drop del pipeline:

<img src="./images/image-4.png" width="500"/>

<img src="./images/image-12.png" width="500"/>

<img src="./images/image-11.png" width="500"/>

#### 4.5 Habilitar el editor clásico de pipelines. Explicar las diferencias claves entre este tipo de editor y el editor YAML.

<img src="./images/image-13.png" width="500"/>

Una de las diferencias claves es que el editor clasico de pipelines está orientadoa usuarios menos experimientados mientras que el editor YAML es para usuarios más técnicos y posee ventajas claves como el versionado.

#### 4.6 Crear un nuevo pipeline con el editor clásico. Descargar el resultado del pipeline y correr localmente el software compilado.

<img src="./images/image-14.png" width="500"/>

<img src="./images/image-15.png" width="500"/>

<img src="./images/image-16.png" width="500"/>

<img src="./images/image-17.png" width="500"/>

<img src="./images/image-18.png" width="500"/>

<img src="./images/image-19.png" width="500"/>

<img src="./images/image-20.png" width="500"/>

#### 4.7 Configurar CI en ambos pipelines (YAML y Classic Editor). Mostrar resultados de la ejecución automática de ambos pipelines al hacer un commit en la rama main.

<img src="./images/image-21.png" width="500"/>

<img src="./images/image-22.png" width="500"/>

<img src="./images/image-23.png" width="500"/>

<img src="./images/image-24.png" width="500"/>

#### 4.8 Explicar la diferencia entre un agente MS y un agente Self-Hosted. Qué ventajas y desventajas hay entre ambos? Cuándo es conveniente y/o necesario usar un Self-Hosted Agent?

Un agente Microsoft-hosted es gestionado por Microsoft, ofrece fácil configuración y actualización automática, ideal para flujos de trabajo simples, pero con limitaciones en tiempo de ejecución y recursos. En contraste, un agente Self-hosted es gestionado por el usuario, ofreciendo mayor control, flexibilidad y sin restricciones de recursos, pero requiere más esfuerzo para mantener y es ideal cuando se necesitan entornos específicos o integración con infraestructura interna. Usar un agente Self-hosted es conveniente cuando se necesitan configuraciones personalizadas, mayor control sobre el entorno, o se busca evitar las limitaciones de los agentes en la nube.

#### 4.8 Crear un Pool de Agentes y un Agente Self-Hosted

<img src="./images/image-5.png" width="500"/>

<img src="./images/image-6.png" width="500"/>

<img src="./images/image-8.png" width="500"/>

#### 4.9 Instalar y correr un agente en nuestra máquina local.

<img src="./images/image-7.png" width="500"/>

<img src="./images/image-9.png" width="500"/>

<img src="./images/image-10.png" width="500"/>

#### 4.10 Crear un pipeline que use el agente Self-Hosted alojado en nuestra máquina local.

<img src="./images/image-25.png" width="500"/>

#### 4.11 Buscar el resultado del pipeline y correr localmente el software compilado.

<img src="./images/image-27.png" width="500"/>

<img src="./images/image-28.png" width="500"/>

<img src="./images/image-26.png" width="500"/>

#### 4.12 Crear un nuevo proyecto en ADO clonado desde un repo que contenga una aplicación en Angular como por ejemplo https://github.com/ingsoft3ucc/angular-demo-project.git

<img src="./images/image-29.png" width="500"/>

<img src="./images/image-30.png" width="500"/>

<img src="./images/image-31.png" width="500"/>

#### 4.13 Configurar un pipeline de build para un proyecto de tipo Angular como el clonado.

<img src="./images/image-32.png" width="500"/>

<img src="./images/image-33.png" width="500"/>

Modificamos el .yaml para que haga las task de publish:

<img src="./images/image-34.png" width="500"/>

Vemos que se ejecuto correctamente:

<img src="./images/image-35.png" width="500"/>

#### 4.14 Habilitar CI para el pipeline.

Viene habilitado por defecto en pipelines .yaml:

<img src="./images/image-36.png" width="500"/>

#### 4.15 Hacer un cambio a un archivo del proyecto (algún cambio en el HTML que se renderiza por ejemplo) y verificar que se ejecute automáticamente el pipeline.

<img src="./images/image-37.png" width="500"/>

<img src="./images/image-38.png" width="500"/>

Vemos que se ejecuto correctamente:

<img src="./images/image-39.png" width="500"/>

#### 4.16 Descargar el resultado del pipeline y correr en un servidor web local el sitio construido.

<img src="./images/image-40.png" width="500"/>

<img src="./images/image-41.png" width="500"/>

<img src="./images/image-42.png" width="500"/>

<img src="./images/image-43.png" width="500"/>

#### 4.17 Mostrar el antes y el después del cambio.

<img src="./images/image-45.png" width="500"/>

<img src="./images/image-44.png" width="500"/>






