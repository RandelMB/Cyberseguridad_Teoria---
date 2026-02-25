
Condición de la carrera y TOCTOU
Las vulnerabilidades de condición de carrera se refieren a fallas de software asociadas con el momento o el orden de los eventos dentro de un programa de software, que pueden manipularse, lo que causa resultados indeseables o impredecibles. Una condición de carrera describe cuándo dos o más operaciones deben ejecutarse en el orden correcto. Cuando la lógica del software no verifica o aplica el orden esperado de los eventos, pueden ocurrir problemas de seguridad como la corrupción de datos, el acceso no autorizado u otras violaciones a la seguridad similares. Las condiciones de carrera se manifiestan en una amplia variedad de formas, como las vulnerabilidades del tiempo potencial de comprobación en tiempo de uso (TOCTOU), donde un estado del sistema cambia entre la etapa de comprobación (verificación) y la etapa de uso (ejecución). 

Imagine un escenario en el que una aplicación bancaria de subprocesos múltiples usara un subproceso de programa para verificar el saldo de una cuenta y otro subproceso para retirar dinero. Si un atacante manipula la secuencia de ejecución en este ejemplo, podría superponer la cuenta. Estas vulnerabilidades subrayan la importancia de las operaciones atómicas en las que la verificación y la ejecución se realizan como una operación única e indivisible, lo que mitiga la probabilidad de explotación.

Dos ejemplos significativos de condiciones de carrera incluyen la vulnerabilidad Dirty COW (CVE-2016-5195), que es una vulnerabilidad de condición de carrera en el kernel de Linux, que permite a un usuario local obtener acceso privilegiado, y la vulnerabilidad de elevación de privilegios de Microsoft Windows (CVE-2020-0796), que es una vulnerabilidad de condición de carrera asociada con el protocolo Microsoft Server Message Block 3.1.1 (SMBv3) que permite a un atacante ejecutar código arbitrario en un servidor o cliente SMB de destino. Los desarrolladores a menudo mitigan las condiciones de carrera mediante el uso de cerraduras, semáforos y monitores en aplicaciones de subprocesos múltiples.

Inyección de memoria
La  inyección de memoria se refiere a un tipo de falla de seguridad en la que un atacante puede introducir (inyectar) código malicioso en la memoria de proceso de una aplicación en ejecución. Los atacantes, a menudo, diseñan el código inyectado para alterar el comportamiento de una aplicación y proporcionar acceso o control no autorizado del sistema. Las vulnerabilidades de inyección son significativas porque a menudo conducen a graves violaciones de seguridad. Los atacantes, con frecuencia, utilizan las vulnerabilidades de inyección de memoria para inyectar código que instala malware, exfiltra datos confidenciales o crea una puerta trasera para el acceso futuro. Por lo general, el código inyectado se ejecuta con el mismo nivel de privilegios que la aplicación en peligro, lo que puede llevar a poner el sistema completo en peligro, si la aplicación explotada tiene permisos de alto nivel. Los ataques comunes de inyección de memoria incluyen ataques de desbordamiento de búfer, vulnerabilidades de cadena de formato y ataques de inyección de código. Estos tipos de ataques por lo general se mitigan con prácticas de codificación seguras, como la validación de entradas y salidas, la codificación, la distribución de tipos, los controles de acceso, las pruebas de aplicaciones estáticas y dinámicas y varias otras técnicas.

Desbordamiento de búfer 

Un búfer es un área de memoria que la aplicación reserva para almacenar los datos esperados. Para explotar un desbordamiento de búfer, el atacante pasa datos que llenan deliberadamente el búfer. Una de las vulnerabilidades más comunes es un desbordamiento de pila. La pila es un área de memoria utilizada por una subrutina de programa. Incluye una dirección de devolución, que es la ubicación del programa que llamó a la subrutina. Un atacante podría usar un buffer overflow (desbordamiento de búfer) para cambiar la dirección de devolución, lo que permitiría al atacante ejecutar código arbitrario en el sistema. 

Los ataques de desbordamiento de búfer se mitigan en el hardware y los sistemas operativos modernos a través de la aleatorización del diseño del espacio de direcciones (ASLR) y los controles de prevención de la ejecución de datos (DEP), mediante lenguajes de programación seguros y la incorporación de prácticas de codificación seguras.
![[Pasted image 20250217141232.png]]


Description

	Sub()
	
	
	
	Sub() Pila
	
	
	
	Dirección de retorno
	
	
	
	Principal()
	
	
	
	Pila Main()
	
	
	
	La flecha que va de Main() a Sub() está etiquetada como Argumentos. Otra flecha va de Return Address a Main().
	
	
	
	La ejecución del exploit de arriba a abajo es:
	
	
	
	Sub()
	
	
	
	NOP
	
	
	
	NOP
	
	
	
	Shellcode
	
	
	
	NOP
	
	
	
	Dirección de retorno
	
	
	
	Principal()
	
	
	
	Pila Main()
	
	
	
	Una flecha de Main() a Sub() está etiquetada como símbolo de peligro. Otra flecha se mueve de Return Address a NOP en la fila 2. La tercera flecha se mueve de NOP en la fila 2 a Shellcode.

Cuando se ejecuta en forma normal, una función devuelve el control a la función que la invoca. Si el código es vulnerable, un atacante puede pasar datos maliciosos a la función, desbordar la pila y ejecutar un código arbitrario para obtener un shell en el sistema de destino.

Actualización maliciosa
Una actualización maliciosa se refiere a una actualización que parece legítima pero que contiene código dañino, a menudo utilizado por los ciberdelincuentes para distribuir malware o ejecutar un ciberataque. La actualización puede fingir que pretende corregir errores de software u que ofrece funciones nuevas, pero en su lugar está diseñada para poner al sistema en peligro. La importancia de tales ataques radica en su naturaleza engañosa; los usuarios confían y con frecuencia aceptan actualizaciones de software, lo que hace que las actualizaciones maliciosas sean una estrategia de infiltración altamente efectiva. Puede ser difícil protegerse contra las actualizaciones maliciosas, pero la gestión segura de la cadena de suministro de software, la verificación de firmas digitales y otras prácticas de seguridad de software ayudan a mitigar estos riesgos.

En 2017, el software legítimo CCleaner se vio comprometido cuando se lanzó una actualización no autorizada que contenía una carga maliciosa. Afectó a millones de usuarios que descargaron la actualización, creyendo que era una actualización estándar para mejorar el rendimiento de su sistema. https://arstechnica.com/information-technology/2017/09/backdoor-malware-planted-in-legitimate-software-updates-to-ccleaner/

Otro caso destacado es el del ataque SolarWinds 2020, en el que los atacantes usaron una actualización de la plataforma SolarWinds Orion para distribuir una puerta trasera maliciosa a numerosas redes gubernamentales y corporativas, lo que llevó a violaciones de datos significativas. https://www.npr.org/2021/04/16/985439655/a-worst-nightmare-cyberattack-the-untold-story-of-the-solarwinds-hack