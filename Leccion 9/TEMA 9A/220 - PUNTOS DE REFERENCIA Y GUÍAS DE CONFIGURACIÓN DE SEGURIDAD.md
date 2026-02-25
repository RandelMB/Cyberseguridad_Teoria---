
Una secure baseline (línea base de seguridad) es una colección de configuraciones y ajustes estándar para dispositivos de red, software, parches y actualizaciones, controles de acceso, registro, monitoreo, políticas de contraseñas, cifrado, protección de puntos de conexión y muchos otros. Las secure baselines (líneas de base de seguridad) mejoran la seguridad, la capacidad de administración y la eficiencia operativa de las tecnologías de la información al establecer reglas y procedimientos consistentes y centralizados con respecto a la configuración y la protección del entorno.

Los puntos de referencia del Centro para la seguridad de Internet (CIS) son un recurso importante para las mejores prácticas de configuración de seguridad. La organización CIS es reconocida mundialmente por publicar y mantener guías de mejores prácticas para proteger los sistemas y datos de TI. Los puntos de referencia de CIS abarcan múltiples dominios, como redes, sistemas operativos y aplicaciones, y se actualizan continuamente en respuesta a los riesgos en evolución. Por ejemplo, existen puntos de referencia para el cumplimiento de los marcos de TI y los programas de cumplimiento, como PCI DSS, NIST 800-53, SOX e ISO 27000. También existen puntos de referencia centrados en el producto, como para Windows Desktop, Windows Server, macOS, Linux, Cisco, navegadores web, servidores web, servidores de bases de datos y correo electrónico, y VMware ESXi. Las Guías de implementación de seguridad técnica (STIG) son una línea de base de seguridad específica desarrollada por la Agencia de Sistemas de Información de Defensa (DISA) para elDepartamento de Defensa de los Estados Unidos. Al igual que los puntos de referencia de CIS, la metodología STIG define un conjunto estandarizado de configuraciones y controles de seguridad diseñados específicamente para la infraestructura de TI del Departamento de Defensa.

Existen varias herramientas y tecnologías disponibles para ayudar a gestionar, implementar y medir el cumplimiento de las líneas de base de seguridad establecidas. Las herramientas de gestión de configuración, como Puppet, Chef, Ansible y la política de grupo de Microsoft, permiten a las organizaciones automatizar la implementación de configuraciones de línea de base de seguridad en varios sistemas diversos. Estas herramientas contribuyen a garantizar la consistencia y a detectar y corregir las desviaciones de la línea de base establecida. Para monitorear el cumplimiento, las herramientas compatibles con el Protocolo de automatización de contenido de seguridad (SCAP), como OpenSCAP, pueden evaluar y verificar la conformidad del sistema con la línea de base. Además, el CIS proporciona la herramienta CIS-CAT Pro, diseñada para evaluar las configuraciones del sistema en comparación con los puntos de referencia de referencia de seguridad del CIS. El Verificador de cumplimiento de SCAP (SCC) es una herramienta mantenida por DISA que se utiliza para medir el cumplimiento de las líneas de base de STIG.

Conceptos de endurecimiento
Los equipos de red, el software y los sistemas operativos utilizan configuraciones predeterminadas del desarrollador o fabricante que intentan equilibrar la facilidad de uso con la seguridad. Las configuraciones predeterminadas son un objetivo atractivo para los atacantes, ya que suelen incluir credenciales bien documentadas, permiten la creación de contraseñas simples, usan protocolos poco seguros y muchas otras configuraciones problemáticas. Al mantener estas configuraciones predeterminadas, las organizaciones aumentan la probabilidad de ataques cibernéticos exitosos. Por lo tanto, es determinante cambiar esta configuración predeterminada para mejorar la seguridad. 

El hardening (endurecimiento) describe los métodos para mejorar la seguridad de un dispositivo cambiando su configuración predeterminada, a menudo mediante la implementación de las recomendaciones en líneas de base de seguridad publicadas. 

Switches y enrutadores
A continuación, se detallan algunos ejemplos de cambios diseñados para mejorar la seguridad de los switches y enrutadores desde la configuración predeterminada:

- El cambio de las credenciales predeterminadas que están bien documentadas y representan un riesgo de seguridad significativo.
- La desactivación de los servicios e interfaces innecesarios en un switch o enrutador. No todos los servicios o interfaces son necesarios. Por ejemplo, se deben evitar servicios como HTTP o Telnet.
- El uso de protocolos de administración segura como SSH en lugar de Telnet, o HTTPS en lugar de HTTP.
- La implementación de listas de control de acceso (ACL) para restringir el acceso al enrutador o switch únicamente a los dispositivos y redes requeridos.
- La habilitación del registro y el monitoreo para ayudar a identificar problemas como errores repetidos de inicio de sesión, cambios de configuración y muchos otros.
- La configuración de la seguridad del puerto para ayudar a limitar los dispositivos que pueden conectarse a un puerto del switch y así evitar el acceso no autorizado.
- Las políticas de contraseñas seguras ayudan a reducir el riesgo de ataques de contraseña.
- Los equipos físicamente seguros, como mantener los dispositivos en una habitación cerrada con llave para prevenir el acceso físico no autorizado.

Hardware de servidor y sistemas operativos
A continuación, se detallan algunos ejemplos de cambios diseñados para mejorar la seguridad de los servidores desde la configuración predeterminada:

- El cambio de las credenciales predeterminadas para prevenir el acceso no autorizado, similar a los dispositivos de red.
- La desactivación de los servicios innecesarios para reducir la superficie de ataque del servidor. Cada servicio que se ejecuta en un servidor representa un potencial punto de entrada para un atacante.
- La aplicación de parches y actualizaciones de seguridad de software con regularidad para corregir vulnerabilidades conocidas y proporcionar mejoras de seguridad. La gestión automatizada de parches garantiza que este proceso sea consistente y oportuno.
- El principio del privilegio mínimo limita a cada usuario a la menor cantidad de privilegios necesarios para realizar una función a fin de reducir el impacto de una cuenta comprometida.
- El uso de cortafuegos y sistemas de detección de intrusión (IDS) para ayudar a bloquear o alertar sobre actividades maliciosas.
- La configuración segura de los servidores debe utilizar configuraciones de referencia, como las proporcionadas por el CIS o las STIG.
- Los controles de acceso sólidos incluyen políticas de contraseñas seguras, autenticación de multifactores (MFA) y administración de acceso con privilegios (PAM).
- La habilitación del registro y el monitoreo para ayudar a identificar problemas como fallos repetidos de inicio de sesión, cambios de configuración y muchos otros similares a los beneficios para los equipos de red.
- El uso de soluciones antivirus y antimalware para detectar y poner en cuarentena el malware de manera automática.
- La seguridad física de los bastidores de equipos de servidores, salas de servidores o centros de datos evita el acceso no autorizado.