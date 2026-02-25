

### Revocación y suspensión de certificados

Un certificado puede **revocarse** o **suspenderse**:
- **Certificado revocado**: deja de ser válido de forma permanente. No puede restablecerse.    
- **Certificado suspendido**: se invalida temporalmente y **puede reactivarse**.   

Tanto el propietario como la Autoridad Certificadora (CA) pueden revocar o suspender un certificado por distintas razones, entre ellas:
- Compromiso de la clave privada    
- Compromiso de la CA    
- Reemplazo del certificado    
- Cese de operaciones    
- Salida de un usuario de la empresa    
- Cambio de nombre de dominio    
- Uso indebido del certificado    

Estas razones se codifican con valores como **No especificado**, **Compromiso de clave**, **Compromiso de CA**, **Reemplazado** o **Cese de operaciones**.  
Cuando un certificado se suspende, se identifica con el código **Certificado retenido**.

---
### Verificación del estado de un certificado
Debe existir un mecanismo que permita a los usuarios saber si un certificado es **válido**, **revocado** o **suspendido**. Para ello, una CA debe mantener una **Lista de Revocación de Certificados (CRL)** que incluya todos los certificados revocados y suspendidos.
La CRL:
- Debe ser accesible públicamente para cualquier entidad que confíe en los certificados de la CA. 
- Debe estar referenciada dentro de cada certificado, indicando al navegador o aplicación dónde verificar su estado.    
---
### Punto de distribución de la CRL
El **campo de punto de distribución** en un certificado digital indica la ubicación donde se publica la CRL.  
La CRL se distribuye como un archivo firmado por la CA, lo que garantiza su autenticidad.

---
### Atributos de una CRL
Una CRL incluye los siguientes elementos:
- **Período de publicación**: fecha y hora en que se genera la CRL. Normalmente es automático.    
- **Puntos de distribución**: ubicaciones donde la CRL está disponible.    
- **Período de validez**: tiempo durante el cual la CRL se considera confiable. Suele ser ligeramente mayor que el intervalo de publicación.    
- **Firma**: la CRL está firmada por la CA para asegurar su integridad y autenticidad.    
---
### Limitaciones del uso de CRL
El principal riesgo del uso de CRL es que un certificado revocado pueda seguir siendo aceptado si:
- La CRL aún no se ha actualizado.    
- El navegador o la aplicación no está configurada para verificar la CRL (situación más común en software heredado).    
---
### OCSP como alternativa
Otra forma de validar el estado de un certificado es mediante **OCSP (Online Certificate Status Protocol)**.  
En lugar de descargar una CRL completa, el cliente consulta directamente el estado de un certificado específico.
Características clave de OCSP:
- El certificado debe incluir la información del servicio OCSP.    
- Permite obtener el estado del certificado casi en tiempo real.    
- Algunos servidores OCSP consultan directamente la base de datos de la CA.    
- Otros dependen de la CRL, por lo que siguen limitados por su intervalo de publicación.

