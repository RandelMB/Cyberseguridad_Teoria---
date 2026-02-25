

Cuando se utiliza infraestructura en la nube, los riesgos de seguridad no se transfieren, sino que se comparten entre el proveedor de la nube y el cliente. El proveedor de la nube es responsable de garantizar la seguridad de la infraestructura subyacente, mientras que al cliente le corresponde la responsabilidad de proteger sus aplicaciones y datos. Es importante elegir un proveedor de servicios en la nube que ofrezca funciones sólidas de seguridad, como cifrado, controles de acceso y seguridad de red. 

El modelo de responsabilidad compartida describe el equilibrio de responsabilidades entre un cliente y un proveedor de servicios en la nube (CSP) para implementar la seguridad en una plataforma en la nube. La complejidad de la división de responsabilidades varía en función de si el modelo de servicio es SaaS, PaaS o IaaS. Por ejemplo, en un modelo SaaS, el CSP realiza la configuración y el control del sistema operativo como parte de la oferta de servicios. Por el contrario, la seguridad del sistema operativo se comparte entre el CSP y el cliente en un modelo IaaS. Una matriz de responsabilidades establece estos deberes en un formato claro y tabular:

![[Pasted image 20250210093401.png]]

Description

Los encabezados de las columnas dicen: responsabilidad, on-premises, IaaS, PaaS, SaaS, FaaS, CIS controls cloud companion guide y CIS foundations benchmarks.



Los datos son los siguientes:



Clasificación y responsabilidad de los datos: cliente de la nube para on-premises, IaaS, PaaS, SaaS y FaaS. Guía complementaria de controles de la nube de CIS, sí. Puntos de referencia de CIS foundations, sí.



Protección de clientes y puntos finales: cliente de nube para locales, IaaS y PaaS. Cliente de nube y proveedor de nube para SaaS y FaaS. Guía complementaria de controles en la nube de CIS, sí. Puntos de referencia de CIS foundations, sí.



Gestión de identidades y accesos: cliente de nube para IaaS y local. Cliente de nube y proveedor de nube para PaaS, SaaS y FaaS. Guía complementaria de controles en la nube de CIS, sí. Puntos de referencia de CIS foundations, sí. Gestión de identidades y accesos: cliente de nube para on-premises e IaaS. Cliente de nube y proveedor de nube para PaaS, SaaS y FaaS. Guía complementaria de controles en la nube de CIS, sí. Puntos de referencia de CIS foundations, sí.



Controles a nivel de aplicaciones: cliente de nube para locales e IaaS. Cliente de nube y proveedor de nube para PaaS, SaaS y FaaS. Guía complementaria de controles en la nube de CIS, sí. Puntos de referencia de CIS foundations, sí.



Controles de red: cliente de nube para locales. Cliente de nube y proveedor de nube para laaS. Proveedor de nube para PaaS, SaaS y FaaS. Guía complementaria de controles en la nube de CIS, sí. CIS foundations benchmarks, sí.



Infraestructura de host: cliente de nube para locales. Cliente de nube y proveedor de nube para laaS. Proveedor de nube para PaaS, SaaS y FaaS. Guía complementaria de controles en la nube de CIS, sí. Puntos de referencia de CIS foundations, no. Seguridad física: cliente de nube para instalaciones locales. Proveedor de nube para laaS, PaaS, SaaS y FaaS. Guía complementaria de controles en la nube de CIS, no. CIS foundations benchmarks, no.

					Modelo de responsabilidad

*Es de suma importancia identificar el límite entre las responsabilidades del cliente y del proveedor de la nube, en términos de seguridad, con el fin de reducir el riesgo de introducir vulnerabilidades en el entorno.*

En términos generales, las responsabilidades del cliente y del proveedor de la nube abarcan las siguientes áreas:

Proveedor de servicios en la nube 

- Seguridad física de la infraestructura
- Protección de equipos informáticos, de almacenamiento y de red
- Seguridad de los elementos fundamentales de la red, como la protección DDoS
- Copia de seguridad y recuperación de almacenamiento en la nube
- Seguridad del aislamiento de recursos de infraestructura en la nube entre inquilinos
- Identidad de recursos del inquilino y control de acceso
- Seguridad, monitoreo y respuesta a incidentes para la infraestructura
- Seguridad y gestión de los centros de datos ubicados en múltiples regiones geográficas
Cliente de servicio en la nube

- Gestión de identidad del usuario
- Configuración de la ubicación geográfica para almacenar datos y ejecutar servicios
- Controles de acceso de usuarios y servicios a recursos de la nube
- Configuración de seguridad de datos y aplicaciones
- Protección de los sistemas operativos, cuando se implementan
- Uso y configuración de cifrado, en especial la protección de claves
La complejidad de la división de responsabilidades varía en función de si el modelo de servicio es SaaS, PaaS o IaaS. Por ejemplo, en un modelo SaaS, el CSP realiza la configuración y el control de la red como parte de la oferta de servicios. En un modelo IaaS, la responsabilidad de la configuración de la red es compartida entre el CSP y el cliente.

Un concepto fundamental al utilizar recursos en la nube radica en que la implementación y gestión de controles de seguridad no es una tarea pasiva o automática. La identificación del límite entre las responsabilidades del cliente y del proveedor de servicios en la nube demanda un esfuerzo deliberado.