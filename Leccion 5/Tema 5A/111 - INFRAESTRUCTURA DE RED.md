


### **1. Modelo de Capas**
- El modelo de **Interconexión de Sistemas Abiertos (OSI)** se usa para analizar y entender la infraestructura y los servicios de red.    
- Divide las funciones de la red en **capas**, cada una con tareas específicas.   

---

### **2. Componentes de una Red**
Una red está formada por:
- **Nodos:** dispositivos conectados a la red.    
- **Enlaces:** medios físicos o inalámbricos que conectan los nodos.    

---

### **3. Capa Física (Capa 1 del Modelo OSI)**

Define cómo se transmiten los datos físicamente:
- **Cables de par trenzado:** señales eléctricas.
- **Fibra óptica:** señales de luz infrarroja.    
- **Dispositivos inalámbricos:** ondas de radio.   

### **4. Tipos de Nodos**

- **Nodos host:**    
    - Inician transferencias de datos.        
    - Ejemplos: servidores, computadoras cliente.        
- **Nodos intermediarios:**    
    - Reenvían tráfico dentro de la red.        
    - Operan en distintas capas y con diferentes alcances.       

---

### **5. Tipos de Redes (Según Alcance)**
- **LAN (Local Area Network):** red de un solo sitio o área pequeña.    
- **WAN (Wide Area Network):** red que abarca áreas grandes (ciudades, países o el mundo).   

---

### **6. Direccionamiento en la Red**
- Cada nodo debe tener una **dirección única**.    
- El **direccionamiento** ocurre en distintas capas del modelo OSI, con distintos alcances.    

---

### **7. Reenvío y Direccionamiento**
Son funciones esenciales manejadas por dispositivos y protocolos de red.
#### **Dispositivo: Switch**
- **Función:** Reenvía **tramas** (frames) entre nodos en una red cableada.    
- **Capa:** Trabaja en la **Capa 2** del modelo OSI (Capa de Enlace de Datos).    
- **Conexión:** Cada host se conecta a un **puerto del switch** mediante un cable.    
- **Estándar común:** **Ethernet**.    
- **Método de decisión:** Usa la **dirección MAC** de los dispositivos conectados.    
    - Ejemplo de dirección MAC: `00-15-5D-01-CA-4A`        
    - Tiene **48 bits**, escrita en formato **hexadecimal**.        
- **Ámbito:** Solo funciona en el **segmento local de red** (dominio de difusión).   

---


![[Pasted image 20241120114122.png]]




Description
El modelo incluye siete capas, Capa 1: Física, Capa 2: Enlace de Datos, Capa 3: Red, Capa 4: Transporte, y Capa 7: Aplicación. La capa de enlace de datos incluye un switch y un punto de acceso. Tiene Dirección MAC, 00 guión 15 guión 5D guión 01 guión CA guión 4A y ID de VLAN, 100. La capa de red incluye un router y un protocolo de internet. Tiene dirección IP, 10.1.0.192 y subred, 10.1.0.0 barra 24. El protocolo de resolución de direcciones está entre la capa de enlace de datos y la capa de red. La capa de transporte incluye el protocolo de control de transmisión y el protocolo de datagrama de usuario. La capa de aplicación incluye un servidor y protocolos de aplicación como HTTP, SMTP, SMB, FTP y DNS. Tiene un nombre de dominio completamente calificado, www.punto515support.punto com. El sistema de nombres de dominio se superpone a las capas de transporte y aplicación.



Aplicaciones, protocolos y funciones de direccionamiento dentro del modelo de referencia de capa de red OSI. (Imágenes © 123RF.com.)

- Los puntos de acceso inalámbricos proporcionan un puente entre una red cableada y los hosts o estaciones inalámbricas. Los puntos de acceso funcionan en la capa 2 del modelo OSI. Los dispositivos inalámbricos también utilizan el direccionamiento MAC en la capa 2.
- Los enrutadores envían paquetes alrededor de una interconexión de redes, tomando decisiones de reenvío basadas en direcciones de Internet Protocol (IP) (Protocolo de Internet [IP]).  Los enrutadores funcionan en la capa 3 del modelo OSI. Por lo general, cada segmento local tendrá un enrutador conectado a él. El enrutador actúa como una puerta de enlace predeterminada para que los hosts del segmento la utilicen para enviar paquetes a otros segmentos.
- Los protocolos de transporte permiten a los clientes intercambiar datos con los servidores de aplicaciones. El Protocolo de control de transmisión [TCP] establece conexiones confiables, mientras que el Protocolo de datagrama de usuario [UDP] permite transferencias no confiables y sin conexión. Cada protocolo de aplicación se identifica mediante un puerto TCP o UDP. Esta funcionalidad se define en la capa 4 del modelo OSI.
- La funcionalidad del cliente/servidor es compatible con los protocolos de aplicación para servicios a nivel de usuario, como la navegación web, el correo electrónico y la transferencia de archivos. Los protocolos de aplicación funcionan en la capa 7 del modelo OSI.
- El sistema de nombres de dominio [DNS] sirve los registros de nombres de host y realiza la resolución de nombres para permitir que las aplicaciones y los usuarios se dirijan a los hosts y servicios utilizando nombres de dominio completamente calificados (FQDN) en lugar de direcciones IP. El DNS también funciona en la capa 7 del modelo OSI, pero es un servicio de infraestructura, en lugar de un servicio a nivel de usuario, como la navegación web.
El modelo OSI tiene tres capas superiores. En términos prácticos, distinguir las funciones de las capas 5, 6 y 7 no es tan útil, así que solo enfóquese en las aplicaciones que funcionan en la capa 7.