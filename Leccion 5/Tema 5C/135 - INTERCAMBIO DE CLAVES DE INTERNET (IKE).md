

A cada host o enrutador que utiliza IPsec se le debe asignar una política. Una política IPsec establece el mecanismo de autenticación y también el uso de AH/ESP y el modo de transporte o túnel para una conexión entre dos pares. 

Las funciones de cifrado y hash de IPsec dependen de un secreto compartido. El secreto debe comunicarse a ambos pares, y estos deben realizar una autenticación mutua para confirmar la identidad del otro. El protocolo de intercambio de claves de internet (IKE) implementa un método de autenticación, selecciona qué cifrados criptográficos son compatibles entre sí por ambos pares y realiza el intercambio de claves. El conjunto de propiedades se denomina asociación de seguridad (SA).

![[Pasted image 20241202174023.png]]


	Configuración de IKE para la autenticación basada en certificados en el dispositivo de seguridad OPNsense. (Captura de pantalla cortesía de OPNsense).

Las negociaciones de IKE se llevan a cabo en dos fases:

1. La fase I establece la identidad de ambos pares y realiza el acuerdo clave mediante el algoritmo Diffie-Hellman para crear un canal seguro. Comúnmente se utilizan dos métodos de autenticación de pares:
	- Certificados digitales: los emite una autoridad certificadora de confianza muta a cada par para identificarse entre sí.
	- Clave previamente compartida (autenticación de grupo): es cuando se configura la misma frase de contraseña en ambos pares.
2. La fase II utiliza el canal seguro creado en la fase I para establecer qué cifrados y tamaños de clave se utilizarán con AH o ESP en la sesión IPsec. 

Existen dos versiones de IKE. La versión 1 fue diseñada para topologías de sitio a sitio y de host a host, y requiere un protocolo de soporte para implementar VPN de acceso remoto. IKEv2 tiene algunas características adicionales que han hecho que el protocolo sea popular para su uso como una solución VPN independiente de acceso remoto de cliente a sitio. Los principales cambios son los siguientes:

- Admite métodos de autenticación EAP, lo que permite, por ejemplo, la autenticación de usuarios contra un servidor RADIUS.
- Proporciona un modo de configuración simple que reduce el ancho de banda sin comprometer la seguridad.
- Permite el recorrido de traducción de dirección de red [NAT] y la multiconexión MOBIKE. El recorrido NAT facilita la configuración de un túnel permitido por un enrutador o cortafuego doméstico. La multiconexión significa que un cliente de teléfono inteligente con interfaces Wi-Fi y celular puede mantener la conexión IPsec activa al cambiar entre ellas.
