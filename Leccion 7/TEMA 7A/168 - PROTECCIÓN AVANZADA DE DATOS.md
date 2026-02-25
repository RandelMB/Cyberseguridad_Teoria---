




Instantáneas
Las instantáneas desempeñan un papel vital en la protección y recuperación de datos, ya que capturan el estado de un sistema en un momento específico. Las instantáneas de la máquina virtual (VM), las de sistema de archivos y las red de área de almacenamiento (SAN) son tres tipos diferentes, cada uno dirigido a un nivel particular de la jerarquía de almacenamiento. 

- Las instantáneas de VM, como las creadas en VMware vSphere o Microsoft Hyper-V, capturan el estado de una máquina virtual, incluida su memoria, almacenamiento y configuración. Esto permite a los administradores revertir la VM a un estado anterior en caso de fallas, corrupción de datos o durante las pruebas de software. 
- Las instantáneas del sistema de archivos, como las proporcionadas por ZFS o Btrfs, capturan el estado de un sistema de archivos en un momento dado, lo que permite a los usuarios recuperar archivos eliminados por accidente o restaurar versiones anteriores de archivos en caso de corrupción de datos. 
- Las instantáneas de SAN se toman en la capa de almacenamiento a nivel de bloque dentro de una red de área de almacenamiento. Los ejemplos incluyen instantáneas en sistemas de almacenamiento NetApp o Dell EMC, que capturan el estado de todo el volumen de almacenamiento, lo que permite una rápida recuperación de grandes conjuntos de datos y aplicaciones. 
Al utilizar instantáneas de VM, sistemas de archivos y SAN, las organizaciones pueden mejorar sus estrategias de protección y recuperación de datos, y, a la vez, garantizar la disponibilidad e integridad de sus datos en diferentes capas y sistemas de almacenamiento.

![[Pasted image 20250217105812.png]]


Sección de la configuración del punto de control para una máquina virtual Hyper-V. Los puntos de verificación se refieren a la implementación de la funcionalidad de instantáneas de Microsoft. (Captura de pantalla utilizada con permiso de Microsoft).

Replicación y registro por diario (journaling)

La replicación y el registro por diario son métodos de protección de datos que garantizan la disponibilidad e integridad de los datos mediante el mantenimiento de múltiples copias y el seguimiento de los cambios en los datos.

La replicación implica crear y mantener copias exactas de los datos en diferentes sistemas o lugares de almacenamiento. Las organizaciones pueden protegerse contra la pérdida de datos debido a fallas de hardware, errores humanos o ataques maliciosos al guardar copias redundantes de los datos. En caso de falla, los datos replicados se pueden utilizar para restaurar el sistema a su estado original. 

Un ejemplo práctico de replicación es la duplicación de bases de datos. En este caso, una organización mantiene bases de datos duplicadas primarias y secundarias. Cualquier cambio que se haga en la base de datos principal se replica automáticamente en la base de datos secundaria, lo que garantiza la consistencia y disponibilidad de los datos, en caso de que se presente algún problema con la base de datos principal.

Por otro lado, con el registro por diario los cambios que sufran los datos se guardan en un registro separado y exclusivo conocido como diario. Las organizaciones pueden rastrear y monitorear las modificaciones de datos y volver a los estados anteriores si es necesario. El registro por diario (journaling) es beneficioso para la recuperación de datos en casos de fallas del sistema. Permite al sistema identificar y deshacer cualquier transacción incompleta que pueda haber causado inconsistencias, o repetir transacciones que ocurrieron después de que se terminó la copia de seguridad completa del sistema. Proporciona una mayor granularidad para las restauraciones y minimiza en gran medida la pérdida de datos. Un ejemplo práctico de registro por diario es usar el registro diario del sistema de archivos, como el Sistema de archivos registrados por diario (JFS) o el sistema de archivos de nueva tecnología (NTFS), con el registro diario habilitado. Con estos sistemas de archivos se mantiene un registro de todos los cambios realizados en los archivos, lo que permite la recuperación de datos y las verificaciones de consistencia después de cierres o bloqueos imprevistos del sistema.

El egistro por diario) remoto, la replicación de SAN y la replicación de VM son métodos avanzados de protección de datos que mantienen la disponibilidad e integridad de los datos en múltiples lugareas y sistemas. Con el registro por diario remoto se crea y mantiene un diario de cambios de datos en un lugar separado y remoto, lo que permite la recuperación de los datos y garantiza la continuidad del negocio en caso de fallas locales, desastres naturales o ataques maliciosos. 

La replicación de SAN duplica los datos de un SAN a otro en tiempo real o casi en tiempo real, lo que proporciona redundancia y protección contra fallas de hardware, errores humanos o corrupción de datos. Esta técnica implica la replicación sincrónica, que garantiza la consistencia de los datos, y la replicación asincrónica, que es más rentable pero ligeramente menos estricta en cuanto a la consistencia. 

Mientras tanto, con la replicación de máquinas virtuales (VM) se crea y mantiene una copia actualizada de una máquina virtual en un host o lugar separados, lo que garantiza que una máquina virtual secundaria pueda hacerse cargo con rapidez de la carga de trabajo en caso de la máquina virtual primaria falle o se corrompa. Mediante la implementación de estos métodos, las organizaciones pueden reforzar sus estrategias de protección de datos, protegerse contra diversos riesgos y garantizar la disponibilidad e integridad de sus datos y sistemas críticos.

Cifrado de copias de seguridad
El cifrado de las copias de seguridad es fundamental por varias razones, principalmente la seguridad de los datos, la privacidad y el cumplimiento. Al cifrar las copias de seguridad, las organizaciones agregan una capa adicional de protección contra el acceso no autorizado o el robo, lo que garantiza que los datos confidenciales permanezcan ilegibles sin la clave de descifrado adecuada. Esto es particularmente fundamental para las empresas que se ocupan de datos confidenciales de clientes, propiedad intelectual o secretos comerciales, ya que el acceso no autorizado puede provocar graves daños a la reputación, pérdidas financieras o consecuencias legales. 

Las copias de datos confidenciales que se almacenan en conjuntos de copia de seguridad suelen pasarse por alto, por lo que muchas industrias y jurisdicciones tienen normas que exigen la protección de los datos confidenciales almacenados en copias de seguridad. El cifrado de copias de seguridad ayuda a las organizaciones a cumplir con estos requisitos reglamentarios y evitar multas, sanciones o acciones legales resultantes del incumplimiento.