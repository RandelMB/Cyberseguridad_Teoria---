
En un IDS, el motor de análisis es el componente que escanea e interpreta el tráfico capturado por el sensor con el objetivo de identificar el tráfico sospechoso. El motor de análisis determina la clasificación de un evento con las opciones típicas de ignorar, solo registrar, alertar y bloquear (IPS). Un conjunto de reglas programadas impulsa el  proceso de toma de decisiones del motor de análisis. Existen varios métodos para formular el conjunto de reglas.

Detección basada en firmas
La detección basada en firmas (o coincidencia de patrones) significa que el motor está cargado con una base de datos de patrones o firmas de ataque. Si el tráfico coincide con un patrón, el motor genera un incidente.

![[Pasted image 20250328115442.png]]

Description
La pantalla muestra, Iniciar ET guión Emerging guión Activex Rules Category, Iniciar GID dos puntos 1 Based Rules, seguido por las alertas. El texto en la parte inferior indica 27185 líneas (advertencia: sin permiso de escritura).



Archivo de reglas de Snort suministrado por el feed de la comunidad de amenazas emergentes de código abierto.

Las firmas y reglas (a menudo llamadas complementos o feeds) que alimentan la detección de intrusiones deben actualizarse de forma periódica para brindar protección contra los últimos tipos de amenazas. El software comercial requiere una suscripción de pago para obtener las actualizaciones. Es importante configurar el software para que se actualice solo a partir de repositorios válidos, idealmente a través de un método de conexión segura como HTTPS.

Detección basada en el comportamiento y en anomalías
La detección basada en el comportamiento significa que el motor está entrenado para reconocer el tráfico o los eventos “normales” de referencia. Todo lo que se desvíe de esta referencia (fuera de un nivel de tolerancia definido) genera un incidente. El software podrá identificar ataques de día cero, amenazas internas y otras actividades maliciosas para las que exista una firma única.

Históricamente, los productos de detección de anomalías y comportamiento de red (NBAD) proporcionan este tipo de detección. Un motor de NBAD utiliza la heurística (que significa aprender de la experiencia) para generar un modelo estadístico de cómo es el tráfico normal de referencia. Puede desarrollar varios perfiles para modelar el uso de la red en diferentes momentos del día. Esto significa que el sistema genera falsos positivos y falsos negativos hasta que haya tenido tiempo de mejorar su modelo estadístico de lo que es “normal”. Un falso positivo es cuando el comportamiento legítimo genera una alerta, mientras que un falso negativo es cuando no se alerta la actividad maliciosa.

Si bien los productos de NBAD eran relativamente poco sofisticados, el uso del aprendizaje automático en productos más recientes los hizo más productivos. Como se identifica en el análisis de mercado de Gartner (gartner.com/en/documents/3917096/market-guide-for-user-and-entity-behavior-analytics), existen dos clases generales de productos de detección basados en el comportamiento que utilizan el aprendizaje automático:

Análisis de comportamiento de usuarios y entidades (UEBA): estos productos analizan indicadores de múltiples fuentes de detección de intrusiones y registros para identificar anomalías. A menudo se integran con plataformas de gestión de información y eventos de seguridad (SIEM).
Análisis de tráfico de red (NTA): son productos más cercanos a IDS y NBAD, ya que aplican técnicas de análisis solo a los flujos de red en lugar de a múltiples fuentes de datos de red y de registro.
Por lo general, se considera que la detección basada en el comportamiento y en anomalías significa lo mismo (en el sentido de que el motor detecta el comportamiento anómalo). Puede que no siempre sea así. La detección basada en anomalías también puede significar buscar específicamente irregularidades en el uso de protocolos. Por ejemplo, el motor puede verificar los encabezados de los paquetes o el intercambio de paquetes en una sesión con respecto a los estándares RFC y generar una alerta si se desvían del estricto cumplimiento de RFC.

Análisis de tendencias
El análisis de tendencias es un aspecto fundamental de la gestión de los sistemas de detección de intrusión (IDS) y los sistemas de prevención de intrusión (IPS), ya que ayuda a comprender un entorno a lo largo del tiempo, y esto ayuda a identificar patrones, anomalías y amenazas potenciales. Los analistas de seguridad pueden identificar patrones y tendencias que indican amenazas continuas o crecientes mediante el seguimiento de eventos y alertas. Por ejemplo, un aumento en las alertas relacionadas con un ataque específico puede sugerir que una red está siendo atacada o que se está explotando activamente una vulnerabilidad. Las tendencias también pueden ayudar a optimizar los sistemas IDS/IPS. Con el tiempo, los analistas de seguridad pueden identificar falsos positivos o alertas innecesarias que aparecen con frecuencia. Estas alertas se pueden ajustar para que los analistas puedan centrarse en alertas más importantes. 

Los datos de tendencias pueden contribuir a las estrategias de seguridad operativa mediante la identificación de las amenazas más comunes y los sistemas que suelen ser objeto de ataques. Este enfoque destaca los puntos débiles que requieren atención, ya sea a través de cambios en la política de seguridad o mediante la inversión en herramientas de seguridad y capacitación adicionales.