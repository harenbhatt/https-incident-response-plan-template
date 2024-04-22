
## Playbook: Ransomware

**Investigar, remediar (contener, erradicar) y comunicar en paralelo. La contención es fundamental en los incidentes de ransomware, priorice en consecuencia.**

### Investigación

**Determinar el tipo de ransomware:**
- Equipo asignado: Equipo de Análisis de Malware.
- Estrategia: Utilizar herramientas avanzadas de análisis de malware para identificar la familia, variante o tipo específico de ransomware involucrado en el incidente. Analizar firmas, comportamiento y características únicas del malware.

**Analizar mensajes relacionados:**
- Equipo asignado: Equipo de Análisis de Mensajes.
- Estrategia: Revisar detenidamente todos los mensajes relacionados con el ransomware, incluyendo interfaces gráficas, archivos de texto/html, mensajes de voz, etc. Identificar patrones de lenguaje, contactos de correo electrónico, instrucciones de rescate y cualquier otra información relevante.

**Examinar archivos afectados:**
- Equipo asignado: Equipo de Análisis de Archivos.
- Estrategia: Investigar a fondo los archivos afectados por el ransomware. Analizar el esquema de cambio de nombre de los archivos encriptados, tipos de archivos afectados, iconos de archivos, etc. Determinar la extensión de la encriptación y evaluar la posibilidad de recuperación de datos.

- Comprobad:
  * Corrupción de archivos frente a encriptación
  * Tipos de archivos y ubicaciones
  * Usuario/grupo propietario de los archivos que son afectados
  * Icono de los archivos encriptados
  * Marcadores de archivos
 
**Determinar el alcance:**
- Equipo asignado: Equipo de Investigación de Alcance.
- Estrategia: Identificar el alcance total del incidente de ransomware. Determinar qué sistemas están afectados, identificar indicadores de compromiso (IOC), evaluar la sensibilidad de los datos comprometidos y encontrar el vector de infección utilizado por el atacante.

1. Evaluación del Impacto: Priorización y Justificación de Recursos
**Evaluación del Impacto Operacional y Económico:**
- Estima las pérdidas económicas potenciales y el riesgo financiero.
- Identifica operaciones críticas afectadas y misiones comprometidas.
- Calcula el costo de la interrupción del negocio, incluyendo la pérdida de productividad y el impacto en las relaciones con clientes y socios.

**Evaluación del Impacto en los Datos:**
- Valora la criticidad de los datos afectados para las operaciones de la empresa o la misión.
- Determina la sensibilidad de los datos comprometidos (por ejemplo, información confidencial, secretos comerciales).
- Analiza las implicaciones legales y de cumplimiento asociadas con los datos afectados (por ejemplo, GDPR para datos personales, HIPAA para información de salud).

2. Identificación del Vector de Infección:
Para localizar cómo se introdujo el ransomware, consulta las tácticas de "Acceso Inicial" en el marco de MITRE ATT&CK. Es crucial revisar las siguientes fuentes de información:

**Adjuntos de Correo Electrónico:**
- Examina los registros de correo electrónico para identificar mensajes sospechosos.
- Utiliza dispositivos y servicios de seguridad de correo electrónico para detectar amenazas.
- Emplea herramientas de descubrimiento electrónico para buscar pruebas de phishing o malware en comunicaciones.

**Protocolo de Escritorio Remoto (RDP) Inseguro:**
- Revisa los resultados de escaneos de vulnerabilidades que puedan indicar exposiciones de RDP.
- Verifica las configuraciones de firewall para detectar reglas permisivas que puedan haber sido explotadas.

**Auto-propagación (Gusano o Virus):**
- Analiza la telemetría del host y los datos del Endpoint Detection and Response (EDR) para rastrear movimientos laterales o signos de auto-propagación.
- Consulta los registros del sistema y realiza análisis forenses para identificar mecanismos de propagación.

**Relación de matrices de ataque MITRE ATT&CK** <br>
- MITRE ATT&CK: T1140 - Deobfuscate/Decode Files or Information puede ser relevante para comprender los mensajes codificados o ofuscados por el ransomware, incluyendo las notas de rescate o las instrucciones de pago.
- Para Adjuntos de Correo Electrónico, T1566 - Spearphishing Attachment es relevante, indicando el uso de correos electrónicos maliciosos como vector de infección.
- En el caso de RDP Inseguro, T1133 - External Remote Services muestra cómo los servicios remotos expuestos pueden ser explotados para ganar acceso.

**Relación de matrices de defensa RE&CT**
- Attribution se enfoca en identificar patrones de lenguaje, contactos de correo electrónico y otras pistas dentro de los mensajes relacionados que pueden ayudar a atribuir el ataque a ciertos actores de amenazas o campañas específicas.
- Detect y Prevent son las acciones correspondientes, centradas en la detección temprana de vectores de infección y la implementación de medidas preventivas como la segmentación de red, la mejora de la seguridad del correo electrónico y la restricción de accesos remotos no seguros.

### Remediar

**Planificar eventos de remediación** en los que estos pasos se lancen juntos (o de forma coordinada), con los equipos apropiados listos para responder a cualquier interrupción.
**Considere el momento y las compensaciones** de las acciones de reparación: su respuesta tiene consecuencias.

### Contención

**Poner en cuarentena sistemas infectados:**
- Equipo asignado: Equipo de Seguridad de Red.
- Estrategia: Implementar medidas de cuarentena para aislar los sistemas infectados y evitar la propagación del ransomware a través de la red. Desconectar los sistemas comprometidos de la red corporativa y bloquear el tráfico malicioso.

**Bloquear dominios y direcciones de comando y control:**
- Equipo asignado: Equipo de Seguridad de Red.
- Estrategia: Utilizar firewalls, sistemas de detección de intrusiones y listas negras de dominios para bloquear el acceso a los servidores de comando y control utilizados por el ransomware. Prevenir cualquier comunicación saliente hacia direcciones maliciosas.

**Erradicación:** 
- Reconstruir sistemas infectados
- Equipo asignado: Equipo de Infraestructura de TI.
- Estrategia: Restaurar los sistemas afectados desde copias de seguridad verificadas y limpias. Reinstalar sistemas operativos y aplicaciones si es necesario. Implementar medidas de seguridad adicionales para prevenir futuros ataques.

**Relación de matrices de ataque MITRE ATT&CK** <br>
- T1562.004 - Impair Defenses: Disable or Modify System Firewall: Los atacantes podrían intentar deshabilitar los firewalls. La contención efectiva puede requerir asegurar y posiblemente modificar la configuración del firewall para aislar sistemas infectados.
- T1571 - Non-Standard Port: Para la contención, es crucial bloquear el tráfico malicioso, lo que puede incluir el tráfico a través de puertos no estándar utilizados por el ransomware.

**Relación de matrices de defensa RE&CT**
- Aislar: Implementar medidas de cuarentena para aislar los sistemas infectados es clave para prevenir la propagación. Esto puede incluir desconectar física o lógicamente los sistemas de la red.
- Bloquear Comunicaciones: Utilizar firewalls y otros dispositivos de seguridad para bloquear el tráfico malicioso hacia y desde los sistemas comprometidos.

### Erradicar

**Reconstrucción de Sistemas Infectados:**
- Acción: Reconstruir los sistemas afectados utilizando fuentes confiables y limpias.
- Responsable: Equipo de Infraestructura de TI.
- Descripción: Restaurar los sistemas comprometidos utilizando imágenes o medios de instalación confiables y verificados.

**Restauración desde Copias de Seguridad:**
- Acción: Restaurar los sistemas desde copias de seguridad conocidas y sin compromisos.
- Responsable: Equipo de Gestión de Respaldo y Recuperación.
- Descripción: Utilizar copias de seguridad verificadas y limpias para restaurar los datos y sistemas afectados por el ransomware.

**Actualización y Activación de Protección de Puntos Finales:**
- Acción: Confirmar y activar la protección de puntos finales en todos los sistemas.
- Responsable: Equipo de Seguridad de TI.
- Descripción: Verificar que las soluciones de seguridad, como antivirus (AV), Next-Generation Antivirus (NGAV), y Detección y Respuesta de Endpoint (EDR), estén actualizadas y activadas en todos los sistemas afectados.

**Despliegue de Parches:**
- Acción: Desplegar parches en todos los sistemas, priorizando según la criticidad.
- Responsable: Equipo de Gestión de Parches.
- Descripción: Asegurar que todos los sistemas estén actualizados con los últimos parches de seguridad para cerrar posibles vulnerabilidades explotadas por el ransomware.

**Despliegue de Firmas Personalizadas:**
- Acción: Implementar firmas personalizadas en las herramientas de seguridad basadas en IOC descubiertos.
- Responsable: Equipo de Seguridad de Red y Endpoint.
- Descripción: Desarrollar y desplegar firmas específicas para detectar y prevenir futuros ataques de ransomware basándose en los indicadores de compromiso (IOC) identificados durante la investigación.

**Vigilancia de Reinfección:**
- Acción: Monitorear y aumentar la prioridad de las alarmas relacionadas con posibles reinfecciones.
- Responsable: Equipo de Monitoreo de Seguridad.
- Descripción: Mantener una vigilancia continua sobre los sistemas y redes para detectar cualquier signo de actividad maliciosa relacionada con el incidente de ransomware. Incrementar la prioridad de las alertas para una respuesta más rápida ante posibles intentos de reinfección.

**Relación de matrices de ataque MITRE ATT&CK** <br>
- T1490 - Inhibit System Recovery: La restauración de sistemas desde copias de seguridad es una táctica directa para contrarrestar los intentos de los atacantes de prevenir la recuperación del sistema.
- T1562.001 - Impair Defenses: Disable or Modify Tools: La actualización y activación de la protección de puntos finales es una medida para contrarrestar esta técnica, asegurando que las defensas estén operativas y actualizadas

**Relación de matrices de defensa RE&CT**
- Restore (Restaurar): La restauración de sistemas a partir de copias de seguridad se alinea con la acción de Recover en RE&CT, donde el enfoque está en recuperar los sistemas y datos afectados para volver a un estado operativo normal.
- RE&CT: Harden (Endurecer): La actualización de soluciones de seguridad y la implementación de protecciones adecuadas pueden considerarse como acciones de Harden, donde se refuerzan las defensas para prevenir reinfecciones o nuevos ataques.

### Comunicar

**No pagar el rescate y activar un plan de continuidad de negocio:**
- Equipo asignado: Equipo de Gestión de Crisis.
- Estrategia: Comunicar claramente la política de la organización de no pagar rescates y activar un plan de continuidad de negocio para mitigar el impacto del ransomware en las operaciones comerciales. Informar a todas las partes interesadas sobre los pasos a seguir y las medidas de contingencia implementadas.

**Recuperación de datos y consideraciones legales:**
- Equipo asignado: Equipo de Gestión Legal y de Cumplimiento.
- Estrategia: Coordinar la recuperación de datos de las copias de seguridad verificadas y limpias. Evaluar las implicaciones legales, regulatorias y financieras del incidente de ransomware. Colaborar con las autoridades pertinentes y cumplir con los requisitos de notificación de violación de datos según sea necesario.

**Relación de matrices de ataque MITRE ATT&CK** <br>
- T1562.001 - **Impair Defenses: Disable or Modify Tools:** Aunque esta técnica se centra en cómo los atacantes pueden intentar deshabilitar las defensas, la acción de evaluar las implicaciones legales y cumplir con los requisitos regulatorios refuerza indirectamente la necesidad de tener defensas robustas y procedimientos de cumplimiento en su lugar.

**Relación de matrices de defensa RE&CT**
- **RE&CT: Harden (Endurecer):** La coordinación de la recuperación de datos y la evaluación de implicaciones legales también se ven como parte de este proceso. Aquí, el enfoque se amplía para incluir la protección legal y regulatoria de la organización, asegurando que las respuestas al incidente no solo sean técnicamente sólidas sino también legalmente defensibles.


### Modelo de ciberresiliencia líder

**Objetivos:**
- Aprender del incidente para mejorar la postura de seguridad y la preparación frente a futuros ataques.
- Implementar cambios basados en las lecciones aprendidas y los insights obtenidos durante el incidente.

**Estrategias:**
- Revisión Post-Incidente: Analizar el manejo del incidente, identificar fortalezas y áreas de mejora.
- Actualización de Políticas y Procedimientos: Refinar los playbooks de respuesta a incidentes, políticas de seguridad y prácticas de formación.
- Inversión en Tecnología y Capacitación: Aumentar las capacidades de detección, protección y respuesta mediante la adquisición de nuevas herramientas y el entrenamiento del personal.

### Recursos

#### Referencia: Acciones de los usuarios ante la sospecha de ransomware

1. **Mantén la Serenidad:** Respire hondo y mantén la calma para pensar con claridad.
   
2. **Aísla tu Equipo:** Desconecta inmediatamente tu computadora de cualquier red para evitar la propagación del ransomware.

3. **Documenta Evidencias:** Utiliza tu teléfono móvil para tomar fotografías de tu pantalla, capturando cualquier mensaje sospechoso, archivos que parezcan estar cifrados, y errores del sistema que observes.

4. **Registra Detalles del Incidente:** Aprovecha la grabadora de voz de tu móvil o usa papel y lápiz para anotar todos los detalles relevantes sobre el incidente.
Esto incluye:
 * Las irregularidades que notaste.
 * Razones por las que te pareció un problema.
 * Actividades que estabas realizando al momento del descubrimiento.
 * Momento exacto o aproximado del primer indicio y frecuencia de los mismos desde entonces.
 * Ubicación y red en uso al momento del incidente (por ejemplo, en casa, en la oficina, usando red alámbrica o inalámbrica, con o sin VPN).
 * Sistemas afectados (por ejemplo, sistema operativo y nombre de host).
 * Cuenta de usuario afectada.
 * Tipo de datos a los que comúnmente se accede.
 * Personas con las que se ha discutido el incidente y los detalles compartidos.

5. **Comunícate con el Soporte Técnico:** Informa al help desk de la situación. Utiliza el enlace provisto para contactar al recurso correspondiente y ofrece toda la información posible para asistir en la resolución del problema.

6. **Paciencia y Colaboración:** La respuesta y solución pueden requerir tiempo y ser complejas. Tu paciencia y cooperación son cruciales para proteger los activos y la seguridad de la organización. Agradecemos tu apoyo.

#### Información adicional

1. <a name="ransomware-playbook-ref-2"></a>[No More Ransom!](https://www.nomoreransom.org/es/index.html)
1. <a name="ransomware-playbook-ref-3"></a>[Identificación de Ransomware](https://latam.kaspersky.com/resource-center/threats/ransomware-attacks-and-types)
1. <a name="ransomware-playbook-ref-4"></a>[MITRE ATT&CK Matrix](https://attack.mitre.org)
