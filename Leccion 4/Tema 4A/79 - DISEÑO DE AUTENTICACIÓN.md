

![[Pasted image 20241118134524.png]]




---

## **1. Proceso de autenticación**

La autenticación ocurre cuando un solicitante presenta sus credenciales a un servidor de autenticación.  
El servidor compara esas credenciales con las que tiene almacenadas y, si coinciden, la cuenta se considera autenticada.

---

## **2. Diseño de autenticación**
El diseño de autenticación implica seleccionar una tecnología que cumpla con los requisitos de:
### **a. Confidencialidad**
- Es esencial en autenticación.    
- Si las credenciales se filtran, un actor malicioso podría hacerse pasar por el usuario legítimo y acceder al sistema con sus privilegios.    

### **b. Integridad**
- El mecanismo de autenticación debe ser confiable.    
- No debe ser fácil de engañar o eludir mediante credenciales falsificadas.    

### **c. Disponibilidad**
- El proceso debe ser rápido y no entorpecer los flujos de trabajo.    
- Debe ser fácil de usar para los usuarios.    

---

## **3. Tecnologías de autenticación**

Las credenciales pueden clasificarse en **factores de autenticación**.  
El más antiguo es _algo que la persona conoce_, también llamado **factor de conocimiento**.

---
## **4. Factores de conocimiento**
### **a. Usuario y contraseña**
- Son el ejemplo más típico.    
- El nombre de usuario normalmente no es secreto, aunque tampoco debe publicarse.    
- La contraseña debe permanecer conocida solo por el titular de la cuenta.    
- Las **frases de contraseña** (password phrases) son más largas y fáciles de recordar, además de ser más seguras.   

### **b. PIN (Personal Identification Number)**
- También es _algo que la persona conoce_.    
- Tradicionalmente eran secuencias cortas de 4 a 6 dígitos usadas con tarjetas bancarias.    
- En el diseño moderno, su característica principal es que el PIN solo autentica en **un dispositivo específico**.    
- Puede usar cualquier tipo de carácter y tener cualquier longitud.
---