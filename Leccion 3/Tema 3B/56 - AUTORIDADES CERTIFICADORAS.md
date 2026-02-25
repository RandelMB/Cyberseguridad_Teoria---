

---

## Criptografía de clave pública

La **criptografía de clave pública** resuelve dos problemas fundamentales en la comunicación segura con terceros:
1. **Distribución segura de claves**    
2. **Autenticación de mensajes**   

Cada usuario posee un **par de claves**:
- **Clave pública**: se comparte libremente.    
- **Clave privada**: se mantiene en secreto.   

### Cifrado para confidencialidad
Cuando alguien desea enviarle un mensaje confidencial:
- Usa **su clave pública** para cifrar el mensaje.    
- El mensaje solo puede ser descifrado con **su clave privada**.    

Esto garantiza que **solo el destinatario legítimo** pueda leer la información.

### Firma digital para autenticación e integridad
Cuando necesita demostrar su identidad o garantizar que un mensaje no fue modificado:
- Se calcula un **hash del mensaje**.    
- El hash se **firma con la clave privada**.    
- Los demás usan la **clave pública** para verificar la firma.    

Como solo el propietario posee la clave privada:
- Se confirma la **identidad del emisor**.    
- Se garantiza la **integridad del mensaje**.    
- Se obtiene **no repudio**.    

---

## El problema de la identidad en la criptografía de clave pública
Aunque la criptografía de clave pública permite cifrar y firmar mensajes, **no garantiza por sí sola la identidad real del propietario de una clave pública**.
Este problema es crítico en entornos como el **comercio electrónico y la banca en línea**:
- Un sitio web puede distribuir una clave pública.    
- Pero eso no prueba que el sitio sea quien afirma ser.    

Surgen entonces preguntas clave:
- ¿Cómo saber que se está usando la **clave pública legítima** del servidor?    
- ¿Cómo evitar que un **atacante en la red** suplante al servidor y realice un ataque de intermediario (MITM)?    
- ¿Cómo confiar en que un sitio bancario o comercial es auténtico?    

---

## Infraestructura de Clave Pública (PKI)

es el **conjunto de componentes, políticas y procedimientos** que permiten **crear, gestionar, distribuir, validar y revocar certificados digitales**, con el fin de **vincular identidades con claves públicas** y establecer confianza en comunicaciones seguras.

Su objetivo principal es:

> **Demostrar que una clave pública pertenece realmente a la entidad que dice poseerla.**
![[Pasted image 20260106104738.png]]
### Certificados digitales

En PKI:
- Las claves públicas se publican dentro de un **certificado digital**.    
- El certificado vincula una **identidad** con una **clave pública**.    
- La validez del certificado es garantizada por una **Autoridad Certificadora (CA)**.    

La CA actúa como **tercero de confianza**.

---

## Autoridades Certificadoras (CA)
Una CA es una entidad que:
- Verifica la identidad de quien solicita un certificado.    
- Firma digitalmente el certificado para avalar esa identidad.   

### Tipos de CA

#### CA privada
- Implementada dentro de una organización.    
- Se usa para **comunicaciones internas**.    
- Sus certificados solo son confiables dentro de la propia organización.   

#### CA pública de terceros
- Usada para comunicaciones **públicas o entre empresas**.    
- Sus certificados son confiables a nivel global.    
- Ejemplos: **DigiCert, Comodo, GeoTrust, IdenTrust, Let’s Encrypt**.   

---

## Funcionamiento del modelo de confianza PKI
El proceso general es el siguiente:
1. La **CA** genera un **certificado raíz**, lo firma con su clave privada y publica su clave pública.    
2. El **cliente** instala el certificado raíz en su almacén de certificados de confianza.    
3. El **servidor web** genera una **Solicitud de Firma de Certificado (CSR)** que contiene su clave pública.    
4. El servidor envía el **CSR a la CA**.    
5. La **CA valida la identidad** del servidor y firma el certificado.    
6. El **servidor** instala el certificado firmado.    
7. El **cliente** verifica que el certificado del servidor esté firmado por una CA confiable.    
8. Cliente y servidor establecen una **conexión segura y cifrada**.   

Este modelo permite establecer **confianza sin contacto previo** entre las partes.

---

## Funciones de una CA pública de terceros
Una CA pública cumple funciones críticas dentro de la PKI:
- Proveer **servicios de certificación** a usuarios y organizaciones.    
- **Verificar la identidad** de los solicitantes de certificados.    
- Establecer y mantener la **confianza institucional** (gobiernos, empresas, sector financiero).    
- Administrar **repositorios de certificados**.    
- Gestionar el **ciclo de vida de certificados y claves**, incluyendo:    
    - Renovación        
    - Revocación        
    - Publicación de listas de certificados revocados (CRL) o uso de OCSP       

---
