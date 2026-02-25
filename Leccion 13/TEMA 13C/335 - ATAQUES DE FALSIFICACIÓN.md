A diferencia de los ataques de reproducción, un ataque de falsificación secuestra una sesión autenticada para realizar alguna acción sin el consentimiento del usuario.

Falsificación de solicitudes entre sitios
Una cross-site request forgery (XSRF) (falsificación de solicitudes entre sitios [XSRF]) puede explotar aplicaciones que utilizan cookies para la autenticación de usuarios y el seguimiento de sesiones. Para que funcione, el agente de amenazas debe convencer a la víctima de que inicie sesión en el sitio objetivo. Luego el atacante debe pasar una solicitud HTTP al navegador de la víctima que suplante una acción en el sitio objetivo (como cambiar una contraseña o una dirección de correo electrónico). Esta solicitud podría camuflarse de manera que lograra el ataque sin que la víctima tuviera que hacer clic necesariamente en un enlace. Si el sitio de destino supone que el navegador está autenticado porque hay una cookie de sesión válida y no completa ningún proceso de autorización adicional en la entrada del atacante, aceptará la solicitud como si fuera genuina. También se denomina “ataque del guardia confundido” (confused deputy attack). 

![[Pasted image 20250404083136.png]]

Description
Los pasos son los siguientes:



Alice se conecta a un sitio web de confianza.



Mallory envía a Alice un enlace malicioso.



Alice confía en el enlace y hace clic en él mientras sigue conectada al sitio de confianza.



El enlace realiza una petición maliciosa en el sitio web



Ejemplo de falsificación de solicitudes entre sitios. (Imágenes © 123RF.com.)

Server-Side Request Forgery (falsificación de solicitudes del lado del servidor)
Una falsificación de solicitudes del lado del servidor (SSRF) hace que una aplicación de servidor procese una solicitud arbitraria que se dirige a otro servicio. El servicio de destino podría ser otra aplicación que se ejecuta en el mismo host o un servicio que se ejecuta en un host remoto. La SSRF explota tanto la falta de autenticación entre los servidores internos como entre los servicios. También se basa en una validación de entrada débil, que permite al atacante enviar solicitudes arbitrarias.

Los ataques SSRF a menudo se dirigen a la infraestructura de la nube, donde el servidor web es solo el componente público de una cadena de procesamiento más profunda. Una aplicación web típica comprende múltiples capas de servidores, con una interfaz de cliente, capas lógicas de middleware y una capa de base de datos. Es probable que las solicitudes iniciadas desde la interfaz del cliente (un formulario web) requieran múltiples solicitudes y respuestas entre el middleware y los servidores back-end. Se implementarán como solicitudes y respuestas de encabezado HTTP entre cada servidor. La SSRF es un medio para acceder a estos servidores internos que hace que el servidor público ejecute solicitudes en ellos. Mientras que con la CSRF el exploit solo tiene los privilegios del cliente, con la SSRF la solicitud manipulada se realiza con el nivel de privilegios del servidor.

![[Pasted image 20250404083127.png]]

Description
Los pasos son los siguientes



1. Mallory no puede acceder directamente al servidor de base de datos.



2. Mallory crea una petición maliciosa y la envía al servidor front-end.



3. El servidor web realiza la petición maliciosa.



4. El servidor de la base de datos acepta la solicitud porque parece proceder del servidor web.



5. Mallory también puede obtener información del servidor interno.

Ejemplo de Server-Side Request Forgery (falsificación de solicitudes del lado del servidor) (Imágenes © 123RF.com.)