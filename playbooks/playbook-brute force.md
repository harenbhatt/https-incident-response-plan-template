## Playbook: Brute Force

### Investigar

- Monitorizar altos volúmenes de fallos de autenticación. Esto implica supervisar los registros de eventos de autenticación en busca de un número inusualmente alto de intentos fallidos de inicio de sesión. Estos intentos pueden indicar diferentes tipos de ataques dirigidos a comprometer las credenciales de usuario.
    - *Password guessing:* Intento de adivinar la contraseña correcta probando diferentes combinaciones de contraseñas comunes o predecibles.
    - *Password Cracking:* Intento de descifrar contraseñas utilizando técnicas como fuerza bruta o ataques de diccionario. Este tipo de ataques suelen producir un número elevado de errores de autenticación.
    - *Password Spraying:* Intenta de inicio de sesión en múltiples cuentas con un conjunto limitado de contraseñas comunes. Este tipo de ataque deja un rastro de múltiples intentos fallidos de inicio de sesión en diversas cuentas.
    - *Credential Stuffing:* Intento de inicio de sesión en una cuenta con credenciales filtradas de otros sitios web o servicios ajenos a la compañía.
- Investigar y eliminar todas las alertas asociadas con los activos afectados. Esto puede implicar la identificación de los sistemas afectados, el análisis de los registros de eventos relacionados y la recopilación de evidencia para una investigación más detallada.
- Verificar regularmente los registros del firewall, IDS (Sistema de Detección de Intrusiones), IPS (Sistema de Prevención de Intrusiones) y SIEM (Sistemas de gestión de información y eventos de seguridad) en busca de actividad inusual.    
- Examinar los comandos y argumentos ejecutados que pueden utilizar técnicas de fuerza bruta para obtener acceso a cuentas cuando se desconocen las contraseñas o cuando se obtienen hashes de contraseñas.

### Remediar

- Restablecer proactivamente las cuentas que se sabe que forman parte de credenciales vulneradas, ya sea inmediatamente o después de detectar intentos de fuerza bruta.
- Implementar la autenticación multifactor. Cuando sea posible, habilitar también la autenticación multifactor en servicios externos.
- Cambiar las contraseñas que hayan sido vulneradas por los atacantes.
    - Consultar las directrices del NIST al crear políticas de contraseñas.
    - En base a estas directrices anteriormente mencionadas, capacitar e instar a los empleados para usar contraseñas que cumplan con estas normas.

#### Contener

- Establecer políticas de bloqueo de cuentas después de una cierta cantidad de intentos fallidos de inicio de sesión para evitar que se adivinen las contraseñas. 
    - Una política demasiado estricta puede crear una condición de denegación de servicio y dejar los entornos inutilizables, bloqueando todas las cuentas utilizadas en la fuerza bruta. Utilice políticas de acceso condicional para bloquear inicios de sesión desde dispositivos no compatibles o desde rangos IP de organización fuera de los definidos.

### Comunicar

- Informar a todos los equipos relevantes dentro de la organización sobre el incidente de fuerza bruta detectado, lo que incluye equipos de seguridad, TI, gestión de riesgos y cualquier otro departamento relevante.
- Si los usuarios fueron afectados por el intento de fuerza bruta (por ejemplo, si sus cuentas fueron objeto de ataques de contraseñas), es importante comunicarse con ellos de manera transparente. Proporcionar orientación sobre cómo proteger sus cuentas, como cambiar sus contraseñas y habilitar la autenticación de dos factores si está disponible.
- Informar a la dirección sobre el incidente de fuerza bruta. 

### Recuperación

- Si se considera conveniente, debido a la intrusión de un/os posible/s atacante/s en la/s cuenta/s vulnerada/s, restaurar hasta el Punto de Recuperación Objetivo (RPO) dentro del Tiempo de Recuperación Objetivo (RTO).
    - El RPO es el punto en el tiempo al que una organización está dispuesta a recuperarse después de un desastre. 
    - El RTO es la cantidad de tiempo que una organización está dispuesta a tolerar para que sus servicios vuelvan a estar disponibles después de un desastre.
- Restaurar los sistemas vulnerados hasta su último backup limpio.
- Antes de restaurar cualquier sistema desde una copia de seguridad, es esencial inspeccionar las copias de seguridad en busca de IOC (Indicadores de Compromiso) que puedan indicar que las copias de seguridad también están comprometidas. Esto ayuda a evitar la restauración de sistemas comprometidos y a garantizar la integridad de los datos restaurados.
- Identificar y abordar cualquier daño colateral para minimizar cualquier impacto adicional en la organización.
- Resolver cualquier incidente de seguridad relacionado tales como posibles vulnerabilidades que hayan podido ser explotadas por los atacantes. 

### Recursos

#### Referencia: Artículos y Recursos

- [MITRE ATT&CK](https://attack.mitre.org/techniques/T1110/)
- [CIRT Playbook Battle Cards](https://github.com/guardsight/gsvsoc_cirt-playbook-battle-cards/blob/master/Markdown/GSPBC-1048%20-%20Credential%20Access%20-%20Brute%20Force.md)
- [RE&CT](https://atc-project.github.io/atc-react/)
- [Directrices del NIST para crear políticas de contraseñas](https://pages.nist.gov/800-63-3/sp800-63b.html)
