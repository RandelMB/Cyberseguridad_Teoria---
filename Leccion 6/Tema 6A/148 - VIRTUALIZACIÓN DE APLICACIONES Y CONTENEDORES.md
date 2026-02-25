

Virtualización de aplicaciones es un tipo más limitado de VDI. En lugar de ejecutar todo el escritorio del cliente como una plataforma virtual, el cliente accede a una aplicación alojada en un servidor o transmite dicha aplicación desde el servidor al cliente para su procesamiento local. La mayoría de las soluciones de virtualización de aplicaciones se basan en Citrix XenApp (anteriormente MetaFrame Presentation Server), aunque Microsoft ha desarrollado un producto App-V dentro de su gama de servidores Windows Server, y VMware cuenta con el producto ThinApp. Estos tipos de soluciones suelen implementarse con aplicaciones de escritorio remoto HTML5, denominadas “sin cliente”, debido a que los usuarios pueden acceder a ellas mediante un software de navegador web convencional.

La contenedorización prescinde de la idea de un hipervisor y, en cambio, impone la separación de recursos a nivel del sistema operativo. El sistema operativo define “celdas” aisladas para cada instancia de usuario en la que se ejecutará. A cada celda o contenedor se le asignan recursos de CPU y memoria, pero todos los procesos se ejecutan a través del kernel nativo del sistema operativo. Estos contenedores pueden ejecutar distribuciones de sistemas operativos ligeramente diferentes, pero no admiten la ejecución de distintos tipos de sistemas operativos invitados (no se puede ejecutar Windows o Ubuntu en un contenedor de Red Hat Linux, por ejemplo). Como alternativa, los contenedores podrían ejecutar procesos de aplicación separados, en cuyo caso se incluyen las variables y bibliotecas requeridas por el proceso de aplicación en el contenedor.

Uno de los productos de virtualización de contenedores más conocidos es Docker (docker.com). La contenedorización sustenta muchos servicios en la nube. En particular, respalda la arquitectura de microservicios y sin servidor. La contenedorización también está siendo ampliamente utilizada para implementar entornos de trabajo corporativos en dispositivos móviles.


![[Pasted image 20250210093819.png]]

	Description
La primera parte que representa a las máquinas virtuales tiene seis capas. Las tres capas de la parte inferior son el servidor, el SO anfitrión y el hipervisor (Tipo 2). Las tres capas siguientes se dividen en tres partes cada una. La cuarta capa se divide en tres SO invitados, la quinta capa en tres contenedores slash libs, y la sexta en app A, app A prime, y app B. Las tres capas superiores se etiquetan colectivamente como VM.  



La segunda parte que representa los contenedores tiene 5 capas. Las tres capas de la parte inferior son servidor, SO anfitrión y motor Docker. La cuarta capa se divide en dos secciones desiguales etiquetadas contenedores barra libs. La quinta capa de la parte superior se divide en app A, app A prime, app B, app B prime, app B prime, app B prime y app B prime.

Comparación de VM frente a contenedores.