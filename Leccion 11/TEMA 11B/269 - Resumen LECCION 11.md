
Deberá poder configurar protocolos seguros para el acceso y la administración de la red local, los servicios de aplicaciones, y el acceso y la administración remotos.

DIRECTRICES PARA MEJORAR LAS CAPACIDADES DE SEGURIDAD DE LAS APLICACIONES
Siga estas directrices al implementar protocolos de red:

- Evalúe los requisitos para asegurar los protocolos de aplicación, como la necesidad de certificados o claves para la autenticación y el uso del puerto TCP/UDP: 
	- Implemente certificados en servidores web para usarlos con HTTPS.
	- Implemente certificados en los servidores de correo electrónico para utilizarlos con SMTP, POP3 e IMAP seguros.
	- Implemente certificados o claves de host en servidores de archivos para usarlos con FTPS o SFTP.
	- Implemente certificados en clientes de correo electrónico para usarlos con S/MIME.


Siga estas directrices para mejorar los proyectos de desarrollo de aplicaciones:

- Capacite a los desarrolladores sobre técnicas de codificación segura para proporcionar una mitigación específica contra los ataques:
	- Comprenda las diferentes categorías de ataques a aplicaciones web que explotan el código vulnerable.
	- Identifique los ataques de inyección (XSS, SQL, XML, LDAP) que explotan la falta de validación de entradas.
	- Reproduzca y solicite ataques de falsificación que exploten la falta de mecanismos seguros de gestión de sesiones.
- Revise y pruebe el código a través de análisis estáticos y dinámicos, prestando especial atención a la validación de entradas, la codificación de salidas, la gestión de errores y la exposición de datos.