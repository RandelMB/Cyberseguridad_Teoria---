La geolocalización es el uso de atributos de red para identificar (o estimar) la posición física de un dispositivo. El dispositivo utiliza servicios de ubicación para determinar su posición actual. Los servicios de ubicación pueden usar dos sistemas:

- Sistema de posicionamiento global (GPS): es un medio para determinar la latitud y longitud del dispositivo en función de la información recibida de los satélites a través de un sensor GPS.
- Sistema de posicionamiento interior (IPS): determina la ubicación de un dispositivo mediante la triangulación de su proximidad a otras fuentes de radio, como torres celulares, puntos de acceso Wi-Fi y balizas Bluetooth o RFID.

Los servicios de ubicación están disponibles para cualquier aplicación a la que el usuario haya otorgado el permiso para utilizarlos.

La principal preocupación en torno a los servicios de ubicación es la privacidad. Si bien es muy útil para mapas y navegación guiada, también representa un mecanismo para rastrear los movimientos de un individuo, lo que implica el seguimiento de sus hábitos sociales y comerciales. El problema se agrava aún más debido al gran volumen de aplicaciones móviles que solicitan acceso a los servicios de ubicación, lo que resulta en el envío de la información a los desarrolladores de aplicaciones y su almacenamiento dentro de la estructura de archivos del dispositivo. Si un atacante logra acceder a estos datos, entonces el acoso, la ingeniería social e incluso el robo de identidad se convierten en posibilidades reales.

**Geofencing y aplicación de normativas para cámara y micrófono**

El Geofencing (geovallado) es la práctica de crear un límite virtual basado en la geografía del mundo real. Puede ser una herramienta útil en lo que respecta al control del uso de las funciones de cámara o video o la aplicación de la autenticación basada en contexto. 

Una organización puede implementar geofencing para establecer un perímetro alrededor de su propiedad de oficina y, posteriormente, restringir la funcionalidad de cualquier dispositivo que sobrepase dicho límite. Un teléfono inteligente sin bloquear podría bloquearse y requerir una nueva autenticación al ingresar a las instalaciones, mientras que la cámara y el micrófono podrían ser desactivados. La posición del dispositivo se obtiene de los servicios de ubicación.

![[Pasted image 20250328150205.png]]


Description
La pantalla está dividida en tres ventanas verticales. La primera ventana se titula, crear perfil. Tiene campos para llenar el nombre, descripción, plataforma y tipo de perfil. La opción de configuración, configurar está seleccionada para abrir la siguiente ventana. Un botón de crear está en la parte inferior. La segunda ventana se titula restricciones de dispositivo, Android. Lista las categorías para configurar ajustes. La opción General, 11 ajustes disponibles está seleccionada para abrir la siguiente ventana, General, Android. Esta ventana muestra varias opciones. Cada opción tiene dos botones, bloquear y no configurado. El botón OK está presente en la parte inferior derecha.

Restricción de los permisos del dispositivo, como la cámara y la captura de pantalla, mediante Intune. (Captura de pantalla utilizada con el permiso de Microsoft).

Etiquetado GPS
El etiquetado GPS es el proceso de agregar metadatos de identificación geográfica, como la latitud y longitud del lugar donde se encontraba el dispositivo en ese momento, a medios como fotografías, mensajes SMS, video, entre otros. Permite que la aplicación coloque los medios en coordenadas específicas de latitud y longitud. El etiquetado GPS es información personal altamente confidencial y datos de organización que puedan ser confidenciales. Las imágenes etiquetadas con GPS cargadas en las redes sociales podrían utilizarse para rastrear los movimientos y la ubicación de una persona. Por ejemplo, un soldado ruso reveló las posiciones de las tropas al subir selfies etiquetadas con GPS en Instagram (arstechnica.com/tech-policy/2014/08/opposite-of-opsec-russian-soldier-posts-selfies-from-inside-ukraine). 