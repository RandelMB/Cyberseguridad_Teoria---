


El acceso remoto significa que el dispositivo del usuario no realiza una conexión directa por cable o inalámbrica a la red. La conexión se realiza a través de una red intermedia. 

Históricamente, el acceso remoto utilizaba módems analógicos conectados a través del sistema telefónico. Hoy en día, la mayoría de los accesos remotos se implementan como redes privadas virtuales (VPN), que funcionan a través de redes de proveedores de servicios de Internet (ISP). 

Con una VPN de acceso remoto, los clientes se conectan a una puerta de enlace VPN en el borde de la red privada. Esta topología de VPN de cliente a sitio es el modelo “teletrabajador”, que permite a los trabajadores remotos y empleados que trabajan en el campo conectarse a la red corporativa El protocolo VPN establece un túnel para mantener privado el contenido, incluso cuando los paquetes pasan por los enrutadores de los proveedores de servicios de Internet.


![[Pasted image 20241202173539.png]]


Description
La subred de acceso remoto rastreada consta de una pasarela VPN y un router o cortafuegos, y la red local consta de un router o cortafuegos y servidores LAN. Los pasos son los siguientes:



El host cliente VPN se conecta a una pasarela VPN utilizando cualquier tipo de método de acceso de abonado a Internet.



La pasarela VPN autentica al usuario y crea un túnel cifrado seguro.



El tráfico del cliente VPN se encamina a través de la red y puede acceder a los servicios autorizados.

Acceso remoto/VPN (Imágenes © 123RF.com.)

También se puede implementar una VPN en un modelo de sitio a sitio para conectar dos o más redes privadas. Mientras que las conexiones VPN de acceso remoto suelen ser iniciadas por el cliente, una VPN de sitio a sitio está configurada para funcionar automáticamente. Las puertas de enlace intercambian información de seguridad utilizando el protocolo en el que se basa la VPN. Así se establece una relación de confianza entre las puertas de enlace y se establece una conexión segura a través de la cual se canalizan los datos. Los hosts de cada sitio no necesitan ser configurados con ninguna información sobre la VPN. La infraestructura de enrutamiento en cada sitio determina si se debe entregar el tráfico localmente o enviarlo a través del túnel de VPN.

![[Pasted image 20241202173554.png]]


Description
Una VPN de sitio a sitio consta de tres componentes. Una sucursal formada por los servidores y clientes de la sucursal y el router o cortafuegos o pasarela VPN. Una subred blindada en la sede central formada por la pasarela VPN y el router o cortafuegos. Una red local en la sede central formada por el router o cortafuegos y los servidores de la sede central. Los pasos son los siguientes



1. La pasarela VPN de una sucursal establece una conexión VPN con la sede central.



2. El tráfico procedente de un host de una sede remota se encamina y encapsula automáticamente mediante el enlace VPN.

VPN de sitio a sitio. (Imágenes © 123RF.com.)

Una tercera topología es un túnel de host a host. Este es un medio para asegurar el tráfico entre dos equipos cuando la red privada no es de confianza.

A lo largo de los años, se utilizaron varios protocolos VPN. Los protocolos heredados, como el Protocolo de túnel punto a punto (PPTP), quedaron obsoletos porque no ofrecen la seguridad adecuada. La seguridad de la capa de transporte (TLS) y la seguridad de protocolo de Internet (IPsec) son actualmente las opciones preferidas para configurar el acceso VPN. 