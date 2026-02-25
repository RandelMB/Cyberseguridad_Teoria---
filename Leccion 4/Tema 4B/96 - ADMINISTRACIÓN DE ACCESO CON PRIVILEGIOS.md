
Los usuarios estándar tienen privilegios limitados, por lo general con acceso para ejecutar programas y para crear y modificar archivos que pertenecen solo a su perfil.

Una cuenta con privilegios es aquella que puede realizar cambios de configuración importantes en un host, como instalar software o desactivar un cortafuegos u otro sistema de seguridad. Las cuentas con privilegios también tienen derecho a administrar dispositivos de red, servidores de aplicaciones y bases de datos.

Privileged access management (PAM) [(administración de acceso con privilegios (PAM)] hace referencia a las políticas, los procedimientos y los controles técnicos para evitar que las cuentas con privilegios se vean comprometidas. Estos controles identifican y documentan las cuentas con privilegios, dan visibilidad de su uso y gestionan las credenciales que se utilizan para acceder a ellas.

Es recomendable restringir la cantidad de cuentas administrativas tanto como sea posible. Cuantas más cuentas hay, más probable es que una de ellas se vea comprometida. Por otro lado, no es recomendable que los administradores compartan cuentas o usen cuentas predeterminadas, ya que compromete la responsabilidad. 

Los usuarios con privilegios administrativos deben tener sumo cuidado con la gestión de credenciales. Las cuentas de acceso con privilegios deben usar contraseñas seguras e idealmente autenticación de multifactores (MFA) o autenticación sin contraseña.

Para proteger las credenciales de la cuenta con privilegios, es importante no iniciar sesión en estaciones de trabajo que no sean de confianza. Una estación de trabajo administrativa segura (SAW) es una computadora con una superficie de ataque muy baja que ejecuta el mínimo de aplicaciones posibles.

Las cuentas de administrador tradicionales tienen permisos permanentes. Los permisos justo a tiempo (JIT) significan que los privilegios elevados de una cuenta no se asignan al iniciar sesión. En su lugar, los permisos deben solicitarse explícitamente y solo se otorgan por un período limitado. Esto se conoce como privilegios permanentes cero (ZSP). Existen tres modelos principales para implementar esto:

Elevación temporal: significa que la cuenta obtiene derechos administrativos por un período limitado. La función User Account Control (control de cuentas de usuario [UAC]) de Windows y el comando sudo en Linux utilizan este concepto.
Bóveda de contraseñas/intermediación: significa que la cuenta con privilegios se debe “sacar” de un repositorio y quedará disponible por un tiempo limitado. El administrador debe registrar una justificación del uso de los privilegios. La aprobación de la solicitud podría automatizarse a través de políticas aplicadas por el sistema o requerir intervención manual, proporcionando así una medida de control M de N. Esto ofrece una mejor supervisión contable que la elevación temporal y una mejor protección contra el compromiso de credenciales con privilegios.
Credenciales efímeras: significa que el sistema genera o habilita una cuenta a fin de utilizarla para realizar la tarea administrativa y luego la destruye o deshabilita una vez que se realizó la tarea. La pertenencia temporal o efímera a grupos o funciones de seguridad puede servir para un propósito similar.
Además de los administradores humanos, la PAM también se aplica a las cuentas de servicio.

