La IaC se ve facilitada en parte por dispositivos de red físicos y virtuales que se pueden configurar a través de scripts y API. A medida que las redes se vuelven más complejas, tal vez con miles de computadoras y dispositivos físicos y virtuales, se vuelve más difícil implementar políticas de red, como garantizar la seguridad y administrar el flujo de tráfico. 

Con tantos dispositivos para configurar, es mejor dar un paso atrás y considerar un modelo simplificado de cómo funciona la red. En este modelo, las funciones de red se pueden dividir en tres “planos”:

- Plano de control: toma decisiones sobre cómo se debe priorizar, asegurar y dónde se debe cambiar el tráfico.
- Plano de datos: maneja la conmutación y el enrutamiento del tráfico y la imposición de controles de acceso de seguridad.
- Plano de gestión: monitorea las condiciones del tráfico y el estado de la red.

Se puede utilizar una aplicación de redes definidas por software (SDN) para definir decisiones de políticas en el plano de control. Estas decisiones se implementan en el plano de datos mediante una aplicación de controlador de red, que interactúa con los dispositivos de red utilizando API. La interfaz entre las aplicaciones de SDN y el controlador de SDN se describe como la API “con dirección norte”, mientras que la interfaz entre el controlador y los dispositivos es la API “con dirección sur”. La SDN se puede utilizar para administrar dispositivos físicos compatibles, pero también conmutadores virtuales, enrutadores y cortafuegos. La arquitectura que admite el rápido despliegue de redes virtuales mediante máquinas virtuales y contenedores de propósito general se denomina virtualización de funciones de red (NFV) (redhat.com/en/topics/virtualization/what-is-nfv).

Esta arquitectura ahorra a los administradores de red y seguridad el trabajo y la complejidad de configurar de forma correcta los ajustes del dispositivo para hacer cumplir una directiva deseada. También permite una implementación (o aprovisionamiento) totalmente automatizado de enlaces de red, dispositivos y servidores. Esto hace que la SDN sea una parte importante de las últimas tecnologías de automatización y orquestación.


	Description
*La red definida por software (S D N) tiene un plano de gestión en la parte superior, que incluye a las personas. El plano de gestión supervisa el plano de control, que a su vez supervisa los routers en el plano de datos.*

Dispositivos de plano de datos gestionados por un dispositivo de plano de control y monitorizados por un plano de gestión. (Imágenes © 123RF.com.)