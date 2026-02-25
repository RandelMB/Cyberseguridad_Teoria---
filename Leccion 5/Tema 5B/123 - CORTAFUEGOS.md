

Un cortafuegos es un control preventivo diseñado para hacer cumplir las políticas sobre el tráfico que entra y sale de una zona de red.

**Filtrado de paquetes**
Un cortafuegos de filtrado de paquetes se configura especificando un grupo de reglas llamado lista de control de acceso (ACL). Cada regla define un tipo específico de paquete de datos y la acción que se debe tomar cuando un paquete coincide con la regla. Un cortafuegos de filtrado de paquetes puede inspeccionar los encabezados de los paquetes de IP. Las reglas se basan en la información que se encuentra en esos encabezados:

- Filtrado de IP: acepta o deniega el tráfico en función de la dirección IP de origen o destino de los bits.  La mayoría de los cortafuegos pueden filtrar por direcciones MAC.
- Tipo/ID de protocolo: es un paquete IP que lleva un protocolo identificado. Lo más habitual es que se trate de datos TCP o UDP. Otros tipos incluyen tráfico de diagnóstico del protocolo de mensajes de control de internet (ICMP) y protocolos que facilitan el enrutamiento.
- Filtrado/seguridad de puerto: acepta o deniega un paquete en función de los números de puerto TCP/UDP de origen y destino.

Si la acción está configurada para aceptar o permitir, el cortafuegos permite que el paquete pase. Una acción de caída o denegación descarta silenciosamente el paquete. Una acción de rechazo bloquea el paquete, pero responde al remitente con un mensaje ICMP, como \"puerto inalcanzable\".

Las ACL separadas filtran el tráfico entrante y saliente. El control del tráfico saliente puede bloquear las aplicaciones no autorizadas para ejecutarse en la red y derrotar el malware, como las backdoors (puertas traseras). 

**Ubicación y atributos del dispositivo de cortafuegos**
Los cortafuegos se pueden implementar como varios tipos de aparatos de hardware o como software que se ejecuta en un host de computación general. Algunos tipos de cortafuegos son más adecuados para colocarlos en los límites o los bordes zonales de la red; otros están diseñados para proteger hosts individuales.

Un cortafuegos de dispositivo es un cortafuegos de hardware autónomo implementado para supervisar el tráfico que entra y sale de una zona de red. Un cortafuegos de dispositivo se puede implementar de tres maneras:

- Enrutado (capa 3): el cortafuegos realiza el reenvío entre subredes. Cada interfaz en el cortafuegos se conecta a una subred diferente y representa una zona de seguridad diferente. Cada interfaz se configura con una dirección IP y una Mac.
- Puente (capa 2): el cortafuegos inspecciona el tráfico que pasa entre dos nodos, como un enrutador y un switch. Puentea las interfaces Ethernet entre los dos nodos, funcionando como un switch. A pesar de realizar el reenvío en la capa 2, el cortafuegos aún puede inspeccionar y filtrar el tráfico sobre la base de toda la gama de encabezados de paquetes. Las interfaces del cortafuegos están configuradas con direcciones MAC, pero no con direcciones IP.
- Inline (capa 1): el cortafuegos actúa como un segmento de cable. Ninguna de las dos interfaces tiene direcciones MAC ni IP. El tráfico recibido en una interfaz se bloquea o reenvía a través de la otra interfaz. También se denomina cable virtual o "bump-in-the-wire". 
- Tanto los modos de cortafuegos inline como puenteados pueden denominarse "modos transparentes". El caso de uso típico para un modo transparente es implementar un cortafuegos sin tener que reconfigurar las subredes ni reasignar las direcciones IP en otros dispositivos. Por ejemplo, podría implementar un cortafuegos transparente frente a un host de servidor web sin tener que cambiar la dirección IP del host. Como alternativa, este tipo de cortafuegos podría colocarse entre un enrutador y un switch.

		Un cortafuegos transparente necesita una interfaz adicional para la gestión y la configuración. Sí tiene una dirección IP. Un cortafuegos enrutado puede tener una interfaz de administración exclusiva o aceptar el tráfico de administración en cualquier interfaz. Usar una interfaz de administración exclusiva es más seguro.


Panel de control de estado para la plataforma de seguridad de código abierto OPNsense. (Captura de pantalla cortesía de OPNsense).

Un cortafuegos de enrutador o un dispositivo de enrutador de cortafuegos implementa la funcionalidad de filtrado como parte del firmware del enrutador. La diferencia es que un dispositivo enrutador está diseñado principalmente para enrutamiento, con un cortafuegos como característica secundaria. Los enrutadores/módems de internet SOHO vienen con un cortafuegos incorporado, por ejemplo. 
