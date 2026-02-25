
Luego de completar un escaneo de vulnerabilidades, la herramienta genera un informe resumido de todos los descubrimientos. El informe codifica por colores las vulnerabilidades en función de su criticidad, siendo el rojo normalmente el color que denota una debilidad que requiere atención inmediata. Las vulnerabilidades pueden ser revisadas por alcance (las más críticas en todos los hosts) o por host. Los informes suelen incluir enlaces a detalles específicos sobre cada vulnerabilidad y cómo se pueden solucionar los problemas.

![[Pasted image 20250317174115.png]]

Description
La captura de pantalla muestra las siguientes pestañas en la parte superior: información, resultados (135 de 1148), hosts (1 de 254), puertos (17 de 30), aplicaciones (19 de 44), sistemas operativos (1 de 6), CVEs (48 de 48), CVEs cerrados (56 de 56), certificados TLS (3 de 5), mensajes de error (2 de 2) y etiquetas de usuario (0). La pestaña de resultados está seleccionada. La tabla debajo lista la vulnerabilidad, severidad, QoD, IP del host, nombre del host, ubicación y el día, fecha y hora de creación.



Informe de escaneo que enumera varias vulnerabilidades de alta gravedad encontradas en un host de Windows. (Captura de pantalla: Greenbone Community Edition greenbone.net/en/community-edition).

Los escaneos activos o intrusivos suelen ser más adecuados para detectar una gama más amplia de vulnerabilidades en los sistemas host y pueden reducir notablemente los false positives (falsos positivos). Un false positive (falso positivo) se refiere a una instancia en la que un escáner u otra herramienta de evaluación identifica incorrectamente una vulnerabilidad. 

Por ejemplo, un escaneo de vulnerabilidades podría señalar un puerto abierto en el cortafuegos como un riesgo de seguridad en función de su uso conocido por un determinado malware. Sin embargo, si este puerto no está abierto en el sistema, se dedicará tiempo y esfuerzo innecesarios a investigar el problema. Si un escaneo de vulnerabilidades arroja un exceso de false positives (falsos positivos), existe el riesgo de ignorar los escaneos por completo, lo que podría derivar en problemas mayores.

Además, se debe permanecer alerta al riesgo de false negatives (falsos negativos) o vulnerabilidades potenciales que pasan desapercibidas en un escaneo. Este riesgo se puede contrarrestar ejecutando escaneos repetidos periódicamente y utilizando escáneres de diferentes proveedores. Los complementos de escaneo automatizado se basan en scripts precompilados y pueden no replicar el éxito de un hacker experto y determinado, lo que potencialmente podría generar una falsa sensación de seguridad.

Examinar los registros de red y del sistema relacionados puede validar los informes de vulnerabilidades. Supongamos que un escáner de vulnerabilidades identifica un proceso en ejecución en una máquina con Windows, etiqueta la aplicación que crea este proceso como inestable y potencialmente hace que el sistema operativo bloquee y arruine otros procesos y servicios. Una revisión de los registros de eventos del equipo revela varias entradas que indican que el proceso ha fallado en las últimas semanas. Las entradas adicionales muestran la falla posterior de algunos otros procesos relacionados. En este caso, se ha utilizado una fuente de datos relevante para confirmar la validez de la alerta de vulnerabilidad.