# Trabajp Práctico 3 - Introducción a Azure Devops

### 2 - Consignas a desarrollar en el trabajo práctico:

 **¿Qué es Azure DevOps?**
  - Breve descripción de Azure DevOps como un conjunto de herramientas para la colaboración en desarrollo de software.

    Azure DevOps es un conjunto de herramientas integradas que permite a los equipos de desarrollo de software planificar, desarrollar, probar, entregar y monitorear aplicaciones de manera eficiente. Proporciona una plataforma para la colaboración continua en todas las etapas del ciclo de vida del software, desde la planificación y la gestión de versiones hasta la integración continua y la entrega continua (CI/CD).

  - Beneficios de utilizar Azure DevOps en comparación con otras soluciones.

    Azure DevOps ofrece una integración completa de herramientas para la planificación, desarrollo, testing y despliegue en un solo entorno, lo que facilita la colaboración y automatización del flujo de trabajo de CI/CD. Su flexibilidad permite implementarlo tanto en la nube como on-premises, y su soporte multiplataforma lo hace ideal para equipos heterogéneos. Además, se integra nativamente con servicios de Azure y herramientas de terceros, proporcionando una seguridad robusta y un ecosistema de extensiones que permite personalizar la plataforma según las necesidades del proyecto.

- **Componentes Principales de Azure DevOps**
  - **Azure Repos**
    - Sistema de control de versiones con Git o TFVC.
    - Funcionalidades clave: branching, pull requests, code reviews.
  - **Azure Pipelines**
    - CI/CD (Integración Continua y Entrega Continua).
    - Creación y gestión de pipelines para la automatización de build, test y deploy.
  - **Azure Boards**
    - Gestión de proyectos con Kanban y Scrum.
    - Seguimiento de tareas, bugs, y trabajo en curso.
  - **Azure Artifacts**
    - Gestión de paquetes (NuGet, npm, Maven).
    - Uso de feeds para compartir artefactos entre equipos.
  - **Azure Test Plans**
    - Herramientas para pruebas manuales y automatizadas.
    - Gestión de casos de prueba y reportes de calidad.
- **Integración con otras herramientas**
  - GitHub, Jenkins, Docker, Kubernetes.
- **Marketplace de extensiones**
  - Añadir funcionalidades adicionales a Azure DevOps.

### 3- Pasos del TP
 - 3.1 Crear una cuenta en Azure DevOps

    <img src="./images/image.png" width="500"/>

 - 3.2 Crear un proyecto Sample01

    <img src="./images/image-1.png" width="500"/>

    <img src="./images/image-2.png" width="500"/>

    Posteriormente, habilité los proyectos públicos y modifiqué la visibilidad de este proyecto:

    <img src="./images/image-13.png" width="500"/>

 - 3.3 Crear un repo GIT desde cero

    <img src="./images/image-3.png" width="500"/>

    También se puede realizar de la siguiente manera:

    <img src="./images/image-5.png" width="500"/>

    <img src="./images/image-4.png" width="500"/>

 - 3.4 Crear un proyecto Sample02

    <img src="./images/image-6.png" width="500"/>

    Posteriormente, habilité los proyectos públicos y modifiqué la visibilidad de este proyecto:

    <img src="./images/image-12.png" width="500"/>

 - 3.5 Importar un repo desde GitHub: https://github.com/ingsoft3ucc/SimpleWebAPI.git

    <img src="./images/image-7.png" width="500"/>

    <img src="./images/image-8.png" width="500"/>

 - 3.6 Realizar un cambio en un archivo, y subirlo al repo de ADO.

    <img src="./images/image-9.png" width="500"/>

    <img src="./images/image-10.png" width="500"/>

 - 3.7 Crear un pipeline, solicitar acceso a jobs de paralelismo

    <img src="./images/image-11.png" width="500"/>

    <img src="./images/image-21.png" width="500"/>

    <img src="./images/image-22.png" width="500"/>

    <img src="./images/image-23.png" width="500"/>

    <img src="./images/image-24.png" width="500"/>

    <img src="./images/image-25.png" width="500"/>

    <img src="./images/image-26.png" width="500"/>

    <img src="./images/image-27.png" width="500"/>

    Procedemos a solicitar acceso a jobs de paralelismo:

    <img src="./images/image-28.png" width="500"/>

    <img src="./images/image-29.png" width="500"/>

 - 3.8 Cambiar el tipo de proceso de Basic a Agile

    <img src="./images/image-14.png" width="500"/>

 - 3.8 Crear un sprint

    <img src="./images/image-15.png" width="500"/>

 - 3.9 Crear User Stories

    <img src="./images/image-16.png" width="500"/>

    <img src="./images/image-17.png" width="500"/>

 - 3.10 Crear Tasks y Bugs

    <img src="./images/image-18.png" width="500"/>

    <img src="./images/image-19.png" width="500"/>

    <img src="./images/image-20.png" width="500"/>








