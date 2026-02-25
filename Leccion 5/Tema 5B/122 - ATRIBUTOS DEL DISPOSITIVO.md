

Los atributos determinan la forma precisa en que se puede colocar un dispositivo dentro de la topología de la red.

### Activo frente a pasivo

Un control de seguridad pasivo es aquel que no requiere ningún tipo de configuración de cliente o agente, ni transferencia de datos de host para funcionar. Por ejemplo, el tráfico de red puede ser dirigido o copiado a un sensor y escaneado por un motor de análisis. Este control es completamente pasivo. Los anfitriones de la red no sabrían que está funcionando. El control no tiene una interfaz direccionable.

Un control de seguridad activo que realiza el análisis debe estar configurado con credenciales y permisos de acceso e intercambiar datos con los hosts de destino. Un control activo que realiza el filtrado requiere que los hosts estén configurados explícitamente para usar el control. Esto puede significar la instalación de software de agente en el host o la configuración de la red para usar el control como puerta de enlace.

### Inline (insertado) frente a Tap/Monitor

Un dispositivo en el que la implementación se hace inline, se convierte en parte de la ruta del cable. No se requieren cambios en la IP ni en la topología de enrutamiento. Las interfaces del dispositivo no están configuradas con direcciones MAC o IP.

Como ejemplo de las opciones de implementación inline versus las monitoreadas, los controles que detectan el tráfico de red se pueden implementar a través de un sensor conectado a un switch o a través de un TAP conectado a un cable de red:

- Analizador de puerto conmutado (SPAN)/espejo de puerto: significa que el sensor está conectado a un puerto especialmente configurado en el switch que recibe copias de las tramas dirigidas a los puertos de acceso nominados (o a todos los demás puertos). Este método no es completamente fiable. Las tramas con errores no se reflejarán y las tramas pueden perderse si hay mucha carga.
- Punto de acceso de prueba (TAP): se trata de una caja con puertos para el cableado de red entrante y saliente, y un inductor o divisor óptico que copia físicamente la señal del cableado a un puerto del monitor. Hay tipos de cableado de cobre y de fibra óptica. A diferencia de un SPAN, no se toman decisiones lógicas, por lo que el puerto de monitorización recibe todas las tramas —corruptas, malformadas o no— y la copia no se ve afectada por la carga.

![[Pasted image 20241202172337.png]]


Un dispositivo TAP se coloca inline con la ruta del cable, mientras que un puerto espejo utiliza el switch para copiar fotogramas a un sistema de detección. El enrutador/cortafuegos es un control activo, ya que los dispositivos cliente deben estar configurados para usarlo para el acceso a internet. Los puertos de TAP y espejo son controles pasivos. Son completamente transparentes para los hosts del servidor y del cliente.

## Apertura ante fallas (fail-open) frente a cierre ante fallas (fail-closed)

Un dispositivo de seguridad podría entrar en un estado de falla por varias razones. Podría haber una falla de energía o hardware, una violación de la política irreconciliable o un error de configuración. La falla del hardware puede ser causada por sobrecargas de energía, sobrecalentamiento y daños físicos. La falla del software puede ocurrir debido a errores, vulnerabilidades de seguridad y problemas de compatibilidad. Los problemas de configuración pueden ser causados por errores humanos como la falta de atención, la fatiga o la falta de capacitación. Finalmente, los dispositivos o sitios pueden verse afectados por desastres naturales como inundaciones, huracanes y terremotos.

Cuando falla, un dispositivo puede diseñarse o configurarse para abrirse o cerrarse ante la falla:

- Apertura automática ante fallas significa que el acceso a la red o al host se conserva, si es posible. Este modo prioriza la disponibilidad sobre la confidencialidad y la integridad. El riesgo de un control de apertura automática ante falla es que un actor de amenaza podría diseñar un estado de falla para derrotar el control.
- Cierre automático ante fallas significa que el acceso está bloqueado o que el sistema entra en el estado más seguro disponible, independientemente de la falla que haya ocurrido. Este modo prioriza la confidencialidad y la integridad sobre la disponibilidad. El riesgo de un control cerrado por falla es el tiempo de inactividad del sistema.
Puede o no ser posible configurar el modo de falla. Por ejemplo, en un dispositivo de seguridad inline con una falla de alimentación se activará un cierre automático ante la falla, a menos que haya una ruta de red alternativa. Algunos dispositivos diseñados para instalarse inline tienen una ruta de cable de respaldo que permitirá una operación de apertura automática.