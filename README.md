# Proyecto Docker + Apache Guacamole

## Introducción

Este proyecto consiste en la implementación de una infraestructura híbrida basada en Docker y Apache Guacamole con el objetivo de proporcionar acceso remoto seguro, centralizado y multiplataforma a distintos servicios internos de una empresa.

La solución ha sido diseñada para mejorar la administración de conexiones remotas, aumentar la seguridad de la infraestructura y reducir el coste de mantenimiento de los sistemas. Para ello, se utilizan tecnologías open source ampliamente utilizadas en entornos profesionales.

El despliegue se realiza mediante contenedores Docker, permitiendo aislar servicios y facilitar tanto la escalabilidad como la portabilidad del entorno.

## Objetivos del proyecto

Los principales objetivos de esta infraestructura son:

Centralizar el acceso remoto mediante una interfaz web.
Reducir la exposición directa de servicios internos.
Mejorar la seguridad de las conexiones SSH y RDP.
Facilitar el despliegue y mantenimiento utilizando Docker Compose.
Implementar una solución multiplataforma accesible desde cualquier navegador.
Utilizar software libre bajo licencias permisivas.

## Tecnologías utilizadas

### Docker

Docker se utiliza como plataforma de virtualización ligera basada en contenedores. Gracias a esta tecnología, cada servicio funciona de manera aislada y con sus propias dependencias.

### Apache Guacamole

Apache Guacamole proporciona acceso remoto vía web sin necesidad de instalar clientes adicionales. Permite conexiones mediante protocolos como SSH, RDP y VNC.

### PostgreSQL

PostgreSQL se utiliza como sistema gestor de bases de datos para almacenar usuarios, configuraciones y conexiones de Apache Guacamole.

### OpenSSH

OpenSSH permite realizar conexiones seguras a sistemas Linux mediante el protocolo SSH.

### Docker Compose

Docker Compose facilita la administración y despliegue de múltiples contenedores desde un único archivo de configuración.

## Funcionamiento de la infraestructura

La infraestructura implementada permite que los usuarios accedan a distintos servicios remotos desde un navegador web utilizando Apache Guacamole como pasarela centralizada.

Todas las conexiones quedan gestionadas desde una única interfaz, evitando exponer múltiples puertos directamente hacia el exterior. Esto reduce considerablemente la superficie de ataque de la infraestructura.

Docker permite mantener cada servicio separado dentro de su propio contenedor, facilitando el mantenimiento, las actualizaciones y la escalabilidad del sistema.

## Ventajas de la solución

La solución desarrollada aporta múltiples beneficios técnicos y operativos:

Mayor seguridad al centralizar accesos remotos.
Reducción de costes gracias al uso de software libre.
Facilidad de despliegue y migración entre servidores.
Aislamiento de servicios mediante contenedores.
Administración simplificada de usuarios y conexiones.
Compatibilidad multiplataforma.
Menor tiempo de recuperación ante incidencias.

## Conclusión

La implementación de una infraestructura basada en Docker y Apache Guacamole permite disponer de un entorno moderno, seguro y fácilmente administrable para el acceso remoto corporativo.

El uso de contenedores mejora significativamente la portabilidad y el mantenimiento de los servicios, mientras que Apache Guacamole proporciona una solución eficiente para centralizar conexiones remotas desde cualquier dispositivo.

Esta solución cumple con requisitos fundamentales de seguridad, disponibilidad y escalabilidad presentes en entornos profesionales actuales.