En los servicios de correo electrónico se utilizan dos tipos de protocolos:

El Simple Mail Transfer Protocol (SMTP) (protocolo de transferencia de correo simple) especifica cómo se envía el correo de un sistema a otro.
Un protocolo de buzón de correo almacena los mensajes para los usuarios y les permite descargarlos en los equipos cliente o administrarlos en el servidor.
SMTP seguro (SMTPS)
Para entregar un mensaje, el servidor SMTP del remitente descubre la dirección IP del servidor SMTP del destinatario por medio de la parte del nombre de dominio de la dirección de correo electrónico. El servidor SMTP del dominio se registra en el DNS mediante un registro de intercambiador de correo (MX).

Las comunicaciones del SMTP pueden asegurarse a través de la TLS. Funciona de forma similar al HTTPS, con un certificado en el servidor SMTP. Existen dos maneras de que el SMTP utilice la TLS: 

- STARTTLS: es un comando que actualiza una conexión no segura existente para usar TLS. También se denomina TLS explícito o TLS oportunista.
- SMTPS: establece la conexión segura antes de que se intercambien los comandos SMTP (por ejemplo, HELO). También se conoce como TLS implícito. 

El método STARTTLS está generalmente más implementado que el SMTPS. Las configuraciones típicas del SMTP usan los siguientes puertos y servicios seguros: 

- Puerto 25: se usa para la retransmisión de mensajes (entre servidores de SMTP o agentes de  transferencia de  mensajes (MTA). Si la seguridad es necesaria y está soportada por ambos servidores, se puede utilizar el comando STARTTLS para establecer la conexión segura. 
- Puerto 587: lo usan los clientes de correo (agentes de envío de mensajes [MSA]) para enviar mensajes mediante un servidor SMTP. Los servidores configurados para soportar el puerto 587 deben utilizar STARTTLS y requerir autenticación antes del envío de mensajes. 
- Puerto 465: lo usan algunos proveedores y clientes de correo para el envío de mensajes a través de TLS implícito (SMTPS), aunque este uso ahora está obsoleto por la documentación de los estándares. 

POP seguro (POP3S)
El Post Office Protocol v3 (POP3) (protocolo de oficina de correo v3) es un protocolo de buzón de correo diseñado para almacenar los mensajes entregados por SMTP en un servidor. Cuando el cliente se conecta al buzón, POP3 descarga los mensajes al cliente de correo electrónico del destinatario.


![[Pasted image 20250403073853.png]]

Configuración de los protocolos de acceso al buzón en un servidor.

Una aplicación de cliente POP3, como Microsoft Outlook o Mozilla Thunderbird, establece una conexión TCP con el servidor POP3 a través del puerto 110. El usuario se autentica (mediante nombre de usuario y contraseña) y el contenido de su buzón de correo se descarga para su procesamiento en la PC local. El POP3S es la versión segura del protocolo que opera a través del puerto TCP 995 de forma predeterminada.

IMAP seguro (IMAPS)
En comparación con el POP3, el Internet Message Access Protocol (IMAP) (protocolo de acceso a mensajes de Internet) admite conexiones permanentes a un servidor y conecta varios clientes al mismo buzón de correo de forma simultánea. También permite que un cliente administre las carpetas de correo en el servidor. Los clientes se conectan a IMAP a través del puerto TCP 143. Se autentican a sí mismos y luego recuperan los mensajes de las carpetas designadas. Al igual que otros protocolos de correo electrónico, la conexión se puede asegurar al establecer un túnel SSL/TLS. El puerto predeterminado para el IMAPS es el puerto TCP 993.