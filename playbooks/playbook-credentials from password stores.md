## Playbook: Credentials from Password Stores

### Investigar

- Monitorizar búsquedas en la memoria de palabras clave comunes, tales como password, pwd, login, store, secure, credentials, etc. 
- Supervisar los comandos y argumentos ejecutados que pueden buscar ubicaciones de almacenamiento de contraseñas comunes para obtener credenciales de usuario, así como procesos a los que se accede, procesos recién ejecutados, llamadas API o archivos accedidos con este fin.
- Tener en cuenta el posible uso de herramientas automatizadas que escanean la memoria en busca de contraseñas.
- Prevenir el almacenamiento de contraseñas en texto plano.
- Supervisar cualquier actividad anómala en torno a todas las aplicaciones de almacenamiento de contraseñas autorizadas.
- Vigilar el uso de aplicaciones de almacenamiento de contraseñas no autorizadas.
- Controlar el acceso a los archivos de la BBDD de almacenamiento de contraseñas del navegador web.

### Remediar
 
- Limitar la cantidad de cuentas y servicios con permiso para consultar información de los almacenes de contraseñas solo a aquellos necesarios. Asegurar que las cuentas y servicios con permisos para consultar almacenes de contraseñas solo tengan acceso a los secretos que necesiten.
- La contraseña para el llavero de inicio de sesión del usuario puede ser cambiada desde la contraseña de inicio de sesión del usuario. Esto aumenta la complejidad para un atacante porque necesitarían conocer una contraseña adicional.
- Realizar escaneos en puntos finales (*endpoints*, o más concretamente, dispositivos finales de una red tales como ordenadores de sobremesa, teléfonos móviles, tablets, portátiles, etc) con antivirus (AV)(***Endpoint/AV Scan***).
- Restablecer cualquier contraseña comprometida, así como las contraseñas de cualquier cuenta comprometida.
- Inspeccionar los backups en busca de IOCs (Indicadores de Compromiso) consistentes con el perfil del ataque previo a la recuperación del sistema.
- Eliminar todas las instancias de credenciales que se almacenaron de forma insegura.

#### Contener

- Utilice software de detección y respuesta de endpoints (EDR) para finalizar los procesos infractores.
- Se debe aislar al equipo o sistema afectado de la red, a fin de evitar que el malware se propague por esta. Esto debe mantenerse hasta que el incidente de seguridad se dé por finalizado y solucionado.
- Identificar y bloquear de inmediato las cuentas de usuario comprometidas que hayan sido utilizadas para acceder o almacenar credenciales en ubicaciones no autorizadas.
- Revisar los permisos de acceso a los almacenes de contraseñas y otras ubicaciones sensibles para asegurar que solo los usuarios autorizados tengan acceso y que los privilegios se ajusten a los principios de menor privilegio.
- Reforzar los controles de acceso mediante la implementación de autenticación de múltiples factores (MFA) o autenticación de un solo uso (OTP) en los sistemas de almacenamiento de contraseñas y otros sistemas críticos.
- Capacitar a los empleados para no usar contraseñas inseguras, no almacenarlas en texto plano, no compartir las contraseñas con nadie, etc.

### Comunicar

- Informar a todos los empleados relevantes sobre el incidente de compromiso de credenciales y las acciones tomadas para contener y remediar la situación.
- Informar a la alta dirección de la organización sobre el incidente, destacando los posibles impactos en la seguridad y en las operaciones del negocio, así como las medidas tomadas para mitigar los riesgos asociados.
- Si el incidente de compromiso de credenciales afecta a socios comerciales, clientes u otras partes externas, es importante comunicarse con ellos de manera transparente y oportuna. Esto puede implicar informarles sobre el incidente, los riesgos potenciales y las medidas que están siendo tomadas para abordar la situación.

### Recuperación

- Restaurar hasta el Punto de Recuperación Objetivo (RPO) dentro del Tiempo de Recuperación Objetivo (RTO).
    - El RPO es el punto en el tiempo al que una organización está dispuesta a recuperarse después de un desastre. 
    -   El RTO es la cantidad de tiempo que una organización está dispuesta a tolerar para que sus servicios vuelvan a estar disponibles después de un desastre. 
- Identificar y abordar cualquier daño colateral para minimizar cualquier impacto adicional en la organización.
- Resolver cualquier incidente de seguridad relacionado tales como posibles vulnerabilidades que hayan podido ser explotadas por los atacantes.
- Después de abordar cualquier daño colateral y resolver cualquier incidente de seguridad relacionado, se deben restaurar los sistemas afectados a su última copia de seguridad limpia. Esto implica volver a un estado conocido y seguro antes del incidente, utilizando copias de seguridad verificadas para garantizar la integridad y la seguridad de los datos y sistemas restaurados.

### Recursos

#### Referencia: Artículos y Recursos

- [MITRE ATT&CK](https://attack.mitre.org/techniques/T1555/)
- [CIRT Playbook Battle Cards](https://github.com/guardsight/gsvsoc_cirt-playbook-battle-cards/blob/master/Markdown/GSPBC-1035%20-%20Credential%20Access%20-%20Credentials%20from%20Password%20Stores.md)
- [RE&CT](https://atc-project.github.io/atc-react/)