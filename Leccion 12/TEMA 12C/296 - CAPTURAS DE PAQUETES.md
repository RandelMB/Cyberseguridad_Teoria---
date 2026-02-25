El tráfico de red puede proporcionar información valiosa sobre posibles infracciones. El tráfico de red generalmente se analiza en detalle a nivel de tramas individuales o utilizando estadísticas resumidas de los flujos de tráfico y del uso del protocolo.

Un SIEM almacenará la información seleccionada de los sensores instalados en diferentes puntos de la red. La información capturada de los paquetes de red se puede agregar y resumir para mostrar el uso general del protocolo y la actividad del punto de conexión. En una red típica, los sensores no están configurados para registrar todo el tráfico de la red, ya que esto generaría una cantidad considerable de datos. Por lo general, solamente se registran los paquetes que activaron un determinado cortafuegos o regla IDS específica. El software SIEM, generalmente, proporcionará la capacidad de pivotar desde un evento o resumen de alerta hasta abrir los paquetes subyacentes en un analizador.

Por otro lado, con recursos suficientes, una solución de análisis retrospectivo de red (RNA) proporciona los medios para registrar la totalidad de los eventos de red, ya sea a nivel del encabezado del paquete o de la carga útil. 

Análisis de paquetes se refiere al análisis profundo, cuadro por cuadro, del tráfico capturado utilizando una herramienta como Wireshark.  El analizador decodifica el paquete para mostrar los campos de encabezado en las capas de enlace de datos/MAC, red/IP y transporte (TCP/UDP). En la capa de la aplicación, muestra los datos del encabezado y el contenido de la carga útil. 

El análisis de paquetes puede identificar si los paquetes que pasan por un puerto estándar han sido manipulados de alguna manera no estándar, para funcionar como un mecanismo para un servidor botnet, por ejemplo. Permite la inspección de las cargas útiles del protocolo para tratar de identificar los intentos de exfiltración de datos o los intentos de contactar con dominios y URL sospechosos. El análisis detallado del contenido del paquete puede ayudar a revelar las herramientas utilizadas en un ataque. También es posible extraer archivos binarios, como malware potencial, para su análisis.

![[Pasted image 20250403090543.png]]


Uso del analizador de paquetes Wireshark para identificar ejecutables maliciosos que se transfieren a través del protocolo de intercambio de archivos de Windows. (Captura de pantalla de Wireshark wireshark.org.)