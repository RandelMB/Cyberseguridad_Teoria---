


## Conceptos básicos

- **Primitivo criptográfico**: una sola función hash, cifrado simétrico o asimétrico.    
- **Sistema criptográfico completo**: combina varios primitivos en un conjunto de cifrado.    
- **Limitaciones**: cada tipo (simétrico, asimétrico, hash) tiene propiedades y restricciones que condicionan su uso en distintos contextos.
    

---

## Usos de la criptografía

1. **Confidencialidad**: proteger que solo el destinatario autorizado lea el mensaje.    
2. **Integridad**: asegurar que los datos no se han modificado.    
3. **Autenticación**: confirmar la identidad del remitente.
    
---

![[Pasted image 20241107150205.png]]


> Ejemplo: si un mensaje se cifra o firma de forma que solo el remitente legítimo puede hacerlo, el receptor confía en su autenticidad.


![[Pasted image 20241107150214.png]]

---

## Identificación y autenticación

- Los **sujetos** pueden ser personas o computadoras (ej. un servidor web).    
- Con **clave pública y privada**:    
    - La clave privada prueba la identidad (solo el dueño puede usarla).        
    - El hash asegura la integridad (cualquier cambio altera el resumen).
        

---

## Firma digital (combinación de hash + cifrado asimétrico)

**Proceso:**

1. Alice genera un **hash** del mensaje (ej. con SHA-256).    
2. Alice **firma** el hash con su **clave privada**.    
3. Envía a Bob:    
    - el mensaje        
    - la firma digital        
4. Bob usa la **clave pública** de Alice para verificar la firma y recuperar el hash original.    
5. Bob genera su propio hash del mensaje y lo cohmpara con el de Alice.   

- **Coinciden**: mensaje íntegro + identidad garantizada.    
- **No coinciden**: el mensaje fue manipulado o la firma no es válida.
    


---



![[Pasted image 20241107150322.png]]


## Ejemplo ilustrado

1. Alice firma el hash de `"HelloWorld"` con su clave privada.    
2. Envía mensaje + firma a Bob.    
3. Bob verifica la firma con la clave pública de Alice → obtiene el hash.    
4. Bob genera su propio hash y lo compara.
---
## Estándares (Normas) de firmas digitales
- **PKCS#1**: uso de RSA para firmas.    
- **DSA**: basado en ElGamal.    
- **ECDSA**: variante moderna de DSA con curvas elípticas, más eficiente y hoy más usada.    
- **FIPS (EE. UU.)**: estándares oficiales que incluyen DSA y ECDSA.
---
---

### Verificación de firma digital con clave pública

1. **Recepción del mensaje y la firma digital**
    - Bob recibe:
        - `M` → mensaje original enviado por Alice.
        - `S` → firma digital (resultado del cifrado del hash con la clave privada de Alice).
            
2. **Obtener la clave pública de Alice**
    - Clave pública `K_pub_Alice` previamente distribuida o accesible de forma segura.
        
3. **Descifrado de la firma**
    - Aplicar el algoritmo asimétrico de verificación (por ejemplo RSA, ECDSA) usando `K_pub_Alice` sobre `S`:        
        ```
        H_recuperado = Verificar(S, K_pub_Alice)
        ```        
    - `H_recuperado` es el hash que Alice calculó y cifró con su clave privada.

4. **Calcular hash propio del mensaje recibido**
    - Bob aplica el mismo algoritmo hash que Alice (ej. SHA-256) sobre el mensaje `M`:
        ```
        H_bob = Hash(M)
        ```        
5. **Comparar hashes**
    - Comparar `H_recuperado` con `H_bob`:
        - Si son iguales → mensaje íntegro y autenticidad de Alice confirmada.
        - Si no coinciden → mensaje alterado o firma no válida.
            

---

### Nota técnica adicional

- En RSA: `S^e mod n` donde `(e, n)` es la clave pública de Alice.
- En ECDSA: se realiza verificación de la firma sobre la curva elíptica, no descifrado directo.
- Este proceso asegura **integridad + autenticación**, pero no confidencialidad.
    

---

Si quieres, puedo hacer un **diagrama de flujo técnico** que muestre cada operación de verificación paso a paso. Esto ayuda a visualizar claramente el proceso matemático. ¿Quieres que lo haga?



# 🔐 Cuadro comparativo: criptografía simétrica vs asimétrica

|Característica|Criptografía simétrica|Criptografía asimétrica|
|---|---|---|
|Número de claves|1 sola clave secreta|2 claves (pública y privada)|
|Relación de claves|La misma clave cifra y descifra|Lo que cifra una clave, la otra lo descifra|
|Velocidad|Muy alta|Más lenta|
|Seguridad del intercambio|Difícil (hay que compartir la clave)|Más segura (se comparte la clave pública)|
|Cifrado de grandes volúmenes|✅ Sí|❌ No|
|Autenticación|❌ No directa|✅ Sí|
|Firma digital|❌ No|✅ Sí|
|Uso principal|Protección de datos|Identidad y confianza|
|Casos de uso típicos|Discos, bases de datos, VPN, TLS (datos)|HTTPS, certificados, SSH, PKI|
|Ejemplos de algoritmos|AES, ChaCha20, 3DES|RSA, ECC, DSA|
|Uso en HTTPS|Cifra la sesión|Intercambia la clave|
|Uso en VPN|Cifra el tráfico|Autentica e intercambia claves|
|Escalabilidad|Difícil (muchas claves)|Alta (una clave pública)|
|Dependencia de PKI|No|Sí|