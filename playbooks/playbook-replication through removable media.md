## Playbook: Replication through Removable Media

### Investigar

- Supervisar las letras de unidad recién construidas o los puntos de montaje en medios extraíbles.
- Monitorizar los archivos inesperados a los que se accede en medios extraíbles.
- Vigilar los archivos recién construidos en medios extraíbles.
- Examinar los procesos recién ejecutados que se ejecutan desde medios extraíbles después de que se montan o cuando los inicia un usuario. Si se utiliza una herramienta de acceso remoto de esta manera para moverse lateralmente, es probable que se produzcan acciones adicionales después de la ejecución, como abrir conexiones de red para Comando y Control y Descubrimiento de información del sistema y de la red.

### Remediar

- Identificar y eliminar archivos maliciosos encontrados en medios extraíbles.
- Desconectar o bloquear el acceso a puertos USB y otros dispositivos de almacenamiento extraíbles en los sistemas afectados.
- Actualizar y parchear sistemas para cerrar posibles brechas de seguridad explotadas por el malware en medios extraíbles.
- Implementar políticas de seguridad claras y restricciones sobre qué dispositivos pueden conectarse y qué archivos pueden ser transferidos a través de medios extraíbles.

#### Contener

- Es importante analizar los archivos relacionados con el ataque en busca de información que pueda ayudar en la investigación. Esto puede incluir direcciones IP utilizadas por los atacantes, agentes de usuario que identifican los navegadores o herramientas utilizadas en el ataque, y detalles sobre las solicitudes de red realizadas durante el incidente.
- Fortalecer los activos críticos no afectados, con el objetivo de prevenir futuros ataques.
- En Windows 10, habilite las reglas de Reducción de superficie de ataque (ASR) para bloquear la ejecución de archivos ejecutables no firmados o que no sean de confianza (como .exe, .dll o .scr) desde unidades extraíbles USB. 
- Desactivar la ejecución automática si no es necesario.
- Aislar el sistema afectado de la red corporativa, con el objetivo que el malware presente en el dispositivo extraíble malicioso no se propague.

### Comunicar

- Notificar a los equipos pertinentes de la organización sobre el incidente de replicación a través de medios extraíbles, incluyendo detalles relevantes sobre el alcance y las medidas de contención tomadas.
- Informar a la alta dirección sobre el incidente, destacando los posibles impactos en la seguridad y las operaciones del negocio, así como las acciones tomadas para mitigar los riesgos asociados.
- Comunicar proactivamente con los usuarios afectados y otros empleados sobre el incidente, proporcionando pautas claras sobre cómo proceder y cómo protegerse de futuros incidentes similares.
- Coordinar la comunicación con partes externas relevantes, como socios comerciales o autoridades reguladoras, según sea necesario y en cumplimiento con las políticas de divulgación de la organización.

### Recuperación

- Restaurar hasta el Punto de Recuperación Objetivo (RPO) dentro del Tiempo de Recuperación Objetivo (RTO).
    - El RPO es el punto en el tiempo al que una organización está dispuesta a recuperarse después de un desastre. 
    -   El RTO es la cantidad de tiempo que una organización está dispuesta a tolerar para que sus servicios vuelvan a estar disponibles después de un desastre. 
- Restaurar los sistemas afectados a su última copia de seguridad limpia. Esto implica volver a un estado conocido y seguro antes del incidente, utilizando copias de seguridad verificadas para garantizar la integridad y la seguridad de los datos y sistemas restaurados.

### Recursos

#### Referencia: Artículos y Recursos

- [MITRE ATT&CK](https://attack.mitre.org/techniques/T1091/)
- [CIRT Playbook Battle Cards](https://github.com/guardsight/gsvsoc_cirt-playbook-battle-cards/blob/master/Markdown/GSPBC-1066%20-%20Initial%20Access%20-%20Replication%20Through%20Removable%20Media.md)
- [RE&CT](https://atc-project.github.io/atc-react/)