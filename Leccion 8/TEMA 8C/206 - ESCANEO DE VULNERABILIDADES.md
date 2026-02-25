


La gestión de vulnerabilidades es una piedra angular de las prácticas modernas de ciberseguridad destinadas a identificar, clasificar, remediar y mitigar las vulnerabilidades dentro de un sistema o red. Un aspecto fundamental de la gestión de vulnerabilidades es el escaneo de vulnerabilidades, un proceso sistemático de sondeo de un sistema o red con el que se utilizan herramientas de software especializadas para detectar debilidades de seguridad. Los escaneos de vulnerabilidades se realizan a nivel interno y externo para inventariar las vulnerabilidades desde diferentes puntos de vista de la red. Las vulnerabilidades identificadas durante el escaneo se clasifican y priorizan para su corrección por parte de los equipos de operaciones de seguridad. 

El escaneo de vulnerabilidades también es compatible con la seguridad de las aplicaciones, ya que ayuda a localizar e identificar errores de configuración y parches faltantes en el software. Las técnicas avanzadas de escaneo de vulnerabilidades centradas en la seguridad de las aplicaciones incluyen escáneres de aplicaciones especializados, marcos de prueba de lápiz y pruebas de código estático y dinámico. 

Las herramientas de escaneo de vulnerabilidades como openVAS y Nessus son herramientas populares que ofrecen una amplia gama de características diseñadas para analizar equipos de red, sistemas operativos, bases de datos, cumplimiento de parches, configuraciones y muchos otros sistemas. Si bien estas herramientas son muy efectivas, el análisis de seguridad de las aplicaciones garantiza enfoques mucho más especializados. Existen varias herramientas especializadas para analizar en mayor detalle cómo están diseñadas las aplicaciones para operar y pueden localizar vulnerabilidades que por lo general no se identifican mediante los enfoques de escaneo generalizados.

Escáner de vulnerabilidades de red
Un escáner de vulnerabilidades de red, como Tenable Nessus (tenable.com/products/nessus) u OpenVAS (openvas.org), está diseñado para probar hosts de red, incluidos PC clientes, dispositivos móviles, servidores, enrutadores y switches. Examina los sistemas, aplicaciones y dispositivos locales de una organización y compara los resultados del análisis con las plantillas de configuración y las listas de vulnerabilidades conocidas. Los resultados típicos de una evaluación de vulnerabilidades identificarán los parches faltantes, las desviaciones de las plantillas de configuración de referencia y otras vulnerabilidades relacionadas.


Description
Escáner de vulnerabilidades OpenVAS de Greenbone con interfaz de aplicación web Security Assistant instalada en Kali Linux. (Captura de pantalla utilizada con el permiso de Greenbone Networks, http://www.openvas.org).

Los escáneres dependen de una base de datos de vulnerabilidades de configuración y software conocidas. La herramienta compila un informe en su base de datos sobre cada vulnerabilidad que se encontró presente en cada host. Cada vulnerabilidad identificada se clasifica y se le asigna una advertencia de impacto. La mayoría de las herramientas también sugieren técnicas de remediación. Esta información es sumamente confidencial, por lo que el uso de estas herramientas y la distribución de los informes producidos deben restringirse para que solo puedan acceder los anfitriones y cuentas de usuario autorizados.

Los escáneres de vulnerabilidades de red están configurados con información sobre vulnerabilidades conocidas y debilidades de configuración para hosts de red típicos. Con estos escáneres se podrán hacer pruebas en sistemas operativos comunes, aplicaciones de escritorio y algunas aplicaciones de servidor. Si bien esto es útil para el escaneo de propósito general, para algunos tipos de aplicaciones se puede necesitar un análisis más riguroso.

Escaneos acreditados y no acreditados

Un escaneo no acreditado es aquel que procede dirigiendo paquetes de prueba a un host sin iniciar sesión en el sistema operativo o la aplicación. La vista es la que el host expone a un usuario sin privilegios en la red. Las rutinas de prueba pueden incluir cosas como el uso de contraseñas predeterminadas para cuentas de servicio e interfaces de administración de dispositivos, pero no se les da acceso privilegiado. Si bien puede descubrir más debilidades con un análisis acreditado, a veces querrá reducir su enfoque al de un atacante que no tiene permisos específicos de alto nivel o acceso administrativo total. El escaneo no acreditado es la técnica más adecuada para la evaluación externa del perímetro de la red o para realizar el escaneo de aplicaciones web.

En un escaneo acreditado se le da una cuenta de usuario con derechos de inicio de sesión a varios hosts, además de cualquier otro permiso que sea apropiado para las rutinas de prueba. Este tipo de pruebas permite un análisis mucho más profundo, en especial para detectar cuándo las aplicaciones o la configuración de seguridad pueden estar mal configuradas. Muestra lo que un ataque interno, o un ataque con una cuenta de usuario comprometida, puede lograr. Un escaneo acreditado es un tipo de escaneo más intrusivo que el escaneo no acreditado.


Description
La barra de menú en la parte superior tiene opciones de Gestión de Escaneo, Gestión de Activos, Gestión de SecInfo, Configuración, Extras, Administración y Ayuda. La nueva ventana de credenciales tiene casillas para ingresar los siguientes detalles:



Nombre: Dominio del Aula.

Inicio de sesión: aula\Administrador.

Comentario (opcional): en blanco

Autogenerar credencial con un botón de radio no seleccionado.

El botón de radio para Contraseña está seleccionado y la contraseña se ingresa en la casilla junto a él.

Par de claves con un botón de radio no seleccionado.

Clave privada seguida de un botón de explorar.

Frase de paso: en blanco

Un botón para crear credencial está en la parte inferior derecha.

	Configuración de credenciales para su uso en definiciones de destino (alcance) en OpenVAS de Greenbone instaladas en Kali Linux. (Captura de pantalla utilizada con el permiso de Greenbone Networks, http://www.openvas.org).

**Aplicaciones y escáneres de aplicaciones web**
De manera similar, el análisis de vulnerabilidades de aplicaciones describe un método especializado de escaneo de vulnerabilidades para identificar debilidades de aplicaciones de software. Esto incluye el análisis estático (revisar el código de la aplicación sin ejecutarlo) y el análisis dinámico (pruebas de aplicaciones en ejecución), que pueden identificar problemas como entradas no validadas, controles de acceso rotos y vulnerabilidades de inyección SQL. El análisis de vulnerabilidades de las aplicaciones por lo general se maneja por separado del análisis general de vulnerabilidades debido a la naturaleza única de las aplicaciones de software y los tipos específicos de vulnerabilidades que introducen. El análisis general de vulnerabilidades está diseñado para detectar debilidades en todo el sistema o en toda la red, como por ejemplo, el software desactualizado o los firewalls mal configurados. 

En cambio, el escaneo de vulnerabilidades de aplicaciones evalúa la codificación y el comportamiento de aplicaciones de software individuales. Busca problemas como las secuencias de comandos entre sitios (XSS), la inyección de SQL y las referencias de objetos directos inseguras exclusivas de las aplicaciones de software. Para estas vulnerabilidades específicas de la aplicación se requieren herramientas y técnicas especializadas de identificación y mitigación, que, por lo general, son diferentes a las herramientas de escaneo utilizadas en el escaneo general de vulnerabilidades. Las aplicaciones con frecuencia tienen sus propios ciclos de lanzamiento y actualización, separados del resto del entorno, lo que requiere un proceso de gestión de vulnerabilidades más específico. 

**Monitoreo de paquetes**
Otra capacidad importante en las prácticas de evaluación de vulnerabilidades de las aplicaciones incluye el monitoreo de paquetes. El monitoreo de paquetes está asociado con la identificación de vulnerabilidades porque rastrea y evalúa la seguridad de los paquetes de software, las bibliotecas y las dependencias de terceros utilizados dentro de una organización, para garantizar que estén actualizados y libres de vulnerabilidades conocidas que los actores maliciosos podrían explotar. El monitoreo de paquetes está asociado con la gestión de la lista de materiales de software (SBOM) y con las prácticas de gestión de riesgos de la cadena de suministro de software.

En un entorno empresarial, el monitoreo de paquetes por lo general se logra a través de herramientas automatizadas y políticas de gobernanza. Las herramientas automatizadas de análisis de la composición del software (SCA) rastrean y monitorean los paquetes de software, las bibliotecas y las dependencias utilizadas en la base de código de una organización. Estas herramientas pueden identificar automáticamente paquetes obsoletos o con vulnerabilidades conocidas y sugerir actualizaciones o reemplazos. Funcionan mediante la comparación continua del inventario de software de la organización con varias bases de datos de vulnerabilidades conocidas, como la Base de datos nacional de vulnerabilidades (NVD) o avisos específicos del proveedor. 

Además de estas herramientas, las organizaciones suelen implementar políticas de gobernanza en torno al uso del software. Estas políticas pueden requerir auditorías periódicas de los paquetes de software, procesos de aprobación para agregar nuevos paquetes o bibliotecas, y procedimientos para actualizar o aplicar parches al software cuando se identifican vulnerabilidades. 