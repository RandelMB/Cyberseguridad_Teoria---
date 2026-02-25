

Un sistema de intrusión es un control que realiza un análisis en tiempo real del tráfico de la red o de los registros del sistema y de las aplicaciones. 

Sensores
Un sistema de intrusión en la red captura el tráfico a través de un rastreador de paquetes, denominado sensor. El sensor podría utilizar un puerto SPAN/espejo o un TAP insertado. Por lo general, el sensor de captura de paquetes se coloca detrás de un cortafuegos o cerca de un servidor de particular importancia. La idea suele ser identificar el tráfico malicioso que ha logrado pasar el cortafuegos. Un solo rastreador puede registrar una gran cantidad de datos de tráfico, por lo que no puede colocar varios sensores en toda la red sin aprovisionar los recursos para administrarlos correctamente. Dependiendo del tamaño y los recursos de la red, se implementan uno o varios sensores para monitorear los activos clave o las rutas de red.

Sistemas de detección de intrusiones
El tráfico capturado por cada sensor se transfiere a un host o dispositivo que ejecuta un sistema de detección de intrusión (IDS), como Snort (snort.org), Suricata (suricata-ids.org) o Zeek/Bro (zeek.org). Cuando el tráfico coincide con una firma de detección, el IDS emite una alerta o genera una entrada de registro, pero no bloquea el host de origen. Este tipo de sensor pasivo no ralentiza el tráfico y es indetectable por el atacante.

Un IDS se utiliza para identificar y registrar hosts y aplicaciones y para detectar intentos de adivinar contraseñas, análisis de puertos, gusanos, aplicaciones backdoor (puerta trasera), paquetes o sesiones mal formados y otras violaciones a la política. 

![[Pasted image 20241202172951.png]]


Description

	El logo de Kibana está en la parte superior izquierda. La opción Descubrir está seleccionada del menú a la izquierda. El panel derecho tiene dos secciones. La sección superior muestra el tiempo y la fuente y la sección inferior tiene pestañas, tabla (seleccionada) y JSON. Proporciona información sobre marca de tiempo, versión, id, índice, puntuación, tipo, alerta, categoría, clasificación y código de continente de destino subrayado geo punto.



Visualización de una alerta de detección de intrusión generada por Snort en la aplicación Kibana en Security Onion. (Captura de pantalla cortesía de Security Onion https://securityonionsolutions.com).

Sistema de prevención de intrusiones
Un sistema de prevención de intrusiones (IPS) es un dispositivo o software capaz de una respuesta activa. Un IPS analiza el tráfico para que coincida con las firmas de detección y se puede configurar para que actúe automáticamente para detener un ataque. Las siguientes respuestas son típicas:

- Bloquear, ya sea temporal o permanentemente, el origen del tráfico que no cumple con las normas. Esto se denomina rechazo.
- Restablecer la conexión, pero no bloquear la dirección de origen.
- Redirigir el tráfico a un honeypot o honeynet para un análisis adicional de amenazas.

Un IPS se puede implementar como un dispositivo inline con un cortafuegos integrado y capacidad de enrutamiento/reenvío. Si se usa con un sensor pasivo, puede implementar la acción de respuesta al reconfigurar otro dispositivo, como un cortafuegos o un enrutador. Esta funcionalidad utiliza una secuencia de comandos o una interfaz de programación de aplicaciones (API) para integrar los dos controles de seguridad.