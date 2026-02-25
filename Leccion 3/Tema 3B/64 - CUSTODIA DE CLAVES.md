


**Gestión y recuperación de claves criptográficas**

1. **Riesgo de pérdida o daño**  
    Si una clave privada o secreta se pierde o se daña, los datos cifrados no pueden recuperarse, salvo que exista una copia de seguridad.  
    Hacer copias de la clave aumenta el riesgo de compromiso y dificulta detectar una filtración.   
2. **Mecanismos de mitigación**  
    Estos riesgos se reducen aplicando:    
    - **Custodia de claves**: la clave (o partes de ella) se archiva con terceros independientes.        
    - **Esquema M de N**: una operación crítica no puede realizarla una sola persona; requiere la autorización de un quórum (M) dentro de un grupo total (N).     
    - **M de N** es una regla de autorización compartida.
		Qué significa:
		- **N**: total de personas o entidades autorizadas.
		- **M**: mínimo necesario para aprobar una acción.
		Ejemplo:
		- **2 de 3** → hay 3 autorizados, pero se necesitan 2 para actuar.
3. **División de la clave**  
    La clave puede dividirse en varias partes y almacenarse con custodios distintos, disminuyendo el impacto de un compromiso individual.    
4. **Agentes de recuperación de claves (KRA)**  
    Las cuentas autorizadas para acceder a claves en custodia se denominan **KRA**.  
    Una política de recuperación puede exigir la aprobación de dos o más KRA para ejecutar la operación, evitando suplantaciones o abusos por parte de un solo agente.

**KRA (Key Recovery Agent)** es una **cuenta, usuario o entidad autorizada para recuperar claves criptográficas** que están bajo custodia.

En simple:
- Tiene permiso para **autorizar o participar en la recuperación de una clave**.    
- No actúa solo: normalmente se usa con **M de N** (varios KRA deben aprobar). 
Para qué sirve:
- Recuperar datos cifrados si el dueño pierde la clave.    
- Evitar que una sola persona tenga control total.    
- Mantener continuidad operativa y cumplimiento de políticas de seguridad.
- 