## Playbook: Compromiso de identidad y acceso

### Investigar

1. Identificar el origen del ataque.
2. Identificar la vía del ataque.
3. Recopilar evidencias forenses.
4. Evaluar el impacto del ataque.
5. Determinar las vulnerabilidades explotadas y las técnicas usadas.

### Remediar

1. Eliminar la amenaza inicial modificando o eliminado la cuenta de usuario afectada.
2. Aplicar parches de seguridad a los sistemas afectados en caso de no haber sido actualizado anteriormente.
3. Si los datos han sido afectados, restaurar la integridad de los mismos a través de las copias de seguridad.
4. Comprobar los logs generados por el sistema sobre el acceso al sistema vulnerado.
5. Reforzar las medidas de control de acceso a los sistemas generando contraseñas más seguras.
6. Actualizar politicas de seguridad.
7. Actualizar playbooks con las lecciones aprendidas y nuevos metodos de remediación.
8. Monitorizar los sitemas para identificar con mayor facilidad los futuros ataques.

### Contención

1. Restringir temporalmente los privilegios de usuario para reducir el riesgo.
2. Bloquear el acceso a recursos compartidos en red al usuario vulnerado y desconectar los dispositivos que hayan sido afectados.
3. Monitorizar las cuentas y actividades de usuario sospechosas para detectar posibles intrusiones no deseadas.

### Erradicar

1. Revocar los permisos a los usuarios que hayan sido afectados y restablecer las contraseñas de sus cuentas.
2. Analizar los logs de acceso para identificar y eliminar cuentas de usuario no autorizadas.
3. Implementar autenticación multifactor en todos los sistemas y aplicaciones.
4. Realizar auditorías de seguridad para asegurar que los empleados cumplen las políticas de seguridad referentes a las contraseñas de las cuentas de usuario.+

### Comunicar

1. Notificar sobre el incidente al superior.
2. El superior deberá notificar inmediatamente al equipo de IT.
3. El equipo de IT deberá inmediatamente notificar a la dirección y a las autoridades competentes en caso de ser necesario.
4. Notificar a los proveedores y clientes si sus datos han sido afectados.

### Recuperación

- En caso de no haber sido recuperada la cuenta del empleado, eliminar la cuenta antigua y crearle una cuenta nueva siguiendo las politicas de seguridad de la empresa.

### Recursos

1. Para eliminar la cuenta de usuario o modificarla podemos usar el administrador de cuentas de Windows llamado "Cuentas".
2. Para monitorizar cuentas de usuario podemos utilizar el propio registro de eventos de Windows.
