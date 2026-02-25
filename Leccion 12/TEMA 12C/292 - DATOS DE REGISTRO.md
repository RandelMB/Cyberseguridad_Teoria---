Los datos de registro son un recurso fundamental para investigar incidentes de seguridad. Además del formato de registro, también debe considerar el rango de fuentes para los archivos de registro y saber cómo determinar qué tipo de archivo de registro respaldará mejor cualquier escenario de investigación dado.

Los datos de eventos se obtienen mediante procesos que se ejecutan en dispositivos de red y hosts informáticos generales. Mediante el proceso, por lo general, se escriben los datos de los eventos en un archivo de registro o en una base de datos específicos. Cada evento está compuesto por datos y metadatos de mensajes:

Los datos de los mensajes de un evento son las notificaciones o alertas específicas generadas por el proceso, como "Error de inicio de sesión" o "Tráfico interrumpido por regla del cortafuegos".
Los metadatos de los eventos son el origen y la hora del evento. El origen puede incluir una dirección de host o de red, un nombre de proceso y campos de categorización o prioridad. 
El registro preciso requiere que todos los hosts se sincronicen con el mismo valor y formato de fecha y hora. Lo ideal es que cada host también esté configurado para usar la misma zona horaria o para usar una zona "neutral", como la hora coordinada universal (UTC).

Los hosts y aplicaciones de Windows pueden usar el registro de formato Event Viewer (Visor de eventos). Cada evento tiene un encabezado que informa el origen, el nivel, el usuario, la marca de tiempo, la categoría, las palabras clave y el nombre del host.

Syslog proporciona un formato, protocolo y software de servidor abiertos para registrar mensajes de eventos. Lo utiliza una amplia gama de tipos de host. Por ejemplo, los switches, los enrutadores, los cortafuegos, y los servidores y estaciones de trabajo UNIX o Linux pueden generar mensajes de syslog.

Un mensaje de syslog consta de un código PRI, un encabezado y una parte donde está el mensaje:

El código PRI se calcula a partir del recurso y un nivel de gravedad. 
El encabezado contiene una marca de tiempo, el nombre del host, el nombre de la aplicación, el ID del proceso y los campos de ID del mensaje. 
La parte del mensaje contiene una etiqueta que muestra el proceso de origen más el contenido. El formato del contenido depende de la aplicación. Puede utilizar campos delimitados por espacios o por comas o pares de nombre/valor.
Los datos de registro pueden mantenerse y analizarse en cada host individualmente, pero la mayoría de las organizaciones requieren una mejor visibilidad de las fuentes de datos y el monitoreo del host. El software SIEM puede ofrecer una vista de \"panel de vidrio\" de todos los hosts y dispositivos de red al recopilar y agregar registros de múltiples fuentes. Los registros se pueden recopilar a través de un agente que se ejecuta en cada host o mediante el uso de syslog (o similar) para reenviar datos de eventos.