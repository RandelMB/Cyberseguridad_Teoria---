El actor de amenaza podría establecer un punto de apoyo en la red comprometiendo una sola estación de trabajo a través de malware o un ataque de contraseña. Una vez que se logró un punto de apoyo inicial, es probable que el objetivo del actor de amenaza sea identificar los activos de datos. Para ello, debe encontrar formas de realizar un movimiento lateral para vulnerar otros hosts de la red y una escalada de privilegios para obtener más permisos sobre los activos de la red. Para lograr estos objetivos, además de descifrar más contraseñas o encontrar más vulnerabilidades, puede usar ataques de reproducción de credenciales. 

En términos de ataques de red, los ataques de reproducción de credenciales se dirigen principalmente a las redes de Windows Active Directory. También hay ataques de reproducción de credenciales que se dirigen a aplicaciones web. Los analizaremos en el siguiente tema.

Si una cuenta de usuario de un host de Windows se autenticó en una red de dominio de Active Directory, el Servicio de subsistema de autoridad de seguridad local (LSASS) almacena en caché varios secretos en la memoria y en la base de datos del registro del Administrador de cuentas de seguridad (SAM) para facilitar el inicio de sesión único. Estos secretos son los siguientes:

el Ticket Granting Ticket (TGT) de Kerberos y la clave de sesión. Esto permite al host solicitar tickets de servicio para acceder a las aplicaciones.
Tickets de servicio para aplicaciones donde el usuario inició una sesión.
Hash NT de cuentas de usuario y servicio locales y de dominio que actualmente están conectadas, ya sea de forma interactiva o remota a través de la red. Las primeras redes empresariales de Windows utilizaban la autenticación de desafío y respuesta NT LAN Manager (NTLM). Si bien el protocolo NTLM está obsoleto para la mayoría de los usos, el hash NT todavía se utiliza como formato de almacenamiento de credenciales. El hash NT se utiliza donde todavía se permite la autenticación NTLM heredada y puede participar en la firma de solicitudes y respuestas de Kerberos. 
Fundamental para la seguridad de la red, si diferentes usuarios inician sesión en el mismo host, LSASS podría almacenar en caché los secretos de todas estas cuentas. Si algunas de estas cuentas son para usuarios con más privilegios, como los administradores de dominio, un actor de amenaza podría usar los secretos para aumentar sus privilegios.

LSASS purga los hashes de la memoria a los pocos minutos de que el usuario cierra sesión. La base de datos SAM almacena en caché las credenciales locales y de la cuenta de Microsoft, pero no las credenciales del dominio. Algunas ediciones de Windows implementan una función de virtualización llamada Credential Guard para proteger estos secretos de procesos maliciosos, incluso si tienen permisos del SISTEMA.

Los ataques de reproducción de credenciales utilizan varios mecanismos para obtener y explotar estos secretos almacenados de forma local para iniciar sesiones autenticadas en otros hosts y aplicaciones de la red. Por ejemplo, si un actor de amenaza puede obtener un hash NT, puede usar un ataque de tipo pass the hash (pasar el hash [PtH]) para iniciar una sesión en otro host si ese host está ejecutando un servicio como el intercambio de archivos o el escritorio remoto que aún permite la autenticación NTLM. 

![[Pasted image 20250404074304.png]]

Description
El proceso consta de los cuatro pasos siguientes:



1. La víctima se conecta. El DC verifica al usuario con Kerberos.



2. La víctima vuelve a conectarse. Las credenciales Kerberos se almacenan en caché en SAM. 



3. El atacante vuelca SAM en el ordenador de la víctima. Se revelan las credenciales codificadas. 



4. El atacante utiliza el hash en otro ordenador. Kerberos reconoce las credenciales con hash.

El proceso de pasar el hash. El Security Accounts Manager (SAM) es una base de datos del registro de Windows que almacena las credenciales de la cuenta local. (Imágenes © 123RF.com.)

La autenticación NTLM heredada a menudo se deshabilita, ya que es un riesgo de seguridad muy alto. Otros tipos de reproducción de credenciales están dirigidos contra la autenticación y autorización de Kerberos. Por ejemplo, un ataque de ticket dorado (Golden Ticket) intenta falsificar un ticket de concesión de tickets. Si tiene éxito, esto le da al actor de amenaza un acceso sin restricciones a todos los recursos del dominio. Un ataque de ticket plateado (Silver Ticket) intenta falsificar tickets de servicio. Estos pueden describirse como ataques de pasar el ticket [PtT].

Microsoft lanzó una serie de mitigaciones contra estos ataques específicos de reproducción de credenciales. Asegurarse de que los hosts cuenten con todas sus actualizaciones de seguridad y utilicen líneas de base de configuración seguras reduce en gran medida su efectividad. Cuando siguen siendo un riesgo, se puede configurar un sistema de detección para correlacionar una secuencia de eventos de registro de seguridad, pero este método puede ser propenso a falsos positivos. La detección de intrusiones mediante antivirus y basadas en host a menudo puede detectar el código de malware utilizado para volcar credenciales o lanzar ataques de falsificación de tickets.