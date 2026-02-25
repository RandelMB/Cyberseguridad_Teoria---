Los ataques dirigidos a los sistemas de autenticación a menudo dependen de que el sistema use criptografía débil.

Ataques de degradación
Un ataque de degradación hace que un servidor o cliente use un protocolo de especificación más baja con cifrados y longitudes de clave más débiles. Por ejemplo, una combinación de un ataque en ruta y de degradación en HTTPS podría intentar forzar al cliente a usar una versión débil de la seguridad de la capa de transporte (TLS) o incluso degradar al protocolo heredado de capa de sockets seguros (SSL). Esto hace que sea más fácil para un actor de amenaza forzar el uso de suites de cifrado débiles y falsificar la firma de una autoridad de certificación en la que el cliente confía.

Se utiliza un tipo de ataque de degradación para atacar a Active Directory. Un ataque Kerberoasting (ataque contra Kerberos) intenta descubrir las contraseñas que protegen las cuentas de servicio obteniendo tickets de servicio y sometiéndolos a ataques de descifrado de contraseñas por fuerza bruta. Si la parte de credenciales del ticket de servicio está encriptada mediante AES, es muy difícil usar la fuerza bruta. Si el ataque puede hacer que el servidor devuelva el ticket utilizando un cifrado RC4 débil, es más probable que el descifrador de contraseñas pueda extraer la contraseña del servicio.

Es probable que se encuentre evidencia de ataques de degradación en los registros del servidor o en los sistemas de detección de intrusiones.

Ataques de colisión
Una colisión es cuando una función o implementación de hash criptográfico débil permite la generación del mismo valor corto (digest) para dos textos no codificados diferentes. Un ataque de colisión explota esta vulnerabilidad para falsificar una firma digital. El ataque trabaja de la siguiente manera:

El atacante crea un documento malicioso y un documento benigno que producen el mismo valor hash. El atacante envía el documento benigno para que el objetivo lo firme.
Luego, el atacante elimina la firma del documento benigno y la agrega al documento malicioso, falsificando la firma del objetivo.
Un ataque de colisión podría usarse para falsificar un certificado digital para falsificar un sitio web de confianza o para hacer que parezca que el malware troyano se deriva de un editor de confianza.

Ataques de cumpleaños
Un ataque de colisión depende de poder crear un documento malicioso que genere el mismo hash que el documento benigno. Algunos ataques de colisión dependen de poder manipular la forma en que se genera el hash. Un ataque de cumpleaños es un medio para explotar las colisiones en las funciones hash a través de la fuerza bruta. La fuerza bruta significa intentar todas las combinaciones posibles hasta que se logre una exitosa. El ataque lleva el nombre de la paradoja del cumpleaños. Esta paradoja muestra que el tiempo computacional requerido para forzar una colisión podría ser menor de lo esperado. 

La paradoja del cumpleaños pregunta qué tan grande debe ser un grupo de personas para que la posibilidad de que dos de ellos compartan un cumpleaños sea del 50 %. La respuesta es 23, pero las personas que no son conscientes de la paradoja a menudo responden alrededor de 180 (365/2). El punto es que las posibilidades de que alguien comparta un cumpleaños en particular son pequeñas, pero las posibilidades de que dos personas en un grupo compartan cualquier fecha de nacimiento en un año calendario mejoran cada vez más a medida que agrega más personas: 1 – (365 * (365 − 1) * (365 – 2) ... * (365 – (N − 1)/365N).

Para explotar la paradoja, el atacante crea múltiples documentos maliciosos y benignos, ambos con cambios menores (puntuación, espacios adicionales, etc.). Dependiendo de la longitud del hash y de los límites de los cambios no sospechosos que se puedan introducir, si el atacante puede generar suficientes variaciones, la posibilidad de que los resultados del hash coincidan puede ser superior al 50 %. Esto significa efectivamente que una función hash que genera hash de 128 bits puede ser atacada por un mecanismo que puede generar 264 variaciones. Computar 264 variaciones tomará mucho menos tiempo que computar 2128 variaciones.

Los ataques que explotan las colisiones son difíciles de lanzar, pero el principio detrás del ataque informa la necesidad de utilizar métodos de autenticación que utilicen cifrados fuertes e implementaciones sólidas de protocolos y software.