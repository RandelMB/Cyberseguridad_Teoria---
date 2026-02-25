


Las características de arquitectura de red que crean segmentos asignados a subredes permiten la creación de una topología de seguridad basada en zonas. Las redes locales tienen un límite organizativo claro en el perímetro de la red. Los hosts que están fuera del perímetro se encuentran en una zona pública de Internet y no son de confianza. Los hosts que están dentro del perímetro tendrán diferentes niveles de confianza y requisitos de control de acceso.

Para representar la topología de seguridad interna, analice los sistemas y activos de datos que admiten flujos de trabajo e identifique aquellos que tienen requisitos de control de acceso similares:

- Los sistemas de bases de datos y archivos que alojan datos de la empresa y datos personales deben priorizar la confidencialidad y la integridad. Sin embargo, los datos no deben mantenerse dentro de una sola zona. Piense en el impacto cuando una zona se ve vulnerada. Si una sola zona almacena todos los tipos de activos de datos, el impacto será extremadamente alto. Separar diferentes tipos de información en diferentes zonas reducirá el impacto de la vulneración.
- Los dispositivos cliente deben priorizar la integridad y la disponibilidad. Estos dispositivos no deben almacenar datos y, por lo tanto, tienen un menor requisito de confidencialidad.
- Los servidores de aplicaciones de cara al público (web, correo electrónico, acceso remoto, etc.) también deben priorizar la integridad y la disponibilidad. No deben almacenar datos confidenciales, como las credenciales de la cuenta. Los servidores de acceso público no deben considerarse de plena confianza.
- Los servidores de aplicaciones que admiten la infraestructura de red (autenticación, directorio y monitoreo/registro, por ejemplo) deben mostrar altos niveles de confidencialidad, integridad y disponibilidad. Cualquier vulneración de estos servicios podría tener un impacto catastrófico.


Este análisis generará una lista de las zonas de seguridad necesarias. La arquitectura de red y la infraestructura de control de seguridad deben garantizar que estas zonas estén segregadas entre sí por segmentación física o lógica. El tráfico entre zonas debe estar estrictamente controlado mediante un dispositivo de seguridad, por lo general un cortafuegos. Las políticas de tráfico deben aplicar el principio del mínimo privilegio.

Se confía en los hosts en el sentido de que están bajo control administrativo y sujetos a los mecanismos de seguridad (software antivirus, derechos de usuario, actualización de software, etc.) que se configuraron para defender la red.

Una zona debe tener un punto de entrada y de salida conocido. Por ejemplo, si el único punto de acceso autorizado para una zona es un enrutador, colocar un punto de acceso inalámbrico dentro de la zona sería una violación de la seguridad.


![[Pasted image 20241120114521.png]]



Description
Un router o switch de capa 3 está conectado a un router de borde o firewall a través de un firewall proxy en línea que tiene una subred, 10.1.128.0/24. También está conectado a tres switches de acceso. El primer switch de acceso tiene una subred, 10.1.48.0/24 y está conectado a impresoras. El segundo switch de acceso está conectado a estaciones de trabajo y teléfonos VoIP. El router está conectado a la VLAN 32 a través de 10.1.32.0/24 y el switch de acceso. También está conectado a la VLAN 40 a través de 10.1.40.0/24 y el switch de acceso. El tercer switch de acceso está conectado a los servidores de aplicaciones privadas y bases de datos. El router está conectado a la VLAN 16 a través de 10.1.16.0/24 y el switch. También está conectado a la VLAN 24 a través de 10.1.24.0/24 y el switch de acceso. El router de borde o firewall está conectado a dos switches de acceso. El primer switch, que tiene una subred, 192.168.42.0/24, está conectado a un punto de acceso Wi-Fi, que, a su vez, está conectado a la red de invitados. El segundo switch, que tiene una subred, 172.16.0.0/24, está conectado a los servidores de aplicaciones públicas.



Las zonas de seguridad son las siguientes:



Zona 1, privilegio bajo: impresoras.

Zona 2, privilegio medio: estaciones de trabajo y teléfonos VoIP.

Zona 3, no confiable: red de invitados y servidores de aplicaciones públicas.

Zona 4: Internet.

Zona 5, privilegio alto: servidores de aplicaciones privadas y bases de datos.

El tráfico entre diferentes zonas de privilegio con respecto a los controles de acceso es el siguiente:



La zona de bajo privilegio acepta la mayoría de las nuevas conexiones (aceptación por defecto) desde la zona de privilegio medio.

La zona de privilegio medio previene nuevas conexiones (bloquear todo) desde la zona de bajo privilegio.

La subred, 10.1.32.0/24 previene nuevas conexiones desde la subred, 10.1.40.0/24 y viceversa.

La subred, 10.1.16.0/24 previene nuevas conexiones desde la subred, 10.1.24.0/24.

La subred, 10.1.24.0/24 acepta la mayoría de las nuevas conexiones desde la subred, 10.1.16.0/24.

La zona de privilegio medio previene nuevas conexiones desde Internet.

Internet acepta algunas nuevas conexiones (bloqueo por defecto) desde la zona de privilegio medio.

La zona de privilegio medio previene nuevas conexiones desde la zona de alto privilegio.

La zona de alto privilegio acepta algunas nuevas conexiones desde la zona de privilegio medio.

Uno de los puertos del router de borde o firewall conectado al firewall proxy en línea previene nuevas conexiones desde la zona no confiable.

La zona no confiable previene nuevas conexiones desde el router de borde.

Uno de los puertos del router de borde asociado con la subred, 192.168.42.0/24 previene nuevas conexiones desde Internet y Internet acepta la mayoría de las nuevas conexiones desde este puerto.

Uno de los puertos del router de borde asociado con la subred, 172.16.0.0/24 acepta la mayoría de las nuevas conexiones desde Internet y Internet previene nuevas conexiones desde este puerto.

Diagrama de red que muestra los niveles de privilegio de la zona de seguridad y las reglas de acceso simplificadas.

El diagrama ilustra cómo el tráfico entre hosts en zonas con diferentes sensibilidades de privilegio puede estar sujeto a controles de acceso:

1. Una zona de bajo privilegio que contiene hosts que son difíciles de proteger y parchear, como las impresoras, puede aceptar conexiones pero no puede iniciar solicitudes a ningún otro host.
2. Los dispositivos cliente en la LAN empresarial pueden realizar solicitudes autorizadas en diferentes zonas, como a servidores internos o sitios web de Internet, pero no pueden aceptar nuevas solicitudes de conexión.
3. Los hosts en una zona de invitados pueden acceder a Internet, pero no pueden acceder a la red LAN de la empresa.
4. Los servidores de cara al público pueden aceptar solicitudes de Internet, pero no pueden iniciar solicitudes a la LAN empresarial o a Internet.
5. Cuando los hosts están separados por VLAN dentro de la misma zona, se pueden configurar reglas de acceso adicionales. Por ejemplo, los servidores de aplicaciones deberían poder realizar solicitudes desde bases de datos, pero no debe poder hacerse al revés.


