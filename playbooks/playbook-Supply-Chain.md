## Playbook: Compromiso de la cadena de suministro

### Investigar

1. Identificar el origen del ataque al sistema afectado.
2. Identificar la vía del ataque.
3. Recopilar evidencias forenses a través de herramientas forenses.
4. Evaluar el impacto del ataque.
5. Determinar las vulnerabilidades explotadas y las técnicas usadas.

### Remediar

1. Eliminar la amenaza inicial si es posible y depedendiendo el sistema afectado en la cadena de suministro y el tipo de ataque.
2. Aplicar parches de seguridad a los sistemas afectados en caso de que no se hayan actualizado anteriormente.
3. Si los datos han sido afectados, restaurar la integridad de los mismos a través de las copias de seguridad.
4. Reforzar las medidas de control de acceso a los sistemas generando contraseñas más seguras en todos los sistemas de la cadena de suministro.
5. Actualizar politicas de seguridad.
6. Actualizar playbooks con las lecciones aprendidas y nuevos metodos de remediación.
7. Monitorizar los sistemas para identificar con mayor facilidad los futuros ataques.

### Contención

1. Aislar el sistema que haya sido comprometido de la red quitando el cable de red.
2. Implementar medidas de control de acceso en el sistema de la cadena de suministro que haya sido comprometido restringiendo sus permisos. 
3. Reforzar los activos críticos no afectados por el ataque a través de actualizaciones del sistema, generando contraseñas más seguras, etc.

### Erradicar

1. Clasificar el vector de ataque del sistema vulnerado en la cadena de suministro.
2. Analizar los activos afectados dentro del sistema afectado a través de herramientas de análisis forenses.
3. Parchear la vulnerabilidad que ha sido identificada y analizada con actualizaciones más recientes.
4. Eliminar completamente el malware que haya vulnerado el sistema en el caso de que haya sido el problema.
5. Restaurar las copias de seguridad a las más recientes.
6. En caso de que haya sido creado un playbook para el tipo de ataque que ha vulnerado el sistema con anterioridad, seguirlo paso a paso.

### Comunicar

1. Notificar sobre el incidente al superior.
2. El superior deberá notificar inmediatamente al equipo de IT.
3. El equipo de IT deberá inmediatamente notificar a la dirección y a las autoridades competentes en caso de ser necesario.
4. Notificar a los proveedores y clientes si sus datos han sido afectados.

### Recuperación

1. Restaruar gradualmente las operaciones de la cadena de suministro.
2. Implementar medidas de seguridad adicionales.
