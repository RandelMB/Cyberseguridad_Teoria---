
Un canal de gestión de acceso remoto se refiere al caso de uso específico de utilizar una red segura y una aplicación de shell para administrar un switch de red, enrutador, cortafuego o servidor. Las estaciones de trabajo administrativas seguras (SAW) utilizadas como clientes de gestión deben estar estrictamente protegidas, idealmente instaladas únicamente con el software necesario para acceder al canal administrativo, como un navegador web mínimo, un cliente de escritorio remoto o una terminal virtual SSH, por ejemplo. A los SAW se les deber denegar el acceso a Internet o estar restringidas a determinados sitios de proveedores aprobados para parches, controladores y soporte. Los dispositivos también deben estar sujetos a un control de acceso riguroso y a auditorías para que cualquier uso indebido se detecte lo más pronto posible.

Gestión fuera de banda
Los métodos de gestión remota son en banda (in-band) o fuera de banda (OOB). Un enlace de gestión en banda comparte el tráfico con otras comunicaciones en la red de producción. El método de conexión debe utilizar sesiones cifradas TLS, IPsec, RDP o SSH para garantizar la confidencialidad e integridad.

Un puerto de módem o de consola serie en un enrutador es un método de gestión físicamente fuera de banda. Un dispositivo de red también se puede gestionar mediante una interfaz basada en un navegador o un terminal virtual a través de Ethernet e IP. Este tipo de enlace de gestión se realiza fuera de banda, ya sea conectando el puerto utilizado para el acceso de gestión a una infraestructura de red físicamente separada o conectándose a una VLAN de gestión dedicada. Esto puede resultar costoso de implementar, pero la gestión fuera de banda es más segura y significa que se mantiene el acceso al dispositivo, incluso cuando surgen problemas que afectan la red de producción. 

Servidores de salto
Uno de los desafíos de la gestión de hosts expuestos a Internet, como en una subred protegida o en una red en la nube, es proporcionar acceso administrativo a los servidores y dispositivos ubicados dentro de ella. Por un lado, es necesario un enlace; por otro, la interfaz administrativa podría verse comprometida y explotada como punto de pivote en el resto de la red. En consecuencia, la gestión de los hosts a los que se les permite acceder a las interfaces administrativas en los hosts de la zona segura debe estar estrictamente controlada. La configuración y auditoría de este tipo de control es compleja cuando hay muchos servidores diferentes operando en la zona.

Una solución a esta complejidad es agregar un único servidor de administración, o servidor de salto (jump server), a la zona segura. El servidor de salto solo ejecuta el protocolo y puerto administrativo necesarios, como SSH o RDP. Los administradores se conectan al servidor de salto y lo utilizan para conectarse a la interfaz de administración en el servidor de aplicaciones.  La interfaz de administración del servidor de aplicaciones tiene una única entrada en su ACL (el servidor de salto) y niega los intentos de conexión de cualquier otro host. 

![[Pasted image 20241202174524.png]]


Description
Los pasos son los siguientes



1. Se puede utilizar una VPN para acceder al servidor de salto, que autoriza y reenvía el tráfico de gestión al servidor de aplicaciones.



2. El tráfico de gestión procedente de hosts autorizados de la red también puede enrutarse a través del servidor de salto.



3. El tráfico de gestión procedente de hosts no autorizados no está permitido.



4. Los servidores de aplicaciones sólo aceptan conexiones de tráfico de gestión desde el servidor de salto.



5. 5. El tráfico de aplicación común utiliza una red diferente.

Protección del tráfico de gestión mediante un servidor Jump. (Imágenes © 123RF.com.)