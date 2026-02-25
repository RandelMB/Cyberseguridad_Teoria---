
La seguridad de la capa de transporte se aplica a nivel de la capa de aplicación. La seguridad del protocolo de Internet (IPsec) opera en la capa de red del modelo OSI (capa 3). Esto significa que se puede implementar sin tener que configurar el soporte específico de la aplicación y que incurre en menos sobrecarga de paquetes.

Existen dos protocolos principales en IPsec, que se pueden aplicar de forma individual o conjunta, dependiendo de la política:

- Encabezado de autenticación (AH): encabezado de autenticación (AH): realiza un hash criptográfico en todo el paquete, incluido el encabezado IP, más una clave secreta compartida (conocida solo por los hosts que se comunican) y agrega este valor en su encabezado como valor de verificación de integridad (ICV). El destinatario realiza la misma función sobre el paquete y la clave y debe obtener el mismo valor para confirmar que el paquete no ha sido modificado. La carga útil no está cifrada, por lo que este protocolo no proporciona confidencialidad.
- La carga de seguridad encapsuladora (ESP): se puede utilizar para cifrar el paquete en lugar de tan solo calcular un ICV. La ESP adjunta tres campos al paquete: un encabezado, un finalizador (que proporciona relleno para la función criptográfica) y un valor de verificación de integridad. A diferencia del AH, la ESP excluye encabezado IP al calcular el ICV.
IPSec puede utilizarse en dos modos:

- Modo de transporte: se utiliza para asegurar las comunicaciones entre hosts en una red privada. Cuando se aplica la ESP en el modo de transporte, el encabezado IP de cada paquete no se cifra, solo los datos de la carga útil. Si se utiliza el AH en el modo de transporte, puede proporcionar integridad para el encabezado IP.

![[Pasted image 20241202173836.png]]

Description
Los cuatro segmentos de izquierda a derecha son los siguientes: Cabecera IP; A H, I C V; E S P (T C P barra U D P y carga útil); y Remolque.

![[Pasted image 20241202173850.png]]


Datagrama IPsec utilizando AH y ESP en el modo de transporte.

Modo túnel: se utiliza para las comunicaciones entre sitios de VPN a través de una red no segura. Con la ESP, todo el paquete IP (encabezado y carga útil) se cifra y encapsula como un datagrama con un encabezado de IP nuevo. AH no tiene ningún caso de uso en el modo túnel, ya que por lo general se requiere confidencialidad.

Datagrama IPsec utilizando ESP en modo túnel.

![[Pasted image 20241202173903.png]]


Configuración de una VPN de sitio a sitio mediante un túnel IPsec con cifrado ESP en el dispositivo de seguridad OPNsense. (Captura de pantalla cortesía de OPNsense).
