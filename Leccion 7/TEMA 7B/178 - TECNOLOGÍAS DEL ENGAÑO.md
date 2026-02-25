
Las deception and disruption technologies (tecnologías disruptivas y de engaño) son herramientas y técnicas de resiliencia de ciberseguridad diseñadas para aumentar el costo de la planificación de ataques para el actor de amenazas. Honeypots, Honeynets, Honeyfiles y Honeytokens son herramientas de ciberseguridad utilizadas para detectar y defenderse de ataques. Los honeypots son sistemas señuelo que imitan sistemas y aplicaciones reales. Están diseñados para permitir que los equipos de seguridad supervisen la actividad de los atacantes y recopilen información sobre sus tácticas y herramientas. Los Honeynets son una red de honeypots interconectados que simulan una red completa, lo que proporciona un entorno más extenso y realista para que los atacantes interactúen. Los Honeyfiles son archivos falsos que aparentan contener información confidencial y se utilizan para detectar intentos de acceso y robo de datos. Los honeytokens son credenciales falsas, de inicio de sesión u otros tipos de datos, que se utilizan para distraer a los atacantes, activar alertas y proporcionar información sobre la actividad de estos intrusos.

Al implementar estas herramientas, las organizaciones pueden detectar y supervisar ataques, recopilar información sobre los atacantes y sus métodos, y defenderse de forma proactiva contra futuros ataques. Estas herramientas también pueden proporcionar una capa adicional de defensa al desviar la atención de los atacantes de los sistemas y aplicaciones reales, lo que ayuda a reducir el riesgo de ataques exitosos. 

Estrategias de disrupción
Otro tipo de defensa activa utiliza estrategias de disrupción Estos adoptan algunas de las estrategias de ofuscación utilizadas por los actores maliciosos. El objetivo es aumentar el costo del ataque e inmovilizar los recursos del adversario. A continuación se muestran algunos ejemplos de estrategias de disrupción:

- Usar entradas DNS falsas para enumerar varios hosts que no existen.
- Configurar un servidor web con varios directorios señuelo o páginas generadas de forma dinámica para ralentizar el escaneo.
- Utilizar la activación del puerto o la suplantación de identidad para devolver datos de fake telemetry (telemetría falsos)  cuando un host detecta una actividad de escaneo de puertos. Esto dará como resultado que varios puertos se reporten falsamente como abiertos, lo que ralentizará el escaneo. La telemetría puede referirse a cualquier tipo de medición o datos devueltos por escaneo remoto. Por ejemplo, se podría utilizar una telemetría falsa similar para reportar direcciones IP como activas cuando no lo están.
- Utilizar un DNS sinkhole (sumidero de DNS) para dirigir el tráfico sospechoso a una red diferente, como una honeynet, donde puede ser analizado.


