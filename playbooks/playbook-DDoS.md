## Playbook: Ataque de Denegación de Servicio Distribuido (DDoS)

**Investigar, mitigar y comunicar en paralelo!**
Asigne los pasos a individuos o equipos para que trabajen simultáneamente; este playbook no es puramente secuencial (Exceptuando la fase "Mitigar" que SIEMPRE debe ser la primera). 

Utilice su mejor criterio.


### Mitigar

1. Implementar filtros de tráfico y reglas de firewall.
    * Bloquee las direcciones IP de origen conocidas del ataque.
    * Considerar bloqueo de IP de un país concreto en caso de que todas las peticiones vengan de un lugar concreto, puede ocurrir.
    * Configure reglas de firewall para filtrar el tráfico malicioso.
2. Escalar la infraestructura.
    * Aumente la capacidad de ancho de banda y los recursos de servidor para absorber el tráfico adicional.
    * Considerar conectar servidores adicionales disponibles para ganar tiempo.
    * Utilice servicios de CDN (Content Delivery Network) para distribuir el tráfico y mitigar el impacto del ataque.

### Comunicar

1. 1. Notificar a la dirección y al equipo de gestión de crisis.
1. 2. Documentar el incidente según el procedimiento establecido.
2. Comunicarse con los equipos de operaciones y desarrollo.
    1. Informar sobre las medidas de mitigación implementadas y las posibles interrupciones del servicio.
    2. Coordinar con los equipos de TI para garantizar la disponibilidad continua de los servicios críticos.
3. Comunicarse con los proveedores de servicios de red.
    1. Notificar a los proveedores de servicios de red sobre el ataque y solicitar asistencia adicional si es necesario.
    2. Coordinar con los proveedores de servicios de mitigación de DDoS para optimizar la respuesta al ataque.
4. Actualizar a los clientes y usuarios.
    1. Informar sobre posibles interrupciones del servicio y tiempo estimado de recuperación.
    2. Proporcionar actualizaciones periódicas sobre el estado del incidente y las medidas de mitigación.
5. Configurar la alerta de respuesta de emergencia.
    * Establezca alertas automáticas para notificar al equipo de seguridad sobre futuros picos inusuales de tráfico.
    * Automatice la respuesta de mitigación para que se active automáticamente ante futuros ataques.

### Investigar

1. Identificar y confirmar el ataque DDoS en curso.
    * Supervise el tráfico de red y analice los patrones de tráfico anómalos que puedan indicar un ataque DDoS en curso.
    * Utilice herramientas de monitoreo de red como Wireshark, Nagios, o soluciones específicas contra DDoS.
2. Determine el tipo de ataque DDoS.
    * Ataque de inundación SYN
    * Ataque de inundación UDP
    * Ataque de inundación HTTP
    * Otros tipos de ataques conocidos.
3. Evaluar la gravedad y el impacto del ataque.
    * Analice la magnitud del tráfico malicioso en comparación con el tráfico normal.
    * Determine si los servicios críticos están siendo afectados y en qué medida.
4. Identificar el origen y las fuentes del ataque.
    * Rastree las direcciones IP de origen del tráfico malicioso.
    * Utilice herramientas de geolocalización para identificar la ubicación aproximada de los atacantes.
    * Recopile información sobre la infraestructura utilizada por los atacantes.
5. Recuperar y conseguir toda la información relativa a los sistemas para ser investigados utilizando técnicas forenses, las cuales nos ayudarán a aprender más sobre el escenario.

### Evaluar y recuperar
1. Determinar el alcance del daño a los sistemas.
    - Daños financieros
    - Daños de imagen
    - Daños físicos en por ejemplo hardware
2. Restablecer sistemas y servicios al estado habitual de los mismos
    - Añadir configuraciones extras derivadas del ataque para el futuro
    - Desactivar las medidas aplicadas en la fase de mitigación


### Aprender

1. Configurar la alerta de respuesta de emergencia.
    * Establezca alertas automáticas para notificar al equipo de seguridad sobre futuros picos inusuales de tráfico.
    * Automatice la respuesta de mitigación para que se active automáticamente ante futuros ataques.
2. Mantener equipos y servicios para un posible nuevo escenario con necesidad de escalada de recursos.



### Recursos

#### Herramientas de Mitigación de DDoS

- Cloudflare
- Akamai
- AWS Shield
- Arbor Networks
- Radware
- F5 Networks

#### Herramientas de Monitoreo de Red

- Wireshark
- Nagios
- SolarWinds
- Cisco NetFlow
- Zabbix

#### Referencia: Artículos y Recursos

1. [Guía sobre DDoS](https://www.cloudflare.com/learning/ddos/what-is-a-ddos-attack/) de Cloudflare.
2. [Cómo protegerse contra ataques DDoS](https://aws.amazon.com/es/shield/) con AWS Shield.
3. [Cómo detectar y mitigar ataques DDoS](https://www.akamai.com/es/es/) con Akamai.
