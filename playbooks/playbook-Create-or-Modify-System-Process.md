## Playbook: Creacción o modificación de procesos para escalado.

### Investigar

1. Identificar el origen del ataque.
2. Identificar la vía del ataque.
3. Recopilar evidencias forenses.
4. Evaluar el impacto del ataque.
5. Determinar las vulnerabilidades explotadas y las técnicas usadas.

### Remediar

1. Eliminar la amenaza inicial dependiendo del origen del ataque.
2. Aplicar parches de seguridad a los sistemas afectados si el sistema no ha sido actualizado con anterioridad.
3. Si los datos han sido afectados, restaurar la integridad de los mismos a través de las copias de seguridad.
4. Comprobar los logs generados por el sistema sobre el acceso al sistema vulnerado.
5. Reforzar las medidas de control de acceso a los sistemas si es posible a través de contraseñas más seguras y autenticación multifactor.
6. Actualizar politicas de seguridad que haya sido afectada o crearla en caso de ser necesaria.
7. Actualizar playbooks con las lecciones aprendidas y nuevos metodos de remediación.
8. Monitorizar los sitemas afectados para identificar con mayor facilidad los futuros ataques.

### Contención

1. Separar el sistema o sistemas afectados de la red.
2. Monitorizar los procesos afectados. 

### Erradicar

- Eliminar el proceso de los dispositivos afectados parandolo o eliminandolo directamente.
- Restaurar el sistema a un punto anterior donde el proceso no haya sido modificado o creado.

### Comunicar

1. Notificar sobre el incidente al superior.
2. El superior deberá notificar inmediatamente al equipo de IT.
3. El equipo de IT deberá inmediatamente notificar a la dirección y a las autoridades competentes en caso de ser necesario.
4. Notificar a los proveedores y clientes si sus datos han sido afectados.

### Recuperación

1. Verificar si hay más procesos y que el sistema es funcion al tras la eliminación del proceso.
2. Si es necesario, restaurar el sistema a un momento anterior a la aparición del proceso.

### Recursos

1. Para la eliminación del proceso se puede utilizar el mismo administrador de tareas de Windows o el comando kill de Linux.
2. Para monitorizar los procesos en Windows podemos usar Process Monitor de Systernals.
