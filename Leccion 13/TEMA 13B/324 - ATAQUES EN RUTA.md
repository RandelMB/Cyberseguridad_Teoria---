Un ataque on-path (en ruta) es cuando el actor de amenazas gana una posición entre dos hosts y captura, supervisa y retransmite de manera transparente toda la comunicación entre ellos. Debido a que el actor de amenazas transmite las comunicaciones interceptadas, es posible que los hosts no puedan detectar la presencia del actor de amenazas. También se podría utilizar un ataque en ruta para modificar el tráfico de forma encubierta. Por ejemplo, un host en ruta podría presentar una estación de trabajo con un formulario de sitio web falsificado para intentar capturar la credencial de usuario. Este ataque también se denomina ataque en ruta o ataque de adversario en el medio (AitM).

Los ataques en ruta se pueden lanzar en cualquier capa de red. Un ejemplo infame ataca la forma en que funciona el reenvío de capa 2 en los segmentos locales. El protocolo de resolución de direcciones (ARP) identifica la dirección Mac de un host en el segmento local que posee una dirección IPv4. Un ataque de envenenamiento de ARP utiliza un creador de paquetes, como Ettercap, para transmitir paquetes de respuesta de ARP no solicitados. Dado que ARP no tiene un mecanismo de seguridad, los dispositivos receptores confían en esta comunicación y actualizan su tabla de caché de direcciones IP MAC con la dirección suplantada.

![[Pasted image 20250404074035.png]]

Description
Una tabla en la parte superior lista el número, tiempo, fuente, destino, protocolo, longitud e información. En el resultado a continuación, el destino y el protocolo de control de transmisión están resaltados.



Captura de paquetes en Wireshark que muestra el envenenamiento de ARP. (Captura de pantalla utilizada con permiso de wireshark.org).

En esta captura de pantalla, se muestran los paquetes capturados durante un ataque típico de envenenamiento de ARP:

En los cuadros 6 a 8, la máquina atacante (con la dirección Mac que termina en :4a) dirige respuestas ARP gratuitas a otros hosts (:76 y :77), que afirman tener las direcciones IP .2 y .102. Este patrón de tráfico ARP gratuito es un indicador del ataque.
En la trama 9, el host .101/:77 intenta enviar un paquete al host .2, pero el host atacante lo recibe (con la MAC de destino :4a).
En la trama 10, el host atacante retransmite la trama 9 al host .2 real. Wireshark colorea la trama en negro y rojo para resaltar la retransmisión.
En las tramas 11 y 12, puede ver la respuesta de .2, que el host atacante recibió en la trama 11 y retransmitió al host legítimo en la trama 12.
El objetivo habitual será la puerta de enlace predeterminada de la subred (el enrutador que accede a otras redes). Si el ataque de envenenamiento de ARP tiene éxito, el atacante recibirá todo el tráfico destinado a las redes remotas, mediante un ataque en ruta.