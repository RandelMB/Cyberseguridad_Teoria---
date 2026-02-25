


Es probable que un cortafuegos que realiza el filtrado de la capa de aplicación se implemente como un proxy. Cuando un cortafuegos de red solamente acepta o bloquea el tráfico, un servidor proxy funciona con un modelo de almacenamiento y reenvío. El proxy deconstruye cada paquete, lo analiza, lo reconstruye y lo reenvía, siempre que se ajuste a las normas. 

		La cantidad de reconstrucciones depende del proxy. Algunos proxies solamente manipulan los encabezados IP y TCP. Los proxies sensibles a las aplicaciones pueden agregar o quitar encabezados HTTP. Un proxy de inspección profunda de paquetes podría eliminar el contenido de una carga útil HTTP.

Servidores proxy directos
Un proxy directo se encarga del tráfico saliente específico del protocolo. Por ejemplo, un proxy web permite a los equipos clientes de la red local conectarse a los sitios web y a las páginas web seguras de internet. Este es un proxy directo que da servicio a los puertos TCP 80 y 443 para el tráfico saliente. 


![[Pasted image 20241202172828.png]]



*Configuración de los ajustes de filtro para el servidor proxy de almacenamiento en caché que se ejecuta en OPNsense. El filtro puede aplicar ACL para prohibir el acceso a direcciones IP y a las URL. (Captura de pantalla cortesía de OPNsense).* 

La principal ventaja de un proxy es que los equipos cliente se conectan a un punto específico de la red perimetral para acceder a la web. De esta forma, se consigue un grado de gestión del tráfico y de seguridad. Además, la mayoría de los servidores proxy ofrecen motores de almacenamiento en caché, por lo que las páginas web solicitadas con frecuencia se conservan en el proxy, lo que evita la necesidad de volver a obtener esas páginas para las solicitudes posteriores.

Un servidor proxy debe entender la aplicación a la que da servicio. Por ejemplo, un proxy web debe ser capaz de analizar y modificar los comandos HTTP y, potencialmente, también el código y los scripts de la página web. Algunos servidores proxy son específicos de una aplicación; otros son multipropósito. Un proxy multipropósito es aquel configurado con filtros para múltiples tipos de protocolo, como los de datos web, los de transferencia de archivos y los de correo electrónico.

Los servidores proxy pueden clasificarse generalmente como no transparentes o transparentes.

- En un proxy no transparente  el cliente debe estar configurado con la dirección del servidor proxy y el número de puerto para utilizarlo. El puerto en el que el servidor proxy acepta las conexiones de los clientes suele estar configurado como puerto TCP/8080.
- Un proxy transparente (o "forzado" o "interceptor") intercepta el tráfico del cliente sin que éste tenga que reconfigurarse. Un proxy transparente debe implementarse como enrutador o como dispositivo de red inline.


![[Pasted image 20241202172840.png]]

Configuración de los ajustes de proxy transparente para el servidor proxy que se ejecuta en OPNsense. El proxy utiliza su propio certificado para interceptar las conexiones seguras e inspeccionar la URL. (Captura de pantalla cortesía de OPNsense).

Ambos tipos de proxy se pueden configurar para requerir que los usuarios se autentiquen antes de permitir el acceso. Es probable que el proxy pueda usar el inicio de sesión único (SSO) para hacer esto sin tener que pedirle al usuario una contraseña. 

		Un script de configuración automática de proxy (PAC) permite que un cliente configure los ajustes de proxy sin intervención del usuario. El protocolo de descubrimiento automático del proxy web (WPAD) permite a los navegadores localizar un archivo PAC. 

**Servidores proxy inversos**
Un servidor proxy inverso se encarga del tráfico entrante específico del protocolo. Un proxy inverso generalmente se despliega en el borde de la red y se configura para escuchar las solicitudes de los clientes de una red pública (internet). El proxy aplica reglas de filtrado y, si se acepta, crea la solicitud adecuada y la reenvía a un servidor de aplicaciones dentro de una zona de subred protegida especialmente en la red local. 