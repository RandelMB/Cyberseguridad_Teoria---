Luego de que el proceso de detección informa sobre uno o más indicadores, en el proceso de análisis, el primer respondedor investiga los datos para determinar si se identificó un incidente genuino y qué nivel de prioridad se le debe asignar. Por el contrario, el informe podría clasificarse como falso positivo y descartarse. La clasificación de un evento incidente verdadero positivo a menudo se basa en la correlación de múltiples indicadores. Para un evento complejo o de alto impacto, el análisis se podría elevar a los miembros sénior del equipo CIRT.

Cuando se verifica que un incidente es un verdadero positivo, el siguiente objetivo es identificar el tipo de incidente y los datos o recursos afectados. Esto establece la categoría del incidente y su impacto, y permite la asignación de un nivel de prioridad. 

Impacto
Varios factores afectan el proceso de determinación del impacto:

Integridad de los datos: el factor más importante para priorizar los incidentes suele ser el valor de los datos en riesgo.
Tiempo de inactividad: se refiere al grado en que un incidente interrumpe los procesos del negocio, otro factor muy importante.   Un incidente puede degradar (reducir el rendimiento) o interrumpir (detener por completo) la disponibilidad de un activo, sistema o proceso del negocio. 
Económico/publicitario: tanto la integridad de los datos como el tiempo de inactividad tienen efectos económicos importantes a corto y largo plazo. Los costos a corto plazo implican la respuesta a incidentes y la pérdida de oportunidades de negocios. Los costos económicos a largo plazo pueden implicar un daño a la reputación y afectar la posición en el mercado.
Alcance: (en términos generales, el número de sistemas afectados) no es un indicador directo de la prioridad. Varios sistemas podrían estar infectados con un tipo de programa malicioso (malware) que degrada el rendimiento, pero no representa un riesgo de vulneración de datos. Incluso podría tratarse de un ataque de enmascaramiento, ya que el adversario busca comprometer los datos de un único servidor de base de datos que almacena información altamente confidencial.
Tiempo de detección: las investigaciones demostraron que más de la mitad de las filtraciones de datos no se detectan durante semanas o meses luego de que ocurre la intrusión, mientras que en una intrusión exitosa, los datos generalmente se filtran en cuestión de minutos. Los sistemas utilizados para buscar intrusiones deben ser exhaustivos y la respuesta a la detección debe ser rápida.
Tiempo de recuperación: para algunos incidentes se requiere  una remediación prolongada, ya que los cambios requeridos en el sistema son complejos de implementar. Este período de recuperación prolongado debería desencadenar un mayor estado de alerta ante ataques nuevos o continuos.
Categoría
Las categorías y definiciones de incidentes garantizan que todos los miembros del equipo de respuesta y otro personal de la organización tengan una comprensión compartida del significado de los términos, conceptos y descripciones. 

El análisis efectivo de incidentes depende de la inteligencia de las amenazas. Esta investigación proporciona información sobre las tácticas, técnicas y procedimientos (TTP) de los adversarios. Los conocimientos de la investigación de amenazas se pueden utilizar para desarrollar herramientas y manuales específicos para abordar diferentes escenarios de eventos. Una herramienta clave para la investigación de amenazas es el marco utilizado para describir las etapas de un ataque.   Estas etapas suelen denominarse cyber kill chain (cadena de eliminación de la seguridad cibernética), término que proviene del influyente informe técnico “Defensa de redes informáticas impulsado por inteligencia”, encargado por Lockheed Martin (lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/LM-White-Paper-Intel-Driven-Defense.pdf).

![[Pasted image 20250403075226.png]]

Description
Las siete etapas de la cadena letal son las siguientes: reconocimiento, militarización, entrega, explotación, instalación, mando y control (C2), y acciones sobre los objetivos.

Etapas de la cadena de eliminación.

Manuales de estrategias (playbooks)

El CIRT debe desarrollar perfiles o situaciones de incidentes típicos, como ataques de denegación de servicio (DDoS), brotes de virus/gusanos, exfiltración de datos por parte de un adversario externo, modificación de datos por parte de un adversario interno, entre otros.  Esto orienta a los investigadores para determinar las prioridades y los planes de remediación.

Un manual (playbook) es un procedimiento operativo estándar (SOP) basado en datos para ayudar a los analistas a detectar y responder a escenarios específicos de amenazas cibernéticas.  El manual comienza con un informe de un panel de alertas. Luego guía al analista a través de los pasos de análisis, contención, erradicación, recuperación y lecciones aprendidas que deben seguirse.