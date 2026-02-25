Además de los eventos registrados por el sistema operativo, también es probable que los hosts generen registros de la aplicación, incluidos los registros del software de seguridad basado en host.

Registros de aplicaciones
Un archivo de registro de la aplicación es simplemente aquel que es administrado por una aplicación en lugar del sistema operativo. La aplicación puede usar el visor de eventos o syslog para escribir datos de eventos con un formato estándar, o puede escribir archivos de registro en sus propios directorios de aplicaciones en cualquier formato que el desarrollador haya seleccionado.

En el visor de eventos de Windows, hay un registro de aplicación específico, en el que cualquier cuenta autenticada puede escribir. También hay registros de aplicaciones y servicios personalizados separados, administrados por procesos específicos. El desarrollador de la aplicación elige qué registro usar o si desea implementar un sistema de registros sin usar el visor de eventos. Revise la documentación del producto para averiguar dónde se registran los eventos de una aplicación de software en particular.

Registros de puntos de conexión (endpoints) 
Es probable que un registro de punto de conexión se refiera a eventos monitoreados por el software de seguridad que se ejecuta en el host, en lugar de por el propio sistema operativo. Puede incluir cortafuegos basados en host y detección de intrusiones, escáneres de vulnerabilidades y suites de protección antivirus/antimalware. Las suites que integran estas funciones en un solo producto a menudo se conocen como plataforma de protección de puntos de conexión (EPP), detección y respuesta mejoradas (EDR) o detección y respuesta extendidas (XDR). Estas herramientas de seguridad pueden integrarse directamente con un SIEM utilizando un software basado en agentes. 

El resumen de los eventos de los registros de protección del punto de conexión puede mostrar los niveles generales de amenaza, como la cantidad de malware detectado, la cantidad de eventos de detección de intrusiones en el host y la cantidad de hosts a los que les faltan parches. Un análisis detallado de los eventos de detección puede ayudar a atribuir eventos de intrusión a un actor específico y a desarrollar inteligencia de amenazas de tácticas, técnicas y procedimientos.


![[Pasted image 20250403090408.png]]

Detección de registros de Windows Defender y cuarentena de malware en el visor de eventos. (Captura de pantalla utilizada con el permiso de Microsoft).

Escaneos de vulnerabilidades
Si bien, por lo general, hay un informe resumido, se puede configurar un escáner de vulnerabilidades para registrar cada vulnerabilidad detectada en un SIEM. Las vulnerabilidades pueden incluir parches faltantes e incumplimiento de una configuración de seguridad de línea base. El SIEM podrá recuperar una lista de estos registros para cada host. Dependiendo de la fecha del último escaneo, puede ser difícil la identificación a partir de los datos de registro que se han corregido, pero en términos generales, proporcionará información útil sobre si un host está configurado correctamente.