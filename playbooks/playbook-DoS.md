## Playbook: Ataque de Denegación de Servicio (DoS)

**Investigar, remediar (contener, erradicar) y comunicar en paralelo!**
Asigne los pasos a individuos o equipos para que trabajen simultáneamente; este playbook no es puramente secuencial. Utilice su mejor criterio.

### Investigar

1. Confirmar el ataque de Denegación de Servicio (DoS).
    * Verificar la degradación del rendimiento del sistema o la indisponibilidad de los servicios.
    * Analizar los registros del servidor en busca de tráfico anormal o patrones de ataque.
2. Identificar posibles fuentes del ataque.
    * Analizar el tráfico de red para identificar direcciones IP sospechosas o rangos de direcciones asociados con el ataque.
    * Diferenciar entre un ataque de Denegación de Servicio distribuido (DDoS) y un ataque DoS convencional.
        * Para ataques DDoS: Investigar la posibilidad de que el ataque provenga de una botnet o de dispositivos comprometidos distribuidos geográficamente.
        * Para ataques DoS convencionales: Investigar si el ataque se origina desde una sola fuente o un conjunto limitado de direcciones IP.
    * Considerar la posibilidad de que el ataque sea perpetrado por un atacante interno o externo.
3. Recopilar evidencia para la investigación.
    * Capturar registros de tráfico y paquetes de red para su análisis posterior.
    * Registrar cualquier actividad sospechosa observada durante el ataque, como intentos de autenticación fallidos o solicitudes de recursos específicos.

### Remediar

**Planificar la remediación** en la que estos pasos se pongan en marcha juntos (o de forma coordinada), con los equipos adecuados listos para responder a cualquier interrupción.

#### Contención

1. Mitigar el ataque en curso.
    * Identificar y bloquear las fuentes de tráfico malicioso utilizando reglas de firewall, listas de bloqueo IP u otras medidas de filtrado.
    * Utilizar servicios de mitigación de DDoS si están disponibles para desviar el tráfico no deseado.

#### Erradicación

1. Identificar la causa raíz del ataque.
    * Analizar los registros de tráfico para determinar el tipo y la fuente del ataque.
    * Investigar posibles vulnerabilidades en el sistema que podrían haber sido explotadas por los atacantes.

### Comunicar

**Comunicarse con las partes interesadas** para informar sobre el incidente y las acciones tomadas para mitigarlo.

1. Notificar a la dirección y al equipo de gestión de crisis.
    * Informar sobre la naturaleza y el alcance del ataque de Denegación de Servicio.
    * Proporcionar actualizaciones regulares sobre la remediación y las medidas de mitigación implementadas.

### Recursos

#### Herramientas y Tecnologías de Mitigación

- Firewalls con capacidades de filtrado avanzado.
- Servicios de mitigación de DDoS proporcionados por proveedores de seguridad.
- Sistemas de detección y prevención de intrusiones (IDS/IPS) para identificar y bloquear el tráfico malicioso.
