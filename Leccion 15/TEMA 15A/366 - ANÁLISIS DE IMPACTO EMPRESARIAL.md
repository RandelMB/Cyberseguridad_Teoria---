Identificación de sistemas críticos
Para respaldar la resiliencia de las funciones empresariales fundamentales y primarias de la misión, es crucial realizar una identificación de los sistemas críticos. Esto significa compilar un inventario de procesos empresariales y los activos que los respaldan. Los tipos de activos son los siguientes: 

Personas (empleados, visitantes y proveedores).
Los activos tangibles (edificios, muebles, equipos y maquinaria (planta), equipos de TIC, archivos de datos electrónicos y documentos en papel). 
Activos intangibles (ideas, reputación comercial, marca, etc.).
Procedimientos (cadenas de suministro, procedimientos críticos, procedimientos operativos estándar).
Para las funciones fundamentales de la misión, es importante reducir el número de dependencias entre los componentes. Las dependencias se identifican mediante la realización de un análisis de procesos empresariales (BPA) para cada función. El BPA debe identificar los siguientes factores: 

Entradas: las fuentes de información para realizar la función (incluido el impacto si se retrasan o están fuera de secuencia). 
Hardware: el servidor o centro de datos particular que realiza el procesamiento.
Personal y otros recursos que apoyan la función.
Producto: los datos o recursos producidos por la función.
Flujo del proceso: una descripción paso a paso de cómo se realiza la función.
El análisis de impacto empresarial (BIA) es un proceso que ayuda a las empresas a comprender los posibles efectos de las interrupciones en sus operaciones. Implica identificar y evaluar el impacto de varios escenarios de amenazas no planificadas por la empresa, como accidentes, emergencias y desastres. Al realizar un análisis de impacto empresarial, las empresas pueden crear de manera proactiva estrategias de recuperación para minimizar el impacto de las interrupciones y garantizar la resiliencia operativa.

Por ejemplo, si un ataque de denegación de servicio distribuido (DDoS) suspende un portal de comercio electrónico durante cinco horas, el análisis del impacto en el negocio podrá cuantificar las pérdidas por los pedidos no realizados y los clientes que se trasladan definitivamente a otros proveedores, basándose en datos históricos. La probabilidad de que se produzca un ataque de DoS puede evaluarse de forma anualizada para determinar el impacto anualizado, en términos de costos. Esta información se utiliza para evaluar si un control de seguridad, como el balanceador de carga o la mitigación de DDoS gestionada, amerita la inversión.

Funciones fundamentales de la misión
Una función esencial de la misión (MEF) es una que no se puede aplazar. Esto significa que la organización debe ser capaz de realizar la función de la manera más continua posible, y si hay alguna interrupción del servicio, las funciones esenciales de la misión deben ser restauradas en primer lugar.

Las funciones que actúan como soporte para la empresa o una MEF, pero que no son críticas en sí mismas, se denominan funciones empresariales primarias (PBF).

El análisis de las funciones esenciales de la misión por lo general se rige por cuatro métricas principales:

El tiempo de inactividad máximo tolerable (MTD) es el período más largo durante el que puede ocurrir una interrupción de la función empresarial sin causar una falla comercial irrecuperable. Cada proceso empresarial puede tener su propio MTD, como un rango de minutos a horas para funciones críticas, 24 horas para funciones urgentes, siete días para funciones normales, etc. Los MTD varían según la empresa y el evento. Cada función puede ser compatible con varios sistemas y activos. El MTD establece el límite superior del tiempo de recuperación que tienen los propietarios de sistemas y activos para reanudar las operaciones. Por ejemplo, una organización especializada en equipos médicos puede existir sin que entren suministros de fabricación durante tres meses porque acumuló un inventario considerable. Después de tres meses, la organización no tendrá suficientes suministros y es posible que no pueda fabricar productos adicionales, lo que conducirá al fracaso. En este caso, el MTD es de tres meses.
El objetivo de tiempo de recuperación (RTO) es el período tras una catástrofe en el que un sistema informático individual puede permanecer sin conexión. Esto representa la cantidad de tiempo que toma identificar que hay un problema y luego realizar la recuperación (por ejemplo, restauración desde la copia de seguridad o cambiar a un sistema alternativo).
El tiempo de recuperación del trabajo (WRT). Tras la recuperación de los sistemas, puede haber un trabajo adicional para reintegrar los diferentes sistemas, probar la funcionalidad general e informar a los usuarios del sistema sobre cualquier cambio o práctica de trabajo diferente para que la función empresarial vuelva a ser totalmente compatible.
El RTO+WRT no debe superar el MTD.

El objetivo de punto de recuperación (RPO) es la cantidad de pérdida de datos que puede soportar un sistema, medida en el tiempo. Es decir, si una base de datos es destruida por un virus, un RPO de 24 horas significa que los datos pueden recuperarse (a partir de una copia de seguridad) hasta un punto no superior a 24 horas antes de que la base de datos fuera infectada. El RPO se determina identificando la pérdida de datos máxima aceptable que una organización puede tolerar en caso de un desastre o falla del sistema y se establece considerando factores como los requisitos comerciales, la criticidad de los datos y las obligaciones regulatorias o contractuales. El cálculo de RPO afecta directamente la frecuencia de las copias de seguridad de los datos, los requisitos de replicación de datos, la selección del sitio de recuperación y las tecnologías que admiten la conmutación por error y la alta disponibilidad.

![[Pasted image 20250407073103.png]]

Description
La flecha hacia la derecha indica tiempo. El tiempo de inactividad máximo tolerable (M T D) es el periodo de tiempo más largo tras una catástrofe. El objetivo de tiempo de recuperación (R T O) sigue a la catástrofe y le sigue el tiempo de recuperación del trabajo (W R T).



Métricas que rigen las funciones fundamentales de la misión. (Imágenes © 123RF.com.)

Por ejemplo, una base de datos de gestión de relaciones con los clientes podría soportar la pérdida de datos de unas pocas horas o días porque los empleados por lo general pueden recordar con quién se comunicaron y las conversaciones que tuvieron durante este período de tiempo. Por el contrario, el procesamiento de pedidos es más sensible al tiempo, ya que las pérdidas  de datos representarán pedidos perdidos y puede ser imposible recuperarlos o los procesosrelacionados iniciados por los sistemas de procesamiento de pedidos, como los datos contables y de cumplimiento.

El MTD y el RPO ayudan a determinar qué funciones comerciales son críticas y también a especificar las contramedidas de riesgo apropiadas. Por ejemplo, si su RPO se mide en días, entonces un simple sistema de copia de seguridad en cinta debería ser suficiente; si el RPO es cero o se mide en minutos o segundos, se requerirá una solución de copia de seguridad y redundancia de clúster de servidor más costosa.

El tiempo medio de reparación (MTTR) y tiempo medio entre fallas (MTBF) son indicadores clave de rendimiento (KPI) utilizados para medir la confiabilidad y eficiencia de los sistemas, procesos y equipos. Ambas métricas son importantes para los procesos de gestión de riesgos, ya que proporcionan información medible sobre los riesgos potenciales y respaldan las estrategias de mitigación de riesgos. El MTTR y el MTBF guían las decisiones con respecto al diseño del sistema, las prácticas de mantenimiento y los requisitos de redundancia o conmutación por error.  

El tiempo medio entre fallas (MTBF)r representa la duración esperada de un producto. El cálculo del MTBF es el tiempo total de funcionamiento dividido por el número de fallas. Por ejemplo, si tiene 10 dispositivos que funcionan durante 50 horas y dos de ellos fallan, el MTBF es de 250 horas/falla (10*50)/2.
El tiempo medio de reparación (MTTR) es una medición del tiempo que se tarda en corregir una falla para que el sistema vuelva a funcionar plenamente. También puede describirse como tiempo medio de sustitución o recuperación. El MTTR se calcula como el número total de horas de mantenimiento no planificado dividido por el número de incidentes de fallas. Este valor medio puede utilizarse para estimar si un objetivo de tiempo de recuperación (RTO) es alcanzable.
Un MTTR más bajo indica una restauración más rápida de la funcionalidad, lo que reduce el tiempo de inactividad y las posibles interrupciones de las operaciones. Esta información ayuda a asignar recursos, priorizar las actividades de mantenimiento y optimizar los procesos de reparación. El MTBF identifica el tiempo promedio entre fallas del sistema o del equipo. Un MTBF más alto sugiere una mayor confiabilidad e intervalos más largos entre fallas, lo que puede afectar la programación de mantenimiento, la gestión de piezas de repuesto y el desempeño general del sistema. Con base en los datos del MTBF, las organizaciones pueden tomar decisiones con respecto a las estrategias de mantenimiento, el reemplazo de equipos y las inversiones para mejorar la confiabilidad.