

Una política de directory service (servicio de directorio) almacena información sobre los usuarios, las computadoras, los grupos/las funciones de seguridad y los servicios. Cada objeto en el directorio tiene una serie de atributos. El esquema del directorio describe los tipos de atributos, la información que contienen y si son obligatorios u opcionales. Para que los productos de diferentes proveedores puedan operar entre ellos, la mayoría de los servicios de directorio se basan en el Lightweight Directory Access Protocol (LDAP) [(protocolo ligero de acceso a directorios (LDAP)], que se desarrolló a partir de un estándar llamado X.500. 

Dentro de un directorio tipo X.500, un distinguished name (DN) [nombre distinguido (DN)] es una colección de atributos que definen un identificador único para cualquier recurso dado. Un nombre distinguido está formado por pares de atributos-valores, separados por comas. El atributo más específico se indica primero y los atributos sucesivos se vuelven más amplios progresivamente. Este atributo más específico es el nombre distinguido relativo, ya que identifica de manera única el objeto dentro del contexto de los valores de atributo sucesivos (primarios).

![[Pasted image 20241118140149.png]]



Description
El menú en la parte superior dice, archivo, acción, vista y ayuda. Debajo, un panel a la izquierda muestra opciones para la edición de ADSI, con la opción CN igual a usuarios seleccionada. La tabla en el centro lista los nombres, clases y nombres distinguidos. El nombre, CN igual a bobby; clase, usuario; y nombre distinguido, CN igual a bobby, CN igual a usuarios, DC igual a aula, DC igual a local está seleccionado. Un panel a la derecha titulado acciones lista las acciones, CN igual a usuarios y CN igual a bobby, cada uno seguido por una opción más.



Exploración de objetos en un esquema de LDAP de Active Directory. (Captura de pantalla usada con el permiso de Microsoft).

Algunos de los atributos que se utilizan habitualmente incluyen el nombre común (CN), la unidad organizacional (OU), la organización (O), el país (C) y el componente de dominio (DC). 

Por ejemplo, el nombre distinguido de un servidor web operado por Widget en el Reino Unido podría ser el siguiente:

CN=WIDGETWEB, OU=Marketing, O=Widget, C=UK, DC=widget, DC=foo