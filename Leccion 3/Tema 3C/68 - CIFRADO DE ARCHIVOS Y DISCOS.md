

**Cifrado de datos en reposo**

### 1. Niveles de cifrado
Los datos en reposo pueden protegerse en distintos niveles:
- **Niveles inferiores** (cifrado de disco completo):    
    - Implementación simple.        
    - Gestión compleja cuando hay múltiples usuarios.        
- **Niveles superiores** (sistema de archivos o base de datos):    
    - Mayor flexibilidad.        
    - Permiten controles de acceso granulares.       
---
## 2. Cifrado de disco completo y particiones

#### Cifrado de disco completo (FDE)
- Cifra **todo el contenido del dispositivo**:  
    - Datos.        
    - Metadatos.        
    - Espacio libre.        
- Protege principalmente contra el **robo físico**.    
- El disco no puede leerse sin las credenciales que desbloquean la clave.   

#### Unidades de autocifrado (SED)
- El cifrado se realiza en el **firmware del disco**.    
- Aplica a HDD, SSD y USB.    
- Las claves se almacenan en un **criptoprocesador interno**, no accesible al sistema operativo.    
- se mueve el disco a otro equipo no se puede recuperar
#### Cifrado por particiones
- Un disco puede dividirse en **particiones lógicas**.    
- Cada partición puede:    
    - Tener su propio sistema de archivos.        
    - Usar claves distintas.        
- Ejemplo:    
    - Particiones de arranque y sistema: sin cifrar.        
    - Partición de datos: cifrada.     
---


| Característica     | **Cifrado de volúmenes**          | **SED**            | **FDE**         | **Cifrado por particiones**  |
| ------------------ | --------------------------------- | ------------------ | --------------- | ---------------------------- |
| Nivel              | **Sistema de archivos (volumen)** | Hardware (disco)   | Disco completo  | Partición                    |
| Dónde se cifra     | Software del SO                   | Firmware del disco | Software del SO | Software del SO              |
| Alcance            | Un volumen lógico                 | Todo el disco      | Todo el disco   | Particiones específicas      |
| Metadatos          | Puede o no cifrarlos              | Siempre            | Normalmente sí  | Solo en particiones cifradas |
| Espacio libre      | Puede o no cifrarlo               | Siempre            | Normalmente sí  | Solo en particiones cifradas |
| Flexibilidad       | Alta                              | Baja               | Media           | Alta                         |
| Rendimiento        | Bajo impacto                      | Nulo               | Bajo            | Bajo                         |
| Dependencia del SO | Alta                              | Baja               | Alta            | Alta                         |
| Ejemplos           | BitLocker, FileVault              | SSD SED            | LUKS, BitLocker | LUKS por partición           |
|                    |                                   |                    |                 |                              |


|Aspecto|**Partición**|**Volumen**|
|---|---|---|
|Tipo de disco requerido|Disco **básico** (MBR / GPT)|Disco **dinámico**|
|Alcance|Un solo disco físico|Puede abarcar **múltiples discos**|
|Flexibilidad|Tamaño fijo, difícil de redimensionar|Redimensionable, admite redundancia|
|Número máximo|4 primarias (MBR) o 128 (GPT)|Hasta ~2.000 volúmenes dinámicos|
![[Pasted image 20260114095816.png]]

```python

# Porque el sistema de archivos siempre va arriba, sin importar qué haya debajo.
Disco
 └─ Partición (MBR/GPT)
     └─ Volumen
         └─ Sistema de archivos (NTFS / ext4 / APFS)

# En discos dinámicos / LVM:
Disco(s)
 └─ Volumen lógico
     └─ Sistema de archivos (NTFS / ext4)

Volumen NTFS
 └─ EFS (cifra archivos específicos)

```

## 3. Cifrado de volúmenes y archivos

#### Cifrado de volúmenes
- Un **volumen** es un recurso de almacenamiento con un único sistema de archivos (Formato).    
- Puede estar basado en:    
    - Un disco.        
    - Una partición.        
    - Un RAID.        
- Se implementa normalmente como **software**.

- Ejemplos:    
    - **BitLocker** (Windows).        
    - **FileVault** (macOS).

- Puede cifrar o no:    
    - Metadatos.        
    - Espacio libre.

### Cifrado de archivos
- Aplica cifrado a **archivos** o carpetas.    
- Depende del sistema de archivos.    
- Ejemplo:    
    - **EFS ( Cifra archivos específicos )**  de Microsoft requiere **NTFS**.        
- Ofrece control fino, pero no protege todo el dispositivo.

## 4. Metadatos y espacio libre
- **Metadatos**:    
    - Lista de archivos.        
    - Propietario.        
    - Fechas de creación y modificación.
    
- **Espacio libre**: 
    - Puede contener restos de archivos eliminados.
- No todos los sistemas de cifrado los protegen.   

## 5. Uso de TPM y HSM

- Si el dispositivo dispone de **TPM o HSM**:    
    - Las claves se almacenan de forma segura en hardware.        
    - El acceso a discos, volúmenes o archivos queda ligado al dispositivo.        
- Mejora la protección de claves y reduce el riesgo de extracción.


