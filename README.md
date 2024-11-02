# Proyecto: Taller de Arquitectura Distribuida

## Descripción General
En este taller, los estudiantes implementarán un sistema distribuido con una estructura de datos replicada para almacenar pares clave-valor. Esta estructura de datos debe admitir comunicación en grupo y ser resiliente a fallos de nodos, además de acomodar la adición dinámica de nuevos nodos y asegurar la transferencia de estado cuando un nuevo nodo se une al sistema.

Los estudiantes también crearán una aplicación web sencilla donde los clientes pueden registrar sus nombres, los cuales se almacenarán en la estructura de datos replicada junto con una marca de tiempo. La interfaz de cliente se construirá usando JavaScript asíncrono para la interacción en tiempo real.

La arquitectura incluirá un servidor de balanceo de carga implementado con **Spring**, que utilizará una estrategia de **round-robin** para distribuir las solicitudes de los clientes a un conjunto de servicios backend responsables del almacenamiento de datos. Además, los estudiantes implementarán un mecanismo de descubrimiento de servicios donde los servicios backend se registran a sí mismos, asegurando que el balanceador de carga sea consciente de las instancias disponibles de manera dinámica.

Al final del taller, los participantes obtendrán experiencia práctica en el desarrollo de un sistema distribuido robusto con tolerancia a fallos, balanceo de carga y descubrimiento de servicios dinámico.

## Arquitectura
El proyecto se compone de los siguientes elementos principales:
- **Estructura de datos replicada**: Maneja la persistencia de los datos y la replicación entre nodos.
- **Balanceador de carga**: Implementado con **Spring**, distribuye las solicitudes de los clientes.
- **Servicios backend**: Almacenan los datos y registran su disponibilidad.
- **Descubrimiento de servicios**: Mecanismo que permite al balanceador identificar y gestionar instancias disponibles.
- **Interfaz de cliente**: Desarrollada con JavaScript asíncrono para una experiencia de usuario en tiempo real.

## Prerrequisitos
- **Java 8+** (JDK)
- **Maven** para gestión de dependencias y compilación
- **Spring Framework**
- **JGroups** (para replicación de datos y comunicación de grupo)
- **Docker** (opcional, para la contenedorización de servicios)
- **Navegador moderno** para pruebas de la aplicación cliente

## Proceso de Configuración y Desarrollo
### Configuración de la Estructura de Datos Replicada
1. **Clonar el repositorio base del proyecto**:
    ```bash
    git clone https://github.com/usuario/distributed-architecture-workshop.git
    cd distributed-architecture-workshop
    ```

2. **Configurar el entorno de JGroups**:
   Sigue los pasos indicados en [JGroups Tutorial](http://www.jgroups.org/tutorial5/index.html) para configurar la replicación y el manejo de nodos.

3. **Compilar el proyecto**:
    ```bash
    mvn clean install
    ```

### Implementación del Balanceador de Carga
1. **Desarrollar el balanceador de carga con Spring**:
   Implementa una estrategia de **round-robin** para la distribución de solicitudes. Asegúrate de integrar el balanceador con el mecanismo de descubrimiento de servicios.

2. **Registrar los servicios backend**:
   Utiliza **Spring Boot** para que los servicios se registren automáticamente y envíen información al balanceador de carga.

### Creación de la Aplicación Web
1. **Desarrollar la interfaz del cliente**:
   Utiliza JavaScript asíncrono (e.g., `fetch`, `WebSockets`) para permitir la interacción en tiempo real con la estructura de datos replicada.

2. **Conectar la interfaz al backend**:
   Configura endpoints REST en el balanceador de carga para manejar las solicitudes del cliente y enrutar las respuestas a los servicios backend.

## Pruebas y Verificación
### Pasos para la Configuración y Compilación Local
1. **Clonar el repositorio**:
    ```bash
   mvn exec:java -D exec.mainClass="org.jgroups.demos.draw"
    ```


