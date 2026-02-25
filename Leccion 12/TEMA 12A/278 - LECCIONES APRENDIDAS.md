El proceso de lecciones aprendidas revisa los incidentes de seguridad graves para determinar su causa raíz, si se podían haber evitado y cómo prevenirlos en el futuro.

La actividad sobre las lecciones aprendidas comienza con una reunión en donde el personal revisa el incidente y las respuestas. En la reunión debe participar tanto el personal directamente implicado, así como también otros responsables no involucrados directamente, quienes pueden aportar perspectivas objetivas y externas. Todo el personal debe contribuir libre y abiertamente a la discusión, por lo que estas reuniones deben evitar señalar culpas y, en cambio, centrarse en mejorar los procedimientos. El equipo directivo debería gestionar las preocupaciones disciplinarias relacionadas con el personal que no sigue los procedimientos establecidos de manera separada. 

Finalizada la reunión, uno o más analistas deberían elaborar un informe de lecciones aprendidas (LLR) o informe posterior a la acción (AAR). 

El proceso de lecciones aprendidas debe invocar un análisis de causa raíz o el esfuerzo para determinar cómo pudo ocurrir el incidente. Se desarrollaron muchos modelos para estructurar el análisis de la causa raíz. Uno es el método de los cinco porqués (Five Whys) Esto comienza con una declaración del problema y luego plantea preguntas sucesivas de “por qué” para profundizar hasta llegar a las causas fundamentales. A continuación se detallan algunos ejemplos:

¿Por qué se encontró nuestra base de datos de seguridad del paciente en un sitio web oscuro? Porque un actor de amenazas pudo copiarla a un USB y salir del edificio con esta información.
¿Por qué un actor de amenazas pudo copiar la base de datos a un USB en primer lugar, o hacerlo sin generar una alerta? Porque pudieron desactivar el sistema de prevención de pérdida de datos.
¿Por qué pudieron desactivar el sistema de prevención de pérdida de datos? Porque se les confió privilegios para hacerlo.
¿Por qué se les asignaron estos privilegios? Nadie parece saber. Todas las cuentas de administrador fueron provistas con esos privilegios.
¿Por qué el acto de desactivar el sistema de prevención de pérdida de datos no generó una alerta? Estaba registrado, pero las alertas para esa categoría habían sido desactivadas porque generaban demasiados falsos positivos.
Esto identifica dos causas raíces: asignaciones de permisos incorrectas y una configuración incorrecta de registro y alertas. Una limitación del modelo de “cinco porqués” es que puede ramificarse rápidamente en diferentes direcciones de investigación.

Otro enfoque es realizar diferentes preguntas con el objetivo de construir una imagen completa del incidente y sus causas:

¿Quién era el adversario? ¿Fue un incidente interno, externo o una combinación de ambos?
¿Por qué se perpetró el incidente? Analice los motivos del adversario y los activos de datos que podría haber elegido como objetivo.
¿Cuándo se produjo el incidente, cuándo se lo detectó y cuánto tiempo se tardó en contenerlo y erradicarlo?
¿Dónde se produjo el incidente (sistemas host y segmentos de red afectados)?
¿Cómo se produjo el incidente? ¿Qué tácticas, técnicas y procedimientos (TTP) empleó el adversario? ¿Se conocían y documentaban las TTP en una base de conocimientos como ATT&CK, o eran únicas?
¿Qué controles de seguridad habrían proporcionado una mejor mitigación o mejorado la respuesta?
Otro enfoque podría consistir en recorrer la cronología del incidente para comprender lo que se sabía, el razonamiento de cada decisión y qué opciones o controles podrían haber sido más beneficiosos para la respuesta.
