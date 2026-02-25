

El protocolo de Shell seguro (SSH) es el principal medio para obtener acceso remoto seguro a un terminal de línea de comandos. Los usos principales de SSH son la administración remota y la transferencia segura de archivos (SFTP). Existen numerosos productos SSH comerciales y de código abierto disponibles para las principales plataformas NOS.  El más utilizado es OpenSSH (openssh.com).

Los servidores SSH se identifican mediante un par de claves públicas o privadas denominadas claves del host. Cada cliente de SSH puede asignar manualmente nombres de host a claves de host, o a través de diversos productos de software empresarial diseñados para la gestión de claves de host de SSH.

![[Pasted image 20241202174210.png]]

Description
	El mensaje de advertencia dice, ¿continuar conectándose a un servidor desconocido y añadir su clave de host a una caché? El texto debajo dice, la clave de host del servidor no se encontró en la caché. No tienes garantía de que el servidor sea el ordenador que crees que es. La huella digital de la clave rsa2 del servidor es: ssh-guion-rsa 2048 cd:dos puntos:88:dos puntos:9a:dos puntos:11:dos puntos:8b:dos puntos:a9:dos puntos:5e:dos puntos:7c:dos puntos:52:dos puntos:55:dos puntos:32:dos puntos:d4:dos puntos:24:dos puntos:82:dos puntos:99:dos puntos:d8. Si confías en este host, presiona Sí. Para conectar sin añadir la clave de host a la caché, presiona No. Para abandonar la conexión presiona Cancelar. Cinco botones, Sí (seleccionado), No, Cancelar, Copiar Clave y Ayuda están en la parte inferior.



Confirmación de la clave del host del servidor SSH mediante el cliente PuTTY SSH (captura de pantalla utilizada con el permiso de PuTTY).

		La clave del host debe ser cambiada si se sospecha que el host está comprometido. Si un atacante obtuvo la clave privada de un servidor o dispositivo, puede hacerse pasar por ese servidor o dispositivo y realizar un ataque de suplantación de identidad, por lo general con el objetivo de obtener otras credenciales de red. 

La clave de host del servidor se utiliza para configurar un canal seguro que se utiliza para que el cliente envíe las credenciales de autenticación.

**Autenticación del cliente SSH**
SSH permite varios métodos para que el cliente se autentique en el servidor. Cada uno de estos métodos pueden habilitados o deshabilitados según sea necesario en el servidor, mediante el archivo /etc/ssh/sshd_config:\n

- Nombre de usuario/contraseña: el cliente envía las credenciales que el servidor SSH verifica con una base de datos de usuarios locales o a través de un servidor RADIUS. 
- Autenticación de clave pública: la clave pública de cada usuario remoto se agrega a una lista de claves autorizadas para cada cuenta local en el servidor SSH. 
- Kerberos: el cliente envía al servidor las credenciales Kerberos (un ticket de concesión de tickets) obtenidas cuando el usuario se conecta a la estación de trabajo mediante la interfaz de programación de aplicaciones de servicios de seguridad genéricos (GSSAPI).    El servidor SSH se comunica con el servicio de concesión de tickets (en un entorno de Windows, sería un controlador de dominio) para validar las credenciales.


		La gestión de claves públicas válidas de clientes es una tarea de seguridad crítica. Muchos ataques recientes en los servidores web han aprovechado una administración deficiente de las claves. Si la clave privada de un usuario se ve comprometida, elimine la clave pública del dispositivo y vuelva a generar el par de claves en el dispositivo cliente del usuario (remediado) y copie la clave pública en el servidor SSH. Elimine siempre las claves públicas cuando se hayan revocado los permisos de acceso del usuario.

**Comandos SSH**

Los comandos SSH se utilizan para conectarse a hosts y configurar métodos de autenticación. Para conectarse a un servidor SSH en 10.1.0.10 a través de una cuenta llamada “bobby” y autenticación de contraseña, ejecute:

	ssh bobby@10.1.0.10

Los siguientes comandos crean un nuevo par de claves y lo copian a una cuenta en el servidor remoto:

	ssh-keygen -t rsa

	ssh-copy-id bobby@10.1.0.10

En un indicador SSH, ahora puede utilizar los comandos de shell estándar de Linux. Utilice `exit` para cerrar la conexión.

Puede utilizar el comando `scp` para copiar un archivo desde servidor remoto al host local:

	scp bobby@10.1.0.10:/logs/audit.log audit.log

Invierta los argumentos para copiar un archivo desde el host local al servidor remoto. Para copiar el contenido de un directorio y cualquier subdirectorio (de forma recursiva), utilice la opción `-r`.