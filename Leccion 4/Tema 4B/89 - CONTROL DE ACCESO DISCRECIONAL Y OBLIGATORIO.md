A una cuenta de usuario que se haya autenticado se le pueden asignar derechos y permisos en redes, computadoras y datos. Un modelo de control de acceso describe los principios que rigen la forma en que los usuarios reciben los derechos. 

Control de acceso discrecional
El control de acceso discrecional (DAC) se basa en la primacía del propietario del recurso. En un modelo DAC, cada recurso tiene un propietario. Si bien la propiedad se puede asignar a otro usuario, el propietario crea un archivo o servicio. Este tiene control total sobre el recurso y puede modificar su lista de control de acceso (ACL) para otorgar derechos a otros.

El DAC es el modelo más flexible y actualmente se implementa de forma generalizada en seguridad informática y de redes. En seguridad de sistemas de archivos, es el modelo que se utiliza de forma predeterminada para la mayoría de las distribuciones de UNIX/Linux y Microsoft Windows. Al ser el modelo más flexible, también es el más débil porque hace que la administración centralizada de las políticas de seguridad sea más difícil de aplicar. También es el más propenso a verse comprometido, ya que es vulnerable a las amenazas internas y al abuso de las cuentas comprometidas.

Control de acceso obligatorio
El modelo DAC expone la información a la amenaza de verse comprometida a través de las cuentas de propietario con privilegios. El control de acceso obligatorio (MAC) se basa en los niveles de autorización de seguridad. En lugar de definir las ACL en los recursos, a cada objeto se le asigna una etiqueta de clasificación y a cada sujeto se le otorga un nivel de autorización. En un sistema multinivel orientado a la confidencialidad, se permite a los sujetos leer objetos clasificados en su propio nivel de autorización o inferior. Por ejemplo, un usuario con autorización de Ultrasecreto podría leer datos con etiquetas de clasificación de Ultrasecreto, Secreto y Confidencial. Un usuario con autorización de Secreto solo puede acceder a los niveles Secreto y Confidencial.

El etiquetado de objetos y la concesión de autorización se llevan a cabo mediante reglas preestablecidas. El punto crítico es que estas reglas no son discrecionales y ninguna cuenta de sujeto puede cambiarlas. 

Como un sistema de clasificación simple es inflexible, la mayoría de los modelos de MAC agregan el concepto de acceso basado en compartimentos. Por ejemplo, un archivo de datos puede tener la clasificación de Secreto y estar ubicado en el compartimiento de RR. HH. Solo los sujetos con autorización de Secreto y RR. HH. pueden acceder al archivo.

En MAC, los usuarios con autorización alta no pueden redactar documentos con autorización baja. Es lo que se conoce como “write up” (escribir hacia arriba), “read down” (leer hacia abajo). Esto evita, por ejemplo, que un usuario con autorización de Ultrasecreto vuelva a publicar algunos datos con clasificación Ultrasecreto a los que puede acceder con autorización de Secreto.

