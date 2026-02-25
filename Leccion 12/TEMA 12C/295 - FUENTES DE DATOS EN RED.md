Los dispositivos de red generan su propio sistema y registros de seguridad/auditoría, pero hay otras fuentes de datos de seguridad de red que pueden ser útiles para una investigación.

Registros de red
Los registros de red se generan mediante dispositivos como enrutadores, cortafuegos, switches y puntos de acceso. Los archivos de registro registrarán el funcionamiento y el estado del dispositivo en sí, el registro del sistema para el dispositivo, además del tráfico y los registros de acceso que graban el comportamiento de la red. Por ejemplo, los registros de acceso de la aplicación de red pueden revelar los siguientes tipos de amenaza:

Un registro de switch podría revelar un endpoint que intenta usar múltiples direcciones MAC para perpetrar un ataque en ruta.
Un registro de cortafuegos puede identificar la actividad de análisis en un puerto bloqueado.
Un registro de punto de acceso podría registrar eventos de desasociación que indiquen que un actor de amenazas intenta atacar la red inalámbrica.

Se extrae de un registro de enrutador SOHO típico a medida que se reinicia. Los eventos muestran que el enrutador restablece una conexión a internet/WAN, actualiza la fecha y la hora del sistema mediante el protocolo de tiempo de red (NTP), ejecuta una verificación de actualización de firmware y conecta un cliente inalámbrico. El cliente no está autenticado inicialmente, probablemente porque el usuario estaba ingresando la frase de contraseña incorrecta.

Registros de cortafuegos
Se puede configurar una regla de cortafuegos cualquiera para generar un evento cada vez que se active. Al igual que con la mayoría de los tipos de datos de seguridad, puede generarse rápidamente en una cantidad abrumadora de eventos. También es posible configurar reglas de solo registro. Por lo general, el registro de cortafuegos se utilizará al probar una regla nueva o solamente se habilitará para las reglas de alto impacto.

Un evento de auditoría de cortafuegos registrará una fecha/marca de tiempo, la interfaz en la que se activó la regla, ya sea que la regla coincida con el tráfico entrante/de entrada o saliente/de salida, y que el paquete haya sido aceptado o descartado. Los datos del evento también registrarán la información del paquete, como la dirección de origen y destino, y los números de puerto. Esta información puede ayudar a investigar el compromiso del host. Por ejemplo, supongamos que un IDS basado en host informa que un proceso malicioso en un servidor local está intentando conectarse a un puerto particular en un host de internet. El registro del cortafuegos podría confirmar si se permitió o denegó la conexión e identificar qué regla, potencialmente, debe ajustarse.

![[Pasted image 20250403090449.png]]


Registro de cortafuegos que muestra qué reglas de paso y bloqueo se han activado, con los puertos de origen y destino y las direcciones IP.

Como la acción de registro se configura por regla, es posible que un solo paquete active múltiples eventos.

Registros IPS/IDS
Un registro IPS/IDS es un evento cuando un patrón de tráfico coincide con una regla. Como esto puede generar un volumen muy alto de eventos, podría ser apropiado registrar solamente reglas de alta sensibilidad/impacto. Al igual que con el registro de cortafuegos, un solo paquete puede desencadenar varias reglas.

Un sistema de prevención de intrusiones también podría configurarse para registrar rechazos, restablecimientos y redirecciones de la misma manera que un cortafuegos.

Al igual que con los registros de protección de puntos de conexión, los datos resumidos de eventos de IDS/IPS se pueden visualizar en gráficos de paneles, para representar los niveles generales de amenaza. Un análisis detallado de los eventos de detección puede ayudar a atribuir eventos de intrusión a un actor específico y a desarrollar inteligencia de amenazas de tácticas, técnicas y procedimientos.

![[Pasted image 20250403090438.png]]

Visualización del mensaje de registro sin procesar generado por una alerta de Suricata IDS en el SIEM de Security Onion.