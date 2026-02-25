

Las restricciones basadas en políticas se pueden utilizar para mitigar algunos riesgos de compromiso de cuentas a través del robo de credenciales.

Políticas basadas en la ubicación
Un usuario o dispositivo puede tener una ubicación de red lógica, identificada por una dirección IP, subred, LAN virtual (VLAN) o unidad organizacional (OU). Esto se puede utilizar como un mecanismo de restricción de cuenta. Por ejemplo, se puede evitar que una cuenta de usuario inicie sesión de manera local en servidores dentro de una OU restringida.

La ubicación geográfica de un usuario o dispositivo se puede calcular mediante un mecanismo de geolocation (geolocalización):

Dirección IP: se puede asociar a una ubicación cartográfica con mayor o menor precisión en función de la información publicada por el solicitante de registro, como el nombre, el país, la región y la ciudad. El solicitante de registro suele ser el proveedor de servicios de Internet (ISP), por lo que la información que reciba proporcionará una ubicación aproximada de un host en función del ISP. Si se trata de un ISP que brinda servicio a un área geográfica extensa o diversa, es más difícil precisar la ubicación de los proveedores de servicios de internet (ISP) anfitriones. Las bibliotecas de software, como GeoIP, facilitan la consulta de estos datos.
Servicios de ubicación: son métodos utilizados por el sistema operativo para calcular la posición geográfica del dispositivo. Un dispositivo con un sensor de sistema de posicionamiento global (GPS) puede informar una ubicación con mucha precisión cuando está al aire libre. Los servicios de ubicación también pueden triangular las torres de telefonía celular, los puntos de acceso wifi y las señales Bluetooth cuando el GPS no es compatible.
Restricciones basadas en el tiempo
Hay cuatro tipos principales de políticas basadas en el tiempo:

Una política de time-of-day restrictions (restricciones horarias) establece las horas de inicio de sesión autorizadas para una cuenta.
Una política de inicio de sesión basada en la duración establece la cantidad máxima de tiempo durante el que una cuenta puede estar conectada.
Una política de tiempo de viaje imposible/inicio de sesión arriesgado realiza un seguimiento de la ubicación de los eventos de inicio de sesión a lo largo del tiempo. Si no alcanzan un umbral, la cuenta se desactivará. Por ejemplo, un usuario inicia sesión en una cuenta desde un dispositivo en la ciudad de Nueva York. Un par de horas más tarde, se realiza un intento de inicio de sesión desde Los Ángeles, pero se rechaza y se genera una alerta porque no es factible que el usuario esté en ambas ubicaciones.
Una política de permisos temporales elimina una cuenta de una función o grupo de seguridad después de un período definido.

