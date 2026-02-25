
Una de las características más importantes de un sistema operativo es el proveedor de autenticación, que es la arquitectura de software y el código que sustenta el mecanismo por el cual el usuario se autentifica antes de iniciar un shell. 

La autenticación basada en el conocimiento se basa en hashes criptográficos. Una contraseña de texto plano no suele ser transmitida o almacenada en una base de datos de credenciales debido al riesgo de compromiso. En cambio, la contraseña se almacena como un hash criptográfico. Cuando un usuario introduce una contraseña para conectarse, un autenticador convierte lo que se ha escrito en un hash y lo transmite a una autoridad. La autoridad compara el hash enviado con el de la base de datos y autentica al sujeto solo si coinciden.

Autenticación de Windows
La autenticación de Windows implica una compleja arquitectura de componentes (docs.microsoft.com/en-us/windows-server/security/windows-authentication/credentials-processes-in-windows-authentication), pero los siguientes tres escenarios son típicos:

Inicio de sesión local de Windows: es el Local Security Authority Subsystem Service (LSASS) (Servicio del Subsistema de la Autoridad de Seguridad Local [LSASS]) que compara la credencial enviada con un hash almacenado en la base de datos del Security Accounts Manager (SAM) (Administrador de cuentas de seguridad [SAM]), que forma parte del registro. Esto también se conoce como inicio de sesión interactivo.
Inicio de sesión en la red de Windows: es el LSASS que puede pasar las credenciales de autenticación a un controlador de dominio de Active Directory (AD). El sistema preferido para la autenticación de red se basa en Kerberos, pero las aplicaciones de red heredadas podrían utilizar la autenticación NT LAN Manager (NTLM).
Inicio de sesión remoto:  se utiliza si el dispositivo del usuario no está conectado directamente a la red local, la autenticación puede realizarse a través de una red privada virtual (VPN), wifi empresarial o portal web. Estos utilizan protocolos para crear una conexión segura entre el equipo cliente, el dispositivo de acceso remoto y el servidor de autenticación.
Autenticación de Linux
En Linux, los nombres de las cuentas locales de los usuarios se almacenan en /etc/passwd. Cuando un usuario se conecta a un shell interactivo local, la contraseña se coteja con un hash almacenado en /etc/shadow. El inicio de sesión interactivo a través de una red se realiza normalmente utilizando Secure Shell (SSH) (Shell Seguro [SAM]). Con SSH, el usuario puede autenticarse utilizando claves criptográficas en lugar de una contraseña.

Una política de pluggable authentication module (PAM) [módulo de autenticación conectable (PAM)] es un paquete que permite habilitar diferentes proveedores de autenticación, como el inicio de sesión con tarjeta inteligente. El marco PAM también puede utilizarse para implementar la autenticación en los servicios de directorio de red.

