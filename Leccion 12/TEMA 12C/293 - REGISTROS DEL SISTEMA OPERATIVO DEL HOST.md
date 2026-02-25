Un sistema operativo (OS) mantiene una variedad de registros para registrar eventos a medida que los usuarios y el software interactúan con el sistema. Los diferentes archivos de registro representan diferentes aspectos de la funcionalidad del sistema. Estos archivos están destinados a albergar eventos de la misma naturaleza general. Algunos archivos contienen eventos de diferentes fuentes de procesos; otros son utilizados por una sola fuente.

Los registros de seguridad específicos del sistema operativo graban los eventos de auditoría. Los eventos de auditoría generalmente se clasifican como exitoso/aceptado o fallido/denegado.

Los eventos de autenticación se registran cuando los usuarios intentan iniciar o cerrar sesión. También es probable que se genere un evento cuando un usuario intenta obtener privilegios especiales o administrativos.
Los eventos del sistema de archivos registran si se permitió o denegó el uso de permisos para leer o modificar un archivo. Como esto generaría una gran cantidad de datos si se habilitara para todos los objetos del sistema de archivos de forma predeterminada, la auditoría del sistema de archivos, generalmente, debe configurarse explícitamente.
Registros de Windows
Los tres archivos principales de registro de eventos de Windows son los siguientes:

Los eventos de la aplicación generados por los procesos de la aplicación, como cuando hay un bloqueo o cuando se instala o elimina una aplicación.
Eventos de auditoría de seguridad, como un inicio de sesión fallido o la denegación de acceso a un archivo.
Los eventos del sistema generados por los procesos y servicios del núcleo del sistema operativo, como cuando un servicio o controlador no se puede iniciar, cuando se cambia el tipo de inicio de un servicio o cuando la computadora se apaga.
Registros de Linux
El registro de Linux se puede implementar de manera diferente para cada distribución. Algunas distribuciones usan syslog para dirigir mensajes relacionados con un subsistema particular a un archivo de texto plano. Otras distribuciones usan Journald como un sistema de registro unificado con un formato de archivo binario, en lugar de texto sin formato. Los mensajes de Journald se leen utilizando el comando journalctl, pero se puede configurar para exportar algunos mensajes a archivos de texto a través de syslog.

Algunos de los archivos de registro principal son los siguientes:

/var/log/messages o /var/log/syslog almacenan todos los eventos generados por el sistema. Algunos de estos se copian a archivos de registro individuales.
/var/log/auth.log (Debian/Ubuntu) o /var/log/secure (RedHat/CentOS/Fedora) registran los intentos de inicio de sesión, el uso de privilegios sudo y otros datos de autenticación y autorización. Además, el registro de fallos rastrea específicamente los eventos de inicio de sesión fallidos. Algunas distribuciones utilizan archivos wtmp, utmp y btmp para usarlos con comandos como w, who y last a fin de identificar sesiones e inicios de sesión fallidos.      
El registro del administrador de paquetes (apt, yum o dnf, según la distribución) almacena información sobre qué software se ha instalado y actualizado.  

![[Pasted image 20250403090323.png]]

El registro de autenticación de Linux que muestra que el acceso remoto SSH está habilitado, fallaron los intentos de autenticación para el usuario raíz y el inicio de sesión fue exitoso para el usuario Lamp. 

Registros de macOS
macOS utiliza un sistema de registro unificado, al que se puede acceder a través de la aplicación gráfica de la consola o el comando de registro.  El comando log se puede usar con filtros para revisar los eventos relacionados con la seguridad, como el inicio de sesión (com.apple.login), las instalaciones de aplicaciones (com.apple.install) y las violaciones de las políticas del sistema (com.apple.syspolicy.exec).