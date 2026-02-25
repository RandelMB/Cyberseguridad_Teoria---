
---
## **Modelo de raíz de confianza**

- Define cómo usuarios y CA confían entre sí.    
- Cada CA tiene un **certificado raíz**, que está **auto firmado**.    
- Usa claves RSA de **2048/4096 bits** o **ECC equivalente**.    
- El “asunto” del certificado raíz suele ser el nombre de la CA (ej: _CompTIA Root CA_).    
- El certificado raíz firma otros certificados.    
- Instalar el certificado raíz hace que el host confíe automáticamente en todo lo que esa CA firme.    

---
## **Modelo de CA única/privada** ( Redes Privadas )

- Una sola CA raíz emite certificados directamente a usuarios y equipos.    
- Se usa en redes privadas.    
- Riesgo: si esa CA se compromete, **la PKI completa cae**.   

---
## **Modelo jerárquico (CA de terceros)**

- La CA raíz firma certificados para una o varias **CA intermedias**.    
- Las CA intermedias emiten certificados a los **usuarios/servidores (certificados de hoja)**.
    - Ventajas:    
    - Permite diferentes políticas por CA intermedia.        
    - Se entiende mejor para qué sirve cada certificado.        
    - Se crea la **cadena de confianza**: hoja → intermedia → raíz.        
- Ejemplo:  
    _[www.example.org](http://www.example.org) → certificado de DigiCert TLS CA1 (intermedia) → firmado por la CA raíz global de DigiCert._    

---
## **Certificados autofirmados**

- Se generan sin intervención de una CA confiable.    
- Usados cuando una PKI completa es demasiado costosa o innecesaria:    
    - Enrutadores domésticos.        
    - Entornos de prueba.        
    - Servicios internos simples.        
- El navegador/OS los marcará como **no confiables**.    
- El usuario puede forzar la confianza manualmente.
- No deben usarse para **sistemas críticos** porque no son fáciles de validar.
---




