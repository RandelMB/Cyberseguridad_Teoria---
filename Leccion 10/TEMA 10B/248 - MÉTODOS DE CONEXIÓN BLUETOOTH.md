
Bluetooth es una tecnología inalámbrica basada en radio diseñada para implementar redes de área personal de corto alcance. A continuación se detallan algunos de los problemas de seguridad asociados con el Bluetooth:

- Detección de dispositivos: es cuando un dispositivo se puede poner en modo de descubrimiento, lo que significa que se conectará a cualquier otro dispositivo Bluetooth cercano. Lamentablemente, puede detectarse incluso un dispositivo en modo no detectable.
- Autenticación y autorización: es cuando los dispositivos se autentican (“emparejan”) mediante una clave de acceso simple configurada en ambos dispositivos. Esto siempre debe cambiarse por alguna frase segura y nunca dejarse como el valor predeterminado, como “0000”. Además, la lista de emparejamiento del dispositivo debe revisarse con regularidad para confirmar que los dispositivos en la lista sean válidos.
- Malware: se refiere a la existencia de gusanos Bluetooth de prueba de concepto y exploits de aplicaciones, en especial el exploit BlueBorne (armis.com/blueborne), que tienen la capacidad de comprometer cualquier sistema activo y sin parches, sin importar si la función de descubrimiento está activada y sin necesidad de ninguna intervención del usuario para ejecutarse. También existen vulnerabilidades en los esquemas de autenticación de muchos dispositivos. Mantenga los dispositivos actualizados con el firmware más reciente.

![[Pasted image 20250328151650.png]]

Description
El panel izquierdo tiene un botón de inicio seguido por una barra de búsqueda. Debajo de la barra hay una lista de dispositivos. El panel derecho está titulado, Bluetooth y otros dispositivos. Un cuadro de diálogo titulado, Emparejar Dispositivo dice, ¿Emparejar dispositivo? El texto debajo dice, ¿El PIN en \COMPTIA-MOBILE\ coincide con el PIN debajo?, 998584. Dos botones, sí y cancelar, están presentes en la parte inferior.



Emparejamiento de una computadora y un teléfono inteligente. (Captura de pantalla utilizada con el permiso de Microsoft).

Es posible que la opción de desactivar la radio Bluetooth desde el centro de control en un dispositivo móvil no la desactive en realidad. Si existe alguna duda sobre el estado de los parches o la exposición a vulnerabilidades, Bluetooth debería desactivarse por completo a través de la configuración del dispositivo.

A menos que se configure la autenticación del dispositivo, un equipo en modo de descubrimiento es vulnerable al bluejacking, una especie de spam en el que alguien te envía un mensaje de texto (o imagen/video) no solicitado o una vCard (detalles de contacto). También puede ser un vector de malware, como se demostró con el malware troyano para Android Obad (securelist.com/the-most-sophisticated-android-trojan/35929).

Bluesnarfing se refiere al uso de un exploit en Bluetooth para robar información del teléfono de otra persona. El exploit (ya corregido) permite a los atacantes eludir el mecanismo de autenticación. Incluso sin un exploit, un código PIN corto (de cuatro dígitos) es vulnerable al proceso de adivinación de contraseñas por fuerza bruta.

Otros riesgos significativos provienen de la conexión del dispositivo a otro dispositivo. Se puede utilizar un dispositivo periférico con firmware malicioso para lanzar ataques altamente efectivos. Este tipo de riesgo tiene una baja probabilidad, ya que se requieren recursos exigentes para crear estos periféricos maliciosos. 

Características de seguridad de Bluetooth
El Bluetooth incorpora varias funciones de seguridad para garantizar la seguridad de los datos y las comunicaciones. 

![[Pasted image 20250328151628.png]]