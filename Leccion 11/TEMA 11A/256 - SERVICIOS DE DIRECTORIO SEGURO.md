Un directorio de red enumera los sujetos (principalmente usuarios, equipos y servicios) y objetos (como directorios y archivos) disponibles en la red además de los permisos que los sujetos tienen sobre los objetos. Un directorio facilita la autenticación y autorización, y es fundamental que se mantenga como un servicio altamente seguro. La mayoría de los servicios de directorio se basan en el protocolo ligero de acceso a directorios (LDAP), que se ejecuta en el puerto 389. El protocolo básico no ofrece seguridad y todas las transmisiones son en texto plano, lo que lo hace vulnerable a los ataques de sniffing (examen) y en ruta. La autenticación (denominada vinculación al servidor) puede implementarse de las siguientes maneras:

- Sin autenticación: se concede acceso anónimo al directorio.
- Enlace simple: el cliente debe proporcionar su nombre distinguido (DN) y su contraseña, pero éstos se pasan como texto plano.
- Capa de autenticación y seguridad simple (SASL): el cliente y el servidor negocian el uso de un mecanismo de autenticación compatible, como Kerberos. El comando STARTTLS se puede utilizar para el cifrado (sellado) y la integridad del mensaje (firma). Este es el mecanismo preferido para la implementación del LDAP en el directorio activo (AD) de Microsoft.
- LDAP Secure (LDAPS) (LDAP seguro): el servidor se instala con un certificado digital, que utiliza para establecer un túnel seguro para el intercambio de credenciales de usuario. LDAPS utiliza el puerto 636.


Si se requiere un acceso seguro, los métodos de acceso anónimo y de autenticación simple se deben desactivar en el servidor.

Por lo general, habrá que conceder dos niveles de acceso al directorio (directorio): acceso de solo lectura (consulta) y acceso de lectura/escritura (actualización). Esto se implementa utilizando una política de control de acceso, pero el mecanismo preciso es específico del proveedor y no se especifica en la documentación de los estándares de LDAP.

A menos que albergue un servicio público, el servidor de directorio LDAP debería ser accesible únicamente desde la red privada. Significa que el puerto LDAP debe ser bloqueado por un cortafuegos para que no se pueda acceder a él a través de la interfaz pública. Si hay integración con otros servicios a través de Internet, lo ideal es que solo se permitan las IP autorizadas.