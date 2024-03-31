## Playbook: Phishing

### Investigar

- Examinar los registros, mensajes y/u otros artefactos de aplicaciones de terceros que puedan enviar mensajes de phishing para obtener acceso a los sistemas de las víctimas. El filtrado basado en DKIM+SPF o análisis de encabezados puede ayudar a detectar cuándo el remitente del correo electrónico es falso. La inspección de URL dentro del correo electrónico (incluida la expansión de enlaces acortados) puede ayudar a detectar enlaces que conducen a sitios maliciosos conocidos.
    - DMARC, DKIM y SPF son tres métodos de autenticación del correo electrónico . Juntos, ayudan a evitar que los spammers, phishers, y otras partes no autorizadas envíen correos electrónicos en nombre de un dominio que no poseen.
- Supervisar los registros de llamadas desde dispositivos corporativos para identificar patrones de posible phishing de voz, como llamadas hacia o desde números de teléfono maliciosos conocidos. Correlacionar estos registros con eventos del sistema.
- Revisar los archivos recién creados a partir de mensajes de phishing para obtener acceso a los sistemas de las víctimas.
- Monitorizar y analizar patrones de tráfico SSL/TLS e inspeccionar de paquetes asociados a protocolos que no siguen los estándares de protocolo y flujos de tráfico esperados (por ejemplo, paquetes extraños que no pertenecen a flujos establecidos, patrones de tráfico anómalos o gratuitos, sintaxis anómala o estructura).
    - Los certificados de SSL/TLS permiten a los navegadores web identificar y establecer conexiones de red cifradas con sitios web mediante el protocolo de capa de conexión segura/seguridad de la capa de transporte (SSL/TLS).
- Evaluar los datos de la red para detectar flujos de datos poco comunes. Los procesos que utilizan la red y que normalmente no tienen comunicación de red o que nunca antes se han visto son sospechosos.   
- Se debe poner especial atención a emails con archivos adjuntos sospechosos o de procedencia dudosa, a emails múltiples enviados desde fuentes desconocidas, emails con errores tipográficos en el nombre del dominio o aquellos que no cumplen con los métodos DKIM o SPF.
    - Revisar enlaces, archivos adjuntos y/o hashes en [VirusTotal](https://www.virustotal.com/gui/home/upload) o en sandboxes de malware tales como [Cuckoo Sandbox](https://github.com/cuckoosandbox), [Hybrid Analysis](https://www.hybrid-analysis.com/), [Joe Sandbox](https://www.joesecurity.org/) o [VMRay](https://www.vmray.com/).
    - También se recomienda analizar el mensaje, haciendo uso de un dispositivo seguro. Este no debe tener acceso a datos sensibles, credenciales o información importante en general. Se deben analizar los puntos siguientes:
        - Receptor del mensaje y objetivo del mismo.
        - Dirección de correo electrónico del remitente.
        - Asunto y cuerpo del mensaje.
        - Archivos adjuntos. Estos sólo deberían abrirse en máquinas virtuales aisladas de la red corporativa, y analizados por el equipo IT.
        - Enlaces, dominios o nombres de host. En este caso se sigue el mismo principio que con los archivos adjuntos, los enlaces no deben abrirse, con la excepción de hacerlo en un entorno controlado por el equipo IT.
        - Metadatos del correo electrónico. 

### Remediar

- Para bloquear la actividad se pueden utilizar sistemas de prevención de intrusiones (IPS) o sistemas de detección de intrusiones (IDS) en la red y sistemas diseñados para escanear y eliminar enlaces o archivos adjuntos de correo electrónico maliciosos.
- Determinar si ciertos sitios web o tipos de archivos adjuntos (por ejemplo: .scr, .exe, .pif, .cpl, etc.) que pueden usarse para phishing son necesarios para las operaciones comerciales y considerar bloquear el acceso si la actividad no se puede monitorizar o bien si plantea un riesgo importante.
- Cerrar el vector de ataque. Esto puede suponer desconectar al equipo afectado de la red, a fin de evitar la posible propagación del malware.
- Realizar escaneos en puntos finales (*endpoints*, o más concretamente, dispositivos finales de una red tales como ordenadores de sobremesa, teléfonos móviles, tablets, portátiles, etc) con antivirus (AV)(***Endpoint/AV Scan***).
- Examinar los logs para identificar si existen otros usuarios afectados.
- Se puede capacitar a los usuarios para que identifiquen técnicas de ingeniería social y correos electrónicos de phishing.

#### Contener

- Contención de la cuenta afectada. Esto supone cambiar sus credenciales, utilizar autenticación multifactor (MFA) y limitar el acceso de la cuenta a cualquier servicio, sistema o información hasta que exista total certeza que es seguro hacerlo. Otra opción es bloquear la cuenta hasta que el problema haya quedado resuelto. 
- Enumerar y evaluar los posibles daños causados por el incidente. Esto nos refiere al punto anterior y a cerrar el vector de ataque, o dicho de otro modo, aislar el equipo de origen, a fin de evitar una propagación del hipotético malware.
- Bloquear la IP externa e interna del equipo de origen, cerrar toda comunicación a través de los puertos del sistema y bloquear cualquier posible comunicación del usuario afectado. También se debe bloquear el dominio del email y el correo electrónico de origen.
- Poner en cuarentena tanto el mensaje recibido como el hipotético archivo adjunto que este pueda contener. Esta cuarentena debe realizarse teniendo en cuenta el formato del archivo, su hash, su ruta y el patrón de contenido del mismo.
    - El antivirus puede poner automáticamente en cuarentena archivos sospechosos.
- Considerar llevar a cabo una actualización del software que pudiera presentar posibles vulnerabilidades. Tras una investigación, se debería detectar la hipotética vulnerabilidad o falla de seguridad que el malware pudo haber apovechado.   

### Comunicar

- Informar a otros usuarios y partes interesadas relevantes sobre el ataque de phishing y las precauciones necesarias que deben tomar.
- Emitir un reporte al proveedor de servicios de correo electrónico o a la empresa de alojamiento web que se utilizó para enviar el correo electrónico malicioso.
- Escalar el incidente al nivel apropiado de gestión, si es necesario.
- Informar el incidente a las autoridades pertinentes, como organismos reguladores o encargados de hacer cumplir la ley, si es necesario.

### Recuperación

- En caso de interrupción del negocio, poner en marcha un plan de recuperación de desastres, además de hacer uso de las copias de seguridad en caso de considerarse necesario.
- Verificar que las credenciales se han cambiado correctamente.
- Es extremadamente recomendable preparar y poner en acción un programa de formación y adiestramiento de los empleados acerca de cómo responder a amenazas informáticas, y cómo prevenirlas en la medida de lo posible. Enfocándonos al phishing, que es el tema que nos ocupa, los empleados deben centrarse en los siguiente aspectos:
    - Errores ortográficos en el mensaje, el asunto o más importante aún, en el nombre del domninio.
    - Inconsistencia entre el nombre del remitente y el correo electrónico de origen.
    - Uso de correos eletrónicos personales como Gmail, Hotmail o Yahoo para asuntos de trabajo.
    - Enlaces sospechosos. En este punto se vuelve a aplicar la regla de los errores ortográficos. También se debe prestar atención a los servicios que acortan las urls, y si esto está presente en el enlace recibido. 

### Recursos

#### Referencia: Artículos y Recursos

- [Formas de detectar un ataque de phishing](https://www.securitymetrics.com/blog/7-ways-recognize-phishing-email)
- [Ejemplos de ataques de phishing](https://www.phishing.org/phishing-examples)
- [MITRE ATT&CK](https://attack.mitre.org/techniques/T1566/)
- [CIRT Playbook Battle Cards](https://github.com/guardsight/gsvsoc_cirt-playbook-battle-cards/blob/master/Markdown/GSPBC-1002%20-%20Credential%20Access%20-%20Spearphishing%20-%20Phishing.md)
- [RE&CT](https://atc-project.github.io/atc-react/)