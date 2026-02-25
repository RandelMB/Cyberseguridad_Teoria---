
---
## Uso del CN y SAN en los certificados digitales

### 1. Evolución del uso del Common Name (CN)

Cuando se introdujeron los certificados por primera vez, el campo **Common Name (CN)** se utilizaba para indicar el **nombre de dominio completamente calificado (FQDN)** del servidor, como _[www.comptia.org](http://www.comptia.org)_.  
Sin embargo:
- Este uso se adoptó por **costumbre**, no porque fuera el diseño ideal.    
- El campo *CN* puede contener distintos tipos de datos, lo que dificulta su interpretación por navegadores.   
- Por ello, hoy en día el *CN* está **en desuso** para validar identidades basadas en direcciones de red.    


![[Pasted image 20251215144550.png]]

### ¿Se usa todavía el Common Name (CN)?
- **El campo CN sigue existiendo** dentro del certificado X.509.    
- **Pero los navegadores modernos ya NO lo usan** para comprobar el nombre del servidor (hostname).  
### ¿Qué cambió entonces?
Hoy la validación del dominio se hace **exclusivamente** con el campo:
👉 **Subject Alternative Name (SAN)**

---
## 2. El campo SAN (Subject Alternative Name)
El campo de extensión **Subject Alternative Name (SAN)** está diseñado específicamente para representar diferentes tipos de identificadores, como:
- FQDN 
- Direcciones IP    
- Correos electrónicos (RFC 822)    
- Otros identificadores permitidos por X.509   
Cuando un certificado incluye un SAN, **los navegadores deben usarlo y no el CN**.

---
### 📌 Ejemplo visual

![[Pasted image 20251215161847.png]]


> El certificado del dominio de ejemplo está configurado con nombres alternativos del sujeto (SAN) para múltiples dominios y subdominios.

---
## 3. ¿Debe seguirse usando el CN?
Aunque SAN es el estándar moderno, aún es recomendable incluir también el **FQDN en el CN**, ya que:
- No todos los navegadores    
- Ni todas las librerías    
- Ni todos los sistemas heredados    
están 100% actualizados con los estándares actuales.
---
## 4. Uso del SAN para subdominios y comodines
El campo SAN permite incluir:
### ✔ Subdominios específicos
Ejemplo:
- _[www.comptia.org](http://www.comptia.org)_    
- _members.comptia.org_    
Esto es lo más seguro, pero si se agrega un subdominio nuevo, se requiere **emitir un nuevo certificado**.
### ✔ Certificados comodín
Un dominio comodín como:

```
*.comptia.org
```

permite que el certificado sea válido para **cualquier subdominio de un solo nivel**, como:
- _www.comptia.org    
- _mail.comptia.org_    
- _store.comptia.org_   
---
### 📌 Ejemplo visual del comodín





> El certificado del sitio web de CompTIA está configurado con un dominio comodín que permite el acceso a través de **[https://comptia.org](https://comptia.org)** y **[https://www.comptia.org](https://www.comptia.org)**. (Captura de pantalla utilizada con el permiso de Microsoft.)

---
## 5. Campos adicionales del certificado
Un certificado también incluye:
- **O**: Organización    
- **OU**: Unidad organizativa    
- **L**: Localidad    
- **ST**: Estado / Provincia    
- **C**: País    
Estos, junto con el CN, forman el **Nombre Distinguido (DN)**.
Ejemplo de DN:

```
CN=www.example.com; OU=Web Hosting; O=Example LLC;
L=Chicago; ST=Illinois; C=US
```

---
## 6. Tipos de certificados según su uso
Los certificados no solo identifican servidores; también se usan para otros fines:
### ✔ Certificados de correo electrónico
- El SAN contiene una **dirección de correo RFC 822**.    
- Se usa para firmar y cifrar correos.   
### ✔ Certificados de firma de código
- Validan al editor o desarrollador de software.    
- No suelen usar SAN.    
- La CA debe validar rigurosamente la información de la organización para evitar suplantaciones. 

---

