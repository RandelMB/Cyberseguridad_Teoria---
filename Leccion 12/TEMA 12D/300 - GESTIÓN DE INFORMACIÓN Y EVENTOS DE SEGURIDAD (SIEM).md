El software diseñado para ayudar a gestionar las entradas de datos de seguridad y proporcionar informes y alertas a menudo se describe como gestión de información y eventos de seguridad (SIEM). La función principal de una herramienta SIEM es recopilar y correlacionar datos de sensores de red y registros de dispositivos/host/aplicación. Además de los registros de los hosts basados en Windows y Linux, podría incluir switches, enrutadores, cortafuegos, sensores IDS, rastreadores de paquetes, escáner de vulnerabilidad, escáner de malware y sistemas de prevención de pérdida de datos (DLP).

![[Pasted image 20250403092007.png]]

Panel SIEM de Wazuh: los paneles configurables proporcionan una vista de estado de alto nivel de las métricas de seguridad de la red. (Captura de pantalla utilizada con permiso de Wazuh Inc.)

Colección basada en agentes y sin agentes
La recopilación es el medio por el cual el SIEM ingiere los datos de eventos de seguridad de varias fuentes. Existen tres tipos principales de recopilación de datos de seguridad:

Agent-based (Basado en agentes): este enfoque implica instalar un servicio de agente en cada host. A medida que ocurren eventos en el host, los datos de registro se filtran, agregan y normalizan en el host, y luego se envían al servidor SIEM para su análisis y almacenamiento. La recopilación de los equipos Windows/Linux/macOS tenderá a usar una colección basada en agentes. El agente debe ejecutarse como un proceso y podría usar de 50 a 500 MB de RAM, dependiendo de la cantidad de actividad y procesamiento que realice.
Oyente/recopilador:  en lugar de instalar un agente, los hosts se pueden configurar para enviar cambios de registro al servidor SIEM. Se ejecuta un proceso en el servidor de administración para analizar y normalizar cada fuente de registro/monitoreo. Este método se usa a menudo para recopilar registros de switches, enrutadores y cortafuegos, ya que es poco probable que sean compatibles con los agentes. Por lo general, se utiliza alguna variante del protocolo syslog para reenviar los registros del dispositivo al SIEM.
Sensor (Sensor): además de los datos de registro, el SIEM puede recopilar capturas de paquetes y datos de flujo de tráfico de los rastreadores. Un rastreador puede grabar datos de red utilizando la funcionalidad del puerto espejo de un switch o utilizando algún tipo de toque en los medios de transmisión de la red.
![[Pasted image 20250403091958.png]]

Archivo de configuración del agente para que las fuentes de eventos informen al SIEM de Wazuh. 

Agregación de registros 
A diferencia de la recopilación, la log aggregation (agregación de registros) se refiere a la normalización de datos de diferentes fuentes para que sean consistentes y se puedan buscar. El software SIEM presenta conectores o complementos para interpretar (o analizar) datos de distintos tipos de sistemas y abordar las diferencias entre las implementaciones de los proveedores. Cada agente, recopilador o fuente de datos del sensor requerirá su propio analizador para identificar los atributos y el contenido que se pueden asignar a los campos estándares en las herramientas de informes y análisis del SIEM. Otra función importante es normalizar las diferencias de fecha/zona horaria en una sola línea de tiempo.