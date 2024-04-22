## Playbook: DDOS

### Introducción

1. **Objetivo**: Este playbook está diseñado para orientar a los equipos en la identificación rápida y la respuesta efectiva ante ataques DDoS, asegurando que las operaciones críticas continúen con el mínimo impacto posible.

2. **Alcance**: Cubre ataques DDoS de varios tipos, como volumétricos, de protocolo y a la capa de aplicación, proporcionando estrategias específicas para contrarrestar cada uno.

3. **Audiencia**: Dirigido al equipo de seguridad cibernética y operaciones de red, este documento sirve como una guía práctica para preparar y proteger la infraestructura tecnológica de la organización frente a ataques DDoS.

### Comprensión de los ataques DDoS

**Definición y Tipos**: Un ataque de denegación de servicio distribuido (DDoS) es un intento malicioso de interrumpir el tráfico normal de un servidor, servicio o red específicos inundándolos con un flujo abrumador de tráfico de internet. Los ataques DDoS se clasifican en tres categorías principales:

1. **Ataques Volumétricos**: Estos son los más comunes y su objetivo es saturar el ancho de banda de la víctima con grandes volúmenes de tráfico. Ejemplos incluyen inundaciones ICMP (Ping flood) y inundaciones UDP.

2. **Ataques de Protocolo:** Apuntan a explotar vulnerabilidades en los protocolos de la capa de red y transporte para consumir recursos de los servidores o equipos de infraestructura (como balanceadores de carga). Ejemplos son SYN floods y ataques de reflexión basados en NTP.

3. **Ataques a la Capa de Aplicación:** Se dirigen específicamente a aplicaciones web, intentando agotar los recursos del servidor ejecutando solicitudes legítimas pero excesivas. Los ataques HTTP flood son un ejemplo típico.

**Motivaciones del Atacante**: Los motivos detrás de los ataques DDoS varían desde el vandalismo y la protesta política (hacktivismo) hasta la extorsión y la competencia desleal. Algunos atacantes buscan interrumpir los servicios por razones ideológicas o como una demostración de poder, mientras que otros pueden emplear ataques DDoS para desviar la atención de las fuerzas de seguridad durante un robo de datos.

**Indicadores de Compromiso (IoCs)**: Los indicadores de compromiso son señales que pueden sugerir que una red o sistema está bajo ataque DDoS. Incluyen: aumento anormal del tráfico, realentización del servicio o inaccesibilidad, aumento en solicitudes fallidas y alertas de seguridad inusuales.

### Preparación

**Evaluación de Riesgo**

1. **Identificación de Activos Críticos:** Comenzar con un inventario de los activos digitales, identificando aquellos que son críticos para las operaciones del negocio. Esto incluye servidores web, DNS, sistemas de correo electrónico, y cualquier otro servicio que, si se ve comprometido, podría impactar significativamente en las operaciones del negocio.

2. **Análisis de Vulnerabilidades:** Realizar pruebas de penetración y evaluaciones de vulnerabilidad para identificar posibles debilidades en la infraestructura que podrían ser explotadas en un ataque DDoS. Esto puede incluir configuraciones de red inadecuadas, sistemas sin parchear, o falta de capacidad de red.

3. **Evaluación de Impacto:** Determinar el impacto potencial de un ataque DDoS en los activos críticos identificados. Considerar factores como la pérdida de ingresos, daño a la reputación, y otros impactos operativos o financieros.

4. **Determinación de Riesgo:** Combinar la información sobre vulnerabilidades y el impacto potencial para clasificar los riesgos asociados a cada activo crítico. Esto ayudará a priorizar las acciones de mitigación y preparación.

**Infraestructura de Resiliencia**

1. **Diseño de Red:** Implementar una arquitectura de red diseñada para soportar ataques DDoS, lo que puede incluir redundancia de ruta, balanceo de carga, y la segregación de la red para aislar los sistemas críticos de otros menos críticos.

2. **Capacidad de Red Sobredimensionada:** Asegurar que la infraestructura tenga capacidad adicional para manejar picos inesperados de tráfico. Esto puede requerir la expansión de la banda ancha disponible o la configuración de límites de tasa de tráfico dinámico.

3. **Defensas en Capas:** Implementar múltiples capas de seguridad, incluyendo firewalls de aplicación web (WAF), sistemas de prevención de intrusiones (IPS), y soluciones específicas de mitigación de DDoS para filtrar el tráfico malicioso antes de que pueda impactar en los servicios críticos.

### Detección y Análisis

**Monitoreo y Alertas**

1. **Implementación de Herramientas de Monitoreo:** Utilizar herramientas avanzadas de monitoreo de tráfico en tiempo real capaces de diferenciar entre picos de tráfico legítimos y actividades sospechosas que podrían indicar un ataque DDoS. Estas herramientas deben estar configuradas para monitorizar tanto el volumen de tráfico como los patrones de acceso.

2. **Establecimiento de Umbrales de Alerta:** Definir umbrales específicos para el tráfico, basados en el comportamiento normal de la red, que, una vez superados, generen alertas automáticas. Estos umbrales deben ser dinámicos y ajustarse según las tendencias de tráfico históricas y eventos conocidos que puedan causar picos legítimos de tráfico.

3. **Integración de Sistemas de Alerta:** Las alertas generadas por las herramientas de monitoreo deben integrarse con los sistemas de gestión de incidentes de la organización para asegurar una respuesta rápida. Esto puede incluir notificaciones a través de correo electrónico, SMS, o sistemas de tickets.

**Análisis del Ataque**

1. **Identificación del Tipo de Ataque:** Una vez detectado un aumento sospechoso en el tráfico, es crucial identificar el tipo de ataque DDoS. Esto puede incluir ataques volumétricos, de agotamiento de estado (por ejemplo, SYN flood), o ataques a la capa de aplicación (por ejemplo, HTTP flood).

2. **Evaluación del Tamaño y Vector del Ataque:** Determinar la magnitud del ataque y los vectores utilizados es esencial para seleccionar la estrategia de mitigación más efectiva. Esto implica analizar el volumen de tráfico, los tipos de paquetes involucrados, y las direcciones IP de origen.

3. **Uso de Análisis Forense:** Implementar técnicas de análisis forense para examinar los patrones de tráfico detalladamente. Esto puede ayudar a identificar las características específicas del ataque, como la geografía de los atacantes, los dispositivos utilizados, y la posible motivación detrás del ataque.

4. **Documentación y Comunicación:** Registrar todos los detalles del ataque, incluyendo cómo fue detectado, sus características, y cualquier medida tomada en respuesta inicial. Esta documentación es vital para la comunicación interna y externa, así como para la revisión post-incidente.

### Contención

**Estrategias de Mitigación**

1. **Filtrado de Tráfico:** Implementar filtros para bloquear tráfico malicioso basado en patrones conocidos asociados con ataques DDoS. Esto puede incluir direcciones IP sospechosas, patrones de paquetes inusuales, o firmas de ataque específicas. Los sistemas de prevención de intrusiones (IPS) y los firewalls de aplicación web (WAF) pueden configurarse para realizar esta tarea automáticamente.

2. **Rate Limiting:** Establecer límites en la cantidad de solicitudes que un usuario puede hacer en un período de tiempo específico ayuda a prevenir el agotamiento de recursos causado por ataques a la capa de aplicación. Esta técnica es particularmente efectiva contra ataques de inundación HTTP.

3. **Redistribución del Tráfico:** Utilizar técnicas de balanceo de carga y enrutamiento de tráfico para redistribuir las cargas de trabajo de manera más uniforme a través de múltiples servidores o centros de datos. Esto puede ayudar a absorber y dispersar el impacto del tráfico malicioso, manteniendo los servicios críticos en funcionamiento.

**Implementación de Controles**

1. **Defensas Pre-configuradas:** Tener defensas listas para ser activadas en el momento en que se detecta un ataque es crucial para una respuesta rápida. Esto incluye listas de bloqueo o permitido preestablecidas, reglas de filtrado, y configuraciones de rate limiting que pueden ajustarse según la naturaleza del ataque.

2. **Coordinación con Terceros:** En el caso de ataques de gran escala que sobrepasan la capacidad de la infraestructura local, es vital coordinar con proveedores de servicios de Internet (ISP) y servicios especializados de mitigación de DDoS. Estos proveedores pueden ofrecer soluciones como la limpieza de tráfico, que redirige el tráfico a través de centros de limpieza para filtrar el tráfico malicioso antes de que alcance la infraestructura de la organización.

3. **Uso de Servicios en la Nube:** La infraestructura en la nube puede ofrecer flexibilidad y recursos adicionales durante un ataque DDoS. Algunos proveedores de servicios en la nube ofrecen servicios de mitigación de DDoS integrados que pueden escalar automáticamente para absorber volúmenes de tráfico elevados.

4. **Pruebas y Actualizaciones Regulares:** Es fundamental probar regularmente las estrategias de mitigación y los controles implementados para asegurar su efectividad contra nuevos y emergentes vectores de ataque. Las pruebas pueden incluir simulacros de ataque y revisiones de configuración.

### Comunicación

**Protocolos de Comunicación**

1. **Definición de Portavoces:** Especificar quién está autorizado para hablar en nombre de la organización sobre el incidente.

2. **Canales de Comunicación:** Identificar los canales internos y externos para la difusión de información, como correos electrónicos internos y comunicados de prensa.

3. **Frecuencia de Actualizaciones:** Establecer un cronograma para las comunicaciones regulares, adaptándose según evolucione el incidente.

**Información Clave a Comunicar**

**Estado Actual del Ataque:** Breve descripción de la situación, incluyendo el inicio del ataque y su estado actual (activo, contenido, mitigado).

**Impacto:** Resumen del efecto del ataque en los servicios y operaciones, detallando cuáles están afectados y cómo.

**Acciones en Curso:** Descripción general de las medidas tomadas para responder al ataque, como la activación de defensas y la colaboración con especialistas en mitigación de DDoS

**Orientación para Afectados:** Consejos prácticos o recomendaciones para los usuarios o empleados impactados por el ataque.

**Compromiso con la Transparencia:** Afirmación del compromiso de la organización con mantener informadas a todas las partes interesadas.

### Remediación

1. **Acciones Correctivas**

2. **Identificación de Vulnerabilidades:** Analizar el ataque para identificar cómo los atacantes pudieron generar un impacto significativo. Esto puede incluir la explotación de configuraciones de red deficientes, fallos de seguridad específicos, o la falta de capacidad adecuada para manejar picos de tráfico.

3. **Aplicación de Parches y Actualizaciones:** Asegurar que todos los sistemas operativos, aplicaciones y dispositivos de red estén actualizados con los últimos parches de seguridad para cerrar las vulnerabilidades explotadas por los atacantes.

4. **Reconfiguración de Sistemas:** Modificar configuraciones de red y seguridad para cerrar las brechas que permitieron el ataque. Esto puede incluir el fortalecimiento de las políticas de firewall, la implementación de reglas de filtrado más estrictas y la mejora de las prácticas de autenticación.

5. **Pruebas de Penetración:** Realizar pruebas de penetración después de aplicar los cambios para validar la efectividad de las acciones correctivas. Las pruebas deben ser realizadas por expertos en seguridad o firmas externas para asegurar una evaluación imparcial.

**Fortalecimiento de la Seguridad**

1. **Evaluación de Herramientas y Procesos:** Revisar y evaluar las herramientas y procesos de seguridad existentes para identificar áreas de mejora. Esto puede incluir la adopción de tecnologías avanzadas de detección y mitigación de DDoS, la mejora de los sistemas de monitoreo y alerta, y la actualización de los protocolos de respuesta a incidentes.

2. **Capacitación y Concientización:** Reforzar la capacitación de los equipos de seguridad y TI, así como aumentar la concientización sobre seguridad en toda la organización. La educación continua sobre las últimas tácticas y herramientas de ataque DDoS puede ayudar a prevenir futuros incidentes.

3. **Desarrollo de Planes de Respuesta Mejorados:** Actualizar los planes de respuesta a incidentes basados en las lecciones aprendidas del ataque reciente. Esto debe incluir una revisión de los protocolos de comunicación, los procedimientos de escalado y la integración de nuevas estrategias de mitigación.

4. **Implementación de Redundancia y Resiliencia:** Aumentar la redundancia y resiliencia de la infraestructura crítica de TI para asegurar que la organización pueda mantener operaciones esenciales durante un ataque. Esto puede incluir soluciones como la distribución geográfica de los recursos, la implementación de sistemas de failover automáticos y el aumento de la capacidad de ancho de banda.

5. **Colaboración con Socios Externos:** Establecer o fortalecer las relaciones con socios externos, incluidos los proveedores de servicios de Internet, proveedores de servicios de mitigación de DDoS y otras organizaciones relevantes para una respuesta coordinada a futuros ataques.

### Recuperación

**Procedimientos de Recuperación**

1. **Restablecimiento de Servicios:** Se debe implementar un plan de acción detallado para restaurar los servicios afectados a su estado normal de funcionamiento. Esto puede incluir acciones como la reinstalación de sistemas, la restauración de copias de seguridad, y la implementación de medidas adicionales de seguridad para prevenir futuros ataques.

2. **Priorización de Servicios Críticos:** Durante la recuperación, es importante priorizar la restauración de servicios críticos para minimizar el impacto en las operaciones comerciales. Esto implica identificar qué servicios son más esenciales y asegurarse de que sean los primeros en ser restablecidos.

3. **Garantía de Seguridad:** Es fundamental restablecer los servicios de manera segura, asegurándose de que no haya puertas traseras o vulnerabilidades que puedan ser explotadas nuevamente por los atacantes. Se deben implementar medidas adicionales de seguridad, como parches de software y actualizaciones de seguridad, para fortalecer la postura de seguridad de la organización.

**Evaluación Post-Incidente**

1. **Análisis del Desempeño:** Se debe llevar a cabo una revisión exhaustiva del manejo del incidente, evaluando la eficacia de las acciones tomadas durante el ataque. Esto incluye revisar los procedimientos de respuesta, identificar áreas de mejora y reconocer lo que se hizo bien.

2. **Identificación de Deficiencias:** Durante la evaluación post-incidente, es importante identificar cualquier deficiencia en los controles y procesos de seguridad que hayan permitido el ataque o dificultado su respuesta. Esto puede incluir debilidades en la detección de amenazas, falta de capacidad de respuesta adecuada, o fallas en la coordinación entre equipos.

3. **Documentación de Lecciones Aprendidas:** Se deben documentar todas las lecciones aprendidas durante el incidente, incluyendo los aspectos positivos y las áreas de mejora. Esto proporciona una base sólida para futuras acciones correctivas y ayuda a fortalecer la postura de seguridad de la organización.

4. **Implementación de Mejoras:** Basándose en los hallazgos de la evaluación post-incidente, se deben implementar medidas correctivas y mejoras en los controles y procesos de seguridad. Esto puede incluir la revisión de políticas y procedimientos, la actualización de herramientas de seguridad, y la capacitación del personal.

**Relacion con matriz de ataque y respuesta**
1.	**Matriz de Ataque MITRE ATT&CK - Técnica de Impacto (Denegación de Servicio - T1499):** Esta técnica dentro de la matriz de ataque MITRE ATT&CK se enfoca en los ataques de denegación de servicio que pueden formar parte de un ataque DDoS. Proporciona una estructura para comprender cómo los atacantes pueden llevar a cabo estos ataques y qué técnicas específicas pueden emplear para interrumpir los servicios objetivo.
2.	**Matriz de Respuesta RE&CT - Infraestructura de Resiliencia (T1036):** Esta técnica dentro de la matriz de respuesta RE&CT se centra en la preparación y protección de la infraestructura tecnológica de una organización frente a ataques DDoS. Establece cómo una organización puede desarrollar una infraestructura robusta y resiliente que pueda resistir y recuperarse de tales ataques, asegurando la continuidad de las operaciones críticas.




