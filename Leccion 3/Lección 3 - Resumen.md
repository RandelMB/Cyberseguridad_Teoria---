<p align="justify">Debería poder resumir los tipos de funciones criptográficas (algoritmo hash, cifrado simétrico, cifrado asimétrico) y explicar cómo se utilizan en firmas digitales, certificados digitales y productos de cifrado de disco/archivo/base de datos/transporte para proporcionar confidencialidad, integridad y autenticación. Debe estar familiarizado con las herramientas y procedimientos que se utilizan para emitir diferentes tipos de certificados y administrar las operaciones de PKI.</p>

## DIRECTRICES PARA LA IMPLEMENTACIÓN DE SOLUCIONES CRIPTOGRÁFICAS

Siga estas directrices cuando implemente soluciones criptográficas:

- Cree políticas para exigir el uso de cifrados fuertes y longitudes de clave, como las siguientes:
	- Par de claves asimétricas para firmar: RSA de 2048 bits o ECC de 256 bits
	- Par de claves asimétricas para intercambio de claves: RSA de 2048 bits o ECDHE de 256 bits
	- Clave secreta: AES-128 o AES-256
	- Hashing: SHA256 o SHA512 (con MD5 permitido para requisitos de compatibilidad documentados)
	
- Determine si va a utilizar una CA privada o certificados de terceros y tome medidas para garantizar la seguridad de cualquier CA raíz privada que utilice. 

- Determine políticas y tipos de certificados que satisfagan las necesidades de los usuarios y los flujos de trabajo empresariales, como los tipos de certificados de servidor/máquina, correo electrónico/usuario y firma de código. Asegúrese de que los campos de atributo estén configurados de manera correcta al emitir certificados, y preste especial atención a que el campo SAN enumere los dominios, subdominios o dominios comodín por los que se accede a un servidor.

- Cree políticas y procedimientos para que los usuarios y servidores envíen CSR, además de los procesos de identificación, autenticación y autorización a fin de garantizar que los certificados solo se emitan a sujetos válidos.

- Establezca procedimientos para administrar claves y certificados, como la revocación y la copia de seguridad/custodia de claves, idealmente a través de criptoprocesadores de hardware dedicados, como TPM y HSM.