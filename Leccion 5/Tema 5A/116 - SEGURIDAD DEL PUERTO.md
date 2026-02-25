Cada puerto de pared y puerto de switch representa una oportunidad para que un actor de amenaza conecte un dispositivo a la red. Un actor de amenazas que puede operar un host con acceso físico a un segmento de red puede lanzar una variedad de ataques. 

El acceso a los puertos físicos del switch y al hardware del switch se debe restringir al personal autorizado. Para lograr esto, coloque los aparatos de switch en salas de servidores seguras o armarios de hardware con llave. Para evitar la conexión de dispositivos cliente no autorizados en puertos de pared no seguros, se puede desactivar de forma administrativa el puerto del switch al que se conecta el cable del puerto de pared o se puede quitar físicamente el cable de conexión del puerto del conmutador. Desactivar por completo los puertos de esta manera puede generar una gran cantidad de gastos administrativos y permite un margen de error. Además, no proporciona una protección completa, ya que un atacante podría desconectar un dispositivo de un puerto habilitado y conectar su propia máquina. En consecuencia, se desarrollaron métodos más sofisticados para garantizar la seguridad del puerto. 

Filtrado MAC y limitación MAC
El adaptador de red en cada equipo host se identifica mediante una dirección MAC. Configurar el filtrado de MAC significa que un puerto del switch solo permite que se conecten ciertas direcciones MAC. Esto se puede hacer mediante la creación de una lista de direcciones MAC válidas o la especificación de un límite en el número de direcciones permitidas. Por ejemplo, si la seguridad de los puertos está activada con un máximo de dos direcciones MAC, el switch registrará las dos primeras Mac que se conecten a ese puerto. El switch luego elimina cualquier tráfico de máquinas con diferentes direcciones MAC que intenten conectarse. 

![[Pasted image 20241120114722.png]]



Configuración de la inspección ARP en un switch Cisco. (Cortesía de Cisco Systems, Inc. No se permite el uso no autorizado).

802.1X y protocolo de autenticación extensible
Restringir el acceso por dirección MAC es difícil de administrar y sigue siendo propenso a la suplantación. Se obtiene una mayor seguridad al obligar a los equipos o usuarios a autenticarse antes de concederle el acceso completo a la red. El Control de acceso a la red [NAC] basado en puertos IEEE 802.1X permite que un switch requiera autenticación cuando un host se conecta a uno de sus puertos.  802.1X utiliza la arquitectura autenticación, autorización y registro [AAA]:

Suplicante (solicitante) es el dispositivo que solicita el acceso, como la PC o la computadora portátil de un usuario.
Autenticador es el dispositivo de conmutación (o cualquier tipo de dispositivo de acceso a la red).  Esto no valida las solicitudes de autenticación directamente, sino que actúa como un conducto para los datos de autenticación.
Servidor de autenticación: el servidor que contiene o puede ponerse en contacto con un directorio de objetos de red y que puede validar las solicitudes de autenticación, emitir autorizaciones y realizar el conteo de los eventos de seguridad.
El estándar 802.1X se implementa mediante dos protocolos:

Protocolo de autenticación extensible [EAP]:proporciona un marco para desplegar diferentes tipos de métodos de autenticación. A menudo se usa con certificados digitales para establecer una relación de confianza y crear un túnel seguro para transmitir la credencial de usuario o realizar la autenticación con una tarjeta inteligente sin una contraseña.
Servicio de autenticación remota de usuario por acceso telefónico [RADIUS]: permite que el autenticador y el servidor de autenticación comuniquen las decisiones de autenticación y autorización. El autenticador es un cliente RADIUS; el servidor de autenticación es un servidor RADIUS.
Cuando un host se conecta a un puerto de switch habilitado para 802.1X, el switch abre el puerto solo para el protocolo EAP sobre LAN (EAPoL). El puerto del switch solo permite el acceso completo a los datos cuando el host se autenticó. El switch recibe un paquete EAP con las credenciales del suplicante. Estos están cifrados y el switch no puede leerlos. El switch utiliza el protocolo RADIUS para enviar el paquete EAP al servidor de autenticación. El servidor de autenticación puede acceder al directorio de cuentas de usuario y validar la credencial. Si la autenticación es satisfactoria, se informa al switch que se puede conceder el acceso completo a la red.



![[Pasted image 20241120114732.png]]


Description
Los pasos son los siguientes:



El servidor RADIUS y el cliente están preconfigurados con el mismo secreto compartido.



El solicitante se conecta a la red.



El switch habilita EAPoL e instruye al solicitante a autenticarse.



El solicitante transmite datos EAP.



El switch cifra los datos EAP utilizando el secreto compartido y los reenvía al servidor RADIUS.



El servidor RADIUS descifra el paquete utilizando el secreto compartido y valida las credenciales.



El servidor RADIUS emite un Acceso-Aceptado.



El switch descifra el Acceso-Aceptado y abre el canal de red para el tráfico regular.

IEEE 802.1X Port-based Network Access Control con autenticación RADIUS y EAP. (Imágenes © 123RF.com.)