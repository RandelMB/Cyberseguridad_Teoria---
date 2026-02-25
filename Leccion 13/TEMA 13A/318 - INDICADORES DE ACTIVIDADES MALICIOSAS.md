Dada la variedad de tipos de malware, existen muchos indicadores potenciales de actividad maliciosa. Algunos tipos de malware muestran cambios obvios, como ajustar la configuración del navegador o mostrar avisos de rescate. Si el malware está diseñado para operar de forma encubierta, los indicadores pueden requerir un análisis detallado del comportamiento del proceso, del sistema de archivos y de la red.

Ejecución sandbox
Si la protección del punto final no detecta la actividad maliciosa, analice el código o host sospechoso en un entorno aislado o de pruebas (sandboxed). Un sandbox es un sistema configurado para estar completamente aislado de la red de producción para que el malware no pueda “escapar”. El sandbox estará diseñado para registrar cambios en el sistema de archivos y en el registro, así como la actividad de red. Del mismo modo, un “sheep dip” es un host aislado que se utiliza para probar software nuevos y medios extraíbles en busca de indicadores de malware antes de autorizar su uso en la red de producción.

Consumo de recursos
Un consumo de recursos anormal se puede detectar mediante un monitor de rendimiento. Los indicadores como el uso excesivo y continuo de la CPU, las fugas de memoria, la actividad de lectura/escritura del disco, el uso del espacio en disco y el consumo del ancho de banda de la red pueden ser signos de malware. El consumo de recursos podría ser una razón para investigar un sistema en lugar de ser una prueba definitiva de actividad maliciosa. Estos síntomas también pueden ser causados por muchos otros problemas de rendimiento y estabilidad del sistema. Además, solo el malware mal escrito o el que realiza operaciones intensivas muestra este comportamiento. Por ejemplo, es característico de los ataques de denegación de servicio distribuido (DDoS) de redes de bots, del criptosecuestro y del ransomware criptográfico el secuestrar los recursos del equipo.

![[Pasted image 20250404073448.png]]

El monitor de rendimiento de Windows que registra la utilización de la CPU en una PC cliente. La actividad anómala es difícil de diagnosticar, pero este gráfico muestra que la carga raramente baja del 50 %. Una carga continua no es típica de un sistema cliente y podría ser un indicador de malware de criptosecuestro. (Captura de pantalla utilizada con el permiso de Microsoft).

Sistema de archivos

El código malicioso puede no ejecutarse desde una imagen de proceso guardada en un disco local, pero es probable que interactúe con el sistema de archivos y el registro, revelando su presencia por comportamiento. El sistema de archivos de un equipo almacena una gran cantidad de metadatos útiles sobre cuándo se crearon, accedieron o modificaron los archivos. Analizar estos metadatos y buscar archivos temporales sospechosos puede ayudar a establecer una cronología de eventos para un incidente que dejó rastros en un host y sus archivos.

Los intentos de acceder a datos valiosos pueden ser revelados por indicadores de contenido bloqueado. Cuando los archivos están simplemente protegidos por listas de control de acceso (ACL), si la auditoría está configurada, se registrará un mensaje de acceso denegado si una cuenta de usuario intenta leer o modificar un archivo para el que no tiene permiso de acceso. La información también puede estar protegida por un sistema de prevención de pérdida de datos (DLP), que también registrará los eventos de contenido bloqueado.

Inaccesibilidad de los recursos
La inaccesibilidad de los recursos significa que una red, un host, un archivo o una base de datos no está disponible. Por lo general, se trata de un indicador de un ataque por denegación de servicio (DoS). Es posible que las puertas de enlace de host y de red no estén disponibles debido al consumo excesivo de recursos. Un ataque a la red a menudo creará una gran cantidad de conexiones. Los recursos de datos pueden estar sujetos a un ataque de ransomware. Además, el malware podría desactivar las utilidades de escaneo y monitoreo para evadir la detección.

Vulneración de la cuenta
Un actor de amenaza a menudo intentará explotar una cuenta existente para lograr sus objetivos. Los siguientes indicadores pueden revelar un comportamiento sospechoso de la cuenta:

Bloqueo de la cuenta: el sistema impidió el acceso a la cuenta debido a que se realizaron demasiados intentos de autenticación fallidos. El bloqueo también podría significar que la contraseña del usuario ya no funciona porque el actor de amenazas la cambió.
Uso concurrente de sesiones: esto indica que el actor de amenazas obtuvo las credenciales de la cuenta e inició sesión en otra estación de trabajo o a través de una conexión de acceso remoto.
Viaje imposible: indica que el actor de la amenaza está intentando utilizar el acceso remoto para iniciar sesión en una cuenta desde una ubicación geográfica a la que físicamente no habrían podido desplazarse desde su última sesión.
Registro de logs
Un actor de amenaza a menudo intentará cubrir sus huellas eliminando los indicadores de los archivos de registro:

Pérdida de registros:  podría significar que el archivo de registro se eliminó. Como esto es fácil de detectar, un actor de amenazas más sofisticado eliminará las entradas de registro. Esto podría estar indicado por brechas inusuales entre los tiempos de entrada en los registros. El tipo de ataque más sofisticado falsificará las entradas del registro para ocultar la actividad maliciosa.
Registro fuera de ciclo: el actor de amenazas también puede manipular la hora del sistema o cambiar las marcas de tiempo de las entradas del registro como un medio para ocultar la actividad.