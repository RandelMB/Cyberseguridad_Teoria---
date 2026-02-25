El primer paso para configurar la biometric authentication (autenticación biométrica) es el registro:

Un módulo de sensor adquiere la muestra biométrica del objetivo.
Un módulo de extracción de características crea una plantilla. La plantilla es una representación matemática de las partes de la muestra que identifican de forma única el objetivo.
Cuando el usuario desea acceder a un recurso, se vuelve a escanear y se compara el escaneo con la plantilla. Si coinciden dentro de un grado de tolerancia definido, se otorga el acceso.

La autenticación biométrica puede ser difícil de implementar. La tasa de eficacia de la adquisición y coincidencia de patrones biométricos y la idoneidad como mecanismo de autenticación se pueden evaluar por medio de las siguientes métricas y factores:

Tasa de falso rechazo (FRR): es cuando no se reconoce a un usuario legítimo. También se denomina error de tipo I o tasa de falsa no coincidencia (FNMR). La FRR se mide como porcentaje.
Tasa de falsa aceptación (FAR): es cuando se acepta un intruso (error de tipo II o tasa de falsa coincidencia [FMR]). La FRR se mide como porcentaje.
El falso rechazo causa inconvenientes a los usuarios, pero la falsa aceptación puede provocar violaciones de seguridad, por lo que por lo general se considera la métrica más importante.

Tasa de error de cruce (CER): el punto en el que la FRR y la FAR se encuentran. Cuanto más baja sea la CER, más eficiente y confiable será la tecnología.
Los errores se reducen con el tiempo al optimizar el sistema. Por lo general, esto se logra al ajustar la sensibilidad del sistema hasta que se alcanza la CER.

Rendimiento (velocidad): es el tiempo necesario para crear una plantilla para cada usuario y el tiempo necesario para autenticarse. Esta es una consideración importante para los puntos de acceso de altos volúmenes de tráfico, como los aeropuertos o las estaciones de tren.
Tasa de falla de registro (FER): son incidentes en los que no se puede crear y hacer coincidir una plantilla para un usuario durante el registro.
Costo/implementación: algunos tipos de escáner son más caros, mientras que otros no son fáciles de incorporar en los dispositivos móviles.
Los usuarios pueden considerarlo intrusivo y amenazante para la privacidad.
La tecnología puede ser discriminatoria o inaccesible para las personas con discapacidad. 
El reconocimiento de huellas digitales es el método de autenticación biométrica más extendido. La tecnología necesaria para escanear y registrar las huellas digitales es relativamente económica y el proceso es bastante sencillo. Por lo general, se implementa un sensor de huellas digitales como una pequeña celda capacitiva o cámara óptica capaz de detectar el patrón único de detalles que forman la huella digital. La tecnología tampoco es intrusiva y es relativamente fácil de usar, aunque la humedad o la suciedad pueden impedir las lecturas.

![[Pasted image 20241118134810.png]]


Description
El encabezado en la parte superior dice, ¡Genial! Ahora repite. El texto debajo del encabezado dice, mueve tu dedo ligeramente para agregar todas las diferentes partes de tu huella dactilar. Debajo del texto hay un sensor de huellas dactilares para registrar la huella.



Configuración del reconocimiento de huellas digitales en un teléfono inteligente AndroidTM. Android es una marca comercial de Google LLC.

El reconocimiento facial registra múltiples indicadores sobre el tamaño y la forma de la cara, como la distancia entre los ojos o el ancho y la longitud de la nariz. El escaneo suele utilizar cámaras o sensores ópticos e infrarrojos para frustrar los intentos de suplantación de identidad en los que se sustituye una cara real por una foto.

