

El control de acceso basado en funciones y atributos utiliza asignaciones de permisos no discrecionales basadas en reglas con más flexibilidad que MAC.

Control de acceso basado en funciones
El control de acceso basado en funciones (RBAC) significa que una organización define sus requisitos de permisos en términos de las tareas que un empleado o servicio debe poder realizar. Cada conjunto de permisos es una función. A cada entidad (cuenta de usuario o servicio) se le asigna una o más funciones. En este sistema, el derecho a modificar los permisos asignados a cada función está reservado al propietario del sistema. Por lo tanto, el sistema no es discrecional, ya que la entidadno puede modificar la ACL de un recurso, aunque pueda modificar el recurso de otras maneras. Las entidades adquieren derechos de forma implícita (a través de la asignación de una función) y no de forma explícita (se les asigna el derecho directamente).

El concepto de cuenta de grupo de seguridad contribuye a convertir un sistema discrecional en uno basado en funciones. En lugar de asignar derechos directamente a las cuentas de usuario, el propietario del sistema asigna las cuentas de usuario a las cuentas de grupo de seguridad. Las entidades adquieren derechos al convertirse en miembros de un grupo de seguridad. Una entidad puede ser un miembro de varios grupos y, por lo tanto, puede recibir derechos y permisos de varias fuentes.


![[Pasted image 20241118135525.png]]


Description
Los pasos son los siguientes 1. Asignar permisos directamente a las cuentas de usuario no es adecuado. 2. En su lugar, las cuentas de usuario pueden hacerse miembros de diferentes grupos de seguridad. 3. El grupo de seguridad recibe permisos sobre el objeto ACL y la cuenta de usuario hereda los permisos del grupo.

Uso de grupos de seguridad para asignar privilegios. (Imágenes © 123RF.com.)

Uso de grupos de seguridad para asignar privilegios. (Imágenes © 123RF.com.)

El RBAC puede implementarse de manera parcial al asignar grupos de seguridad a funciones, pero no son esquemas idénticos. La pertenencia a los grupos de seguridad es en gran medida discrecional (asignada por los administradores en lugar de ser determinada por el sistema). Además, lo ideal es que una entidad solo herede los permisos de una función para completar una tarea en particular, en lugar de retenerlos de forma permanente. Se debe evitar que los administradores escalen sus propios privilegios al asignar funciones a sus propias cuentas de forma arbitraria o al aumentar los permisos de una función.

Control de acceso basado en atributos
El control de acceso basado en atributos (ABAC) es el tipo de modelo de control de acceso más detallado. Como su nombre lo indica, un sistema ABAC toma decisiones de acceso basadas en una combinación de atributos de sujeto y objeto más cualquier atributo sensible al contexto o de todo el sistema. Además de las pertenencias a grupos/funciones, estos atributos podrían incluir información sobre el sistema operativo que se está utilizando actualmente, la dirección IP o la presencia de parches y antimalware actualizados. Un sistema basado en atributos supervisa la cantidad de eventos o alertas asociados con una cuenta de usuario o con un recurso, o realiza un seguimiento de las solicitudes de acceso para garantizar que sean coherentes en términos de tiempo o ubicación geográfica. Se puede programar para implementar políticas como el control M de N y la separación de funciones.