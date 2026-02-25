El filtrado del sistema de nombres de dominio (DNS) es una técnica que bloquea o permite el acceso a sitios web específicos mediante el control de la resolución de nombres de dominio en direcciones IP. Se basa en el principio de que para que un dispositivo acceda a un sitio web, primero debe resolver su nombre de dominio en su dirección IP asociada, un proceso administrado por el DNS. Cuando se realiza una solicitud para resolver la URI de un sitio web, el filtro de DNS compara la solicitud con una base de datos de nombres de dominio. Si el dominio está asociado con actividades maliciosas o está en una lista no aprobada por cualquier razón, el filtro bloquea la solicitud y evita el acceso al sitio web potencialmente dañino.

El filtrado de DNS es sumamente efectivo por diversas razones. Algunas se enumeran a continuación:

- Proporciona un mecanismo de defensa proactivo mediante el bloqueo del acceso a sitios de suplantación de identidad conocidos, sitios de distribución de malware y otros destinos en línea maliciosos.
- Puede ayudar a hacer cumplir las políticas de uso aceptable (AUP) de una organización al bloquear el acceso a sitios web inapropiados o que distraen, y a garantizar que Internet se use de manera responsable y productiva.
- Puede proteger todos los dispositivos conectados a una red, incluidos los dispositivos de IoT, lo que proporciona una capa adicional de seguridad.
- Es una solución simple que es fácil de implementar y presenta un riesgo mínimo, lo que la convierte en un control de seguridad rentable adecuado para redes de cualquier tamaño. 


Si bien el filtrado de DNS es sumamente efectivo, debe combinarse con otras medidas de seguridad para lograr una protección integral.

Implementación del filtrado de DNS
El filtrado de DNS se implementa por medio de diferentes métodos y herramientas. Un método frecuente es a través de servicios de filtrado de DNS, como OpenDNS de Cisco (https://www.opendns.com/), Quad9 (https://www.quad9.net/) o CleanBrowsing (https://cleanbrowsing.org/). Estos servicios proporcionan resolución de DNS con filtrado integrado. Simplemente requieren que las organizaciones y los usuarios redirijan sus solicitudes de DNS a los servidores DNS del servicio de filtrado.

Las organizaciones que administran sus propios servidores DNS, como el servidor DNS de Microsoft o BIND, pueden implementar directamente el filtrado de DNS. Si bien es más complejo, este método proporciona un control completo sobre las políticas de filtrado y permite la integración de listas de bloqueo o fuentes RPZ (Response Policy Zone) en las configuraciones de los servidores.

Otra estrategia implica el uso de cortafuegos de DNS, que interceptan las consultas de DNS a nivel de red y aplican reglas de filtrado en consecuencia. Algunas herramientas de protección de puntos de conexión y software antivirus proporcionan capacidades de filtrado de DNS para brindar una protección a nivel de dispositivo ideal para computadoras portátiles y otros dispositivos móviles que pueden conectarse a numerosas redes con diferentes niveles de seguridad habilitados de manera predeterminada.

El software de código abierto Pi-hole (https://pi-hole.net/) o el ADGuard (https://github.com/AdguardTeam/AdguardHome) se pueden configurar como solucionadores de DNS local con capacidades de filtrado. Estas opciones de software se ejecutan en Linux y, por lo general, se implementan mediante hardware Raspberry Pi debido a su baja sobrecarga de rendimiento. Independientemente del método elegido, la personalización de las políticas de filtrado permite categorizar los sitios web para simplificar la creación de listas de bloqueo o permitir listas por requisitos. Mantener actualizados los filtros de DNS es fundamental para que el filtrado de DNS sea efectivo y se mantenga al día con la evolución de las amenazas y las necesidades cambiantes de la organización.

![[Pasted image 20250403074139.png]]

El panel administrativo de Pi-hole que muestra las estadísticas de resolución de DNS. (Captura de pantalla cortesía de Pi-hole).

Seguridad de DNS
El DNS es un servicio crítico que debe configurarse para ser tolerante a fallas. Los ataques de DoS son difíciles de perpetrarse contra los servidores que realizan la resolución de nombres de Internet, pero si un ataque puede dirigirse al servidor DNS en una red privada, es posible interrumpir seriamente el funcionamiento de esa red.

Para garantizar la seguridad del DNS en una red privada, los servidores DNS locales solo deben aceptar consultas recurrentes de hosts locales (preferiblemente hosts locales autenticados) y no de Internet. También se deben implementar medidas de control de acceso en el servidor para evitar que algún usuario malintencionado altere los registros manualmente. Del mismo modo, los clientes deben limitarse a utilizar solucionadores autorizados para realizar la resolución de nombres.

Los ataques a DNS también pueden dirigirse a la aplicación o configuración del servidor. Muchos servicios de DNS se ejecutan en BIND (Berkley Internet Name Domain), distribuido por el Internet Systems Consortium (isc.org). Existen vulnerabilidades conocidas en muchas versiones del servidor BIND, por lo que es fundamental parchear el servidor a la última versión. El mismo consejo general se aplica a otro software de servidor DNS, como el de Microsoft. Obtenga y compruebe los anuncios de seguridad y, a continuación, pruebe y aplique los parches y actualizaciones críticos y relacionados con la seguridad.

El footprinting de DNS consiste en obtener información sobre una red privada a través de su servidor de DNS, para realizar una transferencia de zona (todos los registros de un dominio) a un DNS no autorizado, o, simplemente, consultando el servicio de DNS mediante una herramienta como nslookup o dig. Para evitarlo, puede aplicar una  lista de  control de  acceso para impedir las transferencias de zonas a hosts o dominios no autorizados, y así evitar que un servidor externo obtenga información sobre la arquitectura de la red privada.

Las DNS Security Extensions (DNSSEC) (extensiones de seguridad de DNS) ayudan a mitigar los ataques de suplantación de identidad y envenenamiento al proporcionar un proceso de validación para las respuestas de DNS. Al habilitar las DNSSEC, el servidor autoritativo para la zona crea un “paquete” de registros de recursos (llamado RRset) que se firma con una clave privada (la clave de firma de zona). Cuando otro servidor solicita un intercambio de registros seguro, el servidor autoritativo devuelve el paquete junto con su clave pública, que se puede utilizar para verificar la firma.

La clave de firma de zona pública está firmada a su vez con una clave de firma de clave independiente. Se utilizan claves independientes para que, en caso de que la clave de firma de zona se vea comprometida, el dominio pueda seguir funcionando de forma segura al revocar la clave comprometida y emitir una nueva.

![[Pasted image 20250403074128.png]]

Servicios de DNS de Windows Server con DNSSEC habilitado. (Captura de pantalla utilizada con el permiso de Microsoft).

La clave de firma de clave para un dominio en particular es validada por el dominio principal o el ISP del host. Los Registros Regionales de Internet validan los fideicomisos de dominio de nivel superior y los servidores raíz de DNS se autovalidan, a través de un tipo de firma de clave de grupo de control M de N. Esto establece una cadena de confianza desde los servidores raíz hasta cualquier subdominio en particular.