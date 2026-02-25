Una de las funciones de un escaneo de vulnerabilidades es evaluar la configuración de los controles de seguridad y los ajustes y permisos de la aplicación en comparación con los puntos de referencia establecidos. 

El escáner podría intentar identificar si hay una falta de controles que podrían considerarse necesarios o si hay alguna configuración incorrecta del sistema que haría que los controles sean menos efectivos o ineficaces, como que el software antivirus no se actualizara o que las contraseñas de administración se dejaran establecidas con la configuración predeterminada. Este tipo de prueba requiere información específica sobre las mejores prácticas en la configuración de la aplicación o control de seguridad en particular. Estas mejores prácticas se proporcionan enumerando los controles y los ajustes de configuración adecuados en una plantilla.

El Protocolo de automatización de contenido de seguridad (SCAP) permite que los escáneres compatibles determinen si un equipo cumple con una línea de base de configuración. SCAP utiliza varios componentes para llevar a cabo esta función. A continuación se detallan algunos de los más importantes:

Lenguaje abierto de evaluación y vulnerabilidad (OVAL): es un esquema XML para describir el estado de seguridad del sistema y consultar informes y datos sobre vulnerabilidades.
Formato de descripción de lista de verificación de configuración extensible (XCCDF): un esquema XML para desarrollar y auditar listas de verificación y reglas de configuración de mejores prácticas. Anteriormente, las guías de mejores prácticas podrían haberse redactado en prosa para que los administradores de sistemas las aplicaran de forma manual. XCCDF proporciona un formato legible por máquina que se puede aplicar y validar con un software compatible.

![[Pasted image 20250403092727.png]]

Description
La captura de pantalla muestra dos secciones. La sección superior lista el tipo de política, grupo de política o clave de registro, configuración de la política, soporte 515 y plantilla. La sección inferior proporciona información sobre la ruta de la política, soporte 515 y plantilla.



Comparación de una política de seguridad de red local con una plantilla. La longitud mínima de la contraseña establecida en la política local es mucho menor que la recomendada en la plantilla. (Captura de pantalla utilizada con el permiso de Microsoft).

Algunos escáneres miden los sistemas y los ajustes de configuración frente marcos de mejores prácticas. Esto se conoce como análisis de cumplimiento. Esto podría ser necesario para el cumplimiento normativo, o podría querer ajustarse de manera voluntaria con los estándares de mejores prácticas acordados externamente. 

![[Pasted image 20250403092719.png]]
Plantilla de monitoreo alineada con los requisitos del marco NIST 800-53. 