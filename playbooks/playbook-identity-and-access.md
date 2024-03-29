
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


## Erradicar

### Pasos para Eliminar la Amenaza

#### Limpieza y Restauración de Sistemas

- **Herramientas**: Software de eliminación de malware, herramientas de restauración de sistemas.
- **Equipo**: TI y Seguridad de TI
- **Acciones**: Eliminación de malware o herramientas de acceso remoto instaladas por atacantes, restauración de sistemas desde copias de seguridad fiables.


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

## Recuperación

### Pasos para la Restauración

#### Restauración de Operaciones Normales

- **Herramientas**: Sistemas de gestión de cambios, herramientas de monitorización.
- **Equipo**: TI y Operaciones
- **Acciones**: Restauración gradual de sistemas y accesos, monitoreo intensivo para detectar anomalías.

## Recursos

- **Financieros y de Personal**: Asignación de presupuesto para herramientas de seguridad adicionales, contratación de expertos en seguridad externos si es necesario.
- **Logísticos**: Planificación de recursos para la restauración de operaciones, incluyendo hardware y software.

## Información adicional

1. <a name="identity-and-access-playbook-ref-1"></a>[Marcos para la gestión de identidad y acceso](https://www.nist.gov/)
2. <a name="ransomware-playbook-ref-2"></a>[Prácticas recomendadas de gestión de identidad y acceso](https://www.strongdm.com/)
