
**Cifrado en bases de datos estructuradas**

### Bases de datos estructuradas
- Almacenan datos en **tablas**.    
- Cada tabla tiene:    
    - **Columnas** (campos con tipo de dato).        
    - **Filas** (registros con valores).        
- Los datos se guardan físicamente como **archivos en un volumen**.
    - El acceso siempre se realiza a través de un **DBMS (Database Management System)(Motor de SQL)** usando lenguajes como **SQL**.    
- Normalmente se alojan en un **servidor** y se consumen desde aplicaciones cliente.

---

## Cifrado en bases de datos

Aunque los archivos pueden cifrarse a nivel de disco o volumen, esto suele afectar el rendimiento.  
Por eso, el cifrado se implementa **dentro del DBMS (Database Management System)(Motor de SQL)**, con distintos niveles de granularidad.

---
# 🔐 Mecanismos de cifrado en bases de datos
## Cifrado a nivel de base de datos (TDE)
- Conocido como **Transparent Data Encryption (TDE)** en SQL Server.    
- El cifrado ocurre cuando los datos pasan **entre disco y memoria**.    
- Funciona a nivel de **páginas de datos (Es un bloque fijo de almacenamiento.)**.    
- **Protege:    
    - Todos los registros almacenados.        
    - Archivos de datos.        
    - Registros de transacciones (logs).
- **Ventaja:    
    - Protección completa contra robo del medio de almacenamiento.
- **Limitación:    
    - Los datos se descifran en memoria.       

## Cifrado a nivel de columna o celda
- Aplica cifrado a **campos específicos** dentro de una tabla.    
- Reduce el impacto en rendimiento frente a TDE.    
- Requiere identificar qué columnas son sensibles.    
- Puede complicar consultas y acceso a los datos.   

## Always Encrypted (SQL Server)
- Los datos:    
    - Permanecen cifrados **en disco y en memoria**.  
    - Solo se descifran en la **aplicación cliente**.        
- El **DBMS no tiene acceso a la clave en texto plano**.    
- El administrador de la base de datos no puede ver los datos.    
- Permite **separación de funciones** y mejora la privacidad.

## Cifrado a nivel de registro (fila)
- Cada fila puede cifrarse con una **clave distinta**.    
- Ejemplo: 
    - Información médica de clientes.        
    - Cada cliente tiene su propio par de claves.        
- La tabla contiene registros protegidos de forma independiente.   
- Permite:    
    - Control muy granular del acceso.        
    - Cumplimiento de normativas de seguridad y privacidad.       
---
### Resumen
- **TDE**: protege toda la base de datos en reposo y cifra toda la base sin cambiar apps.        
- **Cifrado por columna**: protege campos específicos.    
- **Always Encrypted**: ni el DBMS ve los datos en claro.    
- **Disco/volumen**: protege el medio físico.        
- **Fila/registro**: control extremo por usuario.    
- **Aplicación**: máxima seguridad, más complejidad.

| Tipo de cifrado                          | Nivel                  | Qué cifra                        | Dónde se cifra / descifra    | DBMS ve datos en claro | DBA puede ver datos | Impacto en rendimiento | Uso típico                                |
| ---------------------------------------- | ---------------------- | -------------------------------- | ---------------------------- | ---------------------- | ------------------- | ---------------------- | ----------------------------------------- |
| **Cifrado de disco / volumen**           | Infraestructura        | Archivos de la BD, logs, backups | Sistema operativo / hardware | Sí                     | Sí                  | Bajo–medio             | Protección ante robo físico               |
| **TDE (Transparent Data Encryption)**    | Base de datos / página | Toda la BD y logs                | Entre disco ↔ memoria        | Sí                     | Sí                  | Medio                  | Cumplimiento y datos en reposo            |
| **Cifrado a nivel de columna (clásico)** | Columna / celda        | Campos específicos               | Generalmente en el DBMS      | Sí                     | Sí                  | Bajo–medio             | Proteger datos sensibles puntuales        |
| **Always Encrypted (SQL Server)**        | Columna                | Campos específicos               | **Aplicación cliente**       | **No**                 | **No**              | Medio–alto             | Separación de funciones, privacidad       |
| **Cifrado a nivel de fila / registro**   | Registro               | Filas completas                  | Cliente o capa de aplicación | No (parcial)           | No (parcial)        | Alto                   | Datos por usuario, regulaciones estrictas |
| **Cifrado en la aplicación**             | Aplicación             | Cualquier dato                   | Aplicación                   | No                     | No                  | Variable               | Máximo control de seguridad               |


|Mecanismo|Protege data at rest|Protege del DBA|
|---|---|---|
|Disco / volumen|✅|❌|
|TDE|✅|❌|
|Columna / celda|✅|⚠️ Parcial|
|Always Encrypted|✅|✅|
|Fila / registro|✅|✅|
|Tokenización|✅|✅|
|Mascarado|❌|⚠️|


