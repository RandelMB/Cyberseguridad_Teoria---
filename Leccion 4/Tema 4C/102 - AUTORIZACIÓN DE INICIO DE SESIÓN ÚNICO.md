

Suponiendo que el usuario ingresó la contraseña correcta, el cliente puede descifrar la clave de sesión del servicio de otorgamiento de ticket (TGS), pero no el TGT. Esto establece que el cliente y KDC conocen el mismo secreto compartido y que el cliente no puede interferir con el TGT.

Para acceder a los recursos del dominio, la entidad solicita un ticket de servicio (un token que concede el acceso a un servidor de aplicaciones de destino). Este proceso de otorgamiento de tickets de servicio lo maneja el TGS.
La entidad envía al TGS una copia de su TGT y el nombre del servidor de aplicaciones al que desea acceder, además de un autenticador, que consiste en un ID de cliente con marca de tiempo cifrado mediante la clave de sesión del TGS.
El TGS debe poder descifrar ambos mensajes mediante la clave secreta de KDC para el primero y la clave de sesión de TGS para el segundo. Esto confirma que la solicitud es genuina. También comprueba que el ticket no caducó y no se utilizó antes (ataque de repetición).

3.El servicio de TGS responde con lo siguiente:
Una clave de sesión de servicio: se utiliza  entre el cliente y el servidor de aplicaciones. Se cifra con la clave de sesión de TGS.
Un ticket de servicio:  contiene información sobre la entidad, como una marca de tiempo, la dirección IP del sistema, el identificador de seguridad (SID) y los SID de los grupos a los que pertenece, y la clave de sesión del servicio. Se cifra mediante la clave secreta del servidor de aplicaciones.
4.La entidad envía el ticket de servicio, que no puede descifrar, al servidor de aplicaciones y agrega otro autenticador con marca de tiempo, que se cifra mediante la clave de sesión del servicio. 

![[Pasted image 20241118140308.png]]

Description
Los pasos son los siguientes 1. El mandante envía una solicitud de servicio (vale de obtención de vale con usuario, contraseña y fecha y hora) al centro de distribución de claves (servicio de obtención de vales). El KDC envía el ticket de servicio (usuario, contraseña y marca de tiempo) al mandante. 2. La entidad de seguridad presenta el vale de servicio (usuario, contraseña y fecha y hora) al servidor de aplicaciones. 3. 3. El servidor de aplicaciones envía la autenticación mutua (opcional) a la entidad de seguridad. 4. Se produce la transferencia de datos entre el mandante y el servidor de aplicaciones.

Servicio de otorgamiento de tickets de Kerberos. (Imágenes © 123RF.com.)

5.El servidor de aplicaciones descifra el ticket de servicio para obtener la clave de sesión del servicio mediante su clave secreta, lo que confirma que la entidad envió un mensaje sin adulterar. A continuación, descifra el autenticador mediante la clave de sesión del servicio.
6.Opcionalmente, el servidor de aplicaciones responde a la entidad con la marca de tiempo utilizada en el autenticador, que se cifra mediante la clave de sesión del servicio. La entidad descifra la marca de tiempo y verifica que coincida con el valor que ya se envió, y concluye que el servidor de aplicaciones es confiable.
Significa que el servidor está autenticado ante la entidad (lo que se conoce como autenticación mutua). De este modo se evita un ataque en ruta, donde un usuario malintencionado podría interceptar las comunicaciones entre la entidad y el servidor.

7.El servidor ahora responde a las solicitudes de acceso (suponiendo que se ajusten a la lista de control de acceso del servidor). 
Uno de los inconvenientes que se observaron de Kerberos es que el KDC representa un único punto de falla para la red. En la práctica, se pueden implementar servidores KDC de copia de seguridad (por ejemplo, Active Directory admite varios controladores de dominio, cada uno de los cuales ejecuta el servicio KDC).