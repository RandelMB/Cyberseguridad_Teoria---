

La confianza cero es un modelo de seguridad que parte del supuesto de que inherentemente ningún dispositivo, usuario y servicio es confiable, sin considerar si se encuentra dentro o fuera del perímetro de una red. En cambio, el modelo de confianza cero requiere que todos los usuarios y dispositivos sean autenticados y autorizados antes de acceder a los recursos de la red. El modelo de confianza cero incluye varios conceptos fundamentales que proporcionan una solución de seguridad integral.

La identidad adaptativa reconoce que las identidades de los usuarios no son estáticas y que la verificación de la identidad debe ser continua y basada en el contexto actual de un usuario y en los recursos a los que intenta acceder. 
La reducción del alcance de amenazas significa que el acceso a los recursos de la red se otorga en función de la necesidad de conocerlos, y el acceso se limita únicamente a aquellos recursos necesarios para completar una tarea específica. Este concepto reduce la superficie de ataque de la red y limita el daño que puede causar un ataque exitoso. 
El control de acceso impulsado por políticas describe cómo se utilizan las políticas de control de acceso para aplicar las restricciones de acceso en función de la identidad del usuario, la postura del dispositivo y el contexto de la red. 
La postura del dispositivo se refiere al estado de seguridad de un dispositivo, incluidas sus configuraciones de seguridad, versiones de software y niveles de parches. En un contexto de seguridad, la evaluación de la postura del dispositivo implica evaluar el estado de seguridad de un dispositivo para determinar si cumple con ciertos requisitos de seguridad o representa un riesgo para la red.

Importancia de los planos de control y datos en los modelos de confianza cero
En una arquitectura de confianza cero, los planos de control y de datos se implementan por separado y tienen diferentes funciones. 


![[Pasted image 20250210095529.png]]

	Description
Los pasos son los siguientes



1. El motor de políticas se configura con entradas que le permitan tomar decisiones de autenticación y autorización dinámicas y continuas.


2. El Administrador de Políticas implementa una interfaz para comunicar las decisiones a los Sistemas del Plano de Datos.


3. Los sujetos (usuarios u otros servicios) poseen credenciales para acceder a los recursos.


4. Los sujetos deben utilizar sistemas cliente para realizar peticiones, pero éstos no son de confianza implícita.



5. El sistema del Punto de Aplicación de Políticas es el único en el que se confía para comunicar peticiones y recibir decisiones del Administrador de Políticas.



6. 6. El punto de aplicación de políticas implementa la creación y el cierre de sesiones cifradas según las instrucciones del administrador de políticas.



7. Esta arquitectura crea una zona de confianza implícita de alcance y duración limitados para el acceso a los recursos.

Componentes en el marco de arquitectura de confianza cero del NIST.

El plano de control administra las políticas que dictan cómo los usuarios y dispositivos están autorizados a acceder a los recursos de red. Se implementa a través de un punto de decisión de políticas centralizado. El punto de decisión de políticas tiene la responsabilidad de definir políticas que restrinjan el acceso a recursos en función de la necesidad de conocer, supervisar la actividad de la red en busca de comportamientos sospechosos y actualizar las políticas para reflejar las condiciones cambiantes de la red y las amenazas de seguridad. El punto de decisión de políticas se compone de dos subsistemas:

El motor de políticas está configurado con identidades y credenciales de sujetos y hosts, políticas de control de acceso, inteligencia de amenazas actualizada, análisis de comportamientos y otros resultados de escaneos y monitoreo de seguridad de hosts y redes. Estos datos de estado exhaustivos le permiten definir un algoritmo y métricas para tomar decisiones dinámicas de autenticación y autorización por solicitud. 
El administrador de políticas es responsable de gestionar el proceso de emisión de tokens de acceso y establecer o cerrar sesiones, en función de las decisiones tomadas por el motor de políticas. El administrador de políticas implementa una interfaz entre el plano de control y el plano de datos.
Donde los sistemas en el plano de control definen políticas y toman decisiones, los sistemas en el plano de datos establecen sesiones para transferencias de información seguras. En el plano de datos, un sujeto (usuario o servicio) utiliza un sistema (como un equipo de host cliente, equipo portátil o teléfono inteligente) para realizar solicitudes para un recurso determinado. Un recurso suele ser una aplicación empresarial que se ejecuta en un servidor o en la nube. Cada solicitud está mediada por un punto de aplicación de políticas. El punto de aplicación podría implementarse como un agente de software que se ejecuta en el host cliente y que se comunica con una puerta de enlace de aplicaciones. El punto de aplicación de directivas interactúa con el administrador de políticas para configurar una ruta de datos segura si se aprueba el acceso, o para interrumpir una sesión si se deniega o revoca el acceso.

Los procesos que implementan el punto de aplicación de políticas son los únicos permitidos para interactuar con el administrador de políticas. Es fundamental establecer una raíz de confianza para estos procesos para garantizar que las decisiones políticas no puedan ser manipuladas.

La ruta de datos establecida entre el punto de aplicación de políticas y el recurso se denomina zona de confianza implícita. Por ejemplo, el resultado de una solicitud de acceso exitosa podría ser un túnel IPsec establecido entre un proceso de agente firmado por vía digital que se ejecuta en el cliente, una puerta de enlace de aplicaciones web de confianza y el servidor de recursos. Debido a que los datos están protegidos por el cifrado de transporte IPsec, no es posible la manipulación por parte de cualquier persona con acceso a la infraestructura de red subyacente (switches, puntos de acceso, enrutadores y firewalls).

El objetivo del diseño de confianza cero es hacer que esta zona de confianza implícita sea lo más pequeña y transitoria posible. Es posible que las sesiones de confianza se establezcan únicamente para transacciones individuales. Este enfoque granular o microsegmentado contrasta con los modelos basados en el perímetro, donde se asume la confianza una vez que un usuario se autenticó y unió a la red. En confianza cero, el lugar en la red no es una razón suficiente para confiar en una solicitud del sujeto. Del mismo modo, incluso si un usuario se autentica de manera nominal, los análisis de comportamiento podrían provocar que una solicitud se bloquee o que se interrumpa una sesión.

La separación del plano de control y el plano de datos es significativa ya que permite una arquitectura de red más flexible y escalable. El plano de control centralizado garantiza la consistencia en el manejo de solicitudes de acceso tanto en la red empresarial administrada como en Internet no administrado o en redes de terceros, independientemente de los dispositivos que se utilicen o de la ubicación del usuario. Esto facilita la gestión de políticas de control de acceso y el monitoreo de la actividad de la red para detectar comportamientos sospechosos. El monitoreo continuo a través del plano de control independiente significa que las sesiones se pueden finalizar si se detecta un comportamiento anómalo.

Ejemplos de arquitecturade confianza cero
Ejemplo

Descripción

Google BeyondCorp

BeyondCorp de Google es un ejemplo extensamente reconocido de una arquitectura de seguridad de confianza cero. BeyondCorp utiliza un sistema de múltiples capas de seguridad, incluida la verificación de identidad, la verificación de dispositivos y las políticas de control de acceso, para proteger la red interna de Google. Esto permitió que Google proporcione a sus empleados acceso remoto a los recursos de la empresa mientras mantiene una alta seguridad.

Infraestructura de defensa empresarial conjunta (JEDI)

La nube JEDI del Departamento de defensa es un proyecto importante para modernizar su infraestructura de TI. La nube JEDI se basa en una arquitectura de confianza cero que utiliza políticas de control de acceso y otras medidas de seguridad para garantizar que solo los usuarios y dispositivos autorizados puedan acceder a los recursos del Departamento de defensa.

Arquitectura de confianza cero de Cisco

Cisco desarrolló una arquitectura integral de seguridad de confianza cero que integra la segmentación de red, las políticas de control de acceso y las capacidades de detección y respuesta a amenazas. La arquitectura está diseñada para proteger contra una amplia gama de amenazas cibernéticas, incluidas las amenazas internas y los ataques externos.

Prisma Access - Palo Alto Networks

Prisma Access es un servicio de seguridad en la nube, que utiliza una arquitectura de confianza cero para proteger el tráfico de red. Proporciona acceso seguro a recursos en la nube e Internet, al tiempo que previene la exfiltración de datos y otras amenazas cibernéticas.