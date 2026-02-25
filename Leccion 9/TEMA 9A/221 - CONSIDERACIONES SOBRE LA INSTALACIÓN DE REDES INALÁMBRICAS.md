Las consideraciones sobre la instalación de redes inalámbricas hacen referencia a los factores que garantizan una buena disponibilidad de puntos de acceso Wi-Fi autorizados. Una red con cobertura irregular es vulnerable a los ataques de punto de acceso falso y no autorizados.

La banda 5 GHz tiene más espacio para configurar los canales que no se superponen. También tenga en cuenta que un WAP puede usar canales enlazados para mejorar el ancho de banda, pero esto aumenta los riesgos de interferencia.

Colocación del punto de acceso inalámbrico (WAP)
Una red inalámbrica basada en infraestructura comprende uno o más puntos de acceso inalámbricos, cada uno conectado a una red cableada. Los puntos de acceso reenvían el tráfico hacia y desde la red conmutada por cable. Cada WAP se identifica por su dirección MAC, también conocida como su identificador de conjunto de servicios básicos (BSSID). Cada red inalámbrica se identifica por su nombre o identificador de conjunto de servicios [SSID].

Las redes inalámbricas pueden funcionar en la banda de radio de 2,4 GHz o 5 GHz. Cada banda de radio se divide en una serie de canales, y cada WAP debe configurarse para utilizar un canal específico. Por razones de rendimiento, los canales elegidos deben estar lo más espaciados posible para reducir la interferencia.

Sondeo del sitio y mapas de calor
Los factores de cobertura e interferencia significan que los WAP deben colocarse y configurarse para que cubran toda el área con la menor superposición posible. Un sondeo del sitio se utiliza para medir la intensidad de la señal y el uso del canal en toda el área a cubrir. Un sondeo del sitio comienza con un mapa arquitectónico del sitio, en el que se marcan los elementos que pueden causar interferencias de fondo. Estos elementos incluyen paredes sólidas, superficies reflectantes, motores, hornos de microondas, etc. Una computadora portátil o dispositivo móvil habilitados para Wi-Fi con el software del analizador de Wi-Fi instalado realiza el sondeo. El analizador de Wi-Fi registra información sobre la señal obtenida en puntos espaciados de manera regular a medida que el topógrafo se desplaza por la zona.

![[Pasted image 20250317175155.png]]


Ejemplo de salida de la herramienta de escáner Wi-Fi del sistema Lizard. (Captura de pantalla cortesía de Lizard Systems).

Estas lecturas se combinan y analizan para producir un mapa de calor, que muestra dónde una señal es fuerte (rojo) o débil (verde/azul), y qué canal se está utilizando y cómo se superponen. Luego, estos datos se utilizan para optimizar el diseño al ajustar la potencia de transmisión para reducir el rango de un WAP, cambiar el canal en un WAP, agregar un nuevo WAP o mover físicamente un WAP a una nueva ubicación.

![[Pasted image 20250317175143.png]]

Description
El panel de la izquierda titulado, Banda o Nombre muestra la casilla de verificación, 802 punto 11 a n seleccionada. Las cuatro subcasillas que le siguen también están seleccionadas. Las subcasillas son AP virtual hash 1 (5 Gigahercios), AP virtual hash 2 (5 Gigahercios), AP virtual hash 3 (5 Gigahercios) y AP virtual hash 4 (5 Gigahercios). El panel derecho muestra un mapa de calor de una región formada por la sala de conferencias 1, el ascensor, la recepción, la zona mecánica, la zona trasera, los archivos y la sala de conferencias 2. Las cuatro llamadas de la región son las siguientes: virtual AP hash 1 (5 Gigahercios), virtual AP hash 2 (5 Gigahercios), virtual AP hash 3 (5 Gigahercios) y virtual AP hash 4 (5 Gigahercios).

Ilustración de un mapa de calor.