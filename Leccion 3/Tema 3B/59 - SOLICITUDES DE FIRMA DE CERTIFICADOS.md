
---
## Proceso de registro con una Autoridad Certificadora (CA)

El **registro** es el procedimiento mediante el cual los usuarios finales crean una cuenta con la CA y obtienen autorización para solicitar certificados.  
Los pasos exactos dependen de cómo esté implementada la CA, pero en general siguen este flujo:

### 1. **Autorización y verificación de identidad**
- La CA define cómo se **autoriza** a los usuarios y cómo se **verifica su identidad**.    
- En un **dominio de Windows**, los usuarios y dispositivos suelen inscribirse automáticamente autenticándose mediante **Active Directory**.    
- En el caso de una **CA de terceros**, esta puede efectuar múltiples verificaciones para asegurarse de que el solicitante es realmente quien dice ser.    
- Es fundamental para la CA emitir certificados únicamente a sujetos legítimos, ya que su **reputación** depende de ello.   

---

## Solicitud de un certificado digital

Cuando un sujeto desea obtener un certificado, debe seguir los siguientes pasos:
### 1. **Generación del par de claves**
- El sujeto crea un **par de claves asimétricas** compuesto por:    
    - **Clave privada** (mantenerla segura y secreta).        
    - **Clave pública**.        
- Se elige el tipo de cifrado (**RSA**, **ECC**, etc.) y la **longitud de clave**.   

### 2. **Creación de la CSR**
- Con el par de claves, el sujeto genera una **CSR (Certificate Signing Request)**.    
- La CSR contiene:    
    - La **clave pública** del sujeto.        
    - Información que se incluirá en el certificado (nombre, dominio, organización, etc.).       

### 3. **Envío a la CA**
- La CSR se envía a la CA para su revisión.    
---

## Validación por parte de la CA
La CA revisa la solicitud y verifica que los datos sean correctos y legítimos.  
Para un **servidor web**, esto puede incluir:
- Confirmar que:    
    - El **nombre del sujeto** coincide con el **FQDN** del dominio.        
    - La solicitud proviene de la persona con autoridad sobre el dominio.        
	- Validar la información administrativa mediante datos públicos como **registros WHOIS**.   
Si todo es correcto, la CA **firma digitalmente** el certificado y lo entrega al solicitante.

---


## Ejemplo visual
> _Uso de un formulario web en el cortafuegos OPNsense para solicitar un certificado.  
> Los nombres alternativos de DNS e IP (SANs) deben coincidir con los valores que los clientes usarán para acceder al sitio._

