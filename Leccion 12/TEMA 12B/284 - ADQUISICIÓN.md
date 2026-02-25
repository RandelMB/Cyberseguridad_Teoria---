La adquisición es el proceso de obtención de una copia forense limpia de los datos de un dispositivo incautado como evidencia. Si la computadora no es propiedad de la organización, existe la pregunta de si la búsqueda o incautación son legalmente válidas. Esto afecta a las políticas de traiga su propio dispositivo (BYOD). Por ejemplo, si un empleado es acusado de fraude, hay que verificar que el equipo y los datos del empleado se puedan incautar e investigar legalmente. Cualquier error puede hacer que la evidencia obtenida de la búsqueda sea inadmisible. 

La adquisición de datos también se complica por el hecho de que es más difícil capturar evidencia de una escena del crimen digital que de una física. Como se mencionó, si la computadora se apaga, algunas pruebas se perderán; por otro lado, cierta evidencia puede ser imposible de conseguir sino hasta que la computadora se apague. Además, la evidencia se puede perder dependiendo de si el sistema se apaga o se “congela” al desconectar la energía repentinamente.

La adquisición por lo general se realiza mediante el uso de una herramienta para crear una imagen a partir de los datos que se mantienen en el dispositivo de destino. Una imagen se puede adquirir desde un almacenamiento volátil o no volátil. El principio general es capturar la evidencia en el orden de volatilidad, de más volátil a menos volátil. La guía de buenas prácticas para la recopilación y el archivo de evidencia de la ISOC, publicada en tools.ietf.org/html/rfc3227, establece el siguiente orden general.

Registros de la unidad central de procesamiento (CPU) y de la memoria caché (incluida la caché de los controladores de disco, las unidades de procesamiento de gráficas [GPU], etc.).
Contenido de la memoria del sistema (RAM) no persistente, incluida la tabla de enrutamiento, la caché de ARP, la tabla de procesos y las estadísticas del kernel.
3.Datos en dispositivos de mass storage (almacenamiento masivo) persistentes (unidades de discos duros [HHD], unidades de estado sólido [SSD] y dispositivos de memoria):
Bloques de partición y sistema de archivos, espacio no asignado y espacio libre.
Cachés de memoria del sistema, como espacio de swap/memoria virtual y archivos de hibernación.
Cachés de archivos temporales, como la caché del navegador.
Archivos y directorios de usuario, aplicación y sistema operativo.
4.Registro remoto y monitoreo de datos.
5.Configuración física y topología de red.
6.Medios de archivo y documentos impresos.
El registro de Windows se almacena principalmente en el disco, pero hay claves, en particular HKLM\HARDWARE, que solo existen en la memoria. El contenido del registro se puede analizar a través de un volcado de memoria.