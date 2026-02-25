Cualquier tipo de método de acceso a un host que eluda el método de autenticación habitual y otorgue al usuario remoto el control administrativo se puede denominar como puerta trasera. Un troyano de acceso remoto (RAT) es un malware de puerta trasera que imita la funcionalidad de los programas legítimos de control remoto, pero está diseñado específicamente para operar de forma encubierta. Una vez instalado el RAT, permite al actor de amenazas acceder al host, cargar archivos e instalar software, o utilizar técnicas LOTL para realizar compromisos adicionales. 

En este contexto, RAT también puede referirse a “herramienta de administración remota”.    Un host que está bajo control malicioso a veces se describe como un zombie.

Un host comprometido puede instalarse con uno o más bots. Un bot es una secuencia de comando o herramienta automatizada que realiza alguna actividad maliciosa. Un grupo de bots que están todos bajo el control de la misma instancia de malware pueden ser manipulados como una red de robots por el programa pastor (herder).  Una red de bots (botnet) puede ser utilizada con muchos fines maliciosos, incluyendo desencadenar ataques distribuidos de denegación de servicio (DDoS), lanzar campañas de correo no deseado (spam) o realizar criptominería.

![[Pasted image 20250404073239.png]]
Description
La pantalla muestra un botón de expansión llamado conexión seleccionado para listar hipervínculos para escáner de IP, obtener información de PC, obtener información del hogar, opciones de servidor (seleccionado) y notificación de IP. Los botones a la derecha son cambiar puerto, establecer puerto predeterminado, establecer contraseña, eliminar contraseña, desconectar víctima, reiniciar servidor, eliminar servidor, cerrar servidor, actualizar servidor desde archivo local y actualizar servidor desde archivo URL. Los otros botones de expansión en la parte inferior izquierda son claves o mensajes, avanzado, misceláneos, administrador de diversión, diversión extra y opciones locales.



RAT SubSeven. (Captura de pantalla utilizada con el permiso de Wikimedia Commons por CCAS4.0 International).

Tanto si se utiliza una puerta trasera como mecanismo de intrusión independiente o para administrar bots, el actor de la amenaza debe establecer una conexión desde el host comprometido hacia un host o red de comando y control (C2 o C&C). Esta conexión de red suele ser la mejor manera de identificar la presencia de un RAT, puerta trasera o bot. Existen muchos medios para implementar una red de C&C como un canal encubierto para evadir la detección y el filtrado. Históricamente, el protocolo de Internet Relay Chat (IRC) era popular. Los métodos modernos son más propensos a utilizar secuencias de comandos incrustadas en el tráfico de HTTPS o DNS. 

Las puertas traseras pueden crearse de otras maneras que no sean mediante la infección por malware. Los programadores pueden crear puertas traseras en aplicaciones de software para pruebas y desarrollo que posteriormente no se eliminan cuando se implementa la aplicación. Las puertas traseras también se crean por una mala configuración de software o hardware que permite el acceso a usuarios no autorizados. 