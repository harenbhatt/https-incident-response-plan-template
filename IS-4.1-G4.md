# Plan de Respuesta a Incidentes
## Indice
1. [Introducción](#introduccion)  
    1.1. [Identificación de activos](#identificación-de-activos)  
    1.2. [Análisis de amenazas](#análisis-de-amenazas)  
    1.3. [Establecimiento de vulnerabilidades](#establecimiento-de-vulnerabilidades)  
    1.4. [Evaluación y cálculo de riesgo](#evaluación-y-cálculo-de-riesgo)  
    1.5. [Clasificación y priorización de proyectos](#clasificación-y-priorización-de-proyectos)  
    1.6. [Definición de proyectos](#definicion-de-proyectos)  
3. [Plan de respuesta a incidentes](#plan-de-respuesta-a-incidentes)
4. [Playbooks](#playbooks)
5. [Respuesta a las preguntas](#respuesta-a-las-preguntas)
6. [Conclusiones](#conclusiones)
7. [Bibliografía](#Bibliografía)  

## 1. Introducción <div id='introduccion' />

En el siguiente trabajo haremos una implementación de un plan de respuesta a incidentes, donde tocaremos puntos desde la identificación de activos hasta definición de proyectos. También tocaremos la recuperación y el análisis post-incidente. A través de un análisis de amenazas, evaluación de vulnerabilidades y cálculo de riesgos, se establecen las bases para una preparación robusta frente a posibles incidentes. Con la clasificación y priorización de proyectos, se enfoca la atención en las áreas de mayor riesgo, mientras que la definición de proyectos específicos permite una respuesta activa y dirigida. En el plan de respuesta a incidentes junto con los playbooks, ofreceremos un conjunto de herramientas, condiciones, flujos y tareas que se utilizan para responder a sucesos y amenazas de seguridad. 

## 1.1 Identificación de activos <div id='identificación-de-activos' />

Se identificaron los activos de nuestra empresa y se listaron en una hoja de cálculo:

![image](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/assets/86500067/f3535ca0-ec36-4b63-90d5-e988b0bba964)


## 1.2 Análisis de las amenazas <div id='análisis-de-amenazas' />

Hemos usado las amenazas que nos facilita INCIBE

![image](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/assets/86500067/7072adce-8676-444e-9ad5-d045771bb818)


## 1.3 Establecimiento de las vulnerabilidades <div id='establecimiento-de-vulnerabilidades' />

**Copias de seguridad gestionadas por empleados TIC sin procedimiento formal aprobado:**
- Riesgo: Pérdida de información en caso de incidentes.
- Recomendación: Establecer un procedimiento formal, concienciar al personal de TIC y
almacenar las copias de seguridad de manera segura.

**Antivirus gestionado por una subcontrata sin procedimiento aprobado:**
- Riesgos: carencia de actualizaciones y cuidado adecuado de la seguridad del antivirus.
- Recomendación: Establecer un procedimiento reconocido para la gestión y actualización
del software de protección.

**Políticas de seguridad por escrito ausentes:**
- Riesgo: Vulnerabilidad a riesgos y problemas de comunicación acerca de las expectativas
de protección.
- Recomendación: Establecer prácticas de seguridad oficiales que tratan de cuestiones
fundamentales.

**Falta de control sobre la securización de la página web y tienda online:**
- Riesgos: Ausencia de control y visibilidad de los datos digitales externalizados.
- Recomendación: Implementar métodos de observación y medición constantes, y
asegurarse de que el asesor externo exhiba una conducta segura

## 1.4 Evaluación y cálculo de riesgo <div id='evaluación-y-cálculo-de-riesgo' />

Realizamos una evaluación de los riesgos asumibles, clasificandolos con una nota dependiendo de la criticidad del riesgo:

![image](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/assets/86500067/d2b8365f-57eb-4103-bc22-71bad28bcbe3)

## 1.5 Clasificación y priorización de los proyectos <div id='clasificación-y-priorización-de-proyectos' />

 

## 1.6 Definición de proyectos <div id='definicion-de-proyectos' />



## 2. Plan de respuesta a incidentes <div id='plan-de-respuesta-a-incidentes' />
 

## 3. PlayBooks <div id='playbooks' />


## 4. Respuesta a las preguntas <div id='respuesta-a-las-preguntas' />

**1.a   ¿Que relacción existe entre el trabajo que has hecho con las matrices MITRE ATT&CK y RE&CT y el plan de respuesta que estás planteando? ¿De que manera te ha ayudado el trabajo previo sobre las matrices a la hora de generar el plan? Deja evidencias del trabajo que has realizado sobre le navigator de las matrices, para obtener la información.**
  
El trabajo realizado con las matrices MITRE ATT&CK y RE&CT ha proporcionado una base sólida para el desarrollo de cada playbook de respuesta a incidentes. Las tácticas y técnicas identificadas en MITRE ATT&CK nos ayudaron a comprender los posibles vectores de ataque y a desarrollar estrategias de prevención, detección y respuesta específicas para cada tipo de incidente. Por otro lado, las acciones de RE&CT nos permitieron implementar medidas concretas para fortalecer la seguridad de los sistemas, así como desarrollar procedimientos claros para responder de manera efectiva a los incidentes cuando ocurren. En conjunto, el trabajo con estas matrices ha asegurado que nuestros playbooks estén bien informados y sean efectivos en la gestión de incidentes de seguridad de manera integral y coherente.

![layer.svg](https://cdn.discordapp.com/attachments/1167391527862022184/1224001856372740126/G4__Playbook.svg?ex=661be78f&is=6609728f&hm=8b595f1a3be6b5930da6f6f379d10b3de6c699f4fc68a2200434d7a8796d7e63&&)

Para respaldar nuestra planificación de respuesta a incidentes, hemos utilizado el navegador MITRE ATT&CK, una herramienta invaluable que ofrece un marco exhaustivo de tácticas y técnicas. Esta herramienta nos ha permitido identificar y comprender las tácticas específicas de cada tipo de ataque, desde ataques de fuerza bruta hasta amenazas como el ransomware y el phishing.

Utilizando el navegador de MITRE ATT&CK, hemos examinado las tácticas y técnicas asociadas con cada tipo de ataque, lo que nos ha proporcionado una comprensión detallada de cómo se llevan a cabo estos ataques y qué medidas de seguridad y respuesta son necesarias para contrarrestarlos. Esto nos ha permitido desarrollar un plan de respuesta a incidentes sólido y bien fundamentado, que aborda no solo la prevención y detección de ataques, sino también la contención, erradicación y recuperación en caso de que ocurran.

*¿De que manera te ha ayudado el trabajo previo sobre las matrices a la hora de generar el plan?*
  
El trabajo previo sobre las matrices MITRE ATT&CK y RE&CT me ayudó a identificar tácticas y técnicas de ataque, desarrollar estrategias de prevención y detección, crear procedimientos de respuesta detallados y alinearnos con mejores prácticas de seguridad. Esto facilitó la generación de un plan de respuesta integral y efectivo para abordar una variedad de incidentes de seguridad de manera proactiva.

Por ejemplo, al analizar el playbook de Ransomware, pude relacionar las tácticas y técnicas de MITRE ATT&CK (como T1566 - Spearphishing Attachment, T1133 - External Remote Services) con medidas de contención, erradicación y recuperación específicas en el plan de respuesta. De manera similar, las acciones de bloqueo de comunicaciones maliciosas y la restauración desde copias de seguridad se alinean con las tácticas de MITRE ATT&CK y RE&CT para mitigar y recuperarse de un ataque de ransomware.


**1.b   ¿Qué playbooks has identificado como necesarios en este plan de respuesta y en que te has basado para identificar esos playbooks y saber que son los necesarios? Deja algún diagrama que describa el flujo de un playbook.** 

La elección de estos playbooks se basa en la evaluación de riesgos, la experiencia pasada y la comprensión de las tendencias actuales de amenazas. Además, la identificación se alinea con prácticas recomendadas en la industria de la ciberseguridad, considerando la frecuencia y el impacto potencial de cada tipo de incidente. Estos playbooks también reflejan áreas donde es probable que se requiera una respuesta rápida y especializada para minimizar el daño.

![image](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/assets/86500067/e8ca4ec8-a0ff-420e-8ebf-6de74c3a19bd)



**1.c   ¿Como te has asegurado que has cubierto todas las fases del plan de respuesta? ¿Qué fase consideras que está más floja en un plan? ¿Cuál de ellas consideras que está mejor trabajada en tu plan? Asegúrate de hablar de todas las fases y como las cubres.** 

Para asegurarnos de cubrir todas las fases del plan de respuesta, como grupo hemos implementado las siguientes medidas:

1.	**Investigación:** Nos aseguramos de investigar a fondo los posibles escenarios de amenazas y los tipos de ataques a los que podríamos enfrentarnos. Esto nos permite identificar las áreas críticas de nuestra infraestructura que podrían verse comprometidas y nos ayuda a prepararnos mejor para responder a cualquier incidente.
   
2.	**Preparación:** Realizamos evaluaciones de riesgos y vulnerabilidades para identificar las debilidades en nuestra infraestructura y tomamos medidas proactivas para mitigar esos riesgos. Esto incluye la implementación de controles de seguridad, la configuración de sistemas de alerta temprana y la capacitación de nuestro personal en prácticas de seguridad.
   
3.	**Remediación:** En caso de que ocurra un incidente, nos aseguramos de actuar rápidamente para contener y remediar la situación. Esto implica identificar la causa raíz del problema, aplicar parches de seguridad si es necesario y restaurar los servicios afectados a un estado operativo normal.
   
4.	**Contención:** Implementamos medidas de contención para limitar el impacto del incidente y evitar que se propague a otras partes de nuestra infraestructura. Esto puede incluir el bloqueo de direcciones IP maliciosas, la segmentación de la red y la redistribución del tráfico.
   
5.	**Comunicación:** Establecemos protocolos claros de comunicación para mantener informadas a todas las partes interesadas durante un incidente. Esto incluye definir roles y responsabilidades, establecer canales de comunicación y proporcionar actualizaciones regulares sobre la situación.
    
6.	**Recuperación:** Después de que se haya resuelto el incidente, nos enfocamos en la recuperación y en restaurar nuestros sistemas a un estado operativo normal. Esto implica restablecer servicios, fortalecer la seguridad de nuestra infraestructura y aprender de la experiencia para mejorar nuestra preparación para futuros incidentes.
   
 
En nuestro plan de respuesta, consideramos que la fase que está más floja es la de comunicación. Aunque tenemos protocolos establecidos y canales de comunicación definidos, a veces la transmisión de información durante un incidente puede no ser tan efectiva como debería ser. Esto puede deberse a la falta de coordinación entre los equipos involucrados, la falta de claridad en los mensajes o la demora en la entrega de actualizaciones importantes.
En nuestro plan de respuesta, identificamos que la fase más débil podría ser la de remedición. Esta fase implica la capacidad de los equipos para responder efectivamente a un ataque específico, como el cryptojacking, incluso si no tienen experiencia previa en enfrentar ese tipo de amenaza. La falta de experiencia directa puede dificultar la respuesta adecuada, ya que los equipos pueden no estar completamente familiarizados con las tácticas y técnicas utilizadas en ese tipo de ataque. Además, puede llevar más tiempo desarrollar e implementar soluciones efectivas cuando se enfrentan a una amenaza desconocida.


Por otro lado, consideramos que la fase mejor trabajada en nuestro plan es la de preparación. Hemos dedicado tiempo y recursos significativos a la evaluación de riesgos, la identificación de vulnerabilidades y la implementación de controles de seguridad. Además, hemos proporcionado capacitación adecuada a nuestro personal y hemos establecido procedimientos claros para responder a diferentes escenarios de amenazas. Esta preparación nos brinda una base sólida para enfrentar cualquier incidente de seguridad que pueda surgir.


**2.a   ¿En que consiste el Flujo de Toma de Decisiones y Escalado de tu plan de respuesta? ¿Existe un plan de comunicación, protocolos, etc? Si la respuesta es correcta, haz un resumen del plan y protocolos. Deja evidencias del flujo, mediante un diagrama.** 

El Flujo de Toma de Decisiones y Escalado en nuestro plan de respuesta a incidentes se basa en una serie de pasos diseñados para evaluar, decidir y actuar frente a posibles incidentes de seguridad. Este proceso está estructurado para asegurar una respuesta rápida y efectiva, minimizando el impacto del incidente en la organización. 

### Resumen del Plan y Protocolos

#### 1. Evaluar

- **Mantener la Calma**: Prioridad máxima para una respuesta considerada y efectiva.
- **Reunir Información**: 
  - Recopilar datos relevantes sobre el incidente.
  - Fuentes incluyen alarmas, eventos, y toda información pertinente.
- **Evaluar el Impacto**:
  - Determinar el impacto funcional y de la información.
  - Categorizar la severidad del incidente.

#### 2. Iniciar la Respuesta

- **Nombrar el Incidente**: Asignar un nombre en clave para facilitar la comunicación y el seguimiento.
- **Reunir el Equipo de Respuesta**:
  - Convocar al equipo de respuesta, incluyendo al Incident Commander.
  - Asegurar la participación de todos los stakeholders relevantes.
- **Establecer Comunicaciones**:
  - Iniciar canales de comunicación seguros.
  - Preferiblemente canales no afectados por el incidente.

#### 3. Comunicación y Protocolos

- **Comunicación Interna y Externa**:
  - Establecer líneas de comunicación claras con todas las partes interesadas.
  - Incluye reguladores, el público, y posiblemente clientes.
- **Actualizaciones Regulares**:
  - Proporcionar actualizaciones periódicas a todas las partes interesadas.
  - Usar los canales de comunicación establecidos.

#### 4. Escalar según sea necesario

- Basado en la evaluación continua del incidente.
- Escalar la respuesta según sea necesario, lo que puede incluir:
  - Añadir más recursos.
  - Consultar con expertos externos.
  - Notificar a las autoridades.

**3.a  ¿Como te has asegurado de que tu plan tiene respuestas resilientes? ¿Porque son resilientes y en qué fases se centran?**

Para evaluar la resiliencia del plan ante ataques de phishing, es crucial considerar cómo aborda cada fase del ataque, desde la investigación hasta la recuperación, y cómo se asegura de que la organización pueda adaptarse y recuperarse eficazmente. A continuación, analizaré cómo este playbook aborda la resiliencia en cada fase:


**Investigación:**

•	Ámbito del ataque: La investigación inicial se centra en comprender la extensión y el impacto del ataque de phishing, lo que permite una respuesta más rápida y precisa.

•	Analizar el mensaje: Se emplean herramientas seguras para inspeccionar el correo electrónico de phishing y recopilar datos sin comprometer la seguridad.

•	Analizar los enlaces y archivos adjuntos: Se evalúan los enlaces y archivos adjuntos para determinar la naturaleza y el riesgo del contenido sin poner en peligro la seguridad.


**Remediar:**

•	Planificación de eventos de remediación: La coordinación de acciones de remediación simultáneas ayuda a minimizar el tiempo de inactividad y limitar la propagación del ataque.

•	Equipo de Gestión de Crisis: Supervisa la remediación para garantizar una respuesta eficiente y efectiva.


**Contener:**

•	Aislamiento y Gestión de Cuentas Comprometidas: Se toman medidas inmediatas para identificar y aislar las cuentas afectadas, evitando así la propagación del ataque.

•	Reforzamiento de la Seguridad de Acceso: Se implementan medidas adicionales, como la autenticación multifactor y el control de acceso granular, para evitar accesos no autorizados.

•	Bloqueo y Neutralización de Amenazas: Se implementan bloqueos a nivel de DNS y políticas de filtrado de correos electrónicos para prevenir futuros ataques similares.


**Comunicar:**

•	Notificación Interna y Externa: La comunicación transparente y oportuna tanto dentro como fuera de la organización es crucial para coordinar una respuesta eficaz y mantener la confianza de las partes interesadas.


**Recuperación:**

•	Restauración de Sistemas y Servicios: Se restauran los sistemas desde copias de seguridad limpias y se refuerzan las defensas para prevenir futuros ataques.

•	Análisis Forense y Eliminación de Malware: Se realiza un análisis forense para comprender cómo ocurrió el ataque y eliminar completamente cualquier presencia maliciosa.

•	Educación y Concienciación sobre Seguridad: Se desarrollan programas de capacitación para educar a los empleados sobre las tácticas de phishing y mejorar la respuesta ante futuros ataques.


## 5. Conclusiones <div id='conclusiones' />




## 6. Bibliografía <div id='bibliografía' />
