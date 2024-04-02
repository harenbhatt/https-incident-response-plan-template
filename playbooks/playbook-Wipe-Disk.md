## Playbook: Limpieza de disco

### Investigar

1. Identificar el origen del ataque si el problema proviene de un malware.
2. Identificar la vía del ataque.
3. Recopilar evidencias forenses si es posible.
4. Evaluar el impacto del ataque.
5. Determinar las vulnerabilidades explotadas y las técnicas usadas.

### Remediar

1. En caso de no hacerse, planificar copias de seguridad.  
2. Actualizar politicas de seguridad.
3. Actualizar playbooks con las lecciones aprendidas y nuevos metodos de remediación.

### Contención

1. Detectar que datos se guardaron en el disco duro si el origen del ataque ha sido un malware que haya podido extenderse por la red.
2. Eliminar el dispositivo afectado que contenía el disco duro de la red en caso de malware.
3. Prohibir cualquier acceso no autorizado al disco duro.

### Erradicar

- Restaurar las copias de seguridad a la más recientes.

### Comunicar

1. Notificar sobre el incidente al superior.
2. El superior deberá notificar inmediatamente al equipo de IT.
3. El equipo de IT deberá inmediatamente notificar a la dirección y a las autoridades competentes en caso de ser necesario.
4. Notificar a los proveedores y clientes si sus datos han sido afectados.

### Recuperación

- Restaurar la última copia de seguridad de los discos duros afectados.

### Recursos

1. Herramienta para crear copias de seguridad y restaurarlas del servidor llamada Bacula.
