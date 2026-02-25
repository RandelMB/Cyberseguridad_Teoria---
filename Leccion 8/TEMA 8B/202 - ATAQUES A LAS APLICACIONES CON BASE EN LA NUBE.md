

Los ataques a aplicaciones basadas en la nube se dirigen a aplicaciones alojadas en plataformas en la nube y explotan posibles vulnerabilidades dentro de estas aplicaciones o la infraestructura en la nube, en la que se ejecutan para llevar a cabo actividades maliciosas. Por lo general, los ataques a las aplicaciones basadas en la nube implican la explotación de configuraciones erróneas en el entorno de la nube, mecanismos de autenticación débiles, segmentación de red insuficiente o controles de acceso mal implementados.

En comparación con los ataques a aplicaciones tradicionales, los ataques basados en la nube tienen algunas características únicas. En un entorno de nube, el modelo de responsabilidad compartida puede llevar a confusión sobre quién es responsable de qué, lo que podría dejar brechas de seguridad que los atacantes pueden explotar.

La naturaleza altamente accesible y escalable de la nube puede hacer que las aplicaciones basadas en la nube sean objetivos atractivos para los atacantes. Por ejemplo, un atacante puede explotar una vulnerabilidad en una aplicación basada en la nube, lo que resulta en el acceso a otros recursos dentro del mismo entorno de nube, proporcionando acceso a la infraestructura de una manera por lo general imposible de lograr con los ataques a aplicaciones tradicionales.

Algunos tipos de ataques son específicos de la nube, como los ataques de canal lateral, en los que un atacante con una instancia que se ejecuta en el mismo servidor físico que la víctima intenta extraer información de la instancia de la víctima a través de recursos compartidos. Los atacantes pueden explotar configuraciones erróneas y controles de seguridad débiles en entornos de nube para obtener acceso no autorizado a datos confidenciales en depósitos de almacenamiento en la nube mal protegidos. 

Los servicios en la nube también se pueden utilizar para el cryptojacking, donde un atacante utiliza el poder de procesamiento de la nube para extraer criptomonedas sin el consentimiento del usuario, lo que lleva a un aumento (enorme) de los costos para el usuario de la nube y a un rendimiento degradado de sus recursos aprovisionados.

	El modelo de responsabilidad compartida se trata en el tema 6A y es un concepto crítico en la seguridad en la nube.

La nube como plataforma de ataque
Los atacantes también pueden utilizar plataformas en la nube para la distribución de phishing y malware. Pueden configurar fácilmente sitios web fraudulentos que imitan a los legítimos en los servicios en la nube y usar estos sitios para engañar a los usuarios para que revelen información sensible. Además, pueden explotar los servicios de almacenamiento en la nube para alojar archivos maliciosos y luego distribuir estos archivos a través de correos electrónicos de phishing u otros medios.

Agentes de seguridad de acceso a la nube
Un agente de seguridad de acceso a la nube (CASB) es un software de gestión empresarial diseñado para mediar en el acceso de los usuarios a los servicios en la nube mediante todo tipo de dispositivos. Entre los proveedores de CASB figuran Blue Coat, ahora propiedad de Symantec ( broadcom.com/products/cyber-security/information-protection/cloud-application-security-cloudsoc), Skyhigh Security (skyhighsecurity.com), Forcepoint (forcepoint.com/product/casb-cloud-access-security-broker), Microsoft Cloud App Security (microsoft.com/en-us/microsoft-365/enterprise-mobility-security/cloud-app-security) y Cisco Cloudlock (cisco.com/c/en/us/products/security/cloudlock/index.html).

Los CASB proporcionan visibilidad sobre cómo los clientes y otros nodos de red están utilizando los servicios en la nube. Algunas de las funciones de un CASB son las siguientes:

- Permitir la autenticación de inicio de sesión único y aplicar controles de acceso y autorizaciones desde la red empresarial hasta el proveedor de la nube.
- Escanear en busca de programas maliciosos y accesos de dispositivos no autorizados o no compatibles.
- Monitorear y auditar la actividad de los usuarios y recursos.
- Mitigar la exfiltración de datos denegando el acceso a servicios en la nube no autorizados desde dispositivos administrados.
En general, los CASB se implementan de tres maneras:

- Proxy de reenvío : se trata de un dispositivo o host de seguridad situado en el extremo de la red del cliente, que reenvía el tráfico del usuario a la red en la nube si su contenido cumple con la política. Para ello, es necesario configurar los dispositivos de los usuarios o instalar un agente. En este modo, el proxy inspecciona todo el tráfico en tiempo real, incluso aunque no esté destinado a aplicaciones en la nube autorizadas. Un inconveniente es que los usuarios podrían eludir el proxy y conectarse directamente. Un proxy también supone un rendimiento deficiente, ya que, sin una solución de balanceador de carga, se convierte en un obstáculo y en un posible punto único de fallo.
- Proxy reverso: se sitúa en el extremo de la red en la nube y dirige el tráfico a los servicios en la nube si el contenido de ese tráfico cumple la política. No es necesario configurar los dispositivos de los usuarios. Este método solo puede utilizarse si la aplicación en la nube es compatible con proxy.
- Interfaz de programación de aplicaciones [API]: intermedia las conexiones entre el servicio en la nube y el consumidor en la nube en lugar de colocar un dispositivo o host CASB en línea con los consumidores y servicios en la nube. Por ejemplo, si se desactiva una cuenta de usuario o se revoca una autorización en la red local, el CASB lo comunicará al servicio en la nube y utilizará su API para inhabilitar el acceso allí también. Esto depende de que la API admita la serie de funciones que el CASB y las políticas de acceso y autorización exigen. Es muy probable que las soluciones de CASB utilicen tanto el modo proxy como la API con distintos fines de gestión de la seguridad.