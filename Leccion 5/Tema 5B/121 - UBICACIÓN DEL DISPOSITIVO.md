

La selección de controles efectivos para la infraestructura de red es el proceso de elegir el tipo y la ubicación de los dispositivos y el software de seguridad. El objetivo es hacer cumplir la segmentación, aplicar controles de acceso y monitorear el tráfico en busca de violaciones de las políticas.

La selección de controles efectivos se rige por el principio de la defensa en profundidad. La defensa en profundidad  significa que las zonas críticas para la seguridad están protegidas por diversos controles preventivos, de detective y correctivos que operan en cada capa del modelo OSI. La defensa en profundidad se garantiza mediante una selección cuidadosa de la ubicación del dispositivo dentro de la topología de la red. Hay tres opciones:

- Los controles preventivos: a menudo se colocan en el borde de un segmento o una zona de la red. Los controles preventivos, como los cortafuegos, hacen cumplir las políticas de seguridad sobre el tráfico que entra y sale del segmento, lo que garantiza la confidencialidad y la integridad. Un control de balanceador de carga garantiza una alta disponibilidad para el acceso a la zona.
- Controles de detective: se pueden colocar dentro del perímetro para monitorear el tráfico intercambiado entre los hosts dentro del segmento. Esto proporciona alertas de tráfico malicioso que ha evadido los controles perimetrales.
- Los controles preventivos, de detective y correctivos: se pueden instalar en los hosts como una capa de protección del punto de conexión, además de los controles de la infraestructura de red.


![[Pasted image 20241202172127.png]]


Description
Un router o switch de capa 3 está conectado a un router de frontera o firewall. El router o switch de capa 3 está conectado a tres switches de acceso. El primer conmutador de acceso tiene una subred, 10.1.48.0 barra 24 y está conectado a impresoras. El segundo conmutador de acceso está conectado a estaciones de trabajo y terminales VoIP. El router está conectado a la VLAN 32 a través de 10.1.32.0 barra 24 y el conmutador de acceso. También está conectado a la VLAN 40 a través de 10.1.40.0 barra 24 y el conmutador de acceso. El tercer conmutador de acceso está conectado a los servidores privados de aplicaciones y bases de datos. El router está conectado a la VLAN 16 a través de 10.1.16.0 barra 24 y el switch de acceso. También está conectado a la VLAN 24 a través de 10.1.24.0 barra 24 y el conmutador de acceso. El enrutador de frontera o cortafuegos está conectado a dos conmutadores de acceso. El primer conmutador que tiene una subred, 192.168.42.0 barra 24 está conectado a un punto de acceso Wi-Fi, que, a su vez, está conectado a la red de invitados. El segundo switch que tiene una subred, 172.16.0.0 barra 24 y está conectado a servidores públicos de aplicaciones. La colocación de los diferentes controles de seguridad es la siguiente:

*Colocación de controles de seguridad para garantizar la diversidad y la defensa en profundidad.*

A modo de ilustración, el diagrama muestra cómo se pueden colocar diferentes tipos de control dentro de la red para garantizar la defensa en profundidad:

- En el borde de la red, un control preventivo, como un cortafuegos, hace cumplir las reglas de acceso para el tráfico de entrada y salida.
- Un sensor colocado inline (insertado) detrás del cortafuegos fronterizo transmite el tráfico a un sistema de detección de intrusiones para implementar el control de detectives e identificar el tráfico malicioso que ha evadido el cortafuegos.
- Las listas de control de acceso configuradas en los enrutadores internos hacen cumplir las reglas para el tráfico que se reenvía entre las zonas internas y los hosts.
- El tráfico entrante para los servidores públicos puede estar mediado por un balanceador de carga, que proporciona un control correctivo para mitigar los ataques de denegación de servicio.
- Los sensores conectados a los puertos de switch espejados permiten la detección de intrusiones para los hosts o zonas de nivel de privilegio más sensibles.


En cada host, el software de protección de puntos de conexión aplica una serie de controles preventivos, de detectives y correctivos para mitigar las amenazas que han evadido los controles de la red. El software de punto de conexión puede implementar cortafuegos de host, antivirus, detección de intrusión y prevención de pérdida de datos.