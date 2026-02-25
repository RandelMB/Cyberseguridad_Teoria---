Hay que mantener un escáner automático actualizado con información sobre vulnerabilidades conocidas. Esta información se describe a menudo como una vulnerability feed (fuente de vulnerabilidades), aunque la herramienta Nessus se refiere a estas fuentes como complementos, mientras que OpenVAS los denomina pruebas de vulnerabilidad de red (NVT).A menudo, la fuente de vulnerabilidades forma una parte importante de los modelos comerciales de los proveedores de escaneo, ya que las últimas actualizaciones requieren una suscripción válida.

![[Pasted image 20250317174035.png]]

Description
La captura de pantalla muestra las siguientes pestañas en la parte superior: información, resultados (135 de 1148), hosts (1 de 254), puertos (17 de 30), aplicaciones (19 de 44), sistemas operativos (1 de 6), CVEs (48 de 48), CVEs cerrados (56 de 56), certificados TLS (3 de 5), mensajes de error (2 de 2) y etiquetas de usuario (0). La pestaña de resultados está seleccionada. La tabla debajo lista la vulnerabilidad, severidad, QoD, IP del host, nombre del host, ubicación y el día, fecha y hora de creación.



Comprobación del estado de la fuente en el administrador de vulnerabilidades de la herramienta Greenbone Community Edition. (Captura de pantalla: Greenbone Community Edition greenbone.net/en/community-edition).

La base de datos nacional de vulnerabilidades (NVD, por sus siglas en inglés) es un repositorio mantenido por el Instituto Nacional de Estándares y Tecnología (NIST) que proporciona información detallada sobre las vulnerabilidades de software conocidas, incluidas las descripciones de vulnerabilidades, las calificaciones de severidad, las versiones de software afectadas y las medidas de mitigación. https://nvd.nist.gov

Las fuentes de vulnerabilidades utilizan identificadores comunes para facilitar el intercambio de datos de inteligencia en diferentes plataformas. Muchos escáneres de vulnerabilidades utilizan el Security Content Automation Protocol (SCAP) (protocolo de automatización de contenido de seguridad) para obtener actualizaciones de fuentes o complementos (scap.nist.gov). 

Además de proporcionar un mecanismo para distribuir la fuente, SCAP define métodos para comparar la configuración real de un sistema con una línea de base segura para el objetivo, así como varios sistemas de identificadores comunes. Estos identificadores proporcionan un medio estándar para que diferentes productos se refieran a una vulnerabilidad o plataforma de manera consistente.

Common Vulnerabilities and Exposures(CVE) (vulnerabilidades y exposiciones comunes) es un diccionario de vulnerabilidades en sistemas operativos y software de aplicaciones publicados (cve.mitre.org). Los elementos que componen la entrada de una vulnerabilidad en el CVE incluyen:

- CVE-YYYY-####, donde YYYY es el año en que se descubrió la vulnerabilidad y #### son al menos cuatro dígitos que indican el orden en que se descubrió la vulnerabilidad.
- Una breve descripción de la vulnerabilidad.
- Una lista de referencia de las URL que proporcionan más información sobre la vulnerabilidad.
- La fecha de creación de la entrada de vulnerabilidad.
El diccionario CVE proporciona la entrada principal para la Base de datos nacional de vulnerabilidades del NIST (nvd.nist.gov). El NVD complementa las descripciones de CVE con análisis adicionales, una métrica de criticidad calculada con el Common Vulnerability Scoring System (CVSS) (Sistema común de puntuación de vulnerabilidades ), más información sobre correcciones.

El Foro de equipos de seguridad y respuesta a incidentes mantiene el CVSS (first.org/cvss). Las métricas CVSS generan una puntuación de 0 a 10 en base a las características de la vulnerabilidad, como por ejemplo si se puede activar de forma remota o necesita acceso local, si se requiere la intervención del usuario, y así sucesivamente. Las puntuaciones se agrupan según las siguientes descripciones:

Puntuación



0,1+

Baja

4,0+

Media

7,0+

Alta

9,0+

Crítica