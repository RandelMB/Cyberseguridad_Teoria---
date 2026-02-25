

### Cifrado de transporte / comunicación (datos en movimiento)
El **cifrado de transporte** protege los datos mientras se transmiten por una red. Se aplica a distintos escenarios según el tipo de comunicación.

#### Ejemplos comunes
- **WPA (Wi-Fi Protected Access)**: protege el tráfico en redes inalámbricas.    
- **IPsec**: protege el tráfico entre dos puntos a través de redes públicas o no confiables (VPN).    
- **TLS (Transport Layer Security)**: protege datos de aplicaciones como web (HTTPS), correo APIs.
---
### Uso de cifrado simétrico y asimétrico
No se cifra directamente el tráfico con cifrado asimétrico porque es ineficiente.  
Se usa un **intercambio de claves** para acordar una **clave simétrica de sesión**, que luego cifra los datos. 

---
### Intercambio de claves (sobre digital)
1. **Alice obtiene la clave pública de Bob** (RSA o ECC), normalmente desde su certificado digital.    
2. **Alice genera una clave de sesión simétrica** (por ejemplo, AES).    
3. **Alice cifra los datos** usando la clave de sesión.    
4. **Alice cifra la clave de sesión** con la clave pública de Bob.   
5. **Alice envía**:
    - El mensaje cifrado. 
    - La clave de sesión cifrada (sobre digital). 
6. **Bob descifra la clave de sesión** con su clave privada. 
7. **Bob descifra el mensaje** usando la clave de sesión. 
8. **Bob responde a Alice cifrando su mensaje con esa misma clave de sesión**.
9. **Alice descifra** el mensaje usando la misma clave de sesión.
Resultado: confidencialidad sin el costo del cifrado asimétrico en todo el tráfico.
### Cómo se decide el algoritmo simétrico de sesión (ej. en TLS/HTTPS)
1. **El navegador** envía una lista de algoritmos que soporta  
    (Cipher suites: Un **cipher suite** es un **conjunto de algoritmos** que define **cómo se va a proteger una conexión** (normalmente TLS/HTTPS)). 
2. **El servidor web** elige **uno de esa lista** según: 
    - Su configuración.        
    - Sus políticas de seguridad.        
3. Ese algoritmo elegido se usa para la **clave de sesión simétrica**.
---
### Integridad y autenticidad del mensaje
El cifrado de transporte no solo protege la confidencialidad, también garantiza que el mensaje:
- No fue modificado.    
- Proviene del remitente legítimo.   
#### Mecanismos usados
- **HMAC**    
    - Combina la clave de sesión con un hash del mensaje.        
    - Permite verificar integridad y autenticidad.        
- **Cifrado autenticado (AE / AEAD)**    
    - El propio algoritmo simétrico garantiza confidencialidad + integridad.        
    - Ejemplos: **AES-GCM**, **ChaCha20-Poly1305**.       
---

### Resumen rápido
- Asimétrico: **solo para intercambiar la clave**.    
- Simétrico: **para cifrar los datos**.    
- HMAC o AEAD: **para integridad y autenticidad**.    
- TLS, IPsec y WPA aplican este modelo en distintos niveles de red.

| Mecanismo                                  | Qué protege                                  | Usa clave                | Cifra datos          | Garantiza integridad | Garantiza autenticidad | Caso típico                      |
| ------------------------------------------ | -------------------------------------------- | ------------------------ | -------------------- | -------------------- | ---------------------- | -------------------------------- |
| **Cifrado simétrico** (AES, ChaCha20)      | Confidencialidad                             | Clave secreta compartida | ✅ Sí                 | ❌ No (solo)          | ❌ No                   | Discos, archivos, tráfico masivo |
| **Cifrado asimétrico** (RSA, ECC)          | Confianza / intercambio                      | Par pública-privada      | ❌ No (datos grandes) | ❌ No                 | ✅ Sí                   | Handshake TLS, certificados      |
| **Hash** (SHA-256)                         | Integridad                                   | ❌ No                     | ❌ No                 | ✅ Sí                 | ❌ No                   | Checksums, contraseñas           |
| **HMAC**                                   | Integridad + autenticidad                    | Clave secreta            | ❌ No                 | ✅ Sí                 | ✅ Sí                   | APIs, VPN, TLS antiguo           |
| **AE / AEAD** (AES-GCM, ChaCha20-Poly1305) | Confidencialidad + integridad + autenticidad | Clave secreta            | ✅ Sí                 | ✅ Sí                 | ✅ Sí                   | HTTPS, TLS 1.3, WPA3             |
| **Firma digital**                          | Autoría / no repudio                         | Clave privada            | ❌ No                 | ✅ Sí                 | ✅ Sí                   | Firmar documentos, software      |