La adquisición de imágenes de disco se refiere a la adquisición de datos desde un almacenamiento no volátil. El almacenamiento no volátil incluye unidades de disco duro (HDD), unidades de estado sólido (SSD), firmware, otros tipos de memoria flash (unidades USB y tarjetas de memoria) y medios ópticos (CD, DVD y Blu-ray). Esto también se conoce como adquisición de dispositivos, es decir, el almacenamiento SSD en un teléfono inteligente o reproductor multimedia. La adquisición de discos también capturará la instalación del sistema operativo, si se incluye el volumen de arranque.

Existen tres estados de dispositivo para la adquisición de almacenamiento persistente:

Adquisición en vivo: esto significa copiar los datos mientras el host aún se está ejecutando. De este modo se puede capturar más evidencia o más datos para su análisis y reducir el impacto en los servicios en general, pero los datos en los discos reales habrán cambiado, por lo que este método puede no producir evidencia legalmente aceptable. También puede alertar al actor de la amenaza y darles tiempo para que realicen análisis antiforenses.
La adquisición estática al apagar el host: conlleva el riesgo de que el malware detecte el proceso de apagado y realice análisis antiforenses para tratar de eliminar los rastros de sí mismo.
Adquisición estática tirando del enchufe: significa desconectar la energía en el tomacorriente de la pared (no el botón de apagado del hardware). Es muy probable que, de este modo, se conserven los dispositivos de almacenamiento en un estado forense limpio, pero existe el riesgo de corromper los datos.
Con el tiempo suficiente en la escena, un investigador podría decidir realizar una adquisición tanto en vivo como estática. Sea cual sea el método utilizado, es imprescindible documentar los pasos tomados y proporcionar una línea de tiempo y evidencia grabada en video de las acciones tomadas para adquirir la evidencia.

Hay muchas utilidades de imágenes de GUI, incluidas las que vienen con suites forenses. Si no hay una herramienta especializada disponible, en un host Linux, el comando dd hace una copia de un archivo de entrada (if=) a un archivo de salida (of=). A continuación, el SDA es la unidad fija:

dd if=/dev/sda of=/mnt/usbstick/backup.img

Una bifurcación más reciente de dd es dcfldd, que proporciona características adicionales como múltiples archivos de salida y verificación de coincidencia exacta.


![[Pasted image 20250403085735.png]]


Uso de dcfldd (una versión de dd con funcionalidad forense adicional creada por el DoD) y generación de un hash de los datos del disco de origen (SDA).