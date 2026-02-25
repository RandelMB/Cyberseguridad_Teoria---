Un balanceador de carga distribuye las solicitudes de los clientes entre los nodos de servidor disponibles en una granja o grupo. Esto se utiliza para aprovisionar servicios que pueden escalar de cargas ligeras a pesadas y para proporcionar mitigación contra ataques por denegación de servicio. Un balanceador de carga también proporciona tolerancia a errores. Cuando hay varios servidores disponibles en una granja, todos ellos direccionados por un solo nombre/dirección IP a través de un balanceador de carga, si un servidor falla, las solicitudes de los clientes pueden reenviarse a otro servidor de la granja. Un balanceador de carga se puede implementar en cualquier caso en el que haya varios servidores que proporcionen la misma función. Algunos ejemplos son los servidores web, los de correo electrónico front-end, los de conferencias web, las videoconferencias y los de transmisión multimedia.

Hay dos tipos principales de balanceadores de carga:

Balanceador de carga de capa 4: los balanceadores de carga básicos toman decisiones de reenvío en función de la dirección IP y los valores del encabezado TCP/UDP. Trabajan en la capa de transporte del modelo OSI.
Balanceador de carga de capa 7 (switch de contenido): como las aplicaciones web se han vuelto más complejas, los balanceadores de carga modernos deben ser capaces de tomar decisiones de reenvío basadas en datos a nivel de aplicación, como una solicitud de una dirección web concreta del localizador uniforme de recursos (URL) o tipos de datos como la transmisión de video o audio. Esto requiere de una lógica más compleja, pero la potencia de procesamiento de los dispositivos modernos es suficiente para afrontarlo. 

![[Pasted image 20241202173143.png]]



**Description**
Las tres etapas son las siguientes



1. El cliente se conecta al servidor virtual a través de Internet.



2. El balanceador de carga selecciona una instancia de servidor web para gestionar la conexión y reenvía el tráfico.



3. Un mecanismo de persistencia puede mantener al cliente conectado al mismo servidor, si está disponible.

Topología de la arquitectura básica de equilibrio de carga. (Imágenes © 123RF.com.)

**Programación** 
El algoritmo de programación es el código y las métricas que determinan qué nodo se selecciona para procesar cada solicitud entrante. El tipo más simple de programación se llama “round robin”, que significa elegir el próximo nodo. Otros métodos incluyen elegir el nodo con menos conexiones o el mejor tiempo de respuesta. Cada método puede ser ponderado a través de las preferencias establecidas por el administrador o información dinámica de carga, o bien ambas.

El balanceador de carga también debe utilizar algún tipo de latido o sonda de verificación de estado para comprobar si cada nodo está disponible y bajo carga. Los balanceadores de carga de capa 4 solo pueden realizar pruebas de conectividad básicas, mientras que los dispositivos de capa 7 pueden probar el estado de la aplicación y verificar la disponibilidad del host.

**Afinidad por IP de origen y persistencia de sesión** 
Cuando un dispositivo cliente estableció una sesión con un nodo específico en el clúster de servidores, puede ser necesario continuar utilizando esa conexión durante la duración de la sesión. La dirección IP de origen o la afinidad por sesión son enfoques de capa 4 para gestionar las sesiones de usuario. Significa que cuando un cliente establece una sesión, se queda atascado en el nodo que primero aceptó la solicitud.

Un balanceador de carga de capa de aplicación utiliza la persistencia para mantener a un cliente conectado a una sesión. Por lo general, la persistencia funciona configurando una cookie en el nodo o inyectada por el balanceador de carga. Esto puede ser más confiable que la afinidad por la dirección IP de origen, pero requiere que el navegador acepte la cookie.
