

Debería poder evaluar el diseño y el uso de los productos de autenticación en términos de cumplimiento de los requisitos de confidencialidad, integridad y disponibilidad. Con una guía de configuración específica del producto, debería ser capaz de implementar protocolos y tecnologías como MFA, autenticación sin contraseña, SSO de Kerberos y gestión de identidad federada.

DIRECTRICES PARA LA IMPLEMENTACIÓN DE LA ADMINISTRACIÓN DE IDENTIDAD Y ACCESO 

Siga estas directrices cuando implemente controles de autenticación:

- Evalúe los requisitos de diseño para la confidencialidad, la integridad y la disponibilidad dado el contexto de la solución de autenticación (por ejemplo, red privada, web pública, puerta de enlace VPN o instalaciones del sitio físico).
- Determine si se requiere autenticación de multifactores (MFA) o autenticación sin contraseña, y qué token de hardware o tecnologías biométricas cumplirían con el requisito:
	- Entre los factores de propiedad se incluyen tarjetas inteligentes, claves/llaveros OTP y claves de seguridad, y aplicaciones de autenticación OTP instaladas en un dispositivo de confianza.
	- Las tecnologías biométricas incluyen las huellas digitales y el rostro, con una eficacia determinada por métricas como FAR, FRR, CER, velocidad y accesibilidad.
	- La verificación de dos pasos puede proporcionar un token adicional a un dispositivo o cuenta de confianza a través de SMS, llamada telefónica, correo electrónico o notificación emergente.
	- Los administradores de contraseñas pueden proporcionar una mayor seguridad para la autenticación de contraseñas.
- Establezca los requisitos para el control de acceso entre los modelos discrecionales, obligatorios, basados en funciones y en atributos, y si el alcance debe incluir servicios federados (por ejemplo, en las instalaciones y en la nube).
- Configure cuentas/funciones y recursos con la configuración de permisos adecuada utilizando el principio del privilegio mínimo.
- Configure las políticas de la cuenta para proteger la integridad:
	- Políticas de credenciales para garantizar la protección de cuentas estándar y con privilegios, incluida la selección segura de contraseñas.
	- Políticas de la cuenta para aplicar el acceso condicional en función de la ubicación y la hora.
- Establezca procedimientos de aprovisionamiento para emitir identidades digitales y credenciales de cuenta de forma segura.
- Establezca procedimientos de baja para eliminar los privilegios de acceso cuando los empleados o contratistas abandonen la empresa.
- Implemente SAML u OAuth para facilitar el inicio de sesión único entre redes locales y servicios/aplicaciones en la nube.