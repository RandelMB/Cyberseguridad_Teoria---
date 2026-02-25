
El reenvío de capa 3, o enrutamiento, aplica un esquema de direccionamiento lógico para identificar cada red. La arquitectura de capa 3 representa la segmentación lógica de las redes y la creación de redes dentro de las redes o subredes. Cada subred es un dominio de difusión independiente. En la capa 3, los nodos se identifican mediante direcciones de Internet Protocol (IP) (Protocolo de Internet [IP]) y los enlaces se identifican mediante rutas.

Protocolo de internet
El Internet Protocol (IP) [Protocolo de Internet (IP)] proporciona el mecanismo de direccionamiento para redes y subredes lógicas. Una dirección IP de 32 bits versión 4 (IPv4) se escribe en notación decimal con puntos, con un prefijo de red o una máscara de subred para dividir la dirección en partes de ID de red e ID de host. Por ejemplo, en la dirección IP 10.1.1.0/24, el prefijo /24 indica que las primeras tres cuartas partes de la dirección (10.1.0.x) es el ID de red, mientras que el resto identifica de forma única un host en esa red. Este prefijo /24 también se puede escribir como una máscara de subred en la forma 255.255.255.0.

En la arquitectura de red jerárquica, cada bloque de acceso se puede designar como una subred IP separada. Este sistema de direccionamiento lógico de capa 3 facilita la escritura de reglas de control de acceso para el tráfico que puede fluir entre bloques o zonas.

![[Pasted image 20241120114412.png]]


Description
Un router o switch de capa 3 está conectado a un router de borde o firewall a través de un firewall proxy en línea que tiene una subred, 10.1.128.0 barra 24. También está conectado a tres switches de acceso a través de las subredes 10.1.48.0 barra 24, 10.1.32.0 barra 24 y 10.1.16.0 barra 24. El primer switch de acceso está conectado a impresoras, el segundo está conectado a estaciones de trabajo y teléfonos VoIP, y el tercero está conectado a los servidores de aplicaciones privadas y bases de datos. El router de borde o firewall está conectado a un switch de acceso a través de una subred, 192.168.42.0 barra 24. El switch de acceso está conectado a un punto de acceso Wi-Fi, que, a su vez, está conectado a la red de invitados.



A cada bloque de acceso se le asignó una subred. La red de invitado está separada de la LAN empresarial de manera lógica y utiliza una red IP completamente diferente.

Las redes también pueden utilizar el direccionamiento IPv6 de 128 bits. Las direcciones IPv6 se escriben mediante notación hexadecimal en el formato general: 2001:db8::abc:0:def0:1234. En IPv6, los últimos 64 bits se fijan como el ID de interfaz del host. Los primeros 64 bits contienen información de red en una jerarquía establecida. Por ejemplo, los enrutadores de un ISP pueden usar los primeros 48 bits para determinar dónde está alojada la red en el Internet global. Dentro de esa red, el administrador del sitio puede usar los 16 bits restantes (de 64) para dividir la red local en subredes.

Un paquete que se envía a través de IP debe reenviarse mediante el direccionamiento de capa 2. IPv4 utiliza el protocolo de resolución de direcciones (ARP) para asignar la interfaz IP de un host a una dirección MAC. IPv6 utiliza el protocolo Protocolo de descubrimiento cercano (ND) para el mismo propósito.

LAN virtuales
Asignar la topología IP lógica a los conmutadores de hardware físico no siempre es sencillo. Este problema se resuelve con la función de LAN virtual (VLAN) compatible con la mayoría de los switches. Todos los switches conectados juntos en la misma red local se pueden configurar con un conjunto congruente de ID de VLAN. Un ID de VLAN es un valor de 2 a 4094. A cualquier puerto de switch se le puede asignar a una VLAN específica, independientemente de la ubicación física del switch. Se pueden asignar diferentes puertos en el mismo switch a diferentes VLAN. 

Cada VLAN es un dominio de difusión independiente. Todo tráfico enviado de una VLAN a otra debe enrutarse. Esto significa que la segmentación impuesta por las VLAN en la capa 2 se puede asignar a las divisiones lógicas definidas por las subredes IP en la capa 3.


![[Pasted image 20241120114423.png]]




Description
Un router o switch de capa 3 está conectado a un router de borde o firewall a través de un firewall proxy en línea que tiene una subred, 10.1.128.0/24. También está conectado a tres switches de acceso. El primer switch de acceso tiene una subred, 10.1.48.0/24 y está conectado a impresoras. El segundo switch de acceso está conectado a estaciones de trabajo y teléfonos VoIP. El router está conectado a la VLAN 32 a través de 10.1.32.0/24 y el switch de acceso. También está conectado a la VLAN 40 a través de 10.1.40.0/24 y el switch de acceso. El tercer switch de acceso está conectado a los servidores de aplicaciones privadas y bases de datos. El router está conectado a la VLAN 16 a través de 10.1.16.0/24 y el switch de acceso. También está conectado a la VLAN 24 a través de 10.1.24.0/24 y el switch de acceso. El router de borde o firewall está conectado a un switch de acceso que tiene una subred, 192.168.42.0/24. El switch de acceso está conectado a un punto de acceso Wi-Fi, que, a su vez, está conectado a la red de invitados.



La configurón de VLAN pmite l segmentaión de stscocadsal mim sitch. Cada VLAN tiene una ubredsepaada. El ráfco etrehosts e dieentes VLAN debe par por el enado o l switch de capa 3re.

En el diagrama anterior, el bloque de acceso para dispositivos cliente utiliza dos VLAN para segmentar los hosts de la computadora de la estación de trabajo (VLAN32) de los teléfonos de voz sobre protocolo de Internet (VoIP) (VLAN40). Las VLAN se asignan a dos subredes: 10.1.32.0/24 y 10.1.40.0/24. 

Un teléfono VoIP con dirección IP 10.1.40.100 necesitaría usar un enrutador para ponerse en contacto con un host de computadora con IP 10.1.32.100. Los dos hosts pueden estar conectados al mismo switch, pero la configuración de VLAN les impide comunicarse entre sí directamente. Además, una regla de control de acceso configurada en el enrutador podría evitar este tipo de comunicación si se considerara un riesgo para la seguridad.

La topología de VLAN se puede extender a través de múltiples switches. Considere el escenario en el que la oficina se expande a un segundo piso, que requiere un aparato de switch adicional para aprovisionar puertos suficientes. Los mismos ID de VLAN y subredes podrían configurarse para el piso dos, lo que hace que los dispositivos de los dos pisos formen parte de los mismos dos segmentos de estación de trabajo y VoIP. 