El propósito del endurecimiento de dispositivos es incrementar la seguridad de un sistema al minimizar las vulnerabilidades potenciales que una entidad maliciosa podría explotar. Esto se logra mediante la configuración de la red y los ajustes del sistema con el fin de reducir su superficie de ataque.

Segmentación
La segmentación es fundamental para asegurar un entorno empresarial, ya que reduce el impacto potencial de un incidente de ciberseguridad al aislar los sistemas y limitar la propagación de un ataque o infección de malware. En una red segmentada, los sistemas se dividen en segmentos o subredes separados, cada uno con diferentes controles de seguridad y permisos de acceso específicos. Este tipo de segmentación dificulta considerablemente el trabajo de un atacante, lo que otorga a la organización más tiempo para detectar y responder a los ataques. Además, la segmentación permite un control más granular sobre el acceso a los datos para garantizar que los usuarios, dispositivos y aplicaciones solo tengan acceso a la información necesaria para sus tareas específicas, mejorando así la protección y privacidad de los datos.

![[Pasted image 20250328120304.png]]

Una red segmentada que muestra las subredes de marketing y finanzas, junto con la disposición de los dispositivos de red. El tráfico entre las dos redes lo controla el enrutador. (Imágenes © 123RF.com.)

Aislamiento
El aislamiento del dispositivo se refiere a la segregación de dispositivos individuales dentro de una red para limitar su interacción con otros dispositivos y sistemas. Tiene como objetivo mejorar la protección de los puntos de conexión al evitar la propagación lateral de las amenazas en caso de que un dispositivo se vea comprometido. En el contexto de la protección de los puntos de conexión, el aislamiento de dispositivos crea barreras entre ellos, para impedir que una amenaza que se infiltre en un equipo pueda propagarse fácilmente a otros dispositivos. El aislamiento de dispositivos restringe el tráfico de red entre equipos, lo que reduce la superficie de ataque potencial. Este enfoque es particularmente útil para amenazas como gusanos o ransomware, que suelen tener como objetivo propagarse con rapidez a través de las redes. El aislamiento de dispositivos también limita los impactos de las brechas al garantizar que los dispositivos comprometidos no puedan acceder a toda la red.

Antivirus y antimalware
La primera generación de software antivirus se caracteriza por la detección y prevención basada en firmas de virus ya conocidos. Un antivirus ahora realizará una detección exhaustiva de malware, incluyendo no solo virus y gusanos, sino también troyanos, software espía, PUP, cryptojackers y otros tipos de software malicioso. Si bien el software antivirus sigue siendo importante, se reconoce ampliamente que la detección basada en firmas es insuficiente para prevenir las violaciones de datos.

Cifrado de disco
Cifrado de disco completo (FDE) significa que todo el contenido de la unidad (o volumen), incluidos los archivos y carpetas del sistema, está cifrado. Las medidas de seguridad basadas en ACL del sistema operativo son bastante sencillas de evadir si un adversario puede conectar la unidad a un sistema operativo host diferente. El cifrado de la unidad reduce este problema de seguridad al hacer que el contenido de la unidad esté accesible solo en combinación con la clave de cifrado correcta. El cifrado de disco se puede aplicar tanto a unidades de disco duro (HDD) como a unidades de estado sólido (SSD).

FDE requiere el almacenamiento seguro de la clave utilizada para cifrar el contenido de la unidad. Por lo general, esta se guarda en un módulo de plataforma confiable [TPM]. El chip del TPM tiene un área de almacenamiento seguro en la que un programa de cifrado de disco, como Windows BitLocker, puede escribir sus claves. También es posible utilizar una unidad USB extraíble (si el USB es una opción de dispositivo de arranque). Como parte del proceso de configuración, también crea una contraseña o clave de recuperación. Se puede utilizar si el disco se traslada a otro equipo o si el TPM está dañado.


Description
El panel izquierdo dice inicio del panel de control seguido de administración TPM, gestión de discos y declaración de privacidad bajo el encabezado, ver también. El panel derecho está dividido en dos secciones. La superior tiene por título, Cifrado de Unidad BitLocker. El texto debajo dice, Ayuda a proteger tus archivos y carpetas de accesos no autorizados protegiendo tus unidades con BitLocker. La sección inferior tiene por título, unidad del sistema operativo. El enlace debajo dice, C: BitLocker desactivado. Un enlace para activar BitLocker está presente a la derecha.



Activación del cifrado de la unidad BitLocker. (Captura de pantalla usada con el permiso de Microsoft).

Uno de los inconvenientes de FDE es que, debido a que el sistema operativo realiza las operaciones criptográficas, el rendimiento se reduce. Este problema se mitiga mediante unidades de autocifrado (SED), donde las operaciones criptográficas se realizan mediate el controlador de la unidad. El SED utiliza una clave de cifrado de datos/medios simétrico (DEK/MEK) para el cifrado masivo y almacena el DEK de forma segura cifrándolo con un par de claves asimétricas llamadas clave de autenticación (AK) o clave de cifrado de clave (KEK). El uso de la AK se autentica mediante la contraseña del usuario. Esto significa que la contraseña del usuario se puede cambiar sin necesidad de descifrar y volver a cifrar la unidad. Los primeros tipos de SED utilizaban mecanismos patentados, pero muchos proveedores ahora los desarrollan mediante la especificación de almacenamiento Opal (nvmexpress.org/wp-content/uploads/TCGandNVMe_Joint_White_Paper-TCG_Storage_Opal_and_NVMe_FINAL.pdf), desarrollado por la organización Trusted Computing Group (TCG).

Dispositivo Y SU Descripción
	
	Equipos portátiles, computadoras de escritorio, dispositivos móviles y servidores
	
	El cifrado de disco completo garantiza que los datos confidenciales estén protegidos incluso si el dispositivo de almacenamiento se elimina del dispositivo o se accede directamente mediante otros métodos. Para las máquinas virtuales, el FDE impide el acceso directo a los datos almacenados en el archivo de disco de la máquina virtual.
	
	Dispositivos IoT
	
	Los dispositivos del Internet de las cosas (IoT), como los dispositivos inteligentes para el hogar, los dispositivos portátiles y los sensores industriales, a menudo recopilan y transmiten datos confidenciales. El cifrado de disco completo impide el acceso no autorizado a estos datos si los dispositivos se ven comprometidos.
	
	Unidad de disco duro externa, unidad flash USB y medio externo
	
	Los dispositivos de almacenamiento portátiles son propensos a robos o extravíos. El cifrado de disco completo garantiza que los datos almacenados en estos dispositivos permanezcan protegidos, lo que dificulta en gran medida que las personas no autorizadas accedan o recuperen la información.



Gestión de parches
Ningún sistema operativo, aplicación de software o implementación de firmware está libre de vulnerabilidades. Tan pronto como se identifique una vulnerabilidad, los proveedores intentarán corregirla. Al mismo tiempo, los atacantes intentarán explotarla. Los escáneres de vulnerabilidades automatizados pueden detectar de manera efectiva la falta de parches en el sistema operativo, además de una amplia gama de aplicaciones de software y dispositivos o firmware de terceros. El escaneo solo es útil si cuenta con procedimientos efectivos para aplicar los parches faltantes.

Por lo general, en las redes domésticas y pequeñas, los hosts se configuran para actualizarse en automático, lo que significa que buscan e instalan los parches de forma automática. Los principales productos de software de aplicaciones y sistemas operativos cuentan con un sólido respaldo en términos de soluciones proporcionadas por el proveedor para problemas de seguridad. En Windows, este proceso es manejado por Windows Update, mientras que en Linux, se puede configurar a través de herramientas como yum-cron o aptunattended-upgrades, dependiendo del administrador de paquetes utilizado por la distribución. 

Las redes empresariales deben tener cuidado con la implementación automatizada, ya que un parche incompatible con una aplicación o flujo de trabajo puede causar problemas de disponibilidad. En ocasiones excepcionales, como en el notable ataque a la cadena de suministro SolarWinds (npr.org/2021/04/16/985439655/a-worst-nightmare-cyberattack-the-untold-story-of-the-solarwinds-hack?t=1631031433646), los repositorios de actualizaciones pueden verse comprometidos por malware, que luego se puede propagar a través de las actualizaciones automáticas. 

También puede haber problemas de rendimiento y administración cuando varias aplicaciones ejecutan clientes de actualización en el mismo host. Por ejemplo, además de la herramienta de actualización del sistema operativo, es probable que también exista un actualizador para software de seguridad, un actualizador de navegador, de Java, de controladores OEM, y así sucesivamente. Estos problemas se pueden mitigar mediante la implementación de una suite de gestión de parches empresarial. Algunas suites, como el System Center Configuration Manager (SCCM) o Endpoint Manager de Microsoft (docs.microsoft.com/en-us/mem/configmgr) de Microsoft, son específicas del proveedor, mientras que otras están diseñadas para admitir aplicaciones de terceros y sistemas operativos múltiples.

Probar los parches antes de implementarlos en el entorno de producción es fundamental a fin de garantizar la estabilidad y seguridad del software. Al realizar pruebas exhaustivas, las organizaciones pueden identificar posibles problemas o conflictos causados por el parche, asegurándose de que no introduzca nuevas vulnerabilidades o interrumpa las operaciones críticas. Las pruebas ayudan a mitigar el riesgo de consecuencias no deseadas y facilitan un proceso de implementación más controlado, lo que en última instancia protege la integridad y confiabilidad del entorno. Las pruebas por lo general se realizan en entornos de prueba diseñados para reflejar el entorno de producción tanto como sea apropiado.

Además, puede resultar difícil programar las operaciones de correcciones, en especial si la aplicación del parche supone un riesgo de disponibilidad de un sistema crítico. Si las evaluaciones de vulnerabilidad siguen señalando problemas con parches faltantes, se deben mejorar los procedimientos de gestión de parches. Si el problema solo afecta a ciertos hosts, podría indicar un compromiso que debe investigarse más detenidamente.

La gestión de parches puede resultar difícil para los sistemas heredados, los sistemas patentados y los sistemas de proveedores sin planes sólidos de gestión de seguridad, como algunos tipos de dispositivos del Internet de las cosas. Estos sistemas necesitarán controles compensatorio u otras formas de mitigación de riesgos si los parches no están disponibles.