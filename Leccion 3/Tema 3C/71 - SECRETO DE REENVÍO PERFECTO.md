

# 1️⃣ Sobre digital (RSA/ECC + AES)

## Objetivo

Enviar datos cifrados usando:
- Cifrado **asimétrico** → para proteger la clave    
- Cifrado **simétrico** → para proteger el mensaje   

---
## Pasos

1. **Alice obtiene la clave pública de Bob.**    (Mediante el Certificado)
2. **Alice genera una clave simétrica (clave de sesión).**    
3. **Alice cifra el archivo con la clave simétrica.**  
    Ejemplo:  
    `HelloWorld → rWoeldlolH`    
4. **Alice cifra la clave de sesión (Simétrica)** usando la clave pública de Bob.    
5. **Alice envía a Bob:**    
    - El archivo cifrado con la clave de sesión (Simétrico)       
    - La clave de sesión cifrada        
6. **Bob descifra la clave de sesión** con su clave privada.    
7. **Bob descifra el archivo** usando la clave de sesión.  
    `rWoeldlolH → HelloWorld`    
---
## Integridad y autenticidad
Para evitar alteraciones se usa estos mecanismos o tecnicas:
### 🔹 HMAC (Hash-based Message Authentication Code)
- Combina:    
    - Clave secreta        
    - Hash del mensaje        
- Permite verificar que el mensaje no fue modificado.  
### 🔹 AE / AEAD (Cifrado autenticado)

- Cifra y valida integridad al mismo tiempo.    
- Ejemplo moderno: **AES-GCM**.
---
# 2️⃣ Diffie-Hellman (intercambio de clave sin enviarla)

## Objetivo

Generar una clave secreta compartida sin transmitirla directamente.

---
## Valores públicos

- p = 23    
- g = 9  

---
## Pasos

1. **Alice elige un secreto privado:**  
    a = 5    
2. **Bob elige un secreto privado:**  
    b = 3    
3. **Alice calcula:**  
    A = gᵃ mod p  
    A = 9⁵ mod 23 = 8  
    → Envía A a Bob    
4. **Bob calcula:**  
    B = gᵇ mod p  
    B = 9³ mod 23 = 16  
    → Envía B a Alice    
5. **Alice calcula el secreto compartido:**  
    s = Bᵃ mod p  
    s = 16⁵ mod 23 = 6    
6. **Bob calcula el mismo secreto:**  
    s = Aᵇ mod p  
    s = 8³ mod 23 = 6    

✔ Ambos obtienen **s = 6**  
✔ Ese valor se usa para generar la clave simétrica.

---
## Qué puede ver un atacante

Mallory puede conocer:
- p    
- g    
- A    
- B    

Pero no puede calcular **s** sin conocer **a o b**.

---
# 3️⃣ PFS – Perfect Forward Secrecy

Si se usan claves efímeras:
- Cada sesión genera nuevas claves.    
- Si el servidor es comprometido en el futuro:    
    - No se pueden descifrar sesiones anteriores.        
- Si una sesión es comprometida:    
    - No afecta las demás.        

---
## Versiones modernas

- DHE → Diffie-Hellman efímero    
- ECDHE → Versión moderna con curva elíptica (más eficiente y más usada en TLS)    
---

# Diferencia clave entre ambos métodos

| Sobre digital                  | Diffie-Hellman        |
| ------------------------------ | --------------------- |
| Se envía la clave cifrada      | No se envía la clave  |
| Usa clave pública del receptor | Ambos generan secreto |
| Más simple                     | Más seguro con PFS    |
| No siempre tiene PFS           | Sí permite PFS        |

---
Si quieres, te explico cómo esto se integra exactamente en **TLS moderno (HTTPS real)**.

