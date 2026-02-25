Los ataques como la repetición de sesión, la CSRF y la mayoría de los tipos de XSS son ataques del lado del cliente. Esto significa que ejecutan un código arbitrario en el navegador. Un ataque del lado del servidor hace que el servidor realice algún procesamiento o ejecute una secuencia de comandos o consulta de una manera que no está autorizada por el diseño de la aplicación. La mayoría de los ataques del lado del servidor dependen de algún tipo de ataque de inyección.

Un ataque de inyección explota alguna forma insegura en la que la aplicación procesa solicitudes y consultas. Por ejemplo, una aplicación puede permitir que un usuario vea su perfil con una consulta de base de datos que debería devolver el registro único para el perfil de ese usuario. Una aplicación vulnerable a un ataque de inyección podría permitir que el actor de amenaza obtenga los registros de todos los usuarios, o que cambie los campos del registro cuando solo se supone que puede leerlos.

El XSS persistente y el abuso de consultas y parámetros SQL tratados anteriormente en el curso son ambos tipos de ataque de inyección. Existen varios otros tipos de ataques de inyección que representan amenazas graves para las aplicaciones web y la infraestructura.

Inyección de lenguaje de marcado extensible
Las aplicaciones usan Extensible Markup Language (XML) (lenguaje de marcado extensible [XML]) para la autenticación y las autorizaciones, así como para otros tipos de intercambio y carga de datos. Los datos enviados a través de XML sin cifrado ni validación de entrada son vulnerables a spoofing (suplantación de identidad), a la falsificación de solicitudes y a la inyección de datos o código arbitrarios. Por ejemplo, un ataque de Entidad externa XML (XXE) introduce una solicitud de un recurso local:

<?xml version=\"1.0\" encoding=\"UTF-8\"?>

<!DOCTYPE foo [<!ELEMENT foo ANY ><!ENTITY bar SYSTEM \"file:///etc/config\"> ]>

<bar>&bar;</bar>

Esto define una entidad llamada bar que se refiere a una ruta de archivo local. Un ataque exitoso devolverá el contenido de /etc/config como parte de la respuesta.

Inyección de Protocolo ligero de acceso a directorios (LDAP) 
El Protocolo ligero de acceso a directorios [LDAP] es otro ejemplo de lenguaje de consulta. LDAP se utiliza específicamente para leer y escribir bases de datos de directorios de red. Un actor de amenaza podría explotar el acceso no autenticado o una vulnerabilidad en una aplicación cliente para enviar consultas LDAP arbitrarias. Esto podría permitir que se creen o eliminen cuentas, o que el atacante cambie las autorizaciones y los privilegios.

Los filtros LDAP se construyen a partir de pares de atributos (name=value) delimitados por paréntesis y los operadores lógicos AND (&) y OR (|). La adición de parámetros de filtro como entrada no depurada puede omitir los controles de acceso. Por ejemplo, si un formulario web se autentica en un directorio LDAP con las credenciales válidas Bob y Pa$$w0rd, puede construir una consulta como esta a partir de la entrada del usuario: 

(&(username=Bob)(password=Pa$$w0rd))

Ambos parámetros deben ser verdaderos para que se acepte el inicio de sesión. Si la entrada del formulario no se depura, el actor de amenaza podría omitir la verificación de contraseña ingresando un nombre de usuario válido más una cadena de filtro LDAP, como bob (&)). Esto hace que el filtro de contraseña se caiga por una condición que siempre es verdadera:

(&(username=Bob)(&))