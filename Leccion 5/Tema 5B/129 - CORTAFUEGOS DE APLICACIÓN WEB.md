

Un cortafuegos de aplicación web (WAF) está diseñado para proteger el software que se ejecuta en los servidores web y sus bases de datos internas contra ataques de inyección de código y denegación de servicio. Los WAF utilizan reglas de procesamiento conscientes de aplicaciones para filtrar el tráfico y realizar la detección de intrusiones específicas de la aplicación. \n El WAF se puede programar con firmas de ataques conocidos y utilizar la coincidencia de patrones para bloquear solicitudes que contengan código sospechoso. La salida de un WAF se escribirá en un registro, que puede revelar amenazas potenciales para la aplicación web.

![[Pasted image 20241202173248.png]]


Description
La subopción aplicación bajo los registros de ventana es seleccionada desde el menú a la izquierda. El panel derecho tiene dos secciones. La sección superior titulada, aplicación lista el número de eventos: 12,660. Lista el nivel, fecha y hora, y fuente de la aplicación en un formato tabular. La sección inferior titulada, Evento 1, Mod Security tiene dos pestañas: General y Detalles (seleccionada). Tiene dos botones de radio, Vista Amigable (seleccionada) y Vista XML. Un código de computadora está escrito abajo.



Con el WAF ModSecurity instalado en este servidor IIS, se detectó un intento de escaneo y se registró como un evento de aplicación. Como puede ver, el conjunto de reglas predeterminado genera muchos eventos. (Captura de pantalla utilizada con el permiso de Microsoft).

Un WAF se puede implementar como un dispositivo que protege la zona en la que se encuentra el servidor web o como software de complemento para una plataforma de servidor web. 
