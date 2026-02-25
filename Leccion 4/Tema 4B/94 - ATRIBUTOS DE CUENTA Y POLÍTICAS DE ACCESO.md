
Una cuenta de usuario se define mediante un identificador de seguridad (SID), un nombre y una credencial. Cada cuenta también está asociada con un perfil. El perfil se puede definir con atributos de identidad personalizados que describen al usuario, como un nombre completo, dirección de correo electrónico, número de contacto, departamento, entre otros. El perfil puede admitir medios como una imagen de cuenta.

Además de los atributos, el perfil por lo general proporcionará una ubicación para almacenar archivos de datos generados por el usuario (una carpeta de inicio). El perfil también puede almacenar la configuración por cuenta para aplicaciones de software. 

A cada cuenta se le pueden asignar permisos sobre los archivos y otros recursos de la red y políticas de acceso o privilegios sobre el uso y la configuración de los hosts de la red. Estos permisos pueden asignarse directamente a la cuenta o heredarse a través de la pertenencia a un grupo o función de seguridad. Las políticas de acceso determinan cosas como el derecho a iniciar sesión en un equipo de manera local o a través de un escritorio remoto, instalar software, cambiar la configuración de la red, etc.

En una red de Active Directory de Windows, las políticas de acceso pueden configurarse mediante objetos de directiva de grupo (GPO). Los GPO se pueden utilizar para configurar los derechos de acceso para las cuentas de usuario/grupo/función. Los GPO se pueden vincular a los límites administrativos de red en Active Directory, como sitios, dominios y  unidades  organizacionales (OU). 

![[Pasted image 20241118135738.png]]

Description
El menú en la parte superior dice, archivo, acción, vista y ayuda. Debajo, un panel a la izquierda muestra opciones para la política de dominio de soporte 515, con la asignación de derechos de usuario seleccionada. A la derecha, se enumeran varias políticas y configuraciones de políticas. Se selecciona la política de permitir el inicio de sesión a través de servicios de escritorio remoto con la configuración de la política no definida.



Configuración de políticas y derechos de acceso mediante objetos de directiva de grupo en Windows Server 2016. (Captura de pantalla utilizada con el permiso de Microsoft).

