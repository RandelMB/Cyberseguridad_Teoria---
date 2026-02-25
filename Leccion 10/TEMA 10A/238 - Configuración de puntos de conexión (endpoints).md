
Cuando la seguridad de los puntos de conexión es una preocupación, existen varias clases de vectores que se deben considerar para su mitigación:

- Ingeniería social: el malware a menudo se activa a través de los usuarios. La implementación de educación y concienciación de seguridad disminuye la probabilidad de que futuros ataques logren tener éxito. Revisar los permisos de usuario para determinar si las cuentas se pueden utilizar con un nivel de privilegios más bajo.
- Vulnerabilidades: instalar los parches disponibles o aislar los sistemas hasta que se pueda desarrollar e implementar un parche.
- Falta de controles de seguridad: muchos ataques se pueden prevenir mediante la implementación de medidas como protección de los puntos de conexión, antivirus, cortafuegos de host, filtrado de contenido, prevención de pérdida de datos (DLP) o administración de dispositivos móviles (MDM). Investigar la posibilidad de implementar estas protecciones en los puntos de conexión. Si estas medidas no resultan prácticas, aislar los sistemas para que no sean explotados por el mismo vector.
- Configuration Drift (desvíos en configuraciones): los ataques a menudo aprovechan los cambios de configuración no documentados (como la instalación software de TI no autorizados o modificaciones no autorizadas en el sistema). Implementar mecanismos que vuelvan a aplicar configuraciones de línea de base seguras y procedimientos de gestión para prevenir cambios no autorizados.
- Configuración débil: si se aplicó correctamente una configuración de referencia segura, pero el sistema fue comprometido de todos modos, revise los ajustes para identificar configuraciones más seguras. Asegúrse de que la configuración actualizada se aplique a hosts similares. 



Control de acceso
El control de acceso se refiere a la regulación y gestión de los permisos otorgados a individuos, software, sistemas y redes para acceder a recursos o información. Los controles de acceso garantizan que únicamente las entidades autorizadas (usuarios, dispositivos o software) puedan realizar acciones específicas o acceder a determinados datos, mientras que a las entidades no autorizadas se les niega el acceso. Los conceptos de control de acceso se aplican a redes, acceso físico, datos, aplicaciones y la nube.

Principio de mínimo privilegio 
La implementación del principio de mínimo privilegio (PoLP) es una piedra angular para mejorar la protección de los puntos de conexión y minimizar el riesgo de problemas de seguridad. El principio de mínimo privilegio especifica que a los usuarios, aplicaciones y procesos solo se les deben otorgar los permisos mínimos necesarios para completar sus tareas, pero no más que eso. 

Existen varios métodos prácticos para implementar el mínimo privilegio. Un primer paso fundamental para la implementación efectiva de privilegios mínimos es auditar minuciosamente funciones, privilegios y responsabilidades de los usuarios. Este proceso permite a las organizaciones comprender qué acceso necesita cada usuario para desempeñar su función laboral de manera efectiva. Los controles de acceso y los permisos se pueden ajustar para adoptar un principio de mínimo privilegio que refleje mejor los resultados de la auditoría.

Las herramientas de gestión de usuarios y cuentas también son esenciales al implementar el principio de mínimo privilegio. Revisar y eliminar con regularidad las cuentas no utilizadas o innecesarias reduce los potenciales objetivos para un atacante. Del mismo modo, los privilegios temporales, que otorgan derechos de acceso adicionales por un tiempo limitado y únicamente cuando son necesarios, pueden contribuir a mantener los privilegios lo más restringidos posible. 

Otro enfoque práctico para restringir el acceso es el uso de control de acceso basado en roles (RBAC). El modelo de control de acceso RBAC asigna derechos de acceso al sistema en función de roles predefinidos, y cada rol tiene un conjunto de permisos cuidadosamente definido que se ajusta a los requisitos de cualquier función en particular dentro de la organización. Este enfoque garantiza que los usuarios tengan acceso suficiente para realizar sus tareas, pero no más que eso. 

El principio de mínimo privilegio también se aplica a las aplicaciones de software y los sistemas operativos, no solo a los usuarios. Por ejemplo, garantizar que las aplicaciones se ejecuten con los permisos mínimos necesarios puede evitar que sean explotadas para llevar a cabo acciones privilegiadas.

Listas de control de acceso
Las listas de control de acceso (ACL) en redes y sistemas informáticos se utilizan para aplicar políticas de control de acceso. Una ACL es una lista de reglas o entradas que especifican qué usuarios o grupos tienen permitido o denegado el acceso a recursos específicos o la realización de determinadas acciones. En redes, las ACL están asociadas con enrutadores, cortafuegos u otros dispositivos similares, y definen reglas que determinan cómo se filtra o se reenvía el tráfico de red en función de criterios como direcciones IP de origen, direcciones IP de destino, puertos o protocolos. 

Las ACL pueden ayudar a controlar el acceso a la red y proteger contra actividades no autorizadas o maliciosas. Las ACL controlan el acceso a archivos, directorios o recursos del sistema en sistemas operativos y sistemas de archivos. Cada entrada de control de acceso (ACE) suele contener un identificador de usuario o grupo y permisos asociados que supervisan las acciones permitidas o denegadas. Estos permisos suelen abarcar la capacidad de lectura, escritura, ejecución, y en ocasiones, límites más detallados como modificar, eliminar o enumerar. 

Si bien las ACL ofrecen flexibilidad y control, la gestión de políticas complejas de control de acceso con numerosas entradas de ACL puede suponer un desafío. La complejidad aumenta el riesgo de configuraciones incorrectas. Por lo tanto, la planificación adecuada, las revisiones periódicas y las configuraciones de mejores prácticas son indispensables al momento de implementar y mantener las ACL.

Permisos del sistema de archivos 
Con la seguridad del sistema de archivos, cada objeto en el sistema de archivos tiene asociada una lista de control de acceso (ACL). La ACL contiene una lista de cuentas (principales) autorizadas a acceder al recurso y detalla los permisos que tienen sobre él. El orden de las ACE en la ACL es importante para determinar los permisos efectivos de una cuenta específica. Las ACL pueden aplicarse mediante un sistema de archivos que admita permisos, como NTFS, ext3/ext4 o ZFS.


![[Pasted image 20250328121156.png]]

Description
La pantalla está dividida en tres secciones. La primera sección dice, Principal: todos, Tipo: Permitir, y Aplica a: Esta carpeta, subcarpetas y archivos. Un enlace para seleccionar un principal está presente en la parte superior. La segunda sección, permisos avanzados muestra tres casillas seleccionadas: leer atributos, leer atributos extendidos y leer permisos. Un enlace para mostrar permisos básicos está en la parte superior y un botón para borrar todo en la parte inferior. La tercera sección dice, añadir una condición para limitar el acceso. Al principal se le otorgarán los permisos especificados solo si se cumplen las condiciones. Un enlace para añadir una condición está presente en la parte inferior. Dos botones, OK (seleccionado) y Cancelar están presentes en la parte inferior derecha.



Configurar una entrada de control de acceso para una carpeta. (Captura de pantalla usada con el permiso de Microsoft).

Por ejemplo, en Linux existen tres permisos básicos:

- Lectura (r: read): es la capacidad de acceder y ver el contenido de un archivo o enumerar el contenido de un directorio.
- Escritura (w: write): es la capacidad de guardar cambios en un archivo, o de crear, renombrar y eliminar archivos en un directorio (también requiere ejecución).
- Ejecución (x: execute): es la capacidad de ejecutar un script, programa u otro archivo de software, o la capacidad de acceder a un directorio, o ejecutar un archivo desde dicho directorio, o bien realizar una tarea en ese directorio, como la búsqueda de archivos.

Estos permisos se pueden aplicar en el contexto del usuario propietario (u), una cuenta de grupo (g) y todos los demás usuarios (o). Una cadena de permisos enumera los permisos otorgados en cada uno de estos contextos:

d rwx r-x r-x home

La cadena anterior muestra que para el directorio (d), el propietario tiene permisos de lectura, escritura y ejecución, mientras que el grupo y otros usuarios tienen permisos de lectura y ejecución.

El comandochmod se utiliza para modificar permisos. Puede utilizarse en modo simbólico o modo absoluto. En modo simbólico, el comando trabaja de la siguiente manera:

chmod g+w, o-x home

El efecto de este comando es anexar el permiso de escritura al contexto del grupo y eliminar el permiso de ejecución de otro contexto. Por el contrario, el comando también puede utilizarse para reemplazar los permisos existentes. Por ejemplo, el siguiente comando aplica la configuración que se muestra en la primera cadena de permisos:

chmod u=rwx,g=rx,o=rx home

En modo absoluto, los permisos se asignan utilizando notación octal, donde r=4, w=2 y x=1. Por ejemplo, el siguiente comando tiene el mismo efecto:

chmod 755 home

En este ejemplo, el número 755 corresponde a los permisos asignados al usuario, al grupo y a otros usuarios. Los permisos del usuario se representan con el número 7, los permisos de grupo con el número 5, y también los de otros usuarios con el número 5. Los números se generan al sumar los valores asociados con r (lectura), w (escritura) y x (ejecución). La única combinación de valores que puede resultar en 7 es 4+2+1, es decir, r, w, x. Del mismo modo, la única combinación de valores que resulta en 5 es 4+1, es decir, r, x. Esto significa que el propietario tiene r, w y x, mientras que el grupo y otros tienen solo r y x. 

**Listas de aplicaciones permitidas y listas de bloqueos de aplicaciones**

Un elemento de la configuración de los puntos de conexión es una política de control de ejecución que define las aplicaciones que se pueden ejecutar o no.

Una lista de permitidos (o lista aprobada) deniega la ejecución a menos que el proceso esté explícitamente autorizado.
Una lista de bloqueo (o lista de denegación) por lo general permite la ejecución, pero prohíbe los procesos enumerados de manera explícita.
El contenido de las listas de permisos de bloqueo necesita actualizarse en respuesta a incidentes y a la continua detección y monitoreo de amenazas. 

La caza o detección de amenazas también puede provocar un cambio estratégico. Por ejemplo, si depende principalmente de denegaciones explícitas, pero sus sistemas están sujetos a numerosas intrusiones, deberá considerar la adopción de un modelo de “mínimos privilegios” y el uso de un enfoque de denegación a menos que esté especificado en la lista. Sin embargo, este tipo de cambio puede ser altamente disruptivo, por lo que debe ir precedido de una evaluación de riesgos y un análisis de impacto en el negocio.

El control de ejecución también puede ser complejo de configurar de manera efectiva, con muchas oportunidades para que los actores de amenaza evadan los controles. El análisis detallado del ataque podría sugerir la necesidad de cambios en el mecanismo existente o la implementación de un sistema más robusto.

Monitoreo
El monitoreo desempeña un papel fundamental en el fortalecimiento de los puntos de conexión, ayudando a aplicar y mantener las medidas de seguridad establecidas durante el proceso de endurecimiento. Una vez que los dispositivos están endurecidos, el monitoreo ayuda a garantizar que estas condiciones se mantengan vigentes. 

Los analistas de seguridad pueden detectar cambios que debilitan la configuración reforzada mediante un monitoreo continuo. Por ejemplo, si se detecta que un puerto previamente desactivado está abierto o un servicio que estaba desactivado se cambia a activado, las herramientas de monitoreo pueden alertar a los analistas del cambio, lo que podría indicar una intrusión. 

Además, el monitoreo puede aportar datos valiosos para fines de cumplimiento y auditoría. Los informes periódicos sobre el estado de los dispositivos de punto de conexión pueden verificar que las líneas bases de endurecimiento se hayan implementado y mantenido de manera efectiva, lo que respalda el cumplimiento de diversas regulaciones y estándares de la industria.

Aplicación de la configuración
La aplicación de la configuración describe los métodos utilizados para garantizar que los sistemas y dispositivos dentro de la red de una organización cumplan con las configuraciones de seguridad obligatorias. La aplicación de la configuración en general depende de algunas capacidades importantes.

Las líneas de base de configuración estandarizadas las definen organizaciones como el NIST, el CIS o la propia organización, y se utilizan como punto de referencia para definir cómo deben configurarse los sistemas y dispositivos.
Las herramientas de gestión de configuración automatizada se utilizan para aplicar y mantener de forma automática las líneas de base de configuración estandarizadas en todo el entorno.
El monitoreo continuo y los controles de cumplimiento son fundamentales para detectar desviaciones de las configuraciones obligatorias. 
Los procesos de administración de cambios  garantizan que los cambios de configuración sean revisados, probados y aprobados adecuadamente antes de su implementación.
La gestión de reglas de cortafuegos en la red de una organización es un ejemplo práctico de los ajustes de configuración que pueden beneficiarse de la aplicación rigurosa de políticas de configuración. Una organización puede utilizar una herramienta automatizada de gestión de configuración para garantizar que los cortafuegos de los dispositivos estén configurados de manera correcta, incluido el bloqueo de todo el tráfico entrante de forma predeterminada y permitiendo únicamente conexiones específicas y necesarias. El monitoreo continuo detecta cualquier cambio y los revierte en automático para aplicar la configuración segura y aprobada. 

Además, los controles de cumplimiento periódicos garantizan que los cortafuegos cumplan con las configuraciones aprobadas, y cualquier cambio debe ser revisado y aprobado a través de los procesos de administración de cambios  adecuados antes de su implementación.

Directiva de grupo
La directiva de grupo es una característica del sistema operativo Microsoft Windows y proporciona una gestión y configuración centralizadas de sistemas operativos, aplicaciones y ajustes del usuario en un entorno de Active Directory. Las directivas de grupo aplican configuraciones de seguridad, como las requeridas en una línea de base, mediante la aplicación de ajustes consistentes en todos los sistemas vinculados a directivas de grupo específicas. En términos generales, las directivas de grupo están vinculadas a contenedores llamados unidades organizacionales (OU) que por lo general contienen objetos de usuario y de equipo. Las directivas de grupo vinculadas a la unidad organizativa se aplican a todos los objetos contenidos dentro de la misma. 

Algunos ejemplos comunes de configuraciones de directivas de grupo incluyen políticas de contraseñas, derechos de usuario, configuraciones del cortafuegos de Windows, configuraciones de actualización del sistema, restricciones de instalación de software, entre otros. Aplicar configuraciones de forma centralizada mediante la directiva de grupo reduce los potenciales problemas relacionados con configuraciones incorrectas o inconsistentes.

SELinux
SELinux es una característica de seguridad del kernel de Linux que admite políticas de seguridad de control de acceso, incluso controles de acceso obligatorios (MAC). SELinux permite un control de permisos más granular sobre cada proceso y objeto del sistema dentro de un sistema operativo, lo que limita estrictamente los recursos a los que un proceso puede acceder y las operaciones que puede realizar. SELinux opera bajo el principio de que si un proceso o usuario no necesita acceso a los recursos para funcionar, se bloqueará para aislar mejor las aplicaciones, restringir el acceso al sistema y a los archivos, y prevenir que los programas maliciosos o defectuosos causen daños al sistema. Las capacidades de SELinux también están disponibles en el sistema operativo Android https://source.android.com/docs/security/features/selinux. Debido a las importantes diferencias arquitectónicas entre Linux y Android, la capacidad de SELinux en Android se habilita mediante SEAndroid para proporcionar funcionalidades similares, pero utilizando una base de código mantenida de forma independiente.