


Donde el balance de carga distribuye el tráfico entre nodos de procesamiento independientes, el clustering (agrupamiento) permite que varios nodos de procesamiento redundantes que comparten datos entre sí acepten conexiones. De este modo, ofrece redundancia. Si uno de los nodos del clúster deja de funcionar, las conexiones pueden failover (conmutación por error) a un nodo en funcionamiento. Para los clientes, el clúster parece ser un único servidor. Un balanceador de carga distribuye las solicitudes de los clientes a través de los nodos del servidor disponibles en una granja o conjunto y, generalmente, se asocia con la gestión del tráfico web, mientras que los clústeres se utilizan para proporcionar redundancia y alta disponibilidad para sistemas como las bases de datos, los servidores de archivos y otros.

IP virtual 
Por ejemplo, una organización podría querer aprovisionar dos dispositivos balanceadores de carga para que si uno falla, el otro aún pueda gestionar las conexiones del cliente. A diferencia del equilibrio de carga con un solo dispositivo, la IP pública utilizada para acceder al servicio se comparte entre las dos instancias del clúster. Esta disposición se conoce como dirección IP virtual, compartida o flotante. Las instancias se configuran con una conexión privada, en la que cada una se identifica por su dirección IP “real”. Esta conexión ejecuta un protocolo de redundancia, como el Protocolo común de redundancia de direcciones (CARP), que permite que el nodo activo \"posea\" la IP virtual y responda a las conexiones. El protocolo de redundancia también implementa un mecanismo de latido para permitir el failover (conmutación por error) al nodo pasivo en caso de que el activo sufra una falla.

![[Pasted image 20250217111058.png]]

Description

El clúster de equilibrio de carga de la izquierda consta de un servidor virtual, un equilibrador de carga redundante activo y un equilibrador de carga redundante pasivo. La granja de servidores web de la derecha consta de tres servidores web. Los pasos son los siguientes  

1. Servicio de balanceo de carga configurado como cluster activo o pasivo
2. Los nodos del clúster se conectan mediante IPs internas y un protocolo de redundancia.  
3. El nodo activo responde a las peticiones en la IP virtual.


Topología de la arquitectura de balance de carga en clúster. (Imágenes © 123RF.com.)

Clustering (agrupamiento) activo/pasivo (A/P) y activo/activo (A/A)
En el ejemplo anterior, si un nodo está activo, el otro se mantiene pasivo. Esto se conoce como clustering (agrupamiento) activo/pasivo. La mayor ventaja de las configuraciones activo/pasivo es que el rendimiento no se ve afectado de forma negativa durante el failover (conmutación por error). Sin embargo, existen costos mayores de hardware y sistema operativo debido a la capacidad no utilizada.

Un clúster activo/activo significa que ambos nodos están procesando conexiones simultáneamente. Esto permite al administrador utilizar la capacidad máxima del hardware disponible mientras todos los nodos son funcionales. En caso de un failover (conmutación por error), la carga de trabajo del nodo fallido se transfiere de forma inmediata y transparente al nodo restante. En este momento, la carga de trabajo en los nodos restantes es mayor y el rendimiento se degrada.

	En una configuración activo/pasivo estándar, cada nodo activo debe coincidir con un nodo pasivo. Existen configuraciones N+1 y N+M que provisionan menos nodos pasivos que nodos activos, para reducir costos.

Agrupamiento de aplicaciones
El clustering (agrupamiento) también se utiliza comúnmente para aprovisionar servicios de aplicaciones tolerantes a fallas. Si un servidor de aplicaciones sufre una falla en medio de una sesión, se perderán los datos de estado de la sesión. El clustering (agrupamiento) de aplicaciones permite que los servidores del clúster comuniquen entre sí la información de la sesión. Por ejemplo, si un usuario inicia sesión en una instancia, la siguiente sesión puede comenzar en otra instancia y el nuevo servidor puede acceder a las cookies u otra información utilizada para establecer el inicio de sesión.