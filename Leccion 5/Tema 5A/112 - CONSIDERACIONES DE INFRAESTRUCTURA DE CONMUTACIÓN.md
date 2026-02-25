



La función básica de la infraestructura de red es reenviar el tráfico de un nodo a otro. En cada capa, los nodos y los enlaces se organizan en una topología que se adapta mejor a los flujos de trabajo de la aplicación en términos de rendimiento y seguridad. Una topología es un diagrama que muestra cómo los nodos están física o lógicamente conectados por enlaces. 

Una red local es aquella instalada en un solo sitio y operada por una sola empresa. Esto también se conoce como una red de área local [LAN] empresarial. Primero nos centraremos en este tipo de red y luego revisaremos la arquitectura de las redes de sistemas integrados y en la nube. 

La infraestructura de conmutación local comienza con la disposición del cable. Las oficinas y las redes de campus de varios edificios por lo general se instalan de manera estándar, lo que se conoce como cableado estructurado:

- Los puertos de pared proporcionan conectividad para cada estación de trabajo. Un cable de conexión conecta el adaptador de red en la PC o la computadora portátil al puerto de pared.
- El cableado estructurado se ejecuta desde cada puerto de pared a través de conductos o huecos en la pared y el techo hasta un patch panel.
- Otro cable conecta el puerto del patch panel a un puerto del switch.


![[Pasted image 20241120114304.png]]



Description
Los componentes son los siguientes:



El cable de parcheo conecta la tarjeta de red del computador al puerto de pared.



El cable estructurado pasa por un conducto en la pared o el techo desde el puerto de pared hasta el panel de parcheo.



El cable estructurado termina en la parte trasera del panel de parcheo.



El cable de parcheo conecta el puerto del panel de parcheo al puerto del switch.

Topología física de los componentes en un sistema de cableado estructurado.

Puede describirse como una topología en estrella. El switch se encuentra en el centro con enlaces a los hosts que lo rodean. El switch puede establecer enlaces de datos entre dos hosts cualesquiera que estén conectados a él. Además, si un host envía una difusión a todos los nodos locales, el switch garantiza que todos los hosts conectados la reciban. Esto se denomina dominio de difusión. Todos los hosts forman parte del mismo segmento de red local de capa 2. 

Esta topología básica en estrella presenta una serie de problemas. Los dominios de difusión con cientos de hosts sufren penalizaciones de rendimiento. El segmento de red también es “plano” en términos de seguridad. Cualquier host puede comunicarse libremente con cualquier otro host en el mismo segmento. 

“Libremente” significa que ningún dispositivo o política de red impide las comunicaciones. Cada host puede configurarse con reglas de acceso o cortafuegos de host u otras herramientas de seguridad para evitar el acceso, pero la “vista desde la red” es que los hosts del mismo segmento son libres de intentar comunicarse.

Estas desventajas significan que las grandes redes usan un diseño jerárquico con dos o tres capas de reenvío. En el diseño jerárquico, hay varios bloques servidos por switches de acceso. Cada bloque de acceso es una topología en estrella para un grupo o bloque de hosts de red servidos por un switch de acceso. Los switches de acceso están conectados mediante enrutadores. Estos enrutadores crean dominios de difusión separados y pueden controlar el flujo de tráfico entre los bloques. Como cada bloque puede tener diferentes políticas de acceso, esta topología permite la creación de un modelo de seguridad basado en zonas.


![[Pasted image 20241120114324.png]]


Description
La estructura jerárquica incluye enrutamiento o direccionamiento IP, núcleo, acceso y conmutación o direccionamiento MAC. Un router o switch de capa 3 está conectado a un router de borde o firewall y a los tres switches de acceso. El primer switch de acceso está conectado a impresoras, el segundo está conectado a estaciones de trabajo y teléfonos VoIP, y el tercero está conectado a los servidores de aplicaciones privadas y bases de datos. El router de borde o firewall está conectado a un switch de acceso, que a su vez está conectado a un punto de acceso Wi-Fi, el cual está conectado a la red de invitados.



Red con una estructura jerárquica básica. Los switches de acceso implementan bloques de hosts con propiedades de seguridad similares, como impresoras, estaciones de trabajo, servidores y dispositivos invitados. Las comunicaciones dentro de un bloque utilizan el direccionamiento MAC y la función de reenvío del switch de acceso. Las comunicaciones entre estos bloques deben fluir a través de enrutadores en una capa central y utilizan el direccionamiento IP. 

A menudo verá el término “switch de capa 3”. Estos son dispositivos que implementan la red central. Realizan una combinación de enrutamiento y conmutación. Hay muchos tipos de switches con diferentes funciones para desempeñar en las arquitecturas de red locales y de centros de datos.

Mientras que las estaciones de trabajo cliente se conectan a los switches de red a través de puertos de pared y patch panels, los servidores y los dispositivos de red centrales por lo general se instalan en un área separada y segura, denominada sala de equipos o sala de servidores. Las computadoras del servidor se pueden conectar directamente a los puertos del switch mediante cables de conexión.
