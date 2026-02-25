
Existen muchas formas de transferir archivos a través de las redes. Un sistema operativo de red puede alojar carpetas y archivos compartidos, lo que permite copiarlos o acceder a ellos a través de la red local o mediante acceso remoto (por ejemplo, a través de una VPN). Las aplicaciones de correo electrónico y mensajería pueden enviar archivos como adjuntos. El HTTP admite la descarga de archivos (y las cargas a través de varios mecanismos de secuencia de comandos). También existen servicios de intercambio de archivos de punto a punto. 

A pesar de la disponibilidad de estos protocolos y servicios más nuevos, el protocolo de transferencia de archivos (FTP) sigue siendo muy popular porque es eficiente y tiene una amplia compatibilidad multiplataforma.

Protocolo de transferencia de archivos 
Un servidor de File Transfer Protocol (FTP) (protocolo de transferencia de archivos) suele estar configurado con varios directorios públicos, que alojan archivos y cuentas de usuario. La mayoría de los servidores HTTP también funcionan como servidores FTP, y los servicios, cuentas y directorios FTP se pueden instalar y habilitar de forma predeterminada al instalar un servidor web. El FTP es más eficiente que los archivos adjuntos o la transferencia de archivos HTTP, pero no tiene mecanismos de seguridad. Toda la autenticación y la transferencia de datos se comunican como texto plano, lo que significa que las credenciales se pueden extraer fácilmente del tráfico FTP interceptado.

Debe comprobar que los usuarios no instalen servidores no autorizados en sus PC (un servidor fraudulento). Por ejemplo, una versión de IIS que incluye servidores HTTP, FTP y SMTP se incluye con las versiones de cliente de Windows, aunque no se instala de forma predeterminada.

SSH FTP (SFTP) y FTP sobre SSL (FTPS)
El Secure File Transfer Protocol (SFTP) (protocolo de transferencia segura de archivos) aborda los problemas de privacidad e integridad del FTP al cifrar la autenticación y la transferencia de datos entre el cliente y el servidor. En el SFTP, se crea un enlace seguro entre el cliente y el servidor mediante el Secure Shell (SSH) (Shell seguro) sobre el puerto TCP 22. Así, los comandos FTP comunes y la transferencia de datos pueden enviarse a través del enlace seguro sin riesgo de ataques de espionaje o en ruta. Esta solución requiere un servidor SSH que admita el SFTP más un software cliente de SFTP.

Otra forma de asegurar el FTP es utilizar el protocolo de seguridad de conexión SSL/TLS. Hay dos formas de hacerlo:

TLS explícito (FTPES): utiliza el comando AUTH TLS para actualizar una conexión no segura establecida a través del puerto 21 a una segura. Esto protege las credenciales de autenticación. La conexión de datos para las transferencias de archivos también se puede encriptar (mediante el comando PROT).
Implicit TLS (FTPS) (TLS implícito): negocia un túnel SSL/TLS antes del intercambio de cualquier comando de FTP. Este modo utiliza el puerto seguro 990 para la conexión de control.
El FTPS es difícil de configurar cuando hay cortafuegos entre el cliente y el servidor. Por lo tanto, el FTPES suele ser el método preferido.