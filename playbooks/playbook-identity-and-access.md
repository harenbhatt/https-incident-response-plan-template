
# Playbook: Compromiso de identidad y acceso


## Investigar

#### Identificación de la Brecha o Compromiso

- **Equipo**: Seguridad de TI y Análisis Forense
- **Acciones**:
  - Revisión de logs y alertas de seguridad.
  - Identificación de cuentas y accesos comprometidos.
  - Documentación de la línea de tiempo del incidente.

#### Evaluación del Impacto

- **Equipo**: Gestión de Riesgos
- **Acciones**:
  - Determinación del alcance del acceso indebido.
  - Evaluación del impacto sobre datos sensibles y sistemas críticos.
  - Clasificación del incidente según severidad y urgencia.

**Relación de matrices de ataque MITRE ATT&CK** <br>
- T1078 - **Valid Accounts:** Esta técnica se centra en el uso indebido de cuentas legítimas para obtener acceso. Es fundamental en incidentes de compromiso de identidad, ya que los atacantes frecuentemente explotan estas cuentas para moverse lateralmente dentro de la red y acceder a sistemas críticos. La identificación de cuentas y accesos comprometidos es crucial para entender la magnitud del compromiso y la metodología del atacante.
- T1530 - **Data from Cloud Storage Object:** Considerando el acceso indebido a datos sensibles y sistemas críticos, esta técnica refleja cómo los atacantes pueden haber accedido y potencialmente exfiltrado datos importantes almacenados en la nube, lo cual es crítico para evaluar el impacto del compromiso.

**Relación de matrices de defensa RE&CT**
- La acción de analizar logs y alertas de seguridad se alinea perfectamente con Analyse en RE&CT, que implica la revisión detallada de evidencia digital para identificar cómo ocurrió el compromiso, qué cuentas se vieron afectadas y documentar la línea de tiempo de los eventos del incidente.


## Remediar

### Planificación de Eventos de Remediación

- **Coordinador de Respuesta a Incidentes**: Encargado de la planificación y ejecución de la remediación.
- **Acciones**:
  - Programar eventos de remediación coordinando equipos de TI, seguridad, y operaciones.
  - Considerar interrupciones de servicio y comunicarlas proactivamente.
  - Priorizar acciones basadas en el impacto y la severidad del compromiso.

## Contención

### Pasos y Herramientas

#### Aislamiento de Sistemas y Cuentas Comprometidas

- **Herramientas**: Cortafuegos, sistemas de detección de intrusos, herramientas de gestión de identidad y acceso.
- **Equipo**: Operaciones de TI
- **Acciones**: Desconexión de sistemas afectados, revocación de accesos sospechosos.

#### Implementación de Controles de Acceso Temporales

- **Herramientas**: Sistemas de gestión de identidades, autenticación multifactor.
- **Equipo**: Seguridad de TI
- **Acciones**: Establecimiento de controles de acceso más estrictos, actualización de políticas de seguridad.

**Relación de matrices de ataque MITRE ATT&CK** <br>
- T1489 - Service Stop: Aunque no mencionado previamente, esta técnica puede ser relevante cuando se considera la desconexión de sistemas afectados o la desactivación de servicios comprometidos como parte del proceso de aislamiento.
- T1548 - Abuse Elevation Control Mechanism: Aunque no mencionado previamente, esta técnica resalta la importancia de implementar y fortalecer controles como la autenticación multifactor (MFA) para prevenir la elevación indebida de privilegios por parte de atacantes.

**Relación de matrices de defensa RE&CT**
- La desconexión de sistemas afectados y la revocación de accesos sospechosos son acciones directas bajo la estrategia Contain en RE&CT. Implementar un aislamiento efectivo es crucial para prevenir la propagación del ataque y la explotación adicional de recursos de la red.
-El objetivo es reforzar las defensas y mejorar la resiliencia organizacional frente a futuros ataques. La implementación de MFA y la revisión de políticas de acceso son ejemplos de cómo se puede endurecer la seguridad tras un incidente.

## Erradicar

### Pasos para Eliminar la Amenaza

#### Limpieza y Restauración de Sistemas

- **Herramientas**: Software de eliminación de malware, herramientas de restauración de sistemas.
- **Equipo**: TI y Seguridad de TI
- **Acciones**: Eliminación de malware o herramientas de acceso remoto instaladas por atacantes, restauración de sistemas desde copias de seguridad fiables.

**Relación de matrices de ataque MITRE ATT&CK** <br>
- T1485 - **Data Destruction:** Aunque el objetivo aquí es la restauración, es importante considerar que los atacantes pueden haber utilizado técnicas para destruir datos. La restauración de sistemas desde copias de seguridad confiables es un contramedida directa a esta técnica.
  
- T1490 - **Inhibit System Recovery:** Los atacantes pueden intentar complicar la recuperación del sistema mediante la deshabilitación o eliminación de puntos de restauración o copias de seguridad. La restauración de sistemas desde copias de seguridad externas o no comprometidas es esencial para contrarrestar esta táctica.

**Relación de matrices de defensa RE&CT**
- La acción de Eradicate en RE&CT abarca la eliminación de malware, herramientas de acceso remoto y cualquier otra presencia maliciosa de los sistemas comprometidos. Esto asegura que la amenaza sea completamente removida del entorno afectado.
- **Recover:** Aunque primariamente enfocada en la fase posterior de recuperación, esta acción también se relaciona estrechamente con la restauración de sistemas desde copias de seguridad fiables.

#### Referencia: Recursos de remediación

La remediación de incidentes de seguridad, especialmente en lo que respecta al compromiso de identidad y acceso, requiere una combinación de herramientas, estrategias y conocimientos especializados. A continuación, se ofrece una lista de recursos que pueden ser útiles para planificar y ejecutar la remediación de tales incidentes:

### Herramientas de Software

- **Herramientas de Análisis Forense**: Proporcionan capacidades para investigar y determinar cómo se produjo el compromiso. Ejemplos incluyen [Autopsy](https://www.autopsy.com/) y [Encase](https://www.guidancesoftware.com/encase-forensic).
- **Soluciones de Gestión de Identidad y Acceso (IAM)**: Facilitan la administración de identidades digitales, acceso y políticas. Soluciones populares incluyen [Microsoft Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory/) y [Okta](https://www.okta.com/).
- **Herramientas de Respuesta a Incidentes**: Permiten la contención rápida y efectiva de amenazas, como [CrowdStrike Falcon](https://www.crowdstrike.com/) y [FireEye](https://www.fireeye.com/).

### Estrategias y Mejores Prácticas

- **Centro para la Seguridad en Internet (CIS) Controles de Seguridad Cibernética**: Ofrece prácticas recomendadas para la seguridad cibernética, incluyendo la gestión de identidades y el acceso. [CIS Controls](https://www.cisecurity.org/controls/).
- **Marco de Ciberseguridad de NIST**: Proporciona directrices para mejorar la seguridad cibernética en las organizaciones, incluyendo la gestión de identidades y el acceso. [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework).

### Comunicar

### Estrategia de Comunicación

- **Responsable**: Relaciones Públicas y Gestión de Crisis
- **Acciones**:
  - Preparar comunicados internos y externos.
  - Establecer un canal de comunicación para actualizaciones regulares del incidente.
  - Coordinar con asesores legales para cumplir con requisitos de notificación de brechas.

**Relación de matrices de ataque MITRE ATT&CK** <br>
- Preparar comunicados internos y externos: Esta acción es esencial para mantener a todas las partes interesadas informadas sobre el estado del incidente, las medidas que se están tomando para mitigar el daño y cualquier impacto potencial.
- Establecer un canal de comunicación para actualizaciones regulares del incidente: La implementación de un canal dedicado para actualizaciones garantiza que la información sea distribuida de manera consistente y eficiente.

## Recuperación

### Pasos para la Restauración

#### Restauración de Operaciones Normales

- **Herramientas**: Sistemas de gestión de cambios, herramientas de monitorización.
- **Equipo**: TI y Operaciones
- **Acciones**: Restauración gradual de sistemas y accesos, monitoreo intensivo para detectar anomalías.

**Relación de matrices de ataque MITRE ATT&CK** <br>
- T1485 - **Data Destruction:** Aunque el objetivo aquí es la restauración, es importante considerar que los atacantes pueden haber utilizado técnicas para destruir datos. La restauración de sistemas desde copias de seguridad confiables es un contramedida directa a esta técnica.
  
- T1490 - **Inhibit System Recovery:** Los atacantes pueden intentar complicar la recuperación del sistema mediante la deshabilitación o eliminación de puntos de restauración o copias de seguridad. La restauración de sistemas desde copias de seguridad externas o no comprometidas es esencial para contrarrestar esta táctica.

**Relación de matrices de defensa RE&CT**
- La acción de Eradicate en RE&CT abarca la eliminación de malware, herramientas de acceso remoto y cualquier otra presencia maliciosa de los sistemas comprometidos. Esto asegura que la amenaza sea completamente removida del entorno afectado.
- **Recover:** Aunque primariamente enfocada en la fase posterior de recuperación, esta acción también se relaciona estrechamente con la restauración de sistemas desde copias de seguridad fiables.


## Recursos

- **Financieros y de Personal**: Asignación de presupuesto para herramientas de seguridad adicionales, contratación de expertos en seguridad externos si es necesario.
- **Logísticos**: Planificación de recursos para la restauración de operaciones, incluyendo hardware y software.

## Información adicional

1. <a name="identity-and-access-playbook-ref-1"></a>[Marcos para la gestión de identidad y acceso](https://www.nist.gov/)
2. <a name="ransomware-playbook-ref-2"></a>[Prácticas recomendadas de gestión de identidad y acceso](https://www.strongdm.com/)
