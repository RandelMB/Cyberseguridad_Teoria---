
Federation (federación) es la noción de que una red requiere ser accesible a más de un grupo específicamente definido de empleados. En el ámbito empresarial, es posible que una empresa tenga que brindar acceso a zonas de su red a socios, proveedores y clientes. La empresa puede administrar fácilmente las cuentas de sus empleados. Sin embargo, la gestión interna de las cuentas de cada proveedor o cliente podría ser más complicada. La federation (federación) significa que la empresa confía en las cuentas creadas y administradas por una red diferente. Otro ejemplo: en el mundo del consumo, un usuario quizás quiera utilizar tanto Google Workspace como Twitter. Si Google y Twitter establecen una red federada para brindar autenticación y autorización, el usuario podrá iniciar sesión en Twitter con las credenciales de Google o viceversa.

Una red local puede utilizar tecnologías como LDAP y Kerberos, que a menudo se implementan como una red de Active Directory de Windows, porque la administración de cuentas y dispositivos se puede centralizar. Al implementar la federación, el diseño de autenticación y autorización viene con más restricciones y requisitos adicionales para garantizar la interoperabilidad entre las diferentes plataformas. Es posible que las aplicaciones web no admitan Kerberos, mientras que las redes de terceros podrían no admitir la federación directa con Active Directory/LDAP. El diseño de estas redes en la nube probablemente requiera el uso de otros protocolos o marcos estándar para la interoperabilidad entre aplicaciones web.

Estos protocolos de federación interoperables utilizan una identidad basada en reclamos. Si bien la implementación técnica y la terminología son diferentes, el modelo general es similar al del SSO de Kerberos:

La entidad intenta acceder a un proveedor de servicios (SP). El proveedor de servicios redirige a la entidad a un identity provider (IdP) [proveedor de identidad (IdP)] para autenticarse.
La entidad se autentica con el proveedor de identidad y obtiene un reclamo, en forma de algún tipo de token o documento firmado por el IdP.
La entidad presenta el reclamo al proveedor de servicios. El SP puede validar que el IdP firmó el reclamo debido a su relación de confianza con el IdP.
El proveedor de servicios ahora puede conectar la entidad autenticada a su propia base de datos de cuentas para determinar sus permisos y otros atributos. Quizás pueda consultar los atributos del perfil de cuenta de usuario en poder del IdP, si la entidad autorizó este tipo de acceso.
![[Pasted image 20241118140426.png]]


Description
Los 6 pasos son los siguientes 1. El proveedor de servicios (SP) y el proveedor de identidad (IdP) tienen una relación de confianza preestablecida. 2. El usuario inicia una sesión con el SP. 3. El SP redirige al usuario al IdP para autenticarse. 4. El usuario se autentica en el IdP. 5. El IdP emite un token de reclamación al usuario. 6. 6. El usuario presenta el testigo de reclamación al SP y se le asocia una cuenta legítima y un conjunto de autorizaciones.

Descripción general de la administración de identidad federada. (Imágenes © 123RF.com.)

