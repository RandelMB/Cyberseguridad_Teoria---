Los ataques de secuestro/reproducción de sesión, falsificación e inyección son difíciles de identificar, pero es probable que los puntos de partida para la detección sean el análisis de URL y el registro de acceso del servidor web.

Análisis del localizador de recursos uniforme [URL]
Además de apuntar a la ubicación del host o servicio en Internet (por nombre de dominio o dirección IP), un localizador de recursos uniforme [URL] puede codificar alguna acción o datos para enviar al host del servidor. Este es un vector común para la actividad maliciosa. 

![[Pasted image 20250404083322.png]]

Description
http colon slash slash trusted dot foo slash es la URL de un dominio de confianza con un script vulnerable. upload dot php signo de interrogación post igual a es la consulta.



Porcentaje 3Cscript Porcentaje 3D Porcentaje 27http Porcentaje 3A Porcentaje 2F Porcentaje 2F es la codificación porcentual. zyxcba dot foo Porcentaje 2Frat Porcentaje 2Ejs Porcentaje 27 Porcentaje 3E Porcentaje 3C slash script Porcentaje 3E es el dominio ofuscado que aloja el script malicioso.





Análisis del localizador de recursos uniforme [URL]

Como parte del análisis de URL, es importante comprender cómo funciona HTTP. Una sesión HTTP comienza con un cliente (un agente de usuario, como un navegador web) que realiza una solicitud a un servidor HTTP. La conexión establece una conexión TCP. Esta conexión TCP se puede utilizar para múltiples solicitudes, o un cliente puede iniciar nuevas conexiones TCP para diferentes solicitudes. Por lo general, una solicitud comprende un método, un recurso (como una ruta de URL), un número de versión, encabezados y cuerpo. Los principales métodos son los siguientes: 

GET: recuperar un recurso.
POST: enviar datos al servidor para su procesamiento por el recurso solicitado.
PUT: crear o reemplazar el recurso. 
Los datos se pueden enviar a un servidor a través de un método POST o PUT y los encabezados y el cuerpo HTTP, o mediante la codificación de los datos dentro de la URL utilizada para acceder al recurso. Los datos enviados a través de una URL están delimitados por el caracter “?”, que sigue la ruta del recurso. Los parámetros de consulta suelen formatearse como uno o varios pares nombre=valor, con et (símbolo \"&\"), que delimitan cada par. 

La respuesta del servidor comprende el número de versión y un código de estado y mensaje, además de encabezados opcionales y cuerpo del mensaje. Un código de respuesta HTTP es el valor de encabezado devuelto por un servidor cuando un cliente solicita una URL, como 200 para “OK” o 404 para “No encontrado”.

Codificación de porcentaje
Una URL solo puede contener caracteres no reservados y reservados del conjunto estándar. Los caracteres reservados se utilizan como delimitadores dentro de la sintaxis de la URL y solo deben usarse sin codificar para esos fines. Los caracteres reservados son los siguientes:

: / ? # [ ] @ ! $ & ' ( ) * + , ; = 

También hay caracteres que no son seguros y que no se pueden utilizar en una URL. Los caracteres de control, como terminación de cadena nula, retorno de carro, avance de línea, final de archivo y tabulador, no son seguros. La codificación porcentual permite que un agente de usuario envíe cualquier carácter seguro o inseguro (o datos binarios) al servidor dentro de la URL. Sus usos legítimos son codificar caracteres reservados dentro de la URL cuando no son parte de la sintaxis de la URL y enviar caracteres Unicode. La codificación porcentual se puede utilizar de forma incorrecta para ofuscar la naturaleza de una URL (codificar caracteres no reservados) y enviar entradas maliciosas. 