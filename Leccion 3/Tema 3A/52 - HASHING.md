
<p align="justify">Un algoritmo de hashing criptográfico produce una cadena de bits de longitud fija a partir de un texto plano de entrada que puede ser de cualquier longitud. El resultado puede denominarse hash o resumen de mensaje. La función está diseñada para que sea imposible recuperar los datos de texto plano del resumen (unidireccional) y para que sea poco probable que diferentes entradas produzcan la misma salida (una colisión).</p>

El algoritmo de hashing se utiliza para demostrar la integridad. Por ejemplo, Bob y Alice pueden comparar los valores utilizados para una contraseña de la siguiente manera:

1. Bob(Server) tiene un resumen calculado a partir de la contraseña de texto plano de Alice(User). Bob no puede recuperar el valor de la contraseña en texto plano a partir del hash.
2. Cuando Alice necesita autenticarse con Bob, escribe su contraseña, la convierte en un hash y envía el resumen a Bob.
3. Bob compara el resumen de Alice con el valor hash del archivo. Si coinciden, Bob puede estar seguro de que Alice escribió la misma contraseña.

Además de comparar los valores de la contraseña, se puede usar un hash de un archivo para verificar la integridad de ese archivo después de la transferencia:

1. Alice ejecuta una función hash en el archivo setup.exe de su producto. Publica el resumen en su sitio web con un enlace de descarga del archivo.
2. Bob descarga el archivo setup.exe y hace una copia del resumen.
3. Bob ejecuta la misma función hash en el archivo setup.exe descargado y lo compara con el valor de referencia que Alice publicó. Si coincide con el valor publicado en el sitio web, Bob supone que el archivo tiene integridad.
4. Tenga en cuenta que Mallory podría sustituir el archivo de descarga por un archivo malicioso. Sin embargo, Mallory no puede cambiar el hash de referencia.
5. Esta vez, Bob calcula un hash, pero no coincide, lo que lo lleva a sospechar que el archivo fue manipulado.


![[Pasted image 20241107142241.png]]


<u>Descripción</u>
Los pasos involucrados son los siguientes:

- Alice publica un archivo ("*HelloWorld*") y el valor hash de referencia.
- Bob descarga el archivo ("*HelloWorld*") y registra el valor hash de referencia.
- Bob calcula un hash y lo compara con el valor de referencia.
- Mallory inyecta una descarga maliciosa, pero no puede cambiar el valor hash de referencia.
- Bob calcula un hash, pero no coincide con la referencia, por lo que rechaza el archivo.

*Confirmación de la descarga de un archivo mediante hashes criptográficos (Imágenes © 123RF.com)*

Existen dos implementaciones populares de algoritmos de hash:

- Algoritmo de hash seguro (SHA): es considerado el algoritmo más fuerte. Existen variantes que producen resultados de diferentes tamaños, y los resúmenes más largos se consideran más seguros. La variante más popular es SHA256, que produce un resumen de 256 bits.
- Algoritmo de resumen de mensajes #5 (MD5): prooduce un resumen de 128 bits. MD5 no se considera tan seguro como SHA256, pero podría ser necesario para la compatibilidad entre los productos de seguridad.

![[Pasted image 20241107142504.png]]

