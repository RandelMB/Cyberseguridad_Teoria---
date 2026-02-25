

Un cortafuegos de filtrado de paquetes básicos no tiene estado. Significa que no conserva la información sobre las sesiones de red. Cada paquete se analiza de forma independiente, sin registro de los paquetes procesados anteriormente. Este tipo de filtrado requiere el menor esfuerzo de procesamiento, pero puede ser vulnerable a los ataques que se extienden en una secuencia de paquetes. Un cortafuegos sin estado también puede introducir problemas en el flujo de tráfico, especialmente cuando se utiliza algún tipo de balance de cargas o cuando los clientes o servidores necesitan hacer uso de puertos asignados dinámicamente. 

Un cortafuegos de inspección de estado rastrea la información sobre la sesión establecida entre dos hosts. Todos los cortafuegos incorporan ahora algún nivel de capacidad de inspección con estado. Los datos de la sesión se almacenan en una tabla de estado.. Cuando llega un paquete, el cortafuegos lo comprueba para confirmar si pertenece a una conexión existente. Si no lo hace, aplica las reglas ordinarias de filtrado de paquetes para determinar si lo permite. Una vez que se ha permitido la conexión, el cortafuegos, por lo general, permite que el tráfico pase sin supervisarlo, con el fin de reservarse el esfuerzo de procesamiento.

![[Pasted image 20241202172649.png]]



Tabla de estados en el dispositivo de cortafuegos de OPNsense. (Captura de pantalla cortesía de OPNsense). 

La inspección con estado puede producirse en la capa 4 y la capa 7.

**Cortafuegos de capa 4**
La capa 4 es la capa de transporte OSI. Un cortafuegos de capa 4 examina el protocolo de enlace de tres vías TCP para distinguir las conexiones nuevas de las establecidas. Una conexión TCP legítima debe seguir una secuencia SYN > SYN/ACK > ACK para establecer una sesión, que luego se rastrea utilizando números de secuencia. Las desviaciones a partir de aquí, como SYN sin ACK o las anomalías en el número de secuencia, se pueden descartar como inundaciones maliciosas o intentos de secuestro de sesión. El cortafuegos se puede configurar para responder a dichos ataques bloqueando las direcciones IP de origen y limitando las sesiones. También puede rastrear el tráfico UDP, aunque esto es más difícil, ya que UDP es un protocolo sin conexiones. También es probable que pueda detectar anomalías en el encabezado IP y en ICMP.


![[Pasted image 20241202172708.png]]



	Configuración de la regla del cortafuegos de OPNsense: los ajustes avanzados permiten que se apliquen los máximos para los estados y las conexiones. (Captura de pantalla cortesía de OPNsense).

**Cortafuegos de capa 7**
Un cortafuegos de capa 7 puede inspeccionar los encabezados y la carga útil de los paquetes de la capa de aplicación. Una función clave consiste en verificar que el protocolo de la aplicación coincida con el puerto porque el malware puede intentar enviar datos TCP sin procesar a través del puerto 80 solo porque el puerto 80 está abierto, por ejemplo. Como otro ejemplo, un cortafuegos de aplicación web podría analizar los encabezados HTTP y el código de formato de la página web presente en los paquetes HTTP para identificar las cadenas que coinciden con un patrón en su base de datos de amenazas. 

Los cortafuegos sensibles a las aplicaciones tienen muchos nombres diferentes, incluida la puerta de enlace de la capa de aplicación, la inspección multicapa con estado y la inspección profunda de paquetes. Los dispositivos compatibles con la aplicación deben configurarse con filtros separados para cada tipo de tráfico (HTTP y HTTPS, SMTP/POP/IMAP, FTP, etc.).