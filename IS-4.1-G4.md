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

**1.b   ¿Qué playbooks has identificado como necesarios en este plan de respuesta y en que te has basado para identificar esos playbooks y saber que son los necesarios? Deja algún diagrama que describa el flujo de un playbook.** 

La elección de estos playbooks se basa en la evaluación de riesgos, la experiencia pasada y la comprensión de las tendencias actuales de amenazas. Además, la identificación se alinea con prácticas recomendadas en la industria de la ciberseguridad, considerando la frecuencia y el impacto potencial de cada tipo de incidente. Estos playbooks también reflejan áreas donde es probable que se requiera una respuesta rápida y especializada para minimizar el daño.




**1.c   ¿Como te has asegurado que has cubierto todas las fases del plan de respuesta? ¿Qué fase consideras que está más floja en un plan? ¿Cuál de ellas consideras que está mejor trabajada en tu plan? Asegúrate de hablar de todas las fases y como las cubres.** 


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


## 5. Conclusiones <div id='conclusiones' />




## 6. Bibliografía <div id='bibliografía' />
