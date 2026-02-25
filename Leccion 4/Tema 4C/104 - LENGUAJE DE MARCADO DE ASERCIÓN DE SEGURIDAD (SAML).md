

Una red o nube federada necesita protocolos y tecnologías específicos para implementar las confirmaciones de identidad de los usuarios y transmitir reclamos entre la entidad, la parte de confianza y el proveedor de identidad. El Security Assertion Markup Language (SAML) [lenguaje de marcado de aserción de seguridad (SAML)] es una de esas soluciones. Las afirmaciones (reclamos) de SAML están escritas en eXtensible Markup Language (XML) (lenguaje de marcado extensible). Las comunicaciones se establecen mediante HTTP/HTTPS y el Simple Object Access Protocol (SOAP) [protocolo simple de acceso a objetos (SOAP)]. Los tokens seguros se firman mediante la especificación de firma XML. El uso de una firma digital le permite a la parte de confianza confiar en el proveedor de identidad.

Un ejemplo de una implementación de SAML es Amazon Web Services (AWS), que funciona como proveedor de servicios de SAML. Esto les permite a las empresas que utilizan AWS desarrollar aplicaciones en la nube para administrar las identidades de usuario de sus clientes y proporcionarles permisos en AWS sin tener que crear cuentas en esta plataforma.

<samlp:Response xmlns:samlp=\"urn:oasis:names:tc:SAML:2.0:protocol\"

xmlns:saml=\"urn:oasis:names:tc:SAML:2.0:assertion\" ID=\"200\" Version=\"2.0\"

IssueInstant=\"2020-01-01T20:00:10Z \" Destination=\"https://sp.foo/saml/acs\" InResponseTo=\"100\".

 <saml:Issuer>https://idp.foo/sso</saml:Issuer>

 <ds:Signature>...</ds:Signature>

 <samlp:Status>...(success)...</samlp:Status.

<saml:Assertion xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-instance\"

xmlns:xs=\"http://www.w3.org/2001/XMLSchema\" ID=\"2000\" Version=\"2.0\"

IssueInstant=\"2020-01-01T20:00:09Z\">

<saml:Issuer>https://idp.foo/sso</saml:Issuer>

<ds:Signature>...</ds:Signature>

 <saml:Subject>...

 <saml:Conditions>...

 <saml:AudienceRestriction>...

 <saml:AuthnStatement>...

 <saml:AttributeStatement>

 <saml:Attribute>...

 <saml:Attribute>...

 </saml:AttributeStatement>

 </saml:Assertion>

</samlp:Response>

