


La superficie de ataque es todos los puntos en los que un actor de amenaza podría obtener acceso a hosts y servicios. Es útil usar el modelo de capas para analizar la superficie de ataque potencial:

- Capa 1/2: permite que los hosts no autorizados se conecten a puertos de pared o redes inalámbricas y se comuniquen con los hosts dentro del mismo dominio de transmisión.
- Capa 3: permite a los hosts no autorizados obtener una dirección de red válida, posiblemente mediante suplantación, y comunicarse con hosts de otras zonas.
- Capa 4/7: permite a los hosts no autorizados establecer conexiones a puertos TCP o UDP y comunicarse con protocolos y servicios de la capa de aplicación.


Además, debe considerar la superficie de ataque externa/pública por separado de la superficie de ataque interna/privada.

Cada capa requiere su propio tipo de controles de seguridad para prevenir, detectar y corregir ataques. El aprovisionamiento de múltiples categorías y funciones de control para hacer cumplir múltiples capas de protección se conoce como defensa en profundidad. Los controles de seguridad implementados en el perímetro de red están diseñados para evitar que los hosts externos lancen ataques en cualquier capa de red. La división de la red privada en zonas segregadas está diseñada para mitigar los riesgos de los hosts internos que se vieron vulnerados o que se conectaron sin autorización.

Las debilidades en la arquitectura de red la hacen más susceptible a intrusiones no detectadas o a fallas catastróficas del servicio. Los puntos débiles típicos son los siguientes:

- Puntos únicos de falla: un “punto de pellizco” que depende de un solo servidor de hardware o dispositivo o canal de red.
- Dependencias complejas: servicios que requieren que estén disponibles muchos sistemas diferentes. Idealmente, la falla de sistemas o servicios individuales no debería afectar el rendimiento general de otros servicios de red.
- Disponibilidad sobre confidencialidad e integridad: a menudo es tentador tomar “atajos” para poner en marcha un servicio.  Darle menos prioridad a la seguridad puede representar una solución rápida, pero crea riesgos a largo plazo.
- Falta de documentación y control de cambios: los segmentos de red, los aparatos y los servicios pueden agregarse sin los procedimientos adecuados de control de cambios, lo que lleva a una falta de visibilidad de cómo se constituye la red. Es vital que los administradores de red entiendan los flujos de trabajo empresariales y los servicios de red que los sustentan.
- Dependencia excesiva de la seguridad del perímetro: si la arquitectura de red privada es “plana” (es decir, si cualquier host puede ponerse en contacto con cualquier otro host), penetrar el borde de la red le da al atacante libertad de movimiento.
