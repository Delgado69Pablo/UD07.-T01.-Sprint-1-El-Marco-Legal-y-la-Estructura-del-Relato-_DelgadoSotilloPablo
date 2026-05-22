# MEMORIA TÉCNICA  
## Infraestructura híbrida Docker-Guacamole para acceso remoto seguro

### Alumno
Pablo Delgado Sotillo

### Ciclo
DAW – Sistemas Informáticos

### Fecha
15 de mayo de 2026

# Índice

1. Análisis de Necesidades  
   1.1. Contexto y Problemática Actual  
   1.2. Solución Propuesta: Infraestructura Híbrida Docker-Guacamole  
   1.3. Justificación Técnica y Beneficios (TCO)  

# 1. Análisis de Necesidades

## 1.1. Contexto y Problemática Actual

La empresa objeto de este proyecto requiere que los técnicos y administradores de sistemas puedan acceder de manera remota a distintos servidores internos utilizados para desarrollo, pruebas y gestión de bases de datos. Inicialmente, la infraestructura presentaba importantes limitaciones relacionadas con la seguridad, la administración y el mantenimiento de los accesos remotos.

El acceso a los sistemas se realizaba mediante conexiones directas utilizando protocolos como RDP y SSH sobre diferentes equipos de la red corporativa. Esta situación obligaba a mantener múltiples puertos abiertos en el firewall, aumentando considerablemente la superficie de ataque y exponiendo la infraestructura a posibles intentos de acceso no autorizado.

Asimismo, la gestión descentralizada de las conexiones dificultaba la administración de usuarios y permisos. Cada técnico debía configurar clientes específicos en su propio equipo, provocando incompatibilidades entre sistemas operativos, errores de configuración y un incremento del tiempo de soporte técnico.

Otro problema detectado fue la falta de centralización y trazabilidad. No existía un punto único desde el cual controlar las conexiones remotas ni supervisar los accesos realizados por los usuarios. En consecuencia, la empresa carecía de un sistema eficiente de auditoría y control de sesiones.

Desde el punto de vista operativo, también se observó un consumo innecesario de recursos, ya que cada servicio se ejecutaba directamente sobre el sistema anfitrión. Esto dificultaba la escalabilidad y aumentaba el riesgo de conflictos entre dependencias y versiones de software.

Según Drake [1], un análisis adecuado de requisitos permite reducir errores críticos durante la fase de explotación de los sistemas informáticos. Por consiguiente, se consideró necesario diseñar una solución centralizada, segura y fácilmente mantenible.

## 1.2. Solución Propuesta: Infraestructura Híbrida Docker-Guacamole

Tras el análisis de los requisitos funcionales y no funcionales de la organización, se ha optado por implementar una infraestructura híbrida basada en Apache Guacamole desplegado mediante Docker Compose.

Apache Guacamole actúa como una pasarela de acceso remoto accesible desde cualquier navegador web moderno, permitiendo conexiones RDP, SSH y VNC sin necesidad de instalar clientes específicos en los equipos de los usuarios. De este modo, todos los accesos remotos quedan centralizados en un único punto de entrada.

La utilización de Docker permite ejecutar cada servicio dentro de contenedores independientes y aislados. Esta arquitectura facilita la modularidad de la infraestructura y mejora la portabilidad del sistema. Además, cada contenedor mantiene sus propias dependencias, evitando conflictos entre aplicaciones y simplificando el mantenimiento.

La solución implementada incorpora distintos servicios:
- Contenedor Apache Guacamole para la gestión de accesos remotos.
- Contenedor PostgreSQL para el almacenamiento de usuarios y configuraciones.
- Servicio OpenSSH para conexiones seguras a servidores Linux.
- Docker Compose como herramienta de orquestación y despliegue.

La arquitectura propuesta aporta importantes ventajas técnicas:
- **Centralización:** todos los accesos se realizan desde una única interfaz web.
- **Seguridad:** se reducen los puertos expuestos al exterior y se simplifica la administración de permisos.
- **Escalabilidad:** es posible añadir nuevos servicios o contenedores de manera rápida.
- **Portabilidad:** la infraestructura puede desplegarse en distintos entornos sin modificaciones complejas.
- **Mantenimiento simplificado:** las actualizaciones y configuraciones se gestionan de forma modular.

Además, el uso de tecnologías open source permite disponer de documentación extensa y soporte comunitario, reduciendo costes de implantación y dependencia de proveedores externos.

## 1.3. Justificación Técnica y Beneficios (TCO)

La elección de una infraestructura basada en Docker y Apache Guacamole responde a criterios de eficiencia operativa, seguridad y optimización del Coste Total de Propiedad (TCO).

En primer lugar, el uso de software libre bajo licencias permisivas, como Apache License 2.0 y PostgreSQL License, evita costes recurrentes de licenciamiento. Esto permite a la empresa destinar mayores recursos económicos a la mejora de la infraestructura y la ciberseguridad.

Asimismo, Docker proporciona un entorno altamente portable y reproducible. La posibilidad de desplegar la misma infraestructura en distintos servidores minimiza los tiempos de recuperación ante fallos y facilita la implementación de planes de contingencia y recuperación ante desastres (DRP).

Otro beneficio importante es la mejora de la seguridad informática. Al centralizar el acceso remoto mediante Guacamole, se reduce considerablemente la exposición directa de los servidores internos. Además, la autenticación y gestión de usuarios puede administrarse desde una única plataforma, mejorando el control y la auditoría de accesos.

Desde el punto de vista de mantenimiento, la contenerización simplifica las actualizaciones y permite aislar incidencias sin afectar al resto de servicios. Esto reduce tiempos de inactividad y mejora la disponibilidad general de la infraestructura.

De acuerdo con García Notario [2], un análisis correcto de requisitos y una adecuada planificación técnica permiten incrementar la calidad y fiabilidad de los sistemas software. En consecuencia, la solución implementada cumple con los requisitos de seguridad, disponibilidad y escalabilidad exigidos en entornos profesionales modernos.

# 2. Estimación de Costes de Infraestructura.

[Presupuesto_Cloud_Proyecto. - Hoja 1.pdf](https://github.com/user-attachments/files/28148853/Presupuesto_Cloud_Proyecto.-.Hoja.1.pdf)

# 3. Estrategia de Despliegue y Comunicación.

# Referencias

[1] Drake, J. M. (2008). *Análisis de requisitos y especificación de una aplicación*. Disponible en:  
https://www.ctr.unican.es/asignaturas/ingenieria_software_4_f/doc/m3_08_especificacion-2011.pdf

[2] García Notario, D. (2015). *Análisis de requisitos en el desarrollo del software*. Disponible en:  
https://e-archivo.uc3m.es/rest/api/core/bitstreams/a66b0a2d-fa7c-483f-ac5e-1476ff2da8eb/content
