
**Cifrado de datos: conceptos clave y funcionamiento**

### 1. Objetivo del cifrado

Si los datos están cifrados, no importa si el disco es robado o si la información es interceptada en la red: el atacante no puede leerla ni modificarla.  
Esto cumple el objetivo de **confidencialidad**.

---
### 2. Estados de los datos
Al diseñar un sistema criptográfico, se deben proteger los datos en todos sus estados:
- **Datos en reposo**: almacenados en medios persistentes (discos, SSD, backups).    
- **Datos en tránsito**: transmitidos a través de una red.    
- **Datos en uso**: cargados en memoria volátil (RAM, caché y registros de CPU).  

---
### 3. Cifrado masivo
El cifrado de grandes volúmenes de datos (MB o GB) se denomina **cifrado masivo**.
- El **cifrado asimétrico** (RSA, ECC) no se usa para esto porque es lento y costoso computacionalmente.    
- Para cifrar discos, archivos o tráfico de red se utiliza **cifrado simétrico**.   
Ejemplo típico: **AES**.

![[Pasted image 20260112105704.png]]
---

### 4. Problema del cifrado simétrico
El cifrado simétrico es rápido, pero tiene un problema clave:  
**la distribución de la clave**.
- Cuantas más personas conocen la clave, menor es la confidencialidad.    
- La clave debe protegerse muy bien.  

---
### 5. Solución: esquema híbrido (simétrico + asimétrico)
La solución estándar es combinar ambos tipos de cifrado.
#### Paso a paso:
1. **Claves asimétricas (KEK)**    
    - El usuario genera un par de claves (RSA o ECC).        
    - La clave privada está protegida con contraseña o autenticación.        
    - Esta clave privada actúa como **KEK (Key Encryption Key)**.        
2. **Clave simétrica (DEK)**    
    - El sistema genera una clave simétrica (AES-128, AES-256).        
    - Esta es la **DEK (Data Encryption Key)**.        
    - La DEK cifra los datos reales.        
3. **Protección de la DEK**    
    - La DEK se cifra usando la **clave pública** de la KEK.        
4. **Acceso a los datos**    
    - El usuario se autentica.        
    - Usa su clave privada para descifrar la DEK.        
    - Con la DEK se descifran los datos.      
---


