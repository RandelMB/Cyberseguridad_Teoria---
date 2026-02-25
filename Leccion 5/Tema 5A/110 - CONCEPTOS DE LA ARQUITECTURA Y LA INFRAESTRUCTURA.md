

La arquitectura de red es la selección y colocación de medios, dispositivos, protocolos/servicios y activos de datos: 

- La infraestructura de red son los medios, los dispositivos y los protocolos de direccionamiento/reenvío que admiten la conectividad básica.
- Las aplicaciones de red son los servicios que se ejecutan en la infraestructura para respaldar las actividades comerciales, como el procesamiento de facturas o el envío de correos electrónicos. 
- Los activos de datos son la información que se crea, almacena y transfiere como resultado de la actividad comercial.
- La infraestructura de red segura y la arquitectura de aplicaciones se colocan allí para admitir flujos de trabajo empresariales seguros. Un flujo de trabajo es una serie de tareas que una empresa debe realizar, como aceptar pedidos de clientes de una tienda web. Recuerde que seguridad significa tener los atributos de confidencialidad, integridad y disponibilidad.

El análisis de los sistemas involucrados en el aprovisionamiento de correo electrónico puede ilustrar los tipos de decisiones de arquitectura que deben tomarse:

- Acceso: el dispositivo cliente debe acceder a la red a través de un canal físico y obtener una dirección lógica. El usuario debe estar autenticado y autorizado para usar la aplicación de correo electrónico. El corolario es que a los usuarios y dispositivos no autorizados se les debe negar el acceso.
- Servidor de buzón de correo electrónico: el buzón almacena los activos de datos y solo los clientes autorizados deben acceder a él y, por el contrario, debe estar completamente disponible y tolerar fallas para admitir al usuario genuino. El servicio de correo electrónico debe ejecutarse con un número mínimo de dependencias a través de una infraestructura de red que sea resistente a los fallos.
- Servidor de transferencia de correo: debe conectarse con hosts de Internet que no sean de confianza, por lo que las comunicaciones entre la red que no sea de confianza y la LAN de confianza deben controlarse con cuidado. Cualquier dato o software que salga o ingrese a la red debe estar sujeto a controles basados en políticas.

Este tipo de flujo de negocios involucrará sistemas con diferentes requisitos de seguridad. Colocar al cliente, el buzón y el servidor de transferencia de correo en el mismo segmento introducirá muchas vulnerabilidades. Comprender y controlar cómo fluyen los datos entre estos segmentos de red es una parte clave del diseño de arquitectura de red segura y efectiva. 