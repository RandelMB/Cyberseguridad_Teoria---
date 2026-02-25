l igual que otros protocolos de aplicación TCP/IP anteriores, las comunicaciones HTTP no son seguras. Netscape desarrolló la capa de sockets seguro (SSL) en la década de 1990 para abordar la falta de seguridad en HTTP. La SSL demostró ser muy popular en la industria y se adoptó rápidamente como un estándar llamado Transport Layer Security (TLS) (seguridad de la capa de transporte). Por lo general, se usa con la aplicación HTTP (conocida como HTTPS o HTTP seguro), pero también se puede utilizar para proteger otros protocolos de aplicación y como una solución de red privada virtual (VPN).

Para implementar TLS, a un servidor se le asigna un certificado digital firmado por alguna autoridad certificadora (CA) de confianza. El certificado comprueba la identidad del servidor (asumiendo que el cliente confía en la CA) y valida el par de claves pública y privada del servidor. El servidor utiliza su par de claves y el protocolo TLS para acordar con el cliente cifrados mutuamente compatibles y negociar una sesión de comunicaciones cifradas.

HTTPS opera a través de un puerto 443 de manera predeterminada. El funcionamiento de HTTPS se indica mediante el uso de https:// en la URL y por medio del ícono de candado que se muestra en el navegador.

También es posible instalar un certificado en el cliente para que el servidor pueda confiar. Este no se utiliza con frecuencia en la web, pero es una función de las VPN y las redes empresariales que requieren autenticación mutua.

Versiones de SSL/TLS 
Mientras que el acrónimo SSL todavía se usa, las versiones de seguridad de la capa de transporte son las únicas seguras. Un servidor podría ofrecer soporte para los clientes heredados, pero obviamente sería menos seguro. Por ejemplo, un servidor TLS 1.2 podría configurarse para permitir que los clientes cambiaran a una versión inferior, a TLS 1.1 o 1.0, o incluso a SSL 3.0 si no son compatibles con TLS 1.2.

Un ataque de degradación es cuando un ataque en ruta intenta forzar el uso de una suite de cifrado débil y una versión de SSL/TLS.

La versión 1.3 de TLS se aprobó en 2018. Una de las principales características de TLS 1.3 es la eliminación de la capacidad de realizar ataques de degradación al evitar el uso de funciones y algoritmos no seguros de versiones anteriores. También hay cambios en el protocolo de enlace para reducir la cantidad de mensajes y acelerar las conexiones. 

Suites de cifrado
Una cipher suite (suite de cifrado) son los algoritmos admitidos tanto por el cliente como por el servidor para realizar las diferentes operaciones de cifrado y hashing requeridas por el protocolo. Antes de TLS 1.3, una cipher suite (suite de cifrado) se escribía de la siguiente forma:

ECDHE-RSA-AES128-GCM-SHA256

Significa que el servidor puede usar el modo efímero de Diffie-Hellman de curva elíptica para el acuerdo de claves de sesión, firmas RSA, AES-GCM de 128 bits (modo de contador de Galois) para el cifrado masivo simétrico y SHA de 256 bits para las funciones HMAC. Las suites que prefiere el servidor se enumeran anteriormente en su lista de cifrado compatible.

TLS 1.3 utiliza suites simplificadas y acortadas. Una suite de cifrado TLS 1.3 típica aparece de la siguiente manera:

TLS_AES_256_GCM_SHA384

Solamente se admite el acuerdo de clave efímera en 1.3 y el tipo de firma se proporciona en el certificado, por lo que la suite de cifrado solo enumera la intensidad de la clave de cifrado masivo y el modo de funcionamiento (AES_256_GCM), más el algoritmo de hash criptográfico (SHA384) que se utiliza dentro de la nueva función de derivación de clave de hash (HKDF). La HKDF es el mecanismo por el cual el secreto compartido establecido por el acuerdo de claves D-H se utiliza para derivar claves de sesión simétricas.

![[Pasted image 20250402204801.png]]


Visualización del protocolo de enlace de TLS en una captura de paquetes de Wireshark. Tenga en cuenta que en la conexión se está utilizando TLS 1.3 y una de las suites de cifrado acortadas (TLS_AES_128_GCM_SHA256).