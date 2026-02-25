

Una VPN de seguridad de la capa de transporte (TLS) significa que el cliente se conecta al servidor de acceso remoto mediante certificados digitales. El certificado del servidor identifica la puerta de enlace de la VPN ante el cliente. Opcionalmente, el cliente también se puede configurar con su propio certificado. Esto permite la autenticación mutua, donde tanto el servidor como el cliente prueban su identidad entre sí. TLS crea un túnel cifrado para que el usuario envíe las credenciales de autenticación. Estos normalmente serían procesados por un servidor RADIUS. Una vez que el usuario está autenticado y la conexión está completamente establecida, la puerta de enlace VPN tuneliza todas las comunicaciones de la red local a través del socket seguro.


![[Pasted image 20241202173640.png]]


Configuración de un servidor OpenVPN en el dispositivo de seguridad OPNsense. Esta configuración crea una VPN de acceso remoto. Los usuarios se autentican a través de un servidor RADIUS en la red local. (Captura de pantalla cortesía de OPNsense).

![[Pasted image 20241202173653.png]]


Configuración de un certificado de servidor para OpenVPN en el dispositivo de seguridad OPNsense. (Captura de pantalla cortesía de OPNsense).

	Una VPN TLS puede utilizar TCP o UDP. Se podría elegir UDP para obtener un rendimiento ligeramente superior, en especial cuando se tuneliza el tráfico sensible a la latencia, como voz o video. TCP podría ser más fácil de usar con una política de cortafuego predeterminada. TLS sobre UDP también se denomina Datagram Transport Layer Security (DTLS).
	
	Es importante utilizar una versión segura de TLS. La última versión al momento de esta publicación es TLS 1.3. TLS 1.2 también es compatible. Las versiones anteriores están en desuso.