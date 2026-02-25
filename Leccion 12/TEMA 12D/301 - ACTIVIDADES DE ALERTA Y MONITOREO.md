Cuando los datos se han recopilado y agregado, el SIEM se puede utilizar para implementar actividades de alerta, informes y archivo.

Tenga en cuenta que estas actividades se pueden realizar de forma manual o automatizada utilizando herramientas discretas para cada dispositivo de seguridad. La ventaja de un SIEM es que permite consolidar las actividades en una sola interfaz de administración. Esta funcionalidad consolidada denominada "panel de vidrio" se refiere a la visibilidad mejorada en un entorno complejo que ofrece dicho software.

Alerta
Un SIEM puede ejecutar reglas de correlación en los indicadores extraídos de las fuentes de datos para detectar eventos que deben investigarse como incidentes potenciales. Un analista también puede filtrar o consultar los datos en función del tipo de incidente que se ha informado.

Correlación significa interpretar la relación entre los puntos de datos individuales para diagnosticar incidentes de importancia para el equipo de seguridad. Una regla de correlación SIEM es una declaración que cumple con ciertas condiciones. Estas reglas utilizan expresiones lógicas, como \"Y\" (AND) y \"O\" (OR), y operadores, como == (igual), < (menor que), > (mayor que) e \"in\" (en) (contiene).  Por ejemplo, un error de inicio de sesión de un solo usuario no es una condición que deba generar una alerta. Múltiples fallos de inicio de sesión de un usuario para la misma cuenta, que tienen lugar en el plazo de una hora, es más probable que requieran investigación y son candidatos para la detección por una regla de correlación.

Error.LoginFailure > 3 AND LoginFailure.User AND Duration < 1 hour

Además de la correlación entre los indicadores observados en los datos recopilados, es probable que un SIEM se configure con una fuente de inteligencia de amenazas. Significa que los puntos de datos observados en los datos de red recopilados pueden asociarse con indicadores conocidos de actores de amenazas, como direcciones IP y nombres de dominio. 

Los procesos de respuesta a incidentes de análisis, contención, erradicación y recuperación abordarán cada alerta. Cuando se usa junto con un SIEM, se debe prestar especial atención a dos pasos particulares en la respuesta de alerta y la corrección:

La validación durante el proceso de análisis es la forma en que el analista decide si la alerta es un verdadero positivo y debe tratarse como un incidente. Un falso positivo es cuando se genera una alerta, pero no hay actividad de amenaza real.
La cuarentena es el paso de aislar la fuente de indicadores, como una dirección de red, un equipo host o un archivo.
Los pasos de respuesta a alerta y corrección a menudo se guiarán por un manual que ayuda al analista a aplicar todos los procesos de respuesta a incidentes para un determinado escenario. Una de las ventajas de las soluciones SIEM y las soluciones avanzadas de orquestación, automatización y respuesta a incidentes (SOAR) es automatizar total o parcialmente la validación y la corrección. Por ejemplo, una acción de cuarentena podría estar disponible como una acción con un simple clic del mouse mediante la integración con un cortafuegos o un producto de protección para puntos finales. La validación se facilita al poder correlacionar datos de eventos con datos de amenazas conocidas y pivotar entre fuentes, como la inspección de paquetes que activaron una alerta específica del sistema de detección de intrusiones (IDS).

Informes
La generación de informes es un control de gestión que proporciona información sobre el estado del sistema de seguridad. Un SIEM puede ayudar con la actividad de informes al exportar estadísticas y gráficos resumidos. Por lo general, los formatos y contenidos de los informes se adaptan para satisfacer las necesidades de diferentes audiencias:

Los informes ejecutivos proporcionan un resumen de alto nivel para los responsables de la toma de decisiones. Esto orienta la actividad de planificación e inversión.
Los informes del gerencia proporcionan información detallada a los líderes de departamento y de ciberseguridad. Esto orienta la toma de decisiones operativas diarias.
Los informes de cumplimiento proporcionan toda la información requerida por un regulador.
Determinar qué métricas son más útiles en términos de informes siempre es un desafío. Los siguientes tipos ilustran algunos casos de uso comunes para los informes:

Datos de autenticación, como intentos fallidos de inicio de sesión, y datos críticos de auditoría de archivos.
Equipos con parches faltantes o vulnerabilidades de configuración.
Anomalías en cuentas de usuarios con privilegios, como el uso fuera del horario laboral o las solicitudes excesivas de permisos elevados.
Estadísticas de gestión de casos de incidentes, como el volumen general, casos abiertos, tiempo de resolución, entre otros.
Los informes de tendencias muestran los cambios en las métricas clave a lo largo del tiempo.
Archivado
Un SIEM puede implementar una política de retención para que los registros históricos y los datos de tráfico de red se conserven durante un período definido. Esto permite la detección retrospectiva de incidentes y amenazas, y puede ser una valiosa fuente de evidencia forense. También puede cumplir con los requisitos de cumplimiento para mantener archivos de información de seguridad. El rendimiento de un SIEM se degradará si se mantiene disponible una cantidad excesiva de datos para el análisis en tiempo real. Se puede configurar un esquema de rotación de registros para trasladar la información obsoleta al almacenamiento de archivos.