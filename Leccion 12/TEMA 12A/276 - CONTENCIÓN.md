Luego de la detección y el análisis, la base de datos de gestión de incidentes debe contar con un registro de los indicadores del evento, la naturaleza del incidente, su impacto y el investigador responsable de la gestión del caso. La siguiente fase de la gestión de incidentes es determinar una respuesta apropiada.

Dado que los incidentes abarcan una amplia gama de escenarios, tecnologías, motivaciones y grados de gravedad, no existe un enfoque estándar para la contención o el aislamiento de incidentes. Algunos de los muchos problemas complejos a los que se enfrenta el CIRT se detallan a continuación:

¿Qué daños o robos ya ocurrieron? ¿Cuánto más podría infligirse y en qué marco de tiempo (control de pérdidas)?
¿Qué contramedidas están disponibles? ¿Cuáles son sus costos e implicaciones?
¿Qué acciones podrían alertar al actor de amenaza de que se detectó el ataque? ¿Qué evidencia del ataque deben recopilarse y conservarse?
¿Qué notificaciones o informes se requieren en esta etapa del incidente?
Las técnicas de contención se pueden clasificar como basadas en el aislamiento o en la segmentación.

Contención basada en aislamiento 
El aislamiento implica eliminar un componente afectado del entorno más amplio del que forme parte. Esto puede ser cualquier cosa, desde eliminar un servidor de la red luego de que haya sido objeto de un ataque de denegación de servicio hasta colocar una aplicación en un entorno aislado fuera de los entornos de host en los que normalmente se ejecuta. El aislamiento elimina cualquier interfaz entre el sistema afectado y la red de producción o Internet.

Una opción sencilla es desconectar el host de la red mediante la desconexión del cable de red (creando una brecha de aire) o desactivando el puerto del switch. Esta es la opción menos cautelosa y reducirá las oportunidades para analizar el ataque o el malware. 

Si un grupo de hosts se ve afectado, se podría utilizar la infraestructura de enrutamiento para aislar una o más redes de área local virtuales (VLAN) infectadas en un agujero negro (sinkhole) al que no se puede acceder desde el resto de la red. Otra posibilidad es usar cortafuegos u otros filtros de seguridad para evitar que los hosts infectados se comuniquen.

Por último, el aislamiento también puede referirse a la desactivación de una cuenta de usuario o de un servicio de aplicación. La desactivación temporal de las cuentas de red de los usuarios puede resultar útil para contener daños si se detecta un intruso dentro de la red. Sin privilegios para acceder a los recursos, un intruso no podrá causar más daño ni robar más información de la organización. Las aplicaciones que sospeche que pueden ser el vector de un ataque pueden ser mucho menos efectivas para el atacante si se impide que la aplicación se ejecute en la mayoría de los hosts.

Contención basada en segmentación
La contención basada en la segmentación es un medio para lograr el aislamiento de un host o grupo de hosts utilizando tecnologías y arquitectura de red. La segmentación utiliza VLAN, enrutamiento/subredes y listas de control de acceso (ACL) de cortafuego para evitar que un host o grupo de hosts se comunique fuera del segmento protegido. En lugar de aislar completamente los hosts, puede configurar el segmento protegido como un agujero negro o red trampa y permitir que el atacante continúe recibiendo resultados filtrados (y posiblemente modificados) para engañarlos haciéndole creer que el ataque está progresando con éxito. Esto facilita el análisis de los TTP del actor de amenazas y, potencialmente, su identidad. La atribución del ataque a un grupo particular permitirá una estimación de la capacidad del adversario.