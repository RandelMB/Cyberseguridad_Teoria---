
---

## Generación y almacenamiento de claves criptográficas

Una clave secreta puede generarse y almacenarse en el sistema de archivos de una computadora de escritorio o servidor con un sistema operativo de propósito general. Sin embargo, este enfoque presenta varios inconvenientes.

### 1. Generación de claves y entropía

La generación segura de una clave criptográfica requiere un proceso verdaderamente aleatorio. Un sistema con alta entropía garantiza que cualquier valor del espacio de claves tenga la misma probabilidad de ser seleccionado.

Las computadoras tradicionales presentan una entropía limitada debido a su naturaleza determinista. Para mitigar esto, se utilizan:

- **PRNG (Generador de Números Pseudoaleatorios)**: determinista, pero capaz de aproximar un buen nivel de desorden.  
    Ejemplo: **GPG** es **GNU Privacy Guard** obtiene entropía del uso del teclado y el mouse.
    
- **TRNG (Generador de Números Aleatorios Verdaderos)**: utiliza fuentes físicas no deterministas, como ruido electrónico o movimiento del aire, proporcionando mayor seguridad.
    
![[Pasted image 20260109093748.png]]

==La arquitectura del PRNG propuesto basada en FWMHS y el mapa Bernoulli==

![[Pasted image 20260109094008.png]]

---

### 2. Los Riesgos del almacenamiento de claves en el sistema de archivos
Una clave almacenada como archivo es tan segura como cualquier otro archivo del sistema, lo que implica varios riesgos:
- Compromiso por robo de credenciales del usuario.    
- Compromiso por acceso físico al dispositivo.    
- Dificultad para auditar completamente el acceso a las claves.    

Idealmente, el almacenamiento criptográfico debe ser **inviolable**, permitiendo detectar de inmediato cualquier compromiso de una clave privada o secreta y facilitando su revocación y la recodificación del material cifrado.

---
### 3. Uso de criptoprocesadores
Estos problemas pueden mitigarse mediante el uso de un **criptoprocesador** para la generación y almacenamiento de claves.
Ventajas principales:
- Superficie de ataque reducida frente a equipos de propósito general.
- Capacidad de realizar operaciones criptográficas (cifrado, descifrado, firma) internamente.
- El material criptográfico **nunca abandona el hardware**.
---
### 4. Tipos de criptoprocesadores
Existen dos implementaciones principales:

- ###### a) Módulo de Plataforma Confiable (TPM)
	-  Criptoprocesador integrado en la CPU o en dispositivos móviles.
	- Versiones comunes: **TPM 1.2** y **TPM 2.0**.    
	- TPM 2.0 **no es compatible** con TPM 1.2.   
	
- ###### b) Módulo de Seguridad de Hardware (HSM)
	- Dispositivo dedicado o extraíble.    
	- Formatos comunes:    
	    - Montaje en rack        
	    - Tarjetas PCIe        
	    - Llaves USB        
	    - Dispositivos virtuales        

Los fabricantes pueden certificar estos dispositivos bajo el estándar **FIPS 140-2 Nivel 2**, lo que establece confianza y cumplimiento regulatorio.

---
### 5. Acceso a claves mediante APIs
Con un criptoprocesador, las claves no son accesibles desde el sistema de archivos. El acceso se realiza mediante una **API criptográfica**, comúnmente **PKCS#11**, que permite a las aplicaciones usar las claves sin exponerlas.

---
### 6. Vulnerabilidad y mitigación: memoria del sistema
Una debilidad inherente es que los datos descifrados deben cargarse en la **RAM** para que las aplicaciones los utilicen, lo que abre la posibilidad a ataques mediante procesos maliciosos.
#### Mitigación: Enclaves seguros (TEE)
- Uso de entornos de ejecución confiables, como **Intel SGX**.    
- Protegen los datos en memoria contra accesos no autorizados.    
- Ni siquiera procesos con privilegios de **root o sistema** pueden acceder sin autorización.    
- El enclave solo permite acceso a procesos **firmados digitalmente**.
    

---

| Abreviatura    | Nombre completo                   | Tipo                    | Fuente de entropía                       | Determinismo                 | Uso típico                                 | Nivel de seguridad |
| -------------- | --------------------------------- | ----------------------- | ---------------------------------------- | ---------------------------- | ------------------------------------------ | ------------------ |
| **PRNG**       | Pseudo-Random Number Generator    | Software / Algoritmo    | Semilla inicial (hora, PID, eventos)     | **Determinista**             | Apps, SO, simulaciones, claves no críticas | Media              |
| **TRNG**       | True Random Number Generator      | Hardware                | Fenómenos físicos (ruido, caos, térmico) | **No determinista**          | Criptografía, HSM, TPM                     | Alta               |
| **CSPRNG**     | Cryptographically Secure PRNG     | Algoritmo criptográfico | PRNG + entropía del SO/TRNG              | Determinista pero resistente | TLS, VPN, claves                           | Alta               |
| **TPM**        | Trusted Platform Module           | Hardware                | TRNG interno                             | No determinista              | Arranque seguro, claves del sistema        | Alta               |
| **HSM**        | Hardware Security Module          | Hardware dedicado       | TRNG interno                             | No determinista              | PKI, firmas, cifrado empresarial           | Muy alta           |
| **FPGA**       | Field-Programmable Gate Array     | Hardware programable    | Depende del diseño (TRNG/PRNG)           | Variable                     | Prototipos criptográficos                  | Variable           |
| **TEE**        | Trusted Execution Environment     | Entorno seguro          | Depende del hardware                     | Aislado                      | Protección de datos en memoria             | Alta               |
| **SGX**        | Software Guard Extensions (Intel) | TEE                     | Hardware CPU                             | Aislado                      | Enclaves seguros                           | Alta               |
| **PKCS#11**    | Public-Key Cryptography Std       | API                     | N/A                                      | N/A                          | Acceso a claves en HSM/TPM                 | N/A                |
| **FIPS 140-2** | Federal Info Processing Std       | Certificación           | N/A                                      | N/A                          | Validación criptográfica                   | Regulatorio        |
| FPGA           | Field-Programmable Gate Array     | Hardware programable    | **Depende del diseño** (TRNG/PRNG/caos)  | Variable                     | Implementar TRNG, HSM, prototipos          | Variable → Alta    |
