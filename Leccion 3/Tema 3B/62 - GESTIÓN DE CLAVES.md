
### **Gestión de Claves Criptográficas**

La **gestión de claves** abarca todas las consideraciones operativas necesarias durante el **ciclo de vida de una clave criptográfica**, desde su creación hasta su eliminación. Una gestión adecuada garantiza la confidencialidad, integridad y disponibilidad de los datos protegidos.


### **Etapas del Ciclo de Vida de una Clave**

1. **Generación de claves**  
    Se crea una clave simétrica (como AES-256) o un par de claves asimétricas (como RSA o ECC) con la fortaleza requerida.  
    **Ejemplo:**    
    - Un servidor web genera un par de claves RSA de 2048 bits para su certificado SSL/TLS.    
    - Un sistema de cifrado de disco genera una clave AES-256 para proteger la información local del usuario.
        
2. **Almacenamiento**  
    Las claves deben guardarse en un entorno seguro que impida el acceso no autorizado y las pérdidas.  
    **Ejemplo:**    
    - Las claves privadas de un servidor se almacenan en un **HSM (Hardware Security Module)** o en un **TPM (Trusted Platform Module)**.        
    - Los secretos de una aplicación en la nube se guardan en **AWS KMS** o **Azure Key Vault**.

![[Pasted image 20260108161501.png]]        

1. **Distribución**  
    Cuando las claves deben ser compartidas (por ejemplo, entre servidores), se hace de forma segura, evitando su exposición.  
    **Ejemplo:**    
    - Una empresa usa **Vault by HashiCorp** para distribuir claves temporales mediante autenticación y políticas.
        
2. **Uso**  
    Las claves se emplean en operaciones criptográficas como cifrado, descifrado, firma o verificación.  
    **Ejemplo:**    
    - Un usuario firma un correo con su clave privada (PGP).        
    - Un servidor usa su clave simétrica para cifrar archivos antes de enviarlos a almacenamiento.
        
3. **Rotación, caducidad y renovación**  
    Toda clave tiene un **período de validez** limitado para reducir el riesgo de exposición prolongada.  
    **Ejemplo:**    
    - Los certificados HTTPS emitidos por **Let’s Encrypt** caducan cada 90 días y se renuevan automáticamente.        
    - En una base de datos cifrada, las claves AES se rotan cada 6 meses mediante políticas internas.
        
4. **Revocación**  
    Si una clave se ve comprometida, debe revocarse inmediatamente para evitar su uso. Los datos cifrados con esa clave deben volver a cifrarse con una nueva.  
    **Ejemplo:**    
    - Una autoridad certificadora (CA) publica una **CRL (Certificate Revocation List)** cuando un certificado se revoca por robo o mal uso.
        
5. **Destrucción o eliminación segura**  
    Al finalizar su uso, las claves deben eliminarse de forma que no puedan recuperarse.  
    **Ejemplo:**    
    - Se sobrescribe la memoria que contenía la clave tres veces antes de liberar el recurso.
        

---

### **Modelos de Gestión de Claves**

1. **Modelo descentralizado**  
    Las claves se generan y administran directamente en el equipo o cuenta que las usará.  
    **Ventaja:** fácil de implementar.  
    **Desventaja:** difícil detectar si una clave ha sido comprometida.  
    **Ejemplo:**    
    - Cada usuario de correo PGP genera y guarda sus propias claves en su PC.
        
2. **Modelo centralizado**  
    Todas las claves se generan, almacenan y controlan desde un sistema de gestión central, como un **servidor KMS**.  
    **Ejemplo:**    
    - En una empresa, todas las aplicaciones cifran datos usando claves gestionadas por un servidor **AWS KMS** o **Google Cloud KMS**.        
    - Las aplicaciones se comunican con el servidor mediante el **Protocolo de Interoperabilidad de Gestión de Claves (KMIP)**.
        
