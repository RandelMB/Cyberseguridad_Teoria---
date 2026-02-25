Una política de single sign-on (SSO) [inicio de sesión único (SSO)] permite al usuario autenticarse una vez y luego recibir autorizaciones en servidores de aplicaciones compatibles sin tener que volver a introducir las credenciales. 

Kerberos es un protocolo de autenticación y autorización de red de inicio de sesión único que se utiliza en muchas redes, especialmente implementado por el servicio Active Directory (AD) de Microsoft. Kerberos recibió el nombre del perro guardián de tres cabezas de Hades (Cerbero) porque consta de tres partes. Los clientes solicitan servicios a los servidores de aplicaciones, y ambos se apoyan en un intermediario: un key distribution center (KDC) [centro de distribución de claves (KDC)] para garantizar su identidad. Hay dos servicios que componen un KDC: el servicio de autenticación y el servicio de otorgamiento de tickets.

![[Pasted image 20241118140225.png]]


Description
El KDC (servicio de autenticación) envía el ticket de concesión (usuario, pass y marca de tiempo) a la entidad de seguridad, que crea una solicitud de inicio de sesión dirigida al KDC. El servidor de aplicaciones comprueba que la cuenta de usuario está presente.

Servicio de autenticación Kerberos. (Imágenes © 123RF.com.)

Kerberos puede autenticar usuarios humanos y servicios de aplicaciones. En conjunto, se denominan entidades. Con la autenticación a un dominio de Windows como ejemplo, el primer paso en el SSO de Kerberos es autenticarse con un servidor KDC, implementado como controlador de dominio.

La entidad envía al servicio de autenticación (AS) una solicitud de un Ticket Granting Ticket (TGT) [ticket de otorgamiento de tickets (TGT)]. Se compone al cifrar la fecha y la hora en la computadora local con el hash de la contraseña del usuario como clave. 
El hash de la contraseña en sí no se transmite a través de la red. Aunque nos referimos a las contraseñas por cuestiones de simplicidad, el sistema puede usar otros autenticadores, como el inicio de sesión con tarjeta inteligente.

2.El AS comprueba que la cuenta de usuario está presente, que puede decodificar la solicitud al hacer coincidir el hash de la contraseña del usuario con el de la base de datos de Active Directory, y que la solicitud no ha caducado. Si la solicitud es válida, el AS responde con los siguientes datos:
Ticket Granting Ticket (TGT) (ticket de otorgamiento de tickets): contiene información sobre el cliente (nombre y dirección IP), además de una marca de tiempo y un período de validez. Se cifra mediante la clave secreta de KDC.
Clave de sesión de TGS: se comunica entre el cliente y el servicio de otorgamiento de tickets (TGS). Se cifra mediante un hash de la contraseña del usuario.
El TGT es un ejemplo de un token lógico. Lo único que hace el TGT es identificar quién es usted y confirmar que fue autenticado; no le proporciona acceso a ningún recurso de dominio.
