Los informes de gestión pueden utilizarse para la supervisión diaria de los recursos informáticos y la infraestructura de red. No todos los problemas se pueden identificar a partir de alertas y alarmas. La ejecución de un informe personalizado permite a un gerente verificar los resultados de la actividad de registro y monitoreo a fin de garantizar que la red permanezca en un estado seguro.

Monitores de red
A diferencia del monitoreo de tráfico de red, un monitor de red recopila datos sobre los dispositivos de infraestructura de red, como switches, puntos de acceso, enrutadores y cortafuegos. Esto se utiliza para supervisar el estado de carga de la CPU/memoria, las tablas de estado, la capacidad del disco, las velocidades y temperatura del ventilador, las estadísticas de utilización de enlace de red, estadísticas de errores, entre otros. Otra función importante es un mensaje de latido para indicar la disponibilidad. 

Estos datos podrían recopilarse utilizando el Protocolo de administración de red simple (SNMP). Una captura SNMP informa al sistema de administración de un evento destacado, como una falla del puerto, sobrecalentamiento del chasis, falla de energía o utilización excesiva de la CPU. El umbral para activar capturas se puede establecer para cada valor. Esto proporciona un mecanismo para alertas y alarmas ante problemas de hardware.

Además de respaldar la disponibilidad, el monitoreo de red podría revelar condiciones inusuales que podrían indicar algún tipo de ataque.

NetFlow
Un recopilador de flujos es un medio para registrar metadatos y estadísticas sobre el tráfico de red en lugar de registrar cada trama. El tráfico de red y los datos de flujo pueden provenir de una amplia variedad de fuentes (o sondas), como switches, enrutadores, cortafuegos y proxies web. Las herramientas de análisis de flujo pueden proporcionar funciones como las siguientes:

Destacar las tendencias y patrones en el tráfico generado por aplicaciones, hosts y puertos específicos.
Alerta basada en la detección de anomalías, patrones de análisis de flujo o disparadores personalizados.
Herramientas de visualización que muestran un mapa de conexiones de red y facilitan la interpretación de patrones de tráfico y datos de flujo.
Identificación de patrones de tráfico que revelan comportamientos de usuarios no autorizados, malware en tránsito, túneles o aplicaciones que exceden su ancho de banda asignado.
Identificación de intentos de malware para contactar con un controlador o canal de comando y control (C&C).
NetFlow es un medio desarrollado por Cisco para reportar información de flujo de red a una base de datos estructurada. NetFlow se redesarrolló como el éstandar IETF (tools.ietf.org/html/rfc7011) de exportación de información de flujo IP (IPFIX). Un flujo de tráfico particular puede definirse mediante paquetes que comparten las mismas características, denominados claves. Una selección de claves se denomina etiqueta de flujo, mientras que el tráfico que coincide con una etiqueta de flujo se denomina registro de flujo. Una etiqueta de flujo está definida por paquetes que comparten las mismas características clave, como direcciones IP de origen y destino y tipo de protocolo. Estos cinco bits de información se denominan “5-tupla”. Una tupla de 7 agrega los datos de la interfaz de entrada y del tipo de servicio IP. Cada exportador almacena en caché los datos de los flujos recién vistos y configura un temporizador para determinar la caducidad del flujo. Cuando un flujo caduca o se vuelve inactivo, el exportador transmite los datos a un recopilador.

![[Pasted image 20250403092537.png]]

Edición comunitaria de ntopng utilizada para supervisar los datos de tráfico de NetFlow. (Captura de pantalla cortesía de ntop).