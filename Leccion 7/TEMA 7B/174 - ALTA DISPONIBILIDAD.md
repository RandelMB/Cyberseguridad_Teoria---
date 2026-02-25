


La alta disponibilidad (HA) es fundamental en la infraestructura de TI, ya que garantiza que los sistemas permanezcan operativos y accesibles con un tiempo de inactividad mínimo. Implica diseñar e implementar componentes de hardware, servidores, redes, centros de datos y ubicaciones físicas para la tolerancia a fallas y la redundancia. En una configuración de alta disponibilidad, los componentes de hardware redundantes, como fuentes de alimentación, discos duros e interfaces de red, reducen el riesgo de falla al permitir que el sistema continúe funcionando si falla un componente. Por lo general, los servidores se implementan en clústeres o configuraciones emparejadas, lo que permite la conmutación automática por error de un servidor primario a un servidor secundario en caso de que surja un problema. 

Los componentes de red, como los switches, los enrutadores y los balanceadores de carga, también se diseñaron teniendo en cuenta la redundancia para mantener una conectividad perfecta. Como columna vertebral de la infraestructura de alta disponibilidad, los centros de datos emplean fuentes de energía redundantes, sistemas de refrigeración y generadores de respaldo para garantizar un funcionamiento continuo. 

Además, las organizaciones pueden implementar centros de datos en ubicaciones geográficamente diversas para mitigar el impacto de desastres naturales u otros eventos a gran escala. De este modo, mejoran aún más la alta disponibilidad y las capacidades de recuperación ante desastres.

El concepto de “disponibilidad” se puede medir durante un período definido, como un año. La disponibilidad se puede medir como un valor de tiempo de actividad o un porcentaje. También se puede calcular como el tiempo o porcentaje en que un sistema no está disponible (tiempo de inactividad). La métrica de tiempo de inactividad máximo tolerable (MTD) expresa el requisito de disponibilidad para una función empresarial concreta. La alta disponibilidad suele describirse en términos generales como 24 x 7 (24 horas al día, 7 días a la semana) o 24 x 365 (24 horas al día, 365 días al año). Para un sistema crítico, la disponibilidad se describe mediante el término “nueves”, como dos nueves (99 %) hasta cinco o seis nueves (99,9999 %). El siguiente gráfico identifica la cantidad máxima de tiempos de inactividad que representa cada uno de los “nueves”:

![[Pasted image 20250217110935.png]]


El tiempo de inactividad se calcula a partir de la suma de los intervalos de servicio programados más las interrupciones no planificadas durante el período.

	La disponibilidad del sistema puede referirse a un proceso general, pero también a la disponibilidad a nivel de un servidor o componente individual.

Escalabilidad y elasticidad
La alta disponibilidad también significa que un sistema puede hacer frente a un rápido crecimiento de la demanda. Estas propiedades se conocen como escalabilidad y elasticidad. La escalabilidad es la capacidad de aumentar los recursos para satisfacer la demanda dentro de ratios de costos similares. Esto significa que, si la demanda de servicio se duplica, los costos no superan el doble. Existen dos tipos de escalabilidad: 

- El escalado horizontal es agregar más recursos en paralelo con los recursos existentes.
- El escalado vertical es aumentar la potencia de los recursos existentes.

La elasticidad se refiere a la capacidad del sistema para abordar estos cambios a demanda en tiempo real. Un sistema con alta elasticidad no experimentará una pérdida de servicio o rendimiento si la demanda aumenta de manera repentina y rápida.

Tolerancia a fallas y redundancia 
Se dice que un sistema que puede experimentar fallas y continuar brindando el mismo (o casi el mismo) nivel de servicio es tolerante a las fallas. La tolerancia a fallas suele conseguirse mediante la redundancia de componentes críticos y puntos únicos de falla. Un componente redundante es aquel que no es fundamental para el funcionamiento normal de un sistema, pero que permite que el sistema se recupere de la falla de otro componente.

Consideraciones del sitio
Los entornos empresariales a menudo proporcionan resiliencia a nivel del sitio. Un sitio alternativo de procesamiento o recuperación es una ubicación que puede proporcionar el mismo nivel de servicio (o similar). Un sitio de procesamiento alternativo puede estar siempre disponible y en uso, mientras que un sitio de recuperación puede tardar más en configurarse o utilizarse solo en caso de emergencia.

Las operaciones están diseñadas para la conmutación por error al nuevo sitio hasta que el sitio anterior pueda volver a estar en línea. El failover (conmutación por error) es una técnica que garantiza que un componente, dispositivo, aplicación o sitio redundante pueda asumir de manera rápida y eficiente la funcionalidad de un activo que ha fallado. Por ejemplo, los balanceadores de carga aportan un failover (conmutación por error) en caso de que uno o más servidores o sitios detrás del balanceador se caigan o tarden demasiado en responder. Una vez que el balanceador de carga lo detecte, redirigirá el tráfico entrante a un servidor o sitio de procesamiento alternativo. Por lo tanto, los servidores redundantes que funcionan con el balanceador de carga garantizan que no haya interrupciones en el servicio o que sea mínima.

La resiliencia del sitio se describe como caliente, templado o frío:

- Un hot site (sitio caliente) puede conmutar por error casi de inmediato. Por lo general, significa que el sitio es propiedad de la empresa y está listo para implementarse. Por ejemplo, un sitio caliente podría consistir en un edificio con equipos informáticos operativos actualizados con un conjunto de datos en tiempo real.
- Un warm site (sitio templado) podría ser similar, pero con el requisito de que se debe cargar el conjunto de datos más reciente.
- Un cold site (sitio frío) tarda más tiempo en configurarse. Un cold site (sitio frío) puede ser un edificio vacío con un contrato de arrendamiento vigente que permita instalar cualquier equipo que se requiera cuando sea necesario.
Proporcionar redundancia a esta escala suele ser muy complicado y costoso. Otro problema es que la creación de sitios y datos duplicados también duplica (o más) la complejidad de garantizar la seguridad de los recursos. Se deben aplicar los mismos procedimientos de seguridad a los sitios redundantes, sistemas de repuesto y datos de respaldo que se aplican a la copia principal.

Geographic dispersion (Dispersión geográfica) se refiere a la distribución de sitios de recuperación en diferentes ubicaciones geográficas para fines de recuperación ante desastres (DR). El concepto tiene como objetivo garantizar que los sitios de recuperación estén ubicados lo suficientemente separados como para minimizar el impacto de los desastres regionales, como los desastres naturales o los incidentes localizados. Al mantener los sitios de recuperación estratégicamente dispersos, las organizaciones pueden garantizar la resiliencia de sus estrategias de recuperación y reducir el riesgo de que un solo evento catastrófico afecte a todas las operaciones comerciales.

La nube como recuperación ante desastres (DR)
Varios factores impulsan a las organizaciones a utilizar servicios en la nube para la redundancia de sitios o centros de datos. La eficiencia en los costos desempeña un papel muy importante, ya que los proveedores de servicios en la nube ofrecen opciones de redundancia y respaldo más asequibles debido a sus economías de escala. 

	“Economías de escala” es un concepto que se refiere a las ventajas de costos que pueden lograr las empresas cuando aumentan la producción y el rendimiento. En esencia, cuanto más produce una empresa, más económico resulta entregar dichos productos.

La escalabilidad de los servicios en la nube permite a las empresas incorporar capacidades redundantes sin la necesidad de aprovisionar excesivamente los recursos. Por ejemplo, la diversidad geográfica proporcionada por los proveedores de servicios en la nube ayuda a proteger contra interrupciones o desastres regionales. La incorporación de este tipo de redundancia para una organización privada tendría un costo prohibitivo e injustificado. 

Una implementación más rápida de capacidades con plataformas en la nube permite a las organizaciones configurar y desplegar sistemas redundantes de forma rápida, mucho más rápida de lo que se podría lograr al construir una infraestructura desde cero. 

La gestión simplificada es otro factor crítico, ya que los proveedores de servicios en la nube ofrecen herramientas y servicios que reducen la complejidad de la gestión de infraestructura redundante. Las mejoras en seguridad y cumplimiento normativo también son importantes, ya que los proveedores de servicios en la nube invierten considerablemente en estas áreas, lo que ayuda a las organizaciones a cumplir con los requerimientos regulatorios de protección de datos y redundancia. 

Prueba de redundancia y alta disponibilidad
Es fundamental probar las tecnologías de alta disponibilidad, balance de carga y failover (conmutación por error). Además, las pruebas están diseñadas para evaluar la capacidad de mantener la operatividad con cargas de trabajo pesadas, fallos de componentes o mantenimiento programado. 

- En las pruebas de carga se incorporan herramientas de software especializadas para validar el rendimiento de un sistema bajo cargas máximas o esperadas e identificar cuellos de botella o problemas de escalabilidad. 
- Las pruebas de failover (conmutación por error) se centran en la validación de los procesos de failover (conmutación por error) para garantizar una transición perfecta entre las infraestructuras primaria y secundaria. 
- Con las pruebas de los sistemas de monitoreo se validan la detección y respuesta efectivas ante fallas y problemas de rendimiento. 
Las prácticas de prueba sólidas permiten a las organizaciones garantizar que las tecnologías de alta disponibilidad, balance de carga y failover (conmutación por error) cumplan eficazmente su propósito de minimizar las interrupciones inesperadas y maximizar el rendimiento.