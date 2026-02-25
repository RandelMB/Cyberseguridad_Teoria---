
![[Pasted image 20241118112608.png]]

---
## ¿Qué es un certificado digital?

Un **certificado digital** es, esencialmente, un contenedor que almacena la **clave pública** de un sujeto. Además de esta clave, incluye información relevante tanto del **sujeto** como de la **autoridad emisora** del certificado.

El certificado está **firmado digitalmente**, lo que garantiza que fue emitido por una **Autoridad Certificadora (CA)** confiable.  
El _sujeto_ del certificado puede ser:

- Una **persona** (por ejemplo, para firmar digitalmente documentos o mensajes).
- Un **servidor** (como un servidor web que maneja transacciones confidenciales).

> En la siguiente imagen se pueden ver detalles del certificado digital y la clave pública del sujeto. (Captura de pantalla utilizada con permiso de Microsoft).
![[Pasted image 20260107080812.png]]
---

## Estándares en los que se basa

Los certificados digitales se fundamentan en los siguientes estándares:
### ✔ Estándar X.509

Aprobado por la **Unión Internacional de Telecomunicaciones (UIT)** y estandarizado por el **Grupo de Trabajo de Ingeniería de Internet (IETF)**.  
Referencia: RFC 5280.
### ✔ Estándares PKCS

Además, RSA desarrolló el conjunto de estándares llamados **Estándares de Criptografía de Clave Pública (PKCS)**, con el fin de impulsar y facilitar la adopción de la infraestructura de clave pública (PKI).

---

🔐 Cuadro comparativo: criptografía simétrica vs asimétrica

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