En el contexto de un caso de respuesta a incidentes o una investigación forense digital, una fuente de datos es algo que puede someterse a análisis para descubrir indicadores. Estas investigaciones utilizan diversas fuentes de datos:

Datos y metadatos del sistema de archivos del dispositivo multimedia y de la memoria.
Archivos de registro generados por dispositivos de red (switches, enrutadores y cortafuegos/UTM).
Tráfico de red capturado por sensores o cualquier condición alertable o registrable planteada por los sistemas de detección de intrusiones.
Archivos de registro y las alertas generados por los escáneres de vulnerabilidades basados en la red.
Archivos de registro generados por los componentes del sistema operativo de los equipos host cliente y servidor.
Archivos de registro generados por aplicaciones y servicios que se ejecutan en hosts.
Archivos de registro y alertas generados por el software de seguridad de endpoint instalado en los hosts. Puede incluir la detección de intrusiones basada en host, el análisis de vulnerabilidades, antivirus y software de seguridad con cortafuegos.
La gran diversidad y el tamaño de las fuentes de datos es un problema importante para las investigaciones. Las organizaciones utilizan herramientas de gestión de información y eventos de seguridad (SIEM) para agregar y correlacionar múltiples fuentes de datos. Se puede utilizar como una fuente única para los tableros de control de los agentes y los informes automatizados.

Los problemas que se plantean al tratar con grandes cantidades de datos a menudo se describen como las “V”. Incluyen volumen, velocidad, variedad, veracidad y valor.

Paneles
Un panel de eventos proporciona una consola desde la que trabajar para la respuesta diaria a incidentes. Proporciona un resumen de la información extraída de las fuentes de datos subyacentes para respaldar alguna tarea de trabajo. Se pueden crear paneles de control separados para adaptarse a muchos propósitos diferentes. El panel de control de un controlador de incidentes contendrá eventos sin categorizar que se asignaron a su cuenta, además de visualizaciones (gráficos y tablas) que muestran las métricas de estado clave. El panel de control de un administrador mostraría indicadores del estado general, como el número de eventos no clasificados para todos los manejadores de eventos.


![[Pasted image 20250403090146.png]]


Consola de panel de control predeterminada en Security Onion, que proporciona una visión general de los volúmenes y tipos de eventos de detección.  (Captura de pantalla cortesía de Security Onion securityonion.net).

Informes automatizados
Un SIEM se puede utilizar para dos tipos de informes:

Las alertas y alarmas detectan la presencia de indicadores de amenaza en los datos y pueden utilizarse para iniciar casos de incidentes. La gestión diaria de los informes de alertas constituye una gran parte de la carga de trabajo de un analista.
Los informes de estado comunican datos sobre el nivel de amenaza o el número de incidentes que se plantean y la efectividad de los controles de seguridad y los procedimientos de respuesta. Este tipo de informes se puede utilizar para informar las decisiones de la administración. También puede ser necesario para los informes de cumplimiento.
Un SIEM se enviará con una serie de paneles e informes preconfigurados, pero también hará que las herramientas estén disponibles para crear informes personalizados. Es fundamental adaptar la información presentada en un panel o informe para satisfacer las necesidades y los objetivos de su público objetivo. Si el informe contiene una cantidad abrumadora de información o información irrelevante, no será posible identificar rápidamente las acciones de corrección.