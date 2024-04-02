# Plan de respuesta a incidentes para ¿Ciberseguros?

Autor: Grupo 4, grupo4@ciberseguro.es

Revisión 1, Publicado 1 Abr 2024

Este plan de respuesta a incidentes está basado en el plan conciso, directivo, específico, flexible y gratuito disponible en [Github](https://github.com/counteractive/incident-response-plan-template) de Counteractive Security y discutido en [www.counteractive.net](https://www.counteractive.net/blog/an-ir-plan-you-will-use/)


Fue revisado por última vez el 1 Abr 2024. Fue probado por última vez en 1 Abr 2024.

# Introducción

En el siguiente trabajo haremos una implementación de un plan de respuesta a incidentes, donde tocaremos puntos desde la identificación de activos hasta definición de proyectos. También tocaremos la recuperación y el análisis post-incidente. A través de un análisis de amenazas, evaluación de vulnerabilidades y cálculo de riesgos, se establecen las bases para una preparación robusta frente a posibles incidentes. Con la clasificación y priorización de proyectos, se enfoca la atención en las áreas de mayor riesgo, mientras que la definición de proyectos específicos permite una respuesta activa y dirigida. En el plan de respuesta a incidentes junto con los playbooks, ofreceremos un conjunto de herramientas, condiciones, flujos y tareas que se utilizan para responder a sucesos y amenazas de seguridad. 

# Identificación de activos

Se identificaron los activos de nuestra empresa y se listaron:

![image](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/assets/86500067/f3535ca0-ec36-4b63-90d5-e988b0bba964)


# Análisis de las amenazas

Hemos usado las amenazas que nos facilita INCIBE

![image](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/assets/86500067/7072adce-8676-444e-9ad5-d045771bb818)


# Establecimiento de las vulnerabilidades

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

# Evaluación y cálculo de riesgo 

Realizamos una evaluación de los riesgos asumibles, clasificandolos con una nota dependiendo de la criticidad del mismo:

![image](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/assets/86500067/d2b8365f-57eb-4103-bc22-71bad28bcbe3)

# Respuesta a las preguntas

**1.a   ¿Que relacción existe entre el trabajo que has hecho con las matrices MITRE ATT&CK y RE&CT y el plan de respuesta que estás planteando? ¿De que manera te ha ayudado el trabajo previo sobre las matrices a la hora de generar el plan? Deja evidencias del trabajo que has realizado sobre le navigator de las matrices, para obtener la información.**
  
El trabajo realizado con las matrices MITRE ATT&CK y RE&CT ha proporcionado una base sólida para el desarrollo de cada playbook de respuesta a incidentes. Las tácticas y técnicas identificadas en MITRE ATT&CK nos ayudaron a comprender los posibles vectores de ataque y a desarrollar estrategias de prevención, detección y respuesta específicas para cada tipo de incidente. Por otro lado, las acciones de RE&CT nos permitieron implementar medidas concretas para fortalecer la seguridad de los sistemas, así como desarrollar procedimientos claros para responder de manera efectiva a los incidentes cuando ocurren. En conjunto, el trabajo con estas matrices ha asegurado que nuestros playbooks estén bien informados y sean efectivos en la gestión de incidentes de seguridad de manera integral y coherente.

![layer.svg](https://cdn.discordapp.com/attachments/1167391527862022184/1224001856372740126/G4__Playbook.svg?ex=661be78f&is=6609728f&hm=8b595f1a3be6b5930da6f6f379d10b3de6c699f4fc68a2200434d7a8796d7e63&&)

Para respaldar nuestra planificación de respuesta a incidentes, hemos utilizado el navegador MITRE ATT&CK, una herramienta invaluable que ofrece un marco exhaustivo de tácticas y técnicas. Esta herramienta nos ha permitido identificar y comprender las tácticas específicas de cada tipo de ataque, desde ataques de fuerza bruta hasta amenazas como el ransomware y el phishing.

Utilizando el navegador de MITRE ATT&CK, hemos examinado las tácticas y técnicas asociadas con cada tipo de ataque, lo que nos ha proporcionado una comprensión detallada de cómo se llevan a cabo estos ataques y qué medidas de seguridad y respuesta son necesarias para contrarrestarlos. Esto nos ha permitido desarrollar un plan de respuesta a incidentes sólido y bien fundamentado, que aborda no solo la prevención y detección de ataques, sino también la contención, erradicación y recuperación en caso de que ocurran.

*¿De que manera te ha ayudado el trabajo previo sobre las matrices a la hora de generar el plan?*
  
El trabajo previo sobre las matrices MITRE ATT&CK y RE&CT me ayudó a identificar tácticas y técnicas de ataque, desarrollar estrategias de prevención y detección, crear procedimientos de respuesta detallados y alinearnos con mejores prácticas de seguridad. Esto facilitó la generación de un plan de respuesta integral y efectivo para abordar una variedad de incidentes de seguridad de manera proactiva.

Por ejemplo, al analizar el playbook de Ransomware, pude relacionar las tácticas y técnicas de MITRE ATT&CK (como T1566 - Spearphishing Attachment, T1133 - External Remote Services) con medidas de contención, erradicación y recuperación específicas en el plan de respuesta. De manera similar, las acciones de bloqueo de comunicaciones maliciosas y la restauración desde copias de seguridad se alinean con las tácticas de MITRE ATT&CK y RE&CT para mitigar y recuperarse de un ataque de ransomware.


**1.b   ¿Qué playbooks has identificado como necesarios en este plan de respuesta y en que te has basado para identificar esos playbooks y saber que son los necesarios? Deja algún diagrama que describa el flujo de un playbook.** 

La elección de estos playbooks se basa en el estudio previo de nuestra empresa, la evaluación de riesgos y la comprensión de las tendencias actuales de amenazas. Hemos optado por seleccionar playbooks relaccionados con los ataques de Phishing, Ransomware, Inyección de codigo etc. Es decir, áreas donde se require una respuesta rápida y especializada para minimizar el daño.

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

#### Resumen del Plan y Protocolos

##### 1. Evaluar

- **Mantener la Calma**: Prioridad máxima para una respuesta considerada y efectiva.
- **Reunir Información**: 
  - Recopilar datos relevantes sobre el incidente.
  - Fuentes incluyen alarmas, eventos, y toda información pertinente.
- **Evaluar el Impacto**:
  - Determinar el impacto funcional y de la información.
  - Categorizar la severidad del incidente.

##### 2. Iniciar la Respuesta

- **Nombrar el Incidente**: Asignar un nombre en clave para facilitar la comunicación y el seguimiento.
- **Reunir el Equipo de Respuesta**:
  - Convocar al equipo de respuesta, incluyendo al Incident Commander.
  - Asegurar la participación de todos los stakeholders relevantes.
- **Establecer Comunicaciones**:
  - Iniciar canales de comunicación seguros.
  - Preferiblemente canales no afectados por el incidente.

##### 3. Comunicación y Protocolos

- **Comunicación Interna y Externa**:
  - Establecer líneas de comunicación claras con todas las partes interesadas.
  - Incluye reguladores, el público, y posiblemente clientes.
- **Actualizaciones Regulares**:
  - Proporcionar actualizaciones periódicas a todas las partes interesadas.
  - Usar los canales de comunicación establecidos.

##### 4. Escalar según sea necesario

- Basado en la evaluación continua del incidente.
- Escalar la respuesta según sea necesario, lo que puede incluir:
  - Añadir más recursos.
  - Consultar con expertos externos.
  - Notificar a las autoridades.

#### Diagrama de Flujo

![image](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/assets/86500067/69c1c87b-eeca-4889-99ec-a28fada844e3)


**3.a  ¿Como te has asegurado de que tu plan tiene respuestas resilientes? ¿Porque son resilientes y en qué fases se centran?**

Para evaluar la resiliencia del plan ante los ataques, es crucial considerar cómo aborda cada fase del ataque, desde la investigación hasta la recuperación, y cómo se asegura de que la organización pueda adaptarse y recuperarse eficazmente. A continuación, se analizará cómo el playbook de phishing aborda la resiliencia en cada fase:

**Investigación:**

-	Ámbito del ataque: La investigación inicial se centra en comprender la extensión y el impacto del ataque de phishing, lo que permite una respuesta más rápida y precisa.

-	Analizar el mensaje: Se emplean herramientas seguras para inspeccionar el correo electrónico de phishing y recopilar datos sin comprometer la seguridad.

- Analizar los enlaces y archivos adjuntos: Se evalúan los enlaces y archivos adjuntos para determinar la naturaleza y el riesgo del contenido sin poner en peligro la seguridad.


**Remediar:**

-	Planificación de eventos de remediación: La coordinación de acciones de remediación simultáneas ayuda a minimizar el tiempo de inactividad y limitar la propagación del ataque.

-	Equipo de Gestión de Crisis: Supervisa la remediación para garantizar una respuesta eficiente y efectiva.


**Contener:**

-	Aislamiento y Gestión de Cuentas Comprometidas: Se toman medidas inmediatas para identificar y aislar las cuentas afectadas, evitando así la propagación del ataque.

-	Reforzamiento de la Seguridad de Acceso: Se implementan medidas adicionales, como la autenticación multifactor y el control de acceso granular, para evitar accesos no autorizados.

-	Bloqueo y Neutralización de Amenazas: Se implementan bloqueos a nivel de DNS y políticas de filtrado de correos electrónicos para prevenir futuros ataques similares.


**Comunicar:**

-	Notificación Interna y Externa: La comunicación transparente y oportuna tanto dentro como fuera de la organización es crucial para coordinar una respuesta eficaz y mantener la confianza de las partes interesadas.


**Recuperación:**

-	Restauración de Sistemas y Servicios: Se restauran los sistemas desde copias de seguridad limpias y se refuerzan las defensas para prevenir futuros ataques.

-	Análisis Forense y Eliminación de Malware: Se realiza un análisis forense para comprender cómo ocurrió el ataque y eliminar completamente cualquier presencia maliciosa.

-	Educación y Concienciación sobre Seguridad: Se desarrollan programas de capacitación para educar a los empleados sobre las tácticas de phishing y mejorar la respuesta ante futuros ataques.


# Evaluar

1. **Mantenga la calma y la profesionalidad.**
2. Reúna la información pertinente, _por ejemplo_, alarmas, eventos, datos, suposiciones, intuiciones (**observar**).
3. Considerar las categorías de impacto, a continuación (**orientar**), y determinar si hay un posible incidente (**decidir**):
4. Iniciar una respuesta si hay un incidente (**actuar**).  En caso de duda, inicie una respuesta. El responsable de gestión de incidentes y el equipo de respuesta pueden ajustarse tras la investigación y la revisión.

## Evaluar el impacto funcional

¿Cuál es el impacto directo o probable en su trabajo? (_por ejemplo_, operaciones comerciales, empleados, clientes, usuarios)

* Degradación o fracaso del trabajo/negocio: **incidente!**
* Ninguno: evalúe el impacto de la información.

## Evaluar el impacto de la información

¿Cuál es el impacto directo o probable sobre sus datos/información, en particular los sensibles? (_por ejemplo_, información personal, datos de propiedad, financieros o sanitarios)

* Información a la que se ha accedido, cogido, cambiado o borrado: **incidente!**
* Ninguno: gestión a través de canales no relacionados con incidentes (por ejemplo, un ticket de soporte).

**Cada miembro del equipo está facultado para comenzar este proceso.** Si ves algo, dilo.

# Iniciar la respuesta

## Nombrar el incidente

Cree una [frase simple de dos palabras](http://creativityforyou.com/combomaker.html) para referirse al incidente -un nombre en clave- que se utilizará para el archivo y el canal del incidente.

## Reunir el equipo de respuesta

1. Llame al Incident Commander de turno/de guardia.
2. **No** discuta el incidente fuera del equipo de respuesta a menos que el Incident Commander lo autorice
3. Inicie y/o únase al chat de respuesta en discord.gg/ciberseguros.
4. Iniciar y/o unirse a la llamada de respuesta en 956 28 11 28 y/o zoom.acme.tld/cibersecur.
5. Preferible usar la llamada de voz, el chat y el intercambio seguro de archivos sobre cualquier otro método.
6. **No** utilizar el correo electrónico principal si es posible.  Si el correo electrónico es necesario, utilícelo con moderación o use ciberseguros@g.educaand.es.  Encripte los correos electrónicos cuando cualquier participante esté fuera del dominio ciberseguros.es.
7. **No** usar SMS/texto para comunicar el incidente, a menos que sea para decirle a alguien que se mueva a un canal más seguro.
8. Invite al personal de turno/guardia a la llamada y al chat de respuesta.
    * Invite al equipo de seguridad.  
    * Invitar al SME de los equipos y sistemas afectados. 
    * Invitar a las partes interesadas ejecutivas y a los asesores jurídicos lo antes posible, pero dar prioridad a los responsables operativos.  
9. OPCIONAL:_ Establecer una sala de colaboración en persona ("sala de guerra") para incidentes complejos o graves. 

### Referencia: Estructura del equipo de respuesta

* Equipo de Mando
  * [Incident Commander](#rol-incident-commander)
  * [Incident Commander-Adjunto](#rol-delegado-del-incident-commander-subdelegado)
  * [Escriba](#rol-scriba)
* Equipo de enlace
  * Enlace [interno](#rol-enlace)
  * Enlace externo
* Equipo de operaciones
  * [Expertos en la materia](#rol-experto-en-la-materia-subject-matter-expert-sme) (SME) para sistemas
  * SME para equipos/unidades de negocio
  * SME para Funciones Ejecutivas (_por ejemplo_, Legal, RRHH, Finanzas)

### Referencia: Información de contacto del equipo de respuesta

Rol del equipo de respuesta         | Información de contacto
----------------------------------- | ---------------------------
Localizador del Incident Commander  | {INCIDENT_COMMANDER_PAGER_NUMBER}}
Url del Incident Commander          | grupo4.org/ic-page
Lista del Incident Commander        | grupo4.org/ic-roster
Lista del equipo de seguridad       | Naim Cheddi Elkhattabi
Lista del equipo SME                | Álvaro Bueno Ortiz
Lista de ejecutivos                 | Iván Sales Cisneros

## Establecer el ritmo de batalla

### Realizar la primera llamada de respuesta

1. Realice la llamada inicial utilizando la [estructura de llamada de respuesta inicial](#referencia-estructura-de-la-llamada-de-respuesta-inicial)
2. Siga las instrucciones del Incident Commander.  Si el Incident Commander de turno/de guardia no se une a la llamada **dentro de 15 minutos** y usted es un Incident Commander capacitado, tome el mando de la llamada.
3. Siga las [instrucciones correspondientes a su función](#roles).
4. Siga la llamada y el chat, y comente según corresponda.  Si no es un SME, comunique las aportaciones a través del SME de su equipo si es posible.
5. **Mantenga la llamada y el chat activos durante todo el incidente para una comunicación basada en eventos.**
6. Programe actualizaciones **cada 4 horas** sobre la comunicación activa.

#### Referencia: Estructura de la llamada de respuesta inicial

* Incident Commander (IC): Mi nombre es [NOMBRE], soy el Incident Commander.  He designado a [NOMBRE] como adjunto y a [NOMBRE] como esccriba. ¿Quién está en la llamada?
* ESCRIBA: [Toma asistencia]
* IC: [Si falta personal clave] Adjunto, por favor llame a [PERSONAL FALTANTE].
* IC: [Hace preguntas para comprender la situación, los síntomas, el alcance, el vector, el impacto y el calendario del reportador del incidente, los SME aplicables para los sistemas y las unidades de negocio].
* SMEs: [Responde brevemente a las preguntas del IC].
* IC: [Si se trata de un incidente]:
  * En este momento, el resumen del incidente es el siguiente: [reitera el resumen].  El equipo de investigación estará dirigido por [NOMBRE], el equipo de reparación estará dirigido por [NOMBRE] y el equipo de comunicación estará dirigido por [NOMBRE].  Ellos coordinarán la composición del equipo y me informarán.  Los miembros del equipo, por favor, informen a su jefe de equipo correspondiente.
  * ¿Qué medidas de investigación, corrección o comunicación se han tomado ya? [esta debería ser una lista corta, pero tiene que salir ahora]
  * Esta llamada y el chat permanecerán activos y disponibles hasta el cierre del incidente, por favor, utilícelos para todas las comunicaciones relacionadas con el incidente.  Proporcione actualizaciones de estado en tiempo real en el chat, si es posible.  ¿Hay alguna pregunta o aportación restante? [responde a las preguntas]
  * Líderes de equipo, por favor procedan con sus acciones planeadas.  Nos reuniremos de nuevo en [UPDATE_TIME] para discutir el estado.  Gracias.
* IC: [Si esto no es un incidente]: En este momento, estos hechos no alcanzan el nivel de un incidente.  Me coordinaré directamente con el reportador del incidente para las acciones de seguimiento.  Gracias por su tiempo.

#### Referencia: Etiqueta de la llamada

* Únase tanto a la llamada como al chat.
* Mantenga el ruido de fondo al mínimo.
* Mantenga su micrófono silenciado hasta que tenga algo que decir.
* Identifícate cuando te unas a la llamada; di tu nombre y tu función (por ejemplo, "Soy el SME del equipo x").
* Habla con claridad.
* Sea directo y objetivo.
* Mantenga conversaciones/discusiones cortas y al grano.
* Comunicar cualquier preocupación al Incident Commander (CI) en la llamada.
* Respetar las limitaciones de tiempo impuestas por el Incident Commander.
* **Utilizar una terminología clara y evitar acrónimos o abreviaturas. La claridad y la precisión son más importantes que la brevedad.

### Realizar la actualización de la respuesta

* Llevar a cabo actualizaciones programadas utilizando la [estructura de llamada de actualización](#referencia-estructura-de-la-llamada-de-actualización-de-la-respuesta) cada 4 horas en el puente activo.
* Ajustar la frecuencia según sea necesario.
* Coordinar las actualizaciones independientes (_por ejemplo_, ejecutivas, legales) según sea necesario, pero con la menor frecuencia posible.

#### Referencia: Estructura de la llamada de actualización de la respuesta

* Incident Commander (IC): Desde la última actualización programada, el resumen del incidente es el siguiente:
  * [Impacto]
  * [Vector]
  * [Actualización del resumen]
  * [Actualización de la línea de tiempo]
* IC: Equipo de investigación, por favor proporcione una breve actualización
  * LÍDER DE LA INVESTIGACIÓN: [Actividades de investigación o "nada que informar"]
  * ¿Cuál es su plan de investigación recomendado?
  * ¿Qué acciones de investigación necesitan ser asignadas o aprobadas?  [escuchar, obtener consenso, encargar/aprobar]
* IC: Equipo de remediación, por favor proporcione una breve actualización
  * Líder de remediación: [Actividades de remediación o "nada que informar"]
  * ¿Cuál es su estrategia de corrección recomendada?  ¿Objeciones fuertes? [escuchar, obtener el consenso, asignar/aprobar]
  * ¿Qué acciones de corrección necesitan ser asignadas o aprobadas?
* IC: Equipo de comunicación, por favor, proporcione una breve actualización:
  * COMMUNICATIONS LEAD: [Actividades de comunicación o "nada que informar"]
  * ¿Cuál es su estrategia de comunicación recomendada?  ¿Objeciones fuertes? [escuchar, obtener consenso, encargar/aprobar]
  * ¿Qué acciones de comunicación necesitan ser asignadas o aprobadas?
* IC: Esta llamada y el chat permanecerán activos y disponibles hasta el cierre del incidente, por favor, utilícelos para todas las comunicaciones relacionadas con el incidente.  Si es posible, proporcione actualizaciones del estado en tiempo real en el chat.  ¿Hay alguna pregunta o aportación restante? [responde a las preguntas]
* IC: Líderes de equipo, por favor procedan.  Nos reuniremos de nuevo en [] para discutir el estado. Gracias.

## Supervisar el alcance

* Supervisar el alcance de la respuesta para asegurarse de que no excede el ámbito de control del Incident Commander.
* Si un incidente es lo suficientemente complejo y hay suficientes intervinientes, considere la posibilidad de crear subequipos.

### Crear Sub-Equipos

* En la preparación de incidentes complejos, se predefinen tres subequipos: Investigación, Remediación y Comunicación, generalmente responsables de esas funciones de respuesta.
* Crear un puente de llamadas y un chat para cada subequipo.
* El Incident Commander designará a los líderes de los equipos, que dependen del IC, y a los miembros de los equipos, que dependen de su líder.  _Los líderes de equipo no tienen que estar formados como Incident Commanders, pero es preferible que tengan alguna experiencia de liderazgo._
* El Incident Commander puede ajustar el propósito o el nombre de los subequipos según sea necesario.
* Si desea cambiar de equipo, pregunte a su **líder de equipo actual**.  **No** pregunte al Incident Commander, o al líder del otro(s) equipo(s).  Utilice la cadena de mando.

### Incidente dividido

Si un incidente resulta ser dos o más incidentes distintos:

* Establezca un nuevo [archivo de incidentes](#crear-el-archivo-del-incidente).
* Haga un seguimiento y coordine la investigación, la reparación y la comunicación en el archivo correspondiente.
* Considere la posibilidad de establecer subequipos para cada incidente.
* **Mantener un Incident Commander de alto nivel**, para coordinar los activos de baja densidad y alta demanda y mantener la unidad de mando.

# Investigar

**[Investigar](#investigar), [Remediar](#remediar) y [comunicar](#communicate) en paralelo, utilizando equipos separados, si es posible.** El Incident Commander coordinará estas actividades.  Notifique al Incident Commander si hay pasos que el equipo debe considerar.

## Crear el archivo del incidente

1. Cree un nuevo archivo de incidentes en ciberseguros.es/files/codename utilizando el [nombre del incidente](#nombre-del-incidente).  Utilice este archivo para el almacenamiento seguro de documentación, pruebas, artefactos, _etc._.
    * Proporcionar un almacenamiento digital seguro.
    * Proporcionar un intercambio de archivos seguro.
    * Obtener almacenamiento físico.
    * Compartir la ubicación del archivo del incidente en la llamada y el chat.
2. Documente el impacto funcional y de la información, si se conoce (véase [Evaluar](#evaluar)).
3. Documentar el vector, si se conoce (_por ejemplo_ web, correo electrónico, medios extraíbles).
4. Documente el resumen del incidente: un breve resumen del vector, el impacto, la investigación y la situación de la reparación, si se conoce.
5. Documente la línea de tiempo del incidente, incluyendo la actividad del atacante y la actividad de la respuesta.
6. Documente los pasos de investigación, reparación y comunicación.  Documente las actividades de forma independiente para que puedan combinarse y reutilizarse, si es posible.
7. Registre la información significativa, como:
    **Pruebas**, con la hora de recogida, la fuente, la cadena de custodia, _etc._.
    * **Sistemas afectados**, con el modo y el momento en que se identificó el sistema, y el resumen del efecto (_por ejemplo, tiene malware, datos a los que se ha accedido).
    * **Archivos de interés**, como el malware o los archivos de datos, con el sistema y los metadatos.
    * **Datos accedidos y tomados**, con nombres de archivos, metadatos y hora de presunta exposición.
    * **Actividad significativa del atacante**, como inicios de sesión y ejecución de malware, con la hora del evento.
    * **Indicadores de compromiso (IOC)** basados en la red, como direcciones IP y dominios.
    * **Indicadores de compromiso basados en el host**, como nombres de archivos, hashes y claves de registro.
 * **Cuentas comprometidas**, con el alcance del acceso y la hora del compromiso.

## Recoger las pistas iniciales

1. Entrevistar a los reportadores del incidente.
2. Recoger los datos de apoyo iniciales (_e._, alarmas, eventos, datos, suposiciones, intuiciones) en el archivo del incidente.
3. Entrevistar a lo(s) SME con experiencia en el dominio o el sistema, para comprender los detalles técnicos, el contexto y el riesgo.
4. Entrevistar a lo(s) SME de la unidad de negocio afectada, para comprender el impacto de la misión/negocio, el contexto y el riesgo.
5. Asegúrese de que las pistas son relevantes, detalladas y procesables.

### Referencia: Lista de recursos de respuesta

Recurso                             | Ubicación
----------------------------------- | ------------------------------------
Lista de información crítica        | ciberseguros.es/cil
Lista de activos críticos           | ciberseguros.es/cal
Base de datos de gestión de activos | ciberseguros.es/assests
Mapa de red                         | ciberseguros.es/netmap
Consola SIEM                        | siem.ciberseguros.es
Agregador de registros              | elk.ciberseguros.es

## Actualizar el plan de investigación y el archivo del incidente

1. Revisar y perfeccionar el impacto del incidente.
2. Revisar y refinar el vector del incidente.
3. Revisar y perfeccionar el resumen del incidente.
4. Revisar y perfeccionar la línea de tiempo del incidente con hechos e inferencias.
5. Crear hipótesis: qué puede haber ocurrido y con qué seguridad.
6. **Identificar y priorizar las preguntas clave** (lagunas de información) para apoyar o desacreditar las hipótesis.
    * Utilizar la matriz ATT&CK de MITRE o un marco similar para [desarrollar preguntas](#reference-attacker-tactics-to-key-questions-matrix).
        * [ATT&CK for Enterprise](https://attack.mitre.org/wiki/Main_Page), incluyendo enlaces a los específicos de Windows, Mac y Linux.
        * [ATT&CK Mobile Profile](https://attack.mitre.org/mobile/index.php/Main_Page) para dispositivos móviles.
    * Utilizar palabras interrogativas como inspiración:
        * **¿Cuándo?**: primer compromiso, primera pérdida de datos, acceso a x datos, acceso a y sistema, etc.
        * **¿Qué?**: impacto, vector, causa de origen, motivación, herramientas/explotaciones utilizadas, cuentas/sistemas comprometidos, datos atacados/perdidos, infraestructura, COIs, etc.?
        * **¿Dónde?**: ubicación del atacante, unidades de negocio afectadas, infraestructura, etc.?
        * **¿Cómo?**: compromiso (explotación), persistencia, acceso, exfiltración, movimiento lateral, etc.?
        * **¿Por qué?**: objetivo, momento, acceso a x datos, acceso a y sistema, etc.
        * **¿Quién?**: atacante, usuarios afectados, clientes afectados, etc.?
1. **Identificar y priorizar los dispositivos y estrategias testigo** para responder a las preguntas clave.
    * Consultar los diagramas de la red, los sistemas de gestión de activos y la experiencia de las SME
    * Consultar la [Lista de recursos de respuesta](#referencia-lista-de-recursos-de-respuesta))
1. Consulte los [playbook de incidentes](#playbooks) para conocer las preguntas clave, los dispositivos testigos y las estrategias para investigar las amenazas comunes o muy dañinas.

**El plan de investigación es fundamental para una respuesta eficaz; impulsa todas las acciones de investigación.  Utilice el pensamiento crítico, la creatividad y el buen juicio.**

### Referencia: Táctica del atacante a la matriz de preguntas clave

Táctica del atacante    | La forma en que los atacantes ...      | Posibles preguntas clave
----------------------- |----------------------------------------| -----------------------------------------
Reconocimiento          | ... aprender sobre los objetivos       | ¿Cómo? ¿Desde cuándo? ¿Dónde? ¿Qué sistemas?
Desarrollo de recursos  | ... construir infraestructuras.        | ¿Qué sistemas?
Acceso inicial          | ... entrar                             | ¿Cómo? ¿Desde cuándo? ¿Dónde? ¿Qué sistemas?
Ejecución               | ... ejecutar código hostil             | ¿Qué malware? ¿Qué herramientas? ¿Dónde? ¿Cuándo?
Persistencia            | ... quedarse en el sistema             | ¿Cómo? ¿Desde cuándo? ¿Dónde? ¿Qué sistemas?
Escalada de Privilegios | ... obtener acceso de mayor nivel      | ¿Cómo? ¿Dónde? ¿Qué herramientas?
Evasión de la defensa   | ... esquivar la seguridad              | ¿Cómo? ¿Dónde? ¿Desde cuándo?
Acceso a credenciales   | ... obtener/crear cuentas              | ¿Qué cuentas? ¿Desde cuándo? ¿Por qué?
Descubrimiento          | ... aprender nuestra red               | ¿Cómo? ¿Dónde? ¿Qué saben?
Movimiento lateral      | ... moverse                            | ¿Cómo? ¿Cuándo? ¿Qué cuentas?
Recogida                | ... encontrar y reunir datos           | ¿Qué datos? ¿Por qué? ¿Cuándo? ¿Dónde?
Mando y control         | ... herramientas y sistemas de control | ¿Cómo? ¿Dónde? ¿Quién? ¿Por qué?
Exfiltración            | ... tomar datos                        | ¿Qué datos? ¿Cómo? ¿Cuándo? ¿Dónde?
Impacto                 | ... romper cosas.                      | ¿Qué sistemas o datos? ¿Cómo? ¿Cuándo? ¿Dónde? ¿Cómo de malo?

Consulte la página [MITRE ATT&CK](https://attack.mitre.org/) para obtener más información e ideas.

## Crear y desplegar indicadores de compromiso (IOC)

> Haga hincapié en los indicadores **dinámicos y de comportamiento** junto con las huellas digitales estáticas.

* Crear IOCs basados en [pistas iniciales](#recoger-las-pistas-iniciales) y [análisis](#analyze-evidence).
* Cree IOCs usando un formato abierto soportado por sus herramientas (_por ejemplo_, [STIX 2.0](https://oasis-open.github.io/cti-documentation/stix/intro)), si es posible.
* Utilice la automatización, si es posible. 
* **No** desplegar "feeds" de IOCs no relacionados y no curados, ya que pueden causar confusión y fatiga.
* Considerar todos los tipos de IOC:
  * IOC basados en la red, como direcciones IP o MAC, puertos, direcciones de correo electrónico, contenido o metadatos del correo electrónico, URLs, dominios o patrones PCAP.
  * IOC basados en el host, como rutas, hashes de archivos, contenido o metadatos de archivos, claves de registro, MUTEXes, autoejecuciones o artefactos y permisos de usuarios.
  * IOCs basados en la nube, como patrones de registro para despliegues [SaaS](https://en.wikipedia.org/wiki/Software_as_a_service) o [IaaS](https://en.wikipedia.org/wiki/Infrastructure_as_a_service)
  * IOCs de comportamiento (a.ka., patrones, TTPs) tales como patrones de árbol de procesos, heurística, desviación de la línea base y patrones de inicio de sesión.
* Correlacionar varios tipos de IOC, como indicadores basados en la red y en el host en los mismos sistemas.

## Identificar los sistemas de interés

1. Validar si son relevantes.
2. Categorizar la(s) razón(es) por la(s) que son "de interés": tiene malware, acceso por cuenta comprometida, tiene datos sensibles, etc.  Trátelas como "etiquetas", puede haber más de una categoría por sistema.
3. Prioriza la recogida, el análisis y la reparación en función de las necesidades de la investigación, el impacto en el negocio, _etc_.

## Recogida de pruebas

* Priorizar en base al plan de investigación
* Recoger datos de respuesta en vivo utilizando [velociraptor](https://www.velocidex.org).
* Recoger los registros relevantes de los sistemas (si no forman parte de la respuesta en vivo), agregadores, SIEM o consolas de dispositivos.  
* Recoger la imagen de la memoria, si es necesario y si no forma parte de la respuesta en vivo, utilizando [winpmem](https://github.org/Velocidex/WinPmem). 
* Recoger la imagen del disco, si es necesario, utilizando [FTK Imager](https://www.exterro.com/ftk-imager).  
* Recoger y almacenar las pruebas de acuerdo con la política, y con la cadena de custodia adecuada. 

Considere la posibilidad de recopilar los siguientes artefactos como evidencia, ya sea en tiempo real (_por ejemplo_, a través de EDR o un SIEM) o bajo demanda:

###  Ejemplo de artefactos útiles

* Procesos en ejecución
* Servicios en ejecución
* Hashes ejecutables
* Aplicaciones instaladas
* Usuarios locales y de dominio
* Puertos de escucha y servicios asociados
* Configuración de resolución del sistema de nombres de dominio (DNS) y rutas estáticas
* Conexiones de red establecidas y recientes
* Clave de ejecución y otra persistencia de la ejecución automática
* Tareas programadas y trabajos cron
* Artefactos de ejecución pasada (por ejemplo, Prefetch y Shimcache)
* Registros de eventos
* Política de grupo y artefactos WMI
* Detecciones antivirus
* Binarios en ubicaciones de almacenamiento temporal
* Credenciales de acceso remoto
* Telemetría de conexiones de red (por ejemplo, netflow, permisos de cortafuegos)
* Tráfico y actividad de DNS
* Actividad de acceso remoto, incluido el Protocolo de Escritorio Remoto (RDP), la red privada virtual (VPN), SSH, la informática de red virtual (VNC) y otras herramientas de acceso remoto
* Cadenas de identificadores de recursos uniformes (URI), cadenas de agentes de usuario y acciones de aplicación del proxy
* Tráfico web (HTTP/HTTPS)

## Analizar las pruebas

* Priorizar basándose en el plan de investigación
* Analizar y clasificar los datos de la respuesta en vivo
* Analizar la memoria y las imágenes de disco (es decir, realizar análisis forenses)
* Analizar el malware
* _OPCIONAL:_ Enriquecer con investigación e inteligencia
* Documentar nuevos indicadores de compromiso (IOCs)
* Actualizar el archivo del caso

### Ejemplo de indicadores útiles

* Comportamiento inusual de autenticación (_e._, frecuencia, sistemas, hora del día, ubicación remota)
* Nombres de usuario con formato no estándar
* Binarios no firmados que se conectan a la red
* Balizamiento o transferencias de datos significativas
* Solicitudes de línea de comandos PowerShell con comandos codificados en Base64
* Actividad excesiva de RAR, 7zip o WinZip, especialmente con nombres de archivo sospechosos
* Conexiones en puertos no utilizados previamente.
* Patrones de tráfico relacionados con el tiempo, la frecuencia y el recuento de bytes
* Cambios en las tablas de enrutamiento, como la ponderación, las entradas estáticas, las pasarelas y las relaciones entre pares.

## Iterar la investigación

[Actualizar el plan de investigación](#actualizar-el-plan-de-investigación-y-el-archivo-del-incidente) y repetir hasta el cierre.

# Remediar

**[Investigar](#investigar), [Remediar](#remediar) y [Comunicar](#comunicar) en paralelo, utilizando equipos separados, si es posible.** El Incident Commander coordinará estas actividades. Notifique al Incident Commander si hay pasos que el equipo debe considerar

## Actualización del plan de remediación

1. Revise el archivo del incidente en ciberseguros.es/files/codename utilizando el [nombre del incidente](#nombre-del-incidente)
2. Revise los [playbook](#playbooks) aplicables.
3. Revise la [lista de recursos de respuesta](#referencia-lista-de-recursos-de-respuesta).
4. Considere qué tácticas del atacante están en juego en este incidente.  Utilice la lista de MITRE [ATT&CK](https://attack.mitre.org/wiki/Main_Page) (_i._, Persistencia, Escalada de Privilegios, Evasión de la Defensa, Acceso a Credenciales, Descubrimiento, Movimiento Lateral, Ejecución, Recolección, Exfiltración y Mando y Control), o un marco similar.
5. Desarrollar remedios para cada táctica en juego, en la medida en que sea factible teniendo en cuenta las herramientas y los recursos existentes.  Considere remedios para [Proteger](#protección), [Detectar](#detección), [Contener](#contención), y [Erradicar](#erradicar) cada comportamiento del atacante.
6. Priorizar en base a la [estrategia de tiempo](#choose-remediation-timing), el impacto y la urgencia.
7. Documentar en el archivo de incidentes.

Utilice [marcos de seguridad de la información (infosec)](https://www.nist.gov/cyberframework) como inspiración, pero **no utilice la reparación de incidentes como sustituto de un programa de infosec con un marco apropiado.** Utilícelos para complementarse.

### Protección

> "¿Cómo podemos evitar que la táctica X se repita o reducir el riesgo?  ¿Cómo podemos mejorar la protección futura?"

Utilice lo siguiente como punto de partida para la corrección de la protección:

* Parchear las aplicaciones.
* Parchee los sistemas operativos.
* Actualice las firmas de IPS de la red y del host.
* Actualizar las firmas de protección de puntos finales/EDR/antivirus.
* Reducir las ubicaciones con datos críticos.
* Reducir las cuentas administrativas o privilegiadas.
* Habilitar la autenticación multifactor.
* Reforzar los requisitos de las contraseñas.
* Bloquear los puertos y protocolos no utilizados en los límites del segmento y de la red, tanto entrantes como salientes.
* Poner en lista blanca las conexiones de red para los servidores y servicios críticos.

### Detección

> "¿Cómo podemos detectar esto en los nuevos sistemas o en el futuro?  ¿Cómo podemos mejorar la detección y la investigación en el futuro?"

Utilice lo siguiente como punto de partida para la corrección de detecciones:

* Mejorar el registro y la retención de los registros del sistema, en particular de los sistemas críticos.
* Mejorar el registro de las aplicaciones, incluidas las aplicaciones SaaS.
* Mejorar la agregación de registros.
* Actualizar las firmas de IDS de la red y del host utilizando IOC.

### Contención

> "¿Cómo podemos evitar que esto se extienda o se agrave? ¿Cómo podemos mejorar la contención en el futuro?"

Utilice lo siguiente como punto de partida para la corrección de la contención:

* Implementar listas de acceso (ACL) en los límites de los segmentos de la red.
* Implementar bloqueos en el límite de la empresa, en múltiples capas del [modelo OSI](https://en.wikipedia.org/wiki/OSI_model).
* Desactivar o eliminar el acceso de las cuentas comprometidas.
* Bloquear direcciones IP o redes maliciosas.
* Bloquee los dominios maliciosos.
* Actualizar las firmas de IPS y antimalware de la red y el host mediante COI.
* Retirar de la red los sistemas críticos o comprometidos.
* Póngase en contacto con los proveedores para obtener ayuda (por ejemplo, proveedores de servicios de Internet, proveedores de SaaS).
* Poner en lista blanca las conexiones de red para los servidores y servicios críticos.
* Matar o deshabilitar procesos o servicios.
* Bloquear o eliminar el acceso de proveedores y socios externos, especialmente el acceso privilegiado.

### Erradicar

> "¿Cómo podemos eliminar esto de nuestros activos?  ¿Cómo podemos mejorar la erradicación en el futuro?"

Utilice lo siguiente como punto de partida para la remediación de la erradicación:

* Reconstruir o restaurar los sistemas y datos comprometidos a partir de un estado bueno conocido.
* Restablecer las contraseñas de las cuentas.
* Eliminar cuentas o credenciales hostiles.
* Borrar o eliminar malware específico (¡difícil!).
* Implementar proveedores alternativos.
* Activar y migrar a ubicaciones, servicios o servidores alternativos.

## Elegir el momento de la reparación

Determine la estrategia de plazos -cuando se llevarán a cabo las acciones de remediación- involucrando al Incident Commander, a los SME y propietarios del sistema, a los SMEs y propietarios de la unidad de negocio, y al equipo ejecutivo.  Cada estrategia es apropiada en diferentes circunstancias:

* Elija la reparación **inmediata** cuando sea más importante detener inmediatamente las actividades del atacante que seguir investigando.  Por ejemplo, una pérdida financiera en curso, o un fracaso de la misión en curso, una pérdida de datos activa, o la prevención de una amenaza significativa inminente.
* Elija una reparación **retrasada** cuando sea importante completar la investigación o no alertar al atacante.  Por ejemplo, el compromiso a largo plazo de un atacante avanzado, el espionaje corporativo o el compromiso a gran escala de un número desconocido de sistemas.
* Elija la remediación **combinada** cuando las circunstancias inmediatas y retardadas se apliquen en el mismo incidente.  Por ejemplo, la segmentación inmediata de un servidor o red sensible para cumplir con los requisitos reglamentarios mientras se investiga un compromiso a largo plazo.

## Ejecutar la remediación

* Evaluar y explicar los riesgos de las acciones de remediación a las partes interesadas.  
* Implementar inmediatamente aquellas acciones de remediación que afecten poco o nada al atacante (a veces llamadas "acciones de postura"). Por ejemplo, muchas de las acciones de [protección](#protección) y [detección](#detección) anteriores son buenas candidatas.
* Programar y asignar acciones de remediación de acuerdo con la estrategia de tiempo.
* Ejecute las acciones de corrección en lotes, como eventos, para lograr la máxima eficacia y el mínimo riesgo.
* Documentar el estado de ejecución y el tiempo en el archivo de incidentes, especialmente para las medidas temporales.

## Iterar la remediación

[Actualizar el plan de remediación](#actualización-del-plan-de-remediación) y repetir hasta el cierre.

# Comunicar

* [Investigar](#investigar), [Remediar](#remediar) y [Comunicar](#comunicar) en paralelo, utilizando equipos separados, si es posible.  Notifique al Incident Commander si hay pasos que el equipo debe considerar

Toda comunicación debe incluir la información más precisa disponible.  Muestre integridad.  No comunicar especulaciones.

## Comunicación Interna

### Notificar y actualizar a las partes interesadas

* Comunicarse con las partes interesadas como parte de las llamadas iniciales y de actualización, así como a través de actualizaciones basadas en eventos en la llamada y el chat.
* Coordinar las actualizaciones independientes (_e._, ejecutivas, legales) según sea necesario, pero con la menor frecuencia posible, para mantener el foco en la investigación y la reparación.
* Concéntrese en la mejor evaluación del vector, el impacto, el resumen y los aspectos más destacados de la línea de tiempo, incluidos los pasos de remediación.  No especule.

### Notificar y actualizar la organización

* **No** notifique o actualice al personal que no responde hasta que el Incident Commander lo autorice, en particular si existe el riesgo de una amenaza interna.
* Coordine las actualizaciones de los equipos o de toda la organización con los ejecutivos y la dirección de la empresa.
* Concéntrese en la mejor evaluación del vector, el impacto, el resumen y los aspectos más destacados de la línea de tiempo, incluidos los pasos de remediación.  No especule.

### Crear Informe de Incidentes

* Tras el cierre del incidente, capture la información en el [archivo del incidente](#crear-archivo-del-incidente) para su distribución utilizando el formato en ir.ciberseguros.es/report/template.  **Si los informes de vector, impacto, resumen, línea de tiempo y actividad están completos, esto puede ser totalmente automatizado.**
* Distribuir el informe de incidentes a lo siguiente: ir.ciberseguros.es/report/recipients.

## Comunicar al exterior

### Notificar a los reguladores

* **No** notifique ni ponga al día al personal que no ha respondido hasta que el Incident Commander lo autorice.
* Notificar a los organismos reguladores (por ejemplo, HIPAA/HITRUST, PCI DSS, SOX) si es necesario y de acuerdo con la política.
* Coordinar los requisitos, el formato y los plazos con el legal@ciberseguros.es.

### Notificar a los clientes

* **No** notifique o actualice al personal que no responde hasta que el Incident Commander lo autorice.
* Coordine las notificaciones a los clientes con marketing@ciberseguros.es.
* Incluya la fecha en el título de cualquier anuncio, para evitar confusiones.
* No utilice tópicos como "nos tomamos la seguridad muy en serio". Céntrese en los hechos.
* Sea honesto, acepte la responsabilidad y presente los hechos, junto con el plan para prevenir incidentes similares en el futuro.
* Sea lo más detallado posible con la línea de tiempo.
* Sea lo más detallado posible en cuanto a la información que se vio comprometida y cómo afecta a los clientes. Si estábamos almacenando algo que no debíamos, sé honesto al respecto. Saldrá a la luz más tarde y será mucho peor.
* No hablemos de las partes externas que podrían haber causado el problema, a menos que ya lo hayan hecho público, en cuyo caso enlazaremos con su información. Comunícate con ellos de forma independiente (ver [Notificar a los proveedores](#notificar-a-los-proveedores-y-socios))
* Publique la comunicación externa lo antes posible. Las malas noticias no mejoran con el tiempo.
* Si es posible, contacte con los equipos de seguridad internos de los clientes antes de notificar al público.

### Notificar a los proveedores y socios

* **No** notifique o actualice al personal que no responde hasta que el Incident Commander lo autorice.
* Si es posible, póngase en contacto con los equipos de seguridad internos de los proveedores y socios antes de notificar al público.
* Céntrese en los aspectos específicos del incidente que afectan o implican al proveedor o socio.
* Coordine los esfuerzos de respuesta y comparta la información si es posible.

### Notificar a las Fuerzas de Seguridad

* **No** notifique o actualice al personal que no responde hasta que el Incident Commander lo autorice.
* Coordinar con bosses@ciberseguros.es y legal@ciberseguros.es antes de interactuar con las fuerzas del orden.
* Póngase en contacto con las fuerzas del orden locales en policia@local_gov.es.
* Póngase en contacto con el FBI en 1-800-CALL-FBI (225-5324), https://www.fbi.gov/contact-us o a través del [Internet Crime Complaint Center (IC3)](https://www.ic3.gov).
* Póngase en contacto con los operadores de los sistemas utilizados en el ataque, sus sistemas también pueden haber sido comprometidos.

### Contactar con el servicio de asistencia de respuesta externa

* Póngase en contacto con [Counteractive Security](https://www.counteractive.net) para que le ayude a evaluar el riesgo, la gestión de incidentes, la respuesta a los mismos y el apoyo posterior al incidente.
* Póngase en contacto con public relations llc, pr.firm.tld para que le ayude con las relaciones públicas y la comunicación externa.
* Póngase en contacto con AAA insurance co., cyber.insurance.tld para obtener ayuda con el seguro cibernético.

### Compartir Inteligencia

* Comparta los IOCs con [Infragard](https://www.infragard.org/) si procede.
* Comparta los IOCs con su [ISAC](https://en.wikipedia.org/wiki/Information_Sharing_and_Analysis_Center) de servicio a través de FS ISAC, https://en.wikipedia.org/wiki/Information_Sharing_and_Analysis_Center, si procede.

# Recuperación

**La recuperación suele estar dirigida por las unidades de negocio y los propietarios de los sistemas.  Tome medidas de recuperación sólo en colaboración con las partes interesadas pertinentes.**

1. Poner en marcha un plan de continuidad de negocio/recuperación de desastres: Por ejemplo, considerar la migración a ubicaciones operativas alternativas, sitios de conmutación por error, sistemas de copia de seguridad.
2. Integrar las acciones de seguridad con los esfuerzos de recuperación de la organización.
# Playbook

Los siguientes playbooks capturan los pasos comunes de [investigación](#investigate), [remediación](#remediate) y [comunicación](#communicate) para determinados tipos de incidentes.

## Playbook: Defensa contra Deepfakes y Desinformación

**Investigar, remediar (contener, erradicar) y comunicar en paralelo.**
Asigne los pasos a individuos o equipos para trabajar simultáneamente, cuando sea posible; este playbook no es puramente secuencial. Utilice su mejor criterio.

### Investigar

1. Identifique la fuente de deepfake o desinformación.
    * Esto incluye determinar la plataforma original de difusión y rastrear el origen utilizando herramientas de análisis de metadatos y de red.
    * Evalúe el alcance de la distribución y las audiencias afectadas.
    * Identifique el contenido específico (videos, audios, imágenes) y documente su existencia.
2. Analice el contenido para confirmar su falsedad.
    * Utilice herramientas tecnológicas especializadas en la detección de deepfakes.
    * Colabore con expertos en análisis de contenido y verificación de hechos.
3. Determine la intención detrás de la desinformación o deepfake.
    * ¿Busca dañar la reputación de una persona o entidad? ¿Influir en la opinión pública? ¿Desestabilizar eventos políticos o sociales?
    * ¿Hay indicios de quién podría estar detrás de su creación y distribución?
4. Evalúe el impacto potencial.
    * ¿Qué daño puede causar este contenido a individuos, empresas o a la sociedad?
    * Considere las repercusiones a corto y largo plazo en la confianza pública y en la integridad de los sistemas informativos.

**Relación de matrices de ataque MITRE ATT&CK**
- **T1583 - Disseminate Misinformation**: Examinar cómo los atacantes pueden haber utilizado plataformas digitales para difundir desinformación o deepfakes, enfocándose en identificar técnicas específicas empleadas para la creación y distribución.
- **T1584 - Compromise Public Figures**: Analizar intentos de comprometer la reputación de figuras públicas mediante el uso de deepfakes, destacando la necesidad de investigar posibles vulnerabilidades en la protección de la identidad digital.
- **T1591 - Manipulate Social Media**: Investigar cómo los atacantes podrían haber manipulado las redes sociales para amplificar la desinformación, incluyendo la creación de cuentas falsas o la explotación de algoritmos para incrementar la visibilidad del contenido falso.

**Relación de matrices de defensa RE&CT**
- **Identify & Detect**: Implementar soluciones tecnológicas avanzadas para identificar y detectar deepfakes y contenido desinformativo, utilizando IA y aprendizaje automático para analizar patrones de comportamiento y características visuales/auditivas.
- **Analyze & Assess**: Realizar un análisis detallado del contenido sospechoso para evaluar su autenticidad, trabajando con expertos en verificación de hechos y utilizando bases de datos de hechos verificados y herramientas de análisis de metadatos.
- **Mitigate & Remediate**: Desarrollar estrategias para mitigar el impacto del contenido falso y remediar los daños causados, incluyendo la colaboración con plataformas de redes sociales y la implementación de campañas de concienciación pública.

### Contención

1. Comunique con las plataformas de distribución para solicitar la eliminación del contenido falso.
    * Proporcione evidencia clara de la falsedad del contenido para facilitar su pronta eliminación.
    * Trabaje con los departamentos legales para entender y aplicar las políticas de derechos de autor y difamación, si es aplicable.
2. Lance una campaña de información correctiva.
    * Diseñe y distribuya contenido que refute claramente la desinformación o el deepfake.
    * Utilice múltiples plataformas y medios para asegurar una amplia difusión de la verdad.
3. Implemente medidas técnicas para prevenir la propagación.
    * Aplique filtros y algoritmos de detección en sus propias plataformas y redes.
    * Colabore con expertos en ciberseguridad para rastrear y bloquear la distribución del contenido falso.

### Recuperación

1. Refuerce la confianza en su marca o entidad.
    * Organice sesiones informativas, talleres y publique contenido educativo sobre cómo identificar deepfakes y desinformación.
    * Muestre transparencia en sus esfuerzos por combatir la falsedad y proteger al público.
2. Analice los protocolos de respuesta y ajuste según sea necesario.
    * ¿Qué lecciones se han aprendido? ¿Qué se podría haber hecho mejor?
    * Actualice los planes de contingencia y formación para el personal basándose en la experiencia.
3. Vigilancia continua y ajuste de estrategias.
    * Mantenga un monitoreo activo de nuevas amenazas y ajuste sus estrategias de defensa y comunicación conforme evolucionen las tácticas de desinformación y deepfake.

### Comunicar

1. Informe a todas las partes interesadas sobre la situación y las medidas tomadas.
    * Incluya empleados, clientes, socios y, si es relevante, al público general.
    * Utilice todos los canales de comunicación disponibles para asegurar que el mensaje correcto alcance a la audiencia adecuada.
2. Colabore con otras organizaciones afectadas.
    * Comparta inteligencia y estrategias de mitigación.
    * Considere formar o unirse a coaliciones contra la desinformación para fortalecer las respuestas colectivas.

### Recursos

1. **Herramientas de detección de deepfakes:**
    * [Truebees](https://truebees.eu/site/): Es una herramienta versátil que ayuda a verificar la autenticidad de imágenes, incluso después de ser editadas o compartidas en redes sociales.
    * [Reality Defender](https://www.realitydefender.com/): Ofrece una plataforma integral para la identificación y bloqueo proactivo de contenido deepfake. Proporciona soluciones de autenticación avanzada, incluyendo huellas de voz y detección de documentos falsificados.
    * [Sentinel](https://thesentinel.ai/): Plataforma de protección basada en IA. Ofrece análisis automatizado de medios digitales para identificar falsificaciones.
2. **Guías de comunicación en crisis:**
    * [Estrategias y plantillas para comunicar efectivamente durante incidentes de desinformación.](https://www.prsa.org/about/crisis-communications-resources)


## Playbook: Fuerza Bruta

### Investigación

Los ataques de fuerza bruta se aprovechan de debilidades en los sistemas de autenticación y gestión de credenciales. Por lo tanto, es esencial llevar a cabo una evaluación exhaustiva de estas vulnerabilidades. Esto implica:

1. **Identificación de Puntos de Vulnerabilidad:** Analizar los sistemas de autenticación, como el acceso a aplicaciones web, servidores FTP, sistemas de correo electrónico, etc., para identificar posibles puntos débiles donde un atacante podría intentar un ataque de fuerza bruta.

2. **Revisión de Configuraciones de Seguridad:** Examinar las configuraciones de seguridad en estos sistemas para determinar si se están implementando correctamente las políticas de contraseñas, bloqueos de cuentas después de múltiples intentos fallidos y otras medidas de seguridad que podrían prevenir los ataques de fuerza bruta.

3. **Análisis de Historiales de Acceso:** Revisar los registros de acceso y los registros de eventos de seguridad para identificar patrones de actividad sospechosa que podrían indicar intentos de fuerza bruta pasados o en curso.

4. **Evaluación de Protecciones Actuales:** Determinar la eficacia de las medidas de protección actuales contra ataques de fuerza bruta, como la implementación de CAPTCHA, la autenticación multifactor (MFA) o la detección de anomalías de comportamiento.

### Preparación

**Configuración de Seguridad**

1. **Firewalls:** Los firewalls son una primera línea de defensa que controla el tráfico de red entrante y saliente, permitiendo o bloqueando ciertos tipos de tráfico según reglas predefinidas. Configurar y mantener correctamente un firewall es fundamental para prevenir que los atacantes accedan a los sistemas internos y realicen ataques de fuerza bruta.

2. **Sistemas de Detección y Prevención de Intrusiones (IDS/IPS):** Estos sistemas monitorean y analizan el tráfico de red en busca de patrones y comportamientos maliciosos que puedan indicar un ataque en curso. Un IDS detecta y alerta sobre posibles intrusiones, mientras que un IPS puede tomar medidas activas para bloquear o mitigar automáticamente las amenazas identificadas.

**Políticas de Seguridad de Contraseñas**

1. Contraseñas Robustas:** Establecer políticas que requieran contraseñas fuertes y seguras, que sean difíciles de adivinar o de descifrar mediante ataques de fuerza bruta. Esto incluye el uso de contraseñas largas, combinaciones de letras mayúsculas y minúsculas, números y caracteres especiales.

2. **Procedimientos de Gestión de Credenciales:** Implementar procedimientos claros y efectivos para la gestión de credenciales, que abarquen la creación, el almacenamiento seguro, la distribución y la rotación regular de contraseñas. Esto garantiza que las credenciales de acceso se mantengan protegidas y se actualicen periódicamente para reducir el riesgo de compromiso.

### Remediación

**Restauración de Credenciales Comprometidas**

Restablecer las credenciales comprometidas es una medida crítica para evitar que los atacantes continúen accediendo de manera no autorizada a los sistemas. Este proceso implica:

1. **Identificación de Credenciales Comprometidas:** Realizar una auditoría de seguridad para determinar qué cuentas han sido comprometidas durante el ataque de fuerza bruta.

2. **Notificación a los Usuarios Afectados:** Informar a los usuarios cuyas credenciales hayan sido comprometidas sobre la situación y la necesidad de cambiar sus contraseñas de inmediato. Esto puede hacerse a través de correos electrónicos, mensajes en el sistema o comunicados en el sitio web de la organización.

3. **Restablecimiento de Contraseñas:** Facilitar a los usuarios afectados el proceso de restablecimiento de contraseñas, proporcionando instrucciones claras y seguras para cambiar sus credenciales. Esto puede incluir la implementación de políticas de restablecimiento de contraseñas temporales y la verificación de la identidad del usuario antes de permitir el cambio de contraseña.

4. **Monitorización Continua:** Establecer un monitoreo continuo de las cuentas comprometidas y las actividades de inicio de sesión para detectar cualquier actividad sospechosa posterior al restablecimiento de las credenciales.

**Parcheo de Vulnerabilidades**

Aplicar parches de seguridad y actualizaciones en los sistemas afectados es esencial para cerrar las brechas de seguridad que permitieron el éxito del ataque de fuerza bruta. Este proceso involucra:

1. **Identificación de Vulnerabilidades Explotadas:** Realizar un análisis detallado de los sistemas comprometidos para identificar las vulnerabilidades específicas que fueron explotadas durante el ataque de fuerza bruta.

2. **Desarrollo y Despliegue de Parches:** Trabajar con los proveedores de software y los equipos de seguridad internos para desarrollar y desplegar parches de seguridad que solucionen las vulnerabilidades identificadas. Es importante priorizar las actualizaciones según la criticidad de las vulnerabilidades y minimizar el tiempo de exposición a posibles ataques.

3. **Pruebas de Parcheo:** Realizar pruebas exhaustivas después de aplicar los parches para garantizar que no introduzcan nuevas vulnerabilidades o causen interrupciones en el funcionamiento normal de los sistemas.

4. **Actualización de Políticas de Seguridad:** Revisar y actualizar las políticas de seguridad de manera proactiva para abordar las lecciones aprendidas del incidente y fortalecer la postura de seguridad general de la organización.

### Contención

**Bloqueo Automático**

La implementación de medidas automáticas para bloquear direcciones IP que realicen intentos de inicio de sesión fallidos repetidos dentro de un corto período de tiempo es esencial para detener rápidamente los ataques de fuerza bruta. Para desarrollar esta medida:

1. **Configuración de Herramientas de Seguridad:** Utilizar herramientas de seguridad, como sistemas de detección y prevención de intrusiones (IDS/IPS), para identificar y bloquear automáticamente las direcciones IP que realicen un número especificado de intentos de inicio de sesión fallidos en un corto período de tiempo.

2. **Ajuste de Parámetros:** Ajustar los parámetros de las herramientas de seguridad para definir el umbral de intentos de inicio de sesión fallidos y el período de tiempo en el cual se activará el bloqueo automático. Es importante equilibrar la sensibilidad para bloquear intentos legítimos de acceso con la necesidad de proteger contra ataques de fuerza bruta.

3. **Notificación de Bloqueo:** Configurar sistemas de alerta para notificar al personal de seguridad sobre los bloqueos automáticos, permitiendo una revisión y análisis adicionales si es necesario.

**Actualización de Reglas de Firewall**

Ajustar las reglas de firewall para bloquear o limitar el tráfico asociado con intentos de fuerza bruta es otra medida efectiva para contener estos ataques. Aquí están los pasos adicionales para implementar esta estrategia:

1. **Identificación de Patrones de Tráfico:** Analizar los registros de tráfico de red para identificar patrones asociados con intentos de fuerza bruta, como múltiples intentos de inicio de sesión en un corto período de tiempo desde una misma dirección IP.

2. **Desarrollo de Reglas Específicas:** Desarrollar reglas específicas en el firewall para bloquear o limitar el tráfico que cumpla con estos patrones identificados. Esto puede incluir el bloqueo de direcciones IP específicas, la limitación de intentos de inicio de sesión por dirección IP y la restricción de acceso a servicios sensibles.

3. **Prueba y Ajuste:** Probar las nuevas reglas de firewall en un entorno controlado para asegurar que no afecten negativamente la operación normal de la red. Realizar ajustes según sea necesario para equilibrar la seguridad con la funcionalidad.

### Comunicación

**Comunicación Interna:**

1. **Equipo de Respuesta a Incidentes (IRT):** Notificar inmediatamente al equipo de respuesta a incidentes de la organización sobre el ataque de fuerza bruta. Esto garantiza que se pongan en marcha los procedimientos de respuesta adecuados y se coordine la acción interna para mitigar el impacto del incidente.

2. **Personal Relevante:** Informar a los departamentos y equipos relevantes dentro de la organización, como TI, seguridad de la información y recursos humanos, sobre el incidente. Proporcionarles información detallada sobre el alcance del ataque, los sistemas afectados y las acciones que se están tomando para abordar la situación.

3. **Dirección Ejecutiva:** Si es necesario, comunicar a la alta dirección sobre el incidente de fuerza bruta y su posible impacto en las operaciones comerciales. Esto asegura una comprensión completa de la gravedad del incidente y el apoyo necesario para tomar decisiones críticas.

**Comunicación Externa:**

1. **Usuarios y Clientes Afectados:** Notificar a los usuarios y clientes afectados por el incidente de fuerza bruta sobre cualquier compromiso de sus credenciales y proporcionar orientación sobre las medidas que deben tomar, como cambiar sus contraseñas o habilitar la autenticación de dos factores.

2. **Autoridades Regulatorias y Socios Externos:** En casos en los que la ley lo requiera o cuando exista una relación contractual, informar a las autoridades regulatorias pertinentes y a los socios externos sobre el incidente de fuerza bruta y las medidas tomadas para abordarlo.

3. **Comunicados de Prensa y Comunicación Pública:** Preparar y emitir comunicados de prensa y otras formas de comunicación pública para informar al público en general sobre el incidente de fuerza bruta, las medidas de precaución recomendadas y el compromiso continuo de la organización con la seguridad de los datos y la privacidad de los usuarios.

### Recuperación

**Procedimientos de Restauración**

Después de un ataque de fuerza bruta, es esencial llevar a cabo procedimientos de restauración para devolver los sistemas afectados a un estado seguro y funcional. Estos procedimientos generalmente incluyen:

1. **Priorización de Servicios Críticos:** Identificar y priorizar los servicios y sistemas afectados en función de su importancia para las operaciones comerciales. Esto garantiza que los recursos se asignen de manera óptima durante la recuperación.

2. **Restablecimiento de Contraseñas y Credenciales:** Cambiar y restablecer las contraseñas comprometidas o sospechosas para evitar futuros accesos no autorizados.

3. **Revisión de Sistemas Comprometidos:** Realizar una revisión exhaustiva de los sistemas comprometidos para identificar cualquier daño o modificaciones no autorizadas. Esto puede implicar la restauración de archivos desde copias de seguridad limpias o la eliminación de malware y backdoors.

4. **Reconstrucción de la Confianza del Usuario:** Comunicar de manera proactiva con los usuarios afectados sobre las medidas tomadas para mitigar el incidente y restaurar la confianza en los servicios y sistemas afectados.

**Evaluación Post-Incidente**

Una vez que se ha restablecido la funcionalidad operativa y se han implementado medidas correctivas, es fundamental llevar a cabo una evaluación exhaustiva del incidente para aprender de la experiencia y mejorar la resiliencia de la organización ante futuros ataques. Esto implica:

1. **Análisis de Respuesta al Incidente:** Revisar el desempeño de la respuesta al incidente, incluyendo la efectividad de los procedimientos de detección, contención y recuperación. Identificar áreas de mejora y puntos fuertes en la respuesta.

2. **Reforzamiento de Controles de Seguridad:** Basándose en los hallazgos de la evaluación post-incidente, fortalecer los controles de seguridad y las defensas para mitigar futuros ataques de fuerza bruta y otras amenazas cibernéticas.

3. **Identificación de Controles Fallidos:** Determinar si algún control de seguridad ha fallado durante el ataque y tomar medidas correctivas para abordar las debilidades identificadas. Esto puede implicar la implementación de nuevas tecnologías de seguridad o la mejora de los procesos y procedimientos existentes.

4. **Documentación de Lecciones Aprendidas:** Documentar todas las lecciones aprendidas durante el incidente, incluyendo acciones exitosas y áreas de mejora. Estas lecciones pueden informar futuras estrategias de seguridad y mejorar la preparación y respuesta ante incidentes.

### Recursos y Referencias

**Guías de Seguridad:**

1. **Documentación Interna:** Proporcionar manuales y documentos de políticas de seguridad interna que detallen las mejores prácticas para la gestión de contraseñas, la configuración de firewalls y otras medidas de seguridad relevantes.

2. **Directrices Externas:** Referenciar guías de seguridad reconocidas, como las proporcionadas por organizaciones de estándares de seguridad como el NIST (Instituto Nacional de Estándares y Tecnología) o el OWASP (Proyecto Abierto de Seguridad de Aplicaciones Web), que ofrecen recomendaciones detalladas para la protección contra ataques de fuerza bruta.

**Informes de Incidentes:**

1. **Análisis de Incidentes Anteriores:** Compartir informes de incidentes de fuerza bruta previos dentro de la organización o de la industria para destacar los métodos utilizados por los atacantes, las debilidades explotadas y las lecciones aprendidas.

2. **Informes de Agencias de Seguridad:** Consultar informes y análisis de agencias de seguridad gubernamentales y organizaciones de ciberseguridad reconocidas que proporcionen información sobre las últimas tendencias y tácticas utilizadas en ataques de fuerza bruta.

**Herramientas de Mitigación:**

1. **Software de Detección y Prevención:** Recomendar herramientas de detección y prevención de intrusos (IDS/IPS) y sistemas de gestión de eventos e información de seguridad (SIEM) que puedan ayudar a identificar y mitigar los ataques de fuerza bruta en tiempo real.

2. **Herramientas de Autenticación Reforzada:** Explorar soluciones de autenticación multifactor (MFA) y autenticación de dos factores (2FA) que añadan capas adicionales de seguridad a los sistemas y reduzcan la efectividad de los ataques de fuerza bruta al requerir más que solo una contraseña para el acceso.

### Relacion con matriz de ataque y respuesta
**Técnica de Ataque: Credential Access > Brute Force (T1110)**
Esta técnica se enfoca en los métodos que los atacantes pueden utilizar para obtener acceso a las credenciales a través de intentos repetidos de adivinación o fuerza bruta. Incluye sub-técnicas como:
1. T1110.001: Password Guessing
2. T1110.002: Password Cracking
3. T1110.003: Password Spraying
4. T1110.004: Credential Stuffing

**Mitigación:**
1. M1032: Multi-factor Authentication (para dificultar el éxito de un ataque de fuerza bruta al requerir más de una forma de verificación).
2. M1017: User Training (entrenar a los usuarios para que creen contraseñas fuertes y entiendan los riesgos de seguridad relacionados con los ataques de fuerza bruta).
3. M1037: User Account Management (incluye la implementación de políticas de contraseñas fuertes, bloqueo de cuentas después de intentos fallidos, etc.).
4. M1052: Expiration (establecer un límite de tiempo para cuánto tiempo una sesión de usuario puede estar activa).
   
Además, para la fase de detección y respuesta, el marco MITRE ATT&CK también sugiere diversas técnicas de detección y procedimientos para identificar y mitigar ataques de fuerza bruta, como el monitoreo de intentos de inicio de sesión fallidos y la implementación de alertas para actividades sospechosas.





## Playbook: Inyección de Código

### Investigación

La inyección de código es una vulnerabilidad común en aplicaciones web que permite a un atacante ejecutar código arbitrario en un sistema. Es crucial comprender los diferentes tipos de inyección de código, como SQL injection y Cross-Site Scripting (XSS), y cómo se pueden explotar para comprometer la seguridad de una aplicación.

### Identificación

- **SQL Injection (Inyección SQL):** Se aprovecha de las vulnerabilidades en la entrada de datos de una aplicación para insertar instrucciones SQL maliciosas en las consultas a la base de datos, lo que permite al atacante manipular o extraer información de la base de datos.

- **Cross-Site Scripting (XSS):** Permite a un atacante inyectar scripts maliciosos en páginas web vistas por otros usuarios, lo que puede conducir a la ejecución de código no autorizado en el navegador de la víctima y al robo de cookies de sesión, entre otros ataques.

- **Command Injection (Inyección de Comandos):** Se aprovecha de entradas no validadas en aplicaciones que ejecutan comandos del sistema operativo para insertar comandos maliciosos, lo que puede permitir al atacante ejecutar comandos arbitrarios en el servidor.

- **LDAP Injection:** Similar a SQL Injection, pero se dirige a aplicaciones que interactúan con servidores LDAP (Protocolo Ligero de Acceso a Directorios), permitiendo al atacante manipular las consultas LDAP para obtener información no autorizada o realizar operaciones no deseadas.

- **XPath Injection:** Ataca aplicaciones que utilizan XPath (XML Path Language) para buscar y filtrar datos en documentos XML, permitiendo al atacante manipular las consultas XPath para obtener información no autorizada o alterar el comportamiento de la aplicación.

- **HTML Injection:** Similar a XSS, pero se centra en la inserción de código HTML malicioso en páginas web para alterar su contenido o ejecutar acciones no autorizadas en el navegador de la víctima.

- **CSS Injection:** Inyecta código malicioso en hojas de estilo en cascada (CSS) para alterar la apariencia o el comportamiento de una página web, a menudo utilizado en combinación con otras formas de ataques, como XSS.

### Explotación

#### Ejemplos

- **SQL Injection**:
  - Ejemplo 1: Intenta inyectar `' OR 1=1 --` en un campo de búsqueda para bypassar la autenticación.
  - Ejemplo 2: Introduce `'; DROP TABLE users; --` en un campo de entrada para eliminar una tabla de la base de datos.

- **Cross-Site Scripting (XSS)**:
  - Ejemplo 1: Inserta `<script>alert('XSS');</script>` en un campo de comentario para ejecutar un script en el navegador de los usuarios.
  - Ejemplo 2: Inyecta `<img src="javascript:alert('XSS')">` en un campo de entrada para mostrar una alerta en la página.

### Verificación

- Realice pruebas de penetración utilizando herramientas automatizadas como SQLMap para detectar vulnerabilidades de inyección de SQL.
- Utilice herramientas como Burp Suite para interceptar y modificar solicitudes HTTP y verificar si los campos de entrada son vulnerables a XSS.

### Comunicación

- Notifique al equipo de desarrollo sobre las vulnerabilidades encontradas y proporcione ejemplos claros de cómo se pueden explotar.
- Documente detalladamente las vulnerabilidades descubiertas y los pasos necesarios para reproducirlas.

### Mitre Ataque y Defensa

#### Matriz de Tácticas y Técnicas de Mitre

- **Táctica: Explotación**
  - Técnica: Inyección de SQL (T1210)
    - Descripción: Los atacantes pueden utilizar técnicas de inyección de SQL para manipular consultas SQL de forma maliciosa e interactuar con la base de datos subyacente.
    - Defensa: Implementar medidas de mitigación como la validación de entrada de usuario y el uso de consultas parametrizadas para prevenir la inyección de SQL.

- **Táctica: Explotación**
  - Técnica: Inyección de Código Remoto (T1059)
    - Descripción: Los atacantes pueden inyectar código remoto en aplicaciones web para ejecutar comandos arbitrarios en el servidor.
    - Defensa: Implementar medidas de seguridad como la codificación y escape adecuados de datos para prevenir la ejecución de código remoto no autorizado.

#### Incorporación de Mitre al Playbook

- **Detección de Técnicas de Mitre:**
  - Descripción: Integrar la detección de técnicas de Mitre relacionadas con la inyección de código en las herramientas de seguridad de la aplicación para identificar posibles ataques.
  - Acción: Configurar reglas de detección y alertas para detectar actividades maliciosas que coincidan con las tácticas y técnicas de Mitre.
  - Responsable: Equipo de Seguridad de la Información, Equipo de Desarrollo de Aplicaciones.

- **Respuesta a Técnicas de Mitre:**
  - Descripción: Desarrollar procedimientos de respuesta específicos para abordar las técnicas de Mitre utilizadas por los atacantes en inyecciones de código.
  - Acción: Definir pasos claros y acciones a tomar para mitigar las amenazas identificadas basadas en las tácticas y técnicas de Mitre.
  - Responsable: Equipo de Desarrollo de Aplicaciones, Equipo de Respuesta a Incidentes (ERI).

### Mitigación

- Implemente medidas de mitigación como la validación estricta de entrada de usuario y el uso de consultas parametrizadas para prevenir la inyección de SQL.
- Codifique y escape correctamente los datos antes de mostrarlos en la salida de la aplicación para prevenir ataques XSS.

### Remediación

- Realice auditorías de seguridad regulares en el código para identificar y corregir vulnerabilidades de inyección de código.
- Proporcione capacitación y orientación al equipo de desarrollo sobre las mejores prácticas de seguridad en el desarrollo de aplicaciones web.
- Aplique parches de seguridad y actualizaciones para mitigar nuevas vulnerabilidades y mantener la aplicación protegida.

### Recuperación
#### Respuesta Inmediata

- **Aislamiento del Sistema Afectado**: Separe el sistema afectado de la red para prevenir la propagación del ataque y evitar daños adicionales.
    
- **Desactivación de Funcionalidades Vulnerables**: Desactive temporalmente cualquier funcionalidad o servicio que haya sido comprometido para evitar una mayor explotación.
    

#### Investigación y Análisis

- **Análisis Forense**: Realice un análisis forense exhaustivo del sistema comprometido para identificar el alcance total del ataque, cómo ocurrió y qué datos se vieron comprometidos.
    
- **Recolección de Evidencia**: Recopile evidencia relevante, como registros de auditoría, archivos de registro y copias de seguridad, para apoyar la investigación y el análisis forense.
    

#### Restauración y Recuperación

- **Restauración desde Copias de Seguridad**: Restaure el sistema afectado desde una copia de seguridad limpia y verificada para garantizar que no queden artefactos maliciosos.
    
- **Parcheo y Actualización**: Aplique parches de seguridad y actualizaciones en el sistema restaurado para cerrar las vulnerabilidades explotadas y prevenir futuros ataques similares.## Playbook: Defensa contra Cryptojacking

**Investigar, remediar (contener, erradicar) y comunicar en paralelo.**
Asigne los pasos a individuos o equipos para trabajar simultáneamente, cuando sea posible; este playbook no es puramente secuencial. Utilice su mejor juicio.

### Investigar

1. **Identifique la incidencia de cryptojacking.**
    * Determine los sistemas afectados y el tipo de malware de cryptojacking utilizado.
    * Use herramientas de análisis de red y seguridad para detectar la presencia de actividad de minería no autorizada.
    * ¿Cómo se detectó la actividad de cryptojacking?**

2. **Evalúe el alcance del compromiso.**
    * Determine la duración de la actividad de cryptojacking y estime el impacto en los recursos del sistema.
    * Identifique cualquier otra amenaza o malware introducido en la red como parte del ataque.
    * ¿Cuál es el impacto del cryptojacking en el rendimiento y la seguridad de nuestros sistemas?

3. **Recopile evidencia.**
    * Documente detalladamente los indicadores de compromiso (IoCs) y cualquier otra evidencia relevante.
    * Asegúrese de seguir las prácticas recomendadas de cadena de custodia para posibles investigaciones legales futuras.

**Relación de matrices de ataque MITRE ATT&CK**
- **T1496 - Resource Hijacking**: Identificar métodos utilizados por los atacantes para comprometer recursos de sistemas con el objetivo de minar criptomonedas de manera no autorizada, destacando la necesidad de detectar y mitigar estas actividades.
- **T1082 - System Information Discovery**: Examinar cómo los atacantes pueden haber recopilado información sobre los sistemas para identificar objetivos vulnerables y maximizar la eficiencia del cryptojacking.
- **T1562 - Impair Defenses**: Investigar las técnicas empleadas para desactivar o evadir soluciones de seguridad, lo que permite la persistencia del cryptojacking en los sistemas comprometidos.

**Relación de matrices de defensa RE&CT**
- **Detect & Analyze**: Implementar herramientas y procesos para detectar actividad sospechosa relacionada con el cryptojacking, incluyendo el monitoreo de uso anormal de recursos y tráfico de red inusual.
- **Contain & Eradicate**: Desarrollar estrategias para contener la infección y erradicar el malware de los sistemas afectados, asegurando la eliminación completa para prevenir la recurrencia.
- **Recover & Harden**: Restaurar los sistemas afectados a su estado operativo normal mientras se refuerzan las defensas para proteger contra futuros ataques de cryptojacking.


### Contención

1. **Aísle los sistemas afectados.**
    * Desconecte los sistemas comprometidos de la red para evitar la propagación del malware y la extracción adicional de recursos.
    * Aplique reglas de firewall o segmentación de red para limitar el acceso al tráfico de minería de criptomonedas.

2. **Elimine el malware de cryptojacking.**
    * Utilice herramientas de seguridad de confianza para eliminar el malware de los sistemas afectados.
    * Considere reinstalar sistemas operativos y aplicaciones en dispositivos severamente comprometidos.

### Recuperación

1. **Restaure los sistemas a su estado operativo normal.**
    * Asegúrese de que todos los rastros del malware hayan sido eliminados antes de reconectar los sistemas a la red.
    * Monitoree los sistemas restaurados para detectar signos de actividad sospechosa.

2. **Fortalezca las defensas de seguridad.**
    * Actualice el software y los sistemas operativos con los últimos parches de seguridad.
    * Refuerce las políticas de seguridad, incluyendo el uso de contraseñas fuertes y la autenticación de dos factores.

### Comunicar

1. **Informe a las partes interesadas.**
    * Comunique a la gerencia, al equipo de TI y a los usuarios afectados sobre el incidente y las medidas tomadas para resolverlo.
    * Proporcione recomendaciones para evitar incidentes futuros de cryptojacking.

2. **Colabore con otras organizaciones afectadas.**
    * Comparta información sobre el ataque y las medidas de mitigación con otras entidades afectadas para ayudar a prevenir la propagación del cryptojacking.

### Recursos

1. **Herramientas de detección y eliminación de malware:**
    * [Malwarebytes](https://www.malwarebytes.com/): Ofrece protección en tiempo real contra una amplia gama de amenazas, incluyendo el cryptojacking.
    * [Sophos Intercept X](https://www.sophos.com/en-us/products/intercept-x.aspx): Proporciona una solución de seguridad avanzada con capacidades de detección y respuesta ante incidentes de cryptojacking.

2. **Guías de mejores prácticas de seguridad:**
    * [Consejos de seguridad para prevenir el cryptojacking](https://www.cisecurity.org/): El Centro de Seguridad de Internet ofrece recomendaciones para proteger los sistemas contra el cryptojacking y otras amenazas cibernéticas.
﻿## Playbook: DDOS

### Introducción

1. **Objetivo**: Este playbook está diseñado para orientar a los equipos en la identificación rápida y la respuesta efectiva ante ataques DDoS, asegurando que las operaciones críticas continúen con el mínimo impacto posible.

2. **Alcance**: Cubre ataques DDoS de varios tipos, como volumétricos, de protocolo y a la capa de aplicación, proporcionando estrategias específicas para contrarrestar cada uno.

3. **Audiencia**: Dirigido al equipo de seguridad cibernética y operaciones de red, este documento sirve como una guía práctica para preparar y proteger la infraestructura tecnológica de la organización frente a ataques DDoS.

### Comprensión de los ataques DDoS

**Definición y Tipos**: Un ataque de denegación de servicio distribuido (DDoS) es un intento malicioso de interrumpir el tráfico normal de un servidor, servicio o red específicos inundándolos con un flujo abrumador de tráfico de internet. Los ataques DDoS se clasifican en tres categorías principales:

1. **Ataques Volumétricos**: Estos son los más comunes y su objetivo es saturar el ancho de banda de la víctima con grandes volúmenes de tráfico. Ejemplos incluyen inundaciones ICMP (Ping flood) y inundaciones UDP.

2. **Ataques de Protocolo:** Apuntan a explotar vulnerabilidades en los protocolos de la capa de red y transporte para consumir recursos de los servidores o equipos de infraestructura (como balanceadores de carga). Ejemplos son SYN floods y ataques de reflexión basados en NTP.

3. **Ataques a la Capa de Aplicación:** Se dirigen específicamente a aplicaciones web, intentando agotar los recursos del servidor ejecutando solicitudes legítimas pero excesivas. Los ataques HTTP flood son un ejemplo típico.

**Motivaciones del Atacante**: Los motivos detrás de los ataques DDoS varían desde el vandalismo y la protesta política (hacktivismo) hasta la extorsión y la competencia desleal. Algunos atacantes buscan interrumpir los servicios por razones ideológicas o como una demostración de poder, mientras que otros pueden emplear ataques DDoS para desviar la atención de las fuerzas de seguridad durante un robo de datos.

**Indicadores de Compromiso (IoCs)**: Los indicadores de compromiso son señales que pueden sugerir que una red o sistema está bajo ataque DDoS. Incluyen: aumento anormal del tráfico, realentización del servicio o inaccesibilidad, aumento en solicitudes fallidas y alertas de seguridad inusuales.

### Preparación

**Evaluación de Riesgo**

1. **Identificación de Activos Críticos:** Comenzar con un inventario de los activos digitales, identificando aquellos que son críticos para las operaciones del negocio. Esto incluye servidores web, DNS, sistemas de correo electrónico, y cualquier otro servicio que, si se ve comprometido, podría impactar significativamente en las operaciones del negocio.

2. **Análisis de Vulnerabilidades:** Realizar pruebas de penetración y evaluaciones de vulnerabilidad para identificar posibles debilidades en la infraestructura que podrían ser explotadas en un ataque DDoS. Esto puede incluir configuraciones de red inadecuadas, sistemas sin parchear, o falta de capacidad de red.

3. **Evaluación de Impacto:** Determinar el impacto potencial de un ataque DDoS en los activos críticos identificados. Considerar factores como la pérdida de ingresos, daño a la reputación, y otros impactos operativos o financieros.

4. **Determinación de Riesgo:** Combinar la información sobre vulnerabilidades y el impacto potencial para clasificar los riesgos asociados a cada activo crítico. Esto ayudará a priorizar las acciones de mitigación y preparación.

**Infraestructura de Resiliencia**

1. **Diseño de Red:** Implementar una arquitectura de red diseñada para soportar ataques DDoS, lo que puede incluir redundancia de ruta, balanceo de carga, y la segregación de la red para aislar los sistemas críticos de otros menos críticos.

2. **Capacidad de Red Sobredimensionada:** Asegurar que la infraestructura tenga capacidad adicional para manejar picos inesperados de tráfico. Esto puede requerir la expansión de la banda ancha disponible o la configuración de límites de tasa de tráfico dinámico.

3. **Defensas en Capas:** Implementar múltiples capas de seguridad, incluyendo firewalls de aplicación web (WAF), sistemas de prevención de intrusiones (IPS), y soluciones específicas de mitigación de DDoS para filtrar el tráfico malicioso antes de que pueda impactar en los servicios críticos.

### Detección y Análisis

**Monitoreo y Alertas**

1. **Implementación de Herramientas de Monitoreo:** Utilizar herramientas avanzadas de monitoreo de tráfico en tiempo real capaces de diferenciar entre picos de tráfico legítimos y actividades sospechosas que podrían indicar un ataque DDoS. Estas herramientas deben estar configuradas para monitorizar tanto el volumen de tráfico como los patrones de acceso.

2. **Establecimiento de Umbrales de Alerta:** Definir umbrales específicos para el tráfico, basados en el comportamiento normal de la red, que, una vez superados, generen alertas automáticas. Estos umbrales deben ser dinámicos y ajustarse según las tendencias de tráfico históricas y eventos conocidos que puedan causar picos legítimos de tráfico.

3. **Integración de Sistemas de Alerta:** Las alertas generadas por las herramientas de monitoreo deben integrarse con los sistemas de gestión de incidentes de la organización para asegurar una respuesta rápida. Esto puede incluir notificaciones a través de correo electrónico, SMS, o sistemas de tickets.

**Análisis del Ataque**

1. **Identificación del Tipo de Ataque:** Una vez detectado un aumento sospechoso en el tráfico, es crucial identificar el tipo de ataque DDoS. Esto puede incluir ataques volumétricos, de agotamiento de estado (por ejemplo, SYN flood), o ataques a la capa de aplicación (por ejemplo, HTTP flood).

2. **Evaluación del Tamaño y Vector del Ataque:** Determinar la magnitud del ataque y los vectores utilizados es esencial para seleccionar la estrategia de mitigación más efectiva. Esto implica analizar el volumen de tráfico, los tipos de paquetes involucrados, y las direcciones IP de origen.

3. **Uso de Análisis Forense:** Implementar técnicas de análisis forense para examinar los patrones de tráfico detalladamente. Esto puede ayudar a identificar las características específicas del ataque, como la geografía de los atacantes, los dispositivos utilizados, y la posible motivación detrás del ataque.

4. **Documentación y Comunicación:** Registrar todos los detalles del ataque, incluyendo cómo fue detectado, sus características, y cualquier medida tomada en respuesta inicial. Esta documentación es vital para la comunicación interna y externa, así como para la revisión post-incidente.

### Contención

**Estrategias de Mitigación**

1. **Filtrado de Tráfico:** Implementar filtros para bloquear tráfico malicioso basado en patrones conocidos asociados con ataques DDoS. Esto puede incluir direcciones IP sospechosas, patrones de paquetes inusuales, o firmas de ataque específicas. Los sistemas de prevención de intrusiones (IPS) y los firewalls de aplicación web (WAF) pueden configurarse para realizar esta tarea automáticamente.

2. **Rate Limiting:** Establecer límites en la cantidad de solicitudes que un usuario puede hacer en un período de tiempo específico ayuda a prevenir el agotamiento de recursos causado por ataques a la capa de aplicación. Esta técnica es particularmente efectiva contra ataques de inundación HTTP.

3. **Redistribución del Tráfico:** Utilizar técnicas de balanceo de carga y enrutamiento de tráfico para redistribuir las cargas de trabajo de manera más uniforme a través de múltiples servidores o centros de datos. Esto puede ayudar a absorber y dispersar el impacto del tráfico malicioso, manteniendo los servicios críticos en funcionamiento.

**Implementación de Controles**

1. **Defensas Pre-configuradas:** Tener defensas listas para ser activadas en el momento en que se detecta un ataque es crucial para una respuesta rápida. Esto incluye listas de bloqueo o permitido preestablecidas, reglas de filtrado, y configuraciones de rate limiting que pueden ajustarse según la naturaleza del ataque.

2. **Coordinación con Terceros:** En el caso de ataques de gran escala que sobrepasan la capacidad de la infraestructura local, es vital coordinar con proveedores de servicios de Internet (ISP) y servicios especializados de mitigación de DDoS. Estos proveedores pueden ofrecer soluciones como la limpieza de tráfico, que redirige el tráfico a través de centros de limpieza para filtrar el tráfico malicioso antes de que alcance la infraestructura de la organización.

3. **Uso de Servicios en la Nube:** La infraestructura en la nube puede ofrecer flexibilidad y recursos adicionales durante un ataque DDoS. Algunos proveedores de servicios en la nube ofrecen servicios de mitigación de DDoS integrados que pueden escalar automáticamente para absorber volúmenes de tráfico elevados.

4. **Pruebas y Actualizaciones Regulares:** Es fundamental probar regularmente las estrategias de mitigación y los controles implementados para asegurar su efectividad contra nuevos y emergentes vectores de ataque. Las pruebas pueden incluir simulacros de ataque y revisiones de configuración.

### Comunicación

**Protocolos de Comunicación**

1. **Definición de Portavoces:** Especificar quién está autorizado para hablar en nombre de la organización sobre el incidente.

2. **Canales de Comunicación:** Identificar los canales internos y externos para la difusión de información, como correos electrónicos internos y comunicados de prensa.

3. **Frecuencia de Actualizaciones:** Establecer un cronograma para las comunicaciones regulares, adaptándose según evolucione el incidente.

**Información Clave a Comunicar**

**Estado Actual del Ataque:** Breve descripción de la situación, incluyendo el inicio del ataque y su estado actual (activo, contenido, mitigado).

**Impacto:** Resumen del efecto del ataque en los servicios y operaciones, detallando cuáles están afectados y cómo.

**Acciones en Curso:** Descripción general de las medidas tomadas para responder al ataque, como la activación de defensas y la colaboración con especialistas en mitigación de DDoS

**Orientación para Afectados:** Consejos prácticos o recomendaciones para los usuarios o empleados impactados por el ataque.

**Compromiso con la Transparencia:** Afirmación del compromiso de la organización con mantener informadas a todas las partes interesadas.

### Remediación

1. **Acciones Correctivas**

2. **Identificación de Vulnerabilidades:** Analizar el ataque para identificar cómo los atacantes pudieron generar un impacto significativo. Esto puede incluir la explotación de configuraciones de red deficientes, fallos de seguridad específicos, o la falta de capacidad adecuada para manejar picos de tráfico.

3. **Aplicación de Parches y Actualizaciones:** Asegurar que todos los sistemas operativos, aplicaciones y dispositivos de red estén actualizados con los últimos parches de seguridad para cerrar las vulnerabilidades explotadas por los atacantes.

4. **Reconfiguración de Sistemas:** Modificar configuraciones de red y seguridad para cerrar las brechas que permitieron el ataque. Esto puede incluir el fortalecimiento de las políticas de firewall, la implementación de reglas de filtrado más estrictas y la mejora de las prácticas de autenticación.

5. **Pruebas de Penetración:** Realizar pruebas de penetración después de aplicar los cambios para validar la efectividad de las acciones correctivas. Las pruebas deben ser realizadas por expertos en seguridad o firmas externas para asegurar una evaluación imparcial.

**Fortalecimiento de la Seguridad**

1. **Evaluación de Herramientas y Procesos:** Revisar y evaluar las herramientas y procesos de seguridad existentes para identificar áreas de mejora. Esto puede incluir la adopción de tecnologías avanzadas de detección y mitigación de DDoS, la mejora de los sistemas de monitoreo y alerta, y la actualización de los protocolos de respuesta a incidentes.

2. **Capacitación y Concientización:** Reforzar la capacitación de los equipos de seguridad y TI, así como aumentar la concientización sobre seguridad en toda la organización. La educación continua sobre las últimas tácticas y herramientas de ataque DDoS puede ayudar a prevenir futuros incidentes.

3. **Desarrollo de Planes de Respuesta Mejorados:** Actualizar los planes de respuesta a incidentes basados en las lecciones aprendidas del ataque reciente. Esto debe incluir una revisión de los protocolos de comunicación, los procedimientos de escalado y la integración de nuevas estrategias de mitigación.

4. **Implementación de Redundancia y Resiliencia:** Aumentar la redundancia y resiliencia de la infraestructura crítica de TI para asegurar que la organización pueda mantener operaciones esenciales durante un ataque. Esto puede incluir soluciones como la distribución geográfica de los recursos, la implementación de sistemas de failover automáticos y el aumento de la capacidad de ancho de banda.

5. **Colaboración con Socios Externos:** Establecer o fortalecer las relaciones con socios externos, incluidos los proveedores de servicios de Internet, proveedores de servicios de mitigación de DDoS y otras organizaciones relevantes para una respuesta coordinada a futuros ataques.

### Recuperación

**Procedimientos de Recuperación**

1. **Restablecimiento de Servicios:** Se debe implementar un plan de acción detallado para restaurar los servicios afectados a su estado normal de funcionamiento. Esto puede incluir acciones como la reinstalación de sistemas, la restauración de copias de seguridad, y la implementación de medidas adicionales de seguridad para prevenir futuros ataques.

2. **Priorización de Servicios Críticos:** Durante la recuperación, es importante priorizar la restauración de servicios críticos para minimizar el impacto en las operaciones comerciales. Esto implica identificar qué servicios son más esenciales y asegurarse de que sean los primeros en ser restablecidos.

3. **Garantía de Seguridad:** Es fundamental restablecer los servicios de manera segura, asegurándose de que no haya puertas traseras o vulnerabilidades que puedan ser explotadas nuevamente por los atacantes. Se deben implementar medidas adicionales de seguridad, como parches de software y actualizaciones de seguridad, para fortalecer la postura de seguridad de la organización.

**Evaluación Post-Incidente**

1. **Análisis del Desempeño:** Se debe llevar a cabo una revisión exhaustiva del manejo del incidente, evaluando la eficacia de las acciones tomadas durante el ataque. Esto incluye revisar los procedimientos de respuesta, identificar áreas de mejora y reconocer lo que se hizo bien.

2. **Identificación de Deficiencias:** Durante la evaluación post-incidente, es importante identificar cualquier deficiencia en los controles y procesos de seguridad que hayan permitido el ataque o dificultado su respuesta. Esto puede incluir debilidades en la detección de amenazas, falta de capacidad de respuesta adecuada, o fallas en la coordinación entre equipos.

3. **Documentación de Lecciones Aprendidas:** Se deben documentar todas las lecciones aprendidas durante el incidente, incluyendo los aspectos positivos y las áreas de mejora. Esto proporciona una base sólida para futuras acciones correctivas y ayuda a fortalecer la postura de seguridad de la organización.

4. **Implementación de Mejoras:** Basándose en los hallazgos de la evaluación post-incidente, se deben implementar medidas correctivas y mejoras en los controles y procesos de seguridad. Esto puede incluir la revisión de políticas y procedimientos, la actualización de herramientas de seguridad, y la capacitación del personal.

**Relacion con matriz de ataque y respuesta**
1.	**Matriz de Ataque MITRE ATT&CK - Técnica de Impacto (Denegación de Servicio - T1499):** Esta técnica dentro de la matriz de ataque MITRE ATT&CK se enfoca en los ataques de denegación de servicio que pueden formar parte de un ataque DDoS. Proporciona una estructura para comprender cómo los atacantes pueden llevar a cabo estos ataques y qué técnicas específicas pueden emplear para interrumpir los servicios objetivo.
2.	**Matriz de Respuesta RE&CT - Infraestructura de Resiliencia (T1036):** Esta técnica dentro de la matriz de respuesta RE&CT se centra en la preparación y protección de la infraestructura tecnológica de una organización frente a ataques DDoS. Establece cómo una organización puede desarrollar una infraestructura robusta y resiliente que pueda resistir y recuperarse de tales ataques, asegurando la continuidad de las operaciones críticas.





## Playbook: Alteración de sitios web (Website Defacement)

**Investigar, remediar (contener, erradicar) y comunicar en paralelo!**
Asigne los pasos a individuos o equipos para que trabajen simultáneamente, cuando sea posible; este playbook no es puramente secuencial. Utilice su mejor criterio.

### Investigar

1. Desconecte inmediatamente el servidor desconfigurado para investigarlo.
    * Esto es especialmente importante si la desfiguración es insultante o provocadora de algún modo. Elimine esto de la vista del público tan pronto como sea posible para evitar daños, así como para mitigar el impacto del negocio.
    * El mensaje de desfiguración también puede contener información falsa que podría confundir a los usuarios o ponerlos en peligro.
    * Desconectar el servidor permitirá una investigación más profunda de la desfiguración. Esto puede ser necesario, ya que el ciberdelincuente puede haberse adentrado en la organización accediendo a servidores de aplicaciones, bases de datos, etc.
2. Determine el origen de la vulnerabilidad del sistema que ha utilizado el atacante. Los exploits más comunes son:
    * Ataques de inyección SQL
        * Este tipo de ataque se produce cuando un atacante interfiere en las consultas de una aplicación a la base de datos. Por lo tanto, esto puede conducir a un acceso no autorizado a datos privados o sensibles. Lea más sobre los ataques de inyección SQL [aquí](https://www.acunetix.com/websitesecurity/sql-injection/)
    * Ataques de inclusión remota de archivos (RFI)
        * Este tipo de ataque explota la función de referencia de una aplicación para cargar malware desde una URL remota. Más información sobre los ataques RFI [aquí](https://www.acunetix.com/blog/articles/remote-file-inclusion-rfi/)
    * webshells
        * Más información sobre web shells y defacement de sitios web [aquí](https://www.wordfence.com/blog/2017/06/wso-shell/)
    * mal diseño de aplicaciones web
        * hacks de javascript
        * hacks de PHP/ASP
        * Aquí hay más sobre [hacking con javascript](https://itnext.io/how-companies-are-hacked-via-malicious-javascript-code-12aa82560bdc)
    * otros métodos de detección incluyen: 
        * Comprobar los registros del servidor
            * buscar en el registro de acceso y en el registro de errores de la página web cualquier actividad sospechosa o desconocida
            * por supuesto, también es una buena idea comprobar los registros del firewall IDS o IPS, si están disponibles
        * Comprobar los archivos con contenido estático
        * Escanear las bases de datos en busca de contenido malicioso
        * Comprobación de los enlaces presentes en la página
3. Recoge cualquier pista sobre quién es el ciberdelincuente o para qué organización trabaja. Considera las siguientes preguntas:
    * ¿Qué representa la desfiguración? ¿Incluía un mensaje obvio?
    * ¿Parece que la desfiguración es inofensiva o intencionada? ¿Podría ser el ciberdelincuente un niño jugando o un grupo profesional que trabaja con un motivo?
    * ¿Parece que su organización haya sido el objetivo? ¿Quién podría querer atacar a su organización?
    * ¿Qué esperaba conseguir el ciberdelincuente?
    * Consulta [aquí](https://www.geeksforgeeks.org/types-of-hackers/) para saber más sobre los tipos de ciberdelincuentes que pueden haber atacado tu página web.
4. Recoge otra información importante de la página que ha sido desfigurada, como por ejemplo
    * una captura de pantalla de la desfiguración
    * el dominio y la dirección IP de la página
    * detalles del servidor web
    * el código fuente de la página
        * analizarlo cuidadosamente para identificar el problema y asegurarse de que se encuentra en un servidor de la empresa
    * nombre o cualquier información sobre el atacante
6. También existen herramientas que ayudan a la detección y al análisis de los registros. A continuación se enumeran algunas de ellas:
    * Weblog Expert
    * Sawmill
    * Deep Log Analyzer

**Relación de matrices de ataque MITRE ATT&CK**
- **T1190 - Exploit Public-Facing Application**: Identificar cómo los atacantes pueden haber explotado vulnerabilidades en aplicaciones accesibles públicamente para lograr la desfiguración del sitio web.
- **T1505 - Server Software Component**: Examinar si componentes de software vulnerables en el servidor fueron explotados para modificar el contenido del sitio web.
- **T1199 - Trusted Relationship**: Investigar si los atacantes se aprovecharon de relaciones de confianza con terceros para acceder y alterar el sitio web.

**Relación de matrices de defensa RE&CT**
- **Detect**: Implementar herramientas y técnicas para detectar cambios no autorizados en el contenido del sitio web, incluyendo la monitorización de la integridad de los archivos y el análisis de comportamiento anormal en el tráfico web.
- **Respond**: Desarrollar un protocolo de respuesta rápida para cuando se detecte una desfiguración del sitio web, incluyendo la capacidad de revertir rápidamente los cambios no autorizados.
- **Recover**: Establecer procesos para restaurar el contenido legítimo del sitio web de manera eficiente a partir de copias de seguridad verificadas y sin comprometer.


### Remediar

**Planificar eventos de reparación** en los que estos pasos se pongan en marcha juntos (o de forma coordinada), con los equipos adecuados listos para responder a cualquier interrupción.
* **Considere el momento y las compensaciones** de las acciones de remediación: su respuesta tiene consecuencias.

### Contención

1. Haga una copia de seguridad de todos los datos almacenados en el servidor web con fines forenses.
2. Como se ha mencionado anteriormente, asegúrese de que el servidor de la página desfigurada está temporalmente fuera de servicio mientras se lleva a cabo la investigación.
    * Debe tener una página de error preparada para esta situación que informe al usuario y/o a los empleados de que el mantenimiento está en marcha y que la página que buscaban volverá en breve. Incluso podría tener preparada una página web de respaldo en la que pueda publicar contenido mientras se lleva a cabo la investigación y la reparación, y hacer que su página de error temporal redirija a los usuarios a este sitio de respaldo. 
    * Compruebe su mapa de arquitectura de red. Si la brecha es otro sistema de la red, descárguelo e investíguelo.
3. Una vez que se haya determinado el origen del ataque, aplique los pasos necesarios para garantizar que esto no vuelva a suceder. Esto puede incluir la modificación del código o la edición de los derechos de acceso.
    * Consulte la sección "Investigar" para conocer las fuentes comunes de vulnerabilidad.
    * Si esto está fuera de su dominio, simplemente asegúrese de que ha dado al personal apropiado toda la información sobre el ataque que tiene y permita que los expertos hagan su trabajo.

### Recuperación

1. Elimine el mensaje del ciberdelincuente y reemplácelo por el contenido original y legítimo. Si se han perdido datos en el ataque, consulte las copias de seguridad y restaure la página original en la medida de lo posible.
    * Compruebe las copias de seguridad en busca de indicadores de compromiso
    * Considere la recuperación parcial y la prueba de integridad de las copias de seguridad
2. Considere pedir a los usuarios que cambien sus credenciales de acceso si el servidor web tiene autenticación de usuario. 
3. Después de aplicar las medidas para evitar riesgos (como se recomienda a continuación), restaure su servidor mostrando el contenido original de la página. 
4. Si es necesario y/o aplicable, prepare una disculpa/explicación del ataque ocurrido para los usuarios o cualquier persona que haya presenciado la desfiguración. Asegúrese de que queda claro que el contenido desfigurado no refleja a su organización de ninguna manera. 

### Evitar riesgos

1. Utilice el menor número de plug-ins posible. Los piratas informáticos tienen como objetivo los sitios web que son vulnerables y tienen muchas fuentes de entrada. Puedes limitar estas fuentes de entrada utilizando sólo lo que necesites y eliminando los plug-ins y el software que no utilices o sean antiguos. También es importante actualizarlos lo antes posible. 
2. Controle de cerca y ordene el acceso a los contenidos administrativos. Permita que las personas accedan sólo a lo que necesitan. Esto reducirá la posibilidad de que un error humano provoque un ciberataque. Hay más métodos de prevención DIY mencionados en [este artículo](https://cirt.gy/index.php/node/116) (pasos 6-12) y en el recurso #4 al final de este playbook.
3. Comprueba regularmente si hay malware en tu sitio web escaneando el código fuente. Busca scripts, iframes o URLs que te parezcan desconocidos y asegúrate de escanear también las URLs que sí te resulten familiares.
4. Hay muchos escáneres automáticos de sitios web de gran reputación que no le costarán nada de su tiempo y escanearán a fondo su sitio en busca de vulnerabilidades con regularidad. Aquí hay un [enlace a escáneres populares](https://resources.infosecinstitute.com/14-popular-web-application-vulnerability-scanners/#gref).
5. Defiéndase contra los puntos comunes de explotación, como las inyecciones SQL y los ataques XSS. [Este artículo](https://www.banffcyber.com/knowledge-base/articles/best-practices-address-issue-web-defacement/) incluye las mejores prácticas para defender estos ataques.
6. Instala programas de detección de desfiguración para que, si volviera a producirse un ataque, estés preparado y respondas rápidamente. Aquí hay un [artículo](https://www.techradar.com/news/best-website-defacement-monitoring-service) que resume algunos de los mejores servicios de monitoreo de 2020. 
7. Habla con tus empleados de la importancia de mantener el acceso administrativo limitado y confidencial e infórmales de estos pasos para evitar incidentes, incluyendo la formación periódica de concienciación sobre ciberseguridad.

### Comunicar

1. 1. Elevar el incidente y comunicarlo a la dirección según el procedimiento
1. 2. Documentar el incidente según el procedimiento (e informar si procede)
1. Comunicarse con los asesores jurídicos internos y externos según el procedimiento, incluyendo discusiones sobre el cumplimiento, la exposición al riesgo, la responsabilidad, el contacto con las fuerzas del orden, _etc._.
1. Comunicarse con los usuarios (internos)
    1. Comunicar las actualizaciones de la respuesta a incidentes según el procedimiento
    1. Comunicar el impacto del incidente **y** las acciones de respuesta al incidente (por ejemplo, contención: "¿por qué está caído el archivo compartido?")
    1. Comunicar los requisitos: "¿qué deben hacer y no hacer los usuarios?"  
1. Comunicar a los clientes
    1. Centrarse especialmente en aquellos cuyos datos se vieron afectados
    1. Generar las notificaciones requeridas en base a las regulaciones aplicables (particularmente aquellas que puedan considerar la desfiguración como una violación de datos o que requieran notificaciones de otro tipo).
1. Contactar con los proveedores de seguros
    1. Discutir qué recursos pueden poner a disposición, qué herramientas y proveedores apoyan y pagarán, _etc._.
    1. Cumplir con los requisitos de presentación de informes y reclamaciones para proteger la elegibilidad
1. Considerar la posibilidad de notificar e implicar a las fuerzas del orden.
    1. [Aplicación de la ley local](#TODO-link-to-actual-resource)
    1. 1. [Aplicación de la ley a nivel estatal o regional](#TODO-link-to-actual-resource)
    1. 1. [Fuerzas de seguridad federales o nacionales](#TODO-link-to-actual-resource)
1. Comuníquese con los proveedores de seguridad y de TI 
    1. Notifique y colabore con [proveedores gestionados](#TODO-link-to-actual-resource) según el procedimiento
    1. 2. Notificar y colaborar con [consultores de respuesta a incidentes](#TODO-link-to-actual-resource) por procedimiento

### Recursos

1. Mantenga la calma y respire profundamente.
1. 2. Desconecte su sistema de la red `.
1. Haz fotos de la página que veas con tu smartphone mostrando las cosas que has notado: el mensaje de desfiguración y cualquier otro cambio en el sitio habitual.
1. 2. Toma notas sobre el problema o los problemas utilizando la aplicación de notas de voz de tu smartphone o con papel y lápiz.  Todo ayuda.  Documenta lo siguiente:
    1. ¿Qué has notado?
    1. ¿Cuándo ocurrió por primera vez, y con qué frecuencia desde entonces?
    1. ¿A qué datos suele acceder?
    1. ¿Con quién más se ha puesto en contacto en relación con este incidente y qué le ha dicho?
1. Ponte en contacto con el [servicio de asistencia](#TODO-enlace-al-recurso) y sé lo más servicial posible.
1. Ten paciencia: deja que el personal informático lo controle, ¡puedes estar protegiendo a otros de un daño!  **Gracias.**

#### Referencia: Acciones del Help Desk ante un presunto ataque de defacement

1. Mantenga la calma y respire profundamente.
1. Abra un ticket para documentar el incidente, según el procedimiento. 
1. Utiliza tu mejor criterio para decidir qué pasos priorizar (por ejemplo, si la desfiguración dejó contenido dañino o desencadenante, prioriza la retirada del servidor inmediatamente).
1. Pídele al usuario que tome fotos de su pantalla con su teléfono inteligente mostrando las cosas que notó.
1. Toma notas sobre el problema o los problemas utilizando la aplicación de notas de voz de tu smartphone o con papel y lápiz.  2. Si se trata de un informe de usuario, haga preguntas detalladas, incluyendo
       1. ¿Qué has notado?
    1. ¿Cuándo ocurrió por primera vez, y con qué frecuencia desde entonces?
    1. ¿A qué datos suele acceder?
    1. ¿Con quién más se ha puesto en contacto en relación con este incidente y qué le ha dicho?
1. Haga las preguntas de seguimiento que sean necesarias.  **Usted es una persona que responde al incidente, contamos con usted.**
1. Obtenga información de contacto detallada del usuario (domicilio, oficina, móvil), si procede.
1. Registre toda la información en el ticket, incluyendo notas manuscritas y de voz.
1. Ponga en cuarentena a los usuarios y sistemas afectados.
1. Póngase en contacto con el [equipo de seguridad] (#TODO-link-to-actual-resource) y prepárese para participar en la respuesta según las indicaciones: investigación, reparación, comunicación y recuperación.

#### Información adicional
1. <a name="defacement-playbook-ref-1"></a>Un útil y detallado [paper](https://pdfs.semanticscholar.org/899e/2d629e06d920b9059edb21fcb52cdb33f783.pdf) sobre la detección de la desfiguraciónw
2. <a name="defacement-playbook-ref-2"></a>10 herramientas para[better website monitoring and security](https://geekflare.com/website-defacement-monitoring/)
3. <a name="defacement-playbook-ref-3"></a>[2019 Website Threat Research Report](https://sucuri.net/reports/2019-hacked-website-report/) con estadísticas útiles
4. <a name="defacement-playbook-ref-4"></a>[Article](https://www.imperva.com/learn/application-security/website-defacement-attack/) incluyendo bricolaje y mejores prácticas para evitar la desfiguración de sitios web
## Playbook de Privilegio de Elevación

### Introducción

La escalada de privilegios ocurre cuando un atacante logra obtener acceso y privilegios de administrador en un sistema al explotar vulnerabilidades de seguridad. Al alterar los permisos de usuario para otorgarles más derechos y capacidades de administración, la escalada de privilegios permite a los atacantes realizar acciones maliciosas con niveles más altos de acceso, lo que puede causar daños importantes.

### Tipos de Escalada de Privilegios
#### *Escalada de Privilegios Locales*
Este tipo de escalada de privilegios se produce cuando un atacante ya tiene acceso a una cuenta de usuario en el sistema comprometido y utiliza vulnerabilidades del sistema operativo o aplicaciones instaladas para obtener permisos de administrador.

#### *Escalada de Privilegios Remotos*
En este caso, un atacante explota una vulnerabilidad de software remoto para ganar acceso y control sobre un sistema remoto. Esto puede incluir el uso de exploits de día cero o vulnerabilidades conocidas en servicios de red accesibles desde el exterior.

#### *Métodos Comunes de Escalada de Privilegios*
1. **Explotación de Vulnerabilidades del Sistema Operativo**
Los atacantes pueden aprovechar vulnerabilidades del sistema operativo, como errores de desbordamiento de búfer, condiciones de carrera o privilegios mal configurados, para ejecutar código arbitrario con privilegios elevados.

2. **Explotación de Vulnerabilidades de Aplicaciones**
Las aplicaciones instaladas en el sistema también pueden tener vulnerabilidades que pueden ser explotadas para obtener privilegios elevados. Esto puede incluir aplicaciones de servidor, navegadores web, software de correo electrónico, etc.

3. **Uso de Exploits de Escalada de Privilegios**
Existen exploits específicamente diseñados para llevar a cabo la escalada de privilegios en sistemas operativos y aplicaciones populares. Estos exploits pueden ser utilizados por los atacantes para automatizar el proceso de escalada de privilegios.

### Procedimiento

1. **Identificación de la vulnerabilidad**:

   Para identificar posibles vulnerabilidades que permitan la elevación de privilegios, es crucial realizar una evaluación exhaustiva del sistema. Esto puede incluir revisar los permisos de archivos y directorios, examinar configuraciones de servicios y aplicaciones, así como buscar debilidades conocidas en el software instalado. Herramientas como Nessus, OpenVAS o Nmap pueden ayudar en el escaneo de vulnerabilidades. También se pueden buscar exploits conocidos en bases de datos como Exploit Database (Exploit-DB).

    1. **Análisis de Permisos y Configuraciones**:
        - Revisar los permisos de archivos y directorios para identificar posibles configuraciones laxas que podrían permitir la elevación de privilegios.
        - Examinar la configuración de servicios y aplicaciones en busca de vulnerabilidades conocidas que podrían ser explotadas para elevar privilegios.

    2. **Escaneo de Vulnerabilidades**:
        - Utilizar herramientas como Nessus, OpenVAS o Nmap para escanear el sistema en busca de posibles vulnerabilidades que podrían ser aprovechadas para la elevación de privilegios.

    3. **Auditoría de Logs**:
        - Revisar los registros de eventos del sistema en busca de actividades inusuales o intentos de acceso no autorizado que podrían indicar una posible explotación de vulnerabilidades para la elevación de privilegios.


2. **Explotación de la vulnerabilidad**:

   Una vez identificada una vulnerabilidad, la explotación puede variar dependiendo de la naturaleza específica del problema. Por ejemplo, si se trata de una vulnerabilidad de inyección de comandos en un servicio, se puede intentar enviar comandos maliciosos para obtener acceso con privilegios. Si es una vulnerabilidad de desbordamiento de búfer, se pueden crear payloads especialmente diseñados para sobrescribir partes importantes de la memoria y ejecutar código arbitrario. Herramientas como Metasploit pueden ser útiles para la explotación de vulnerabilidades conocidas.

     1. **Identificación de Exploits**:
        - Buscar exploits conocidos que puedan aprovechar las vulnerabilidades identificadas para elevar privilegios en el sistema.

    2. **Desarrollo de Payloads**:
        - Desarrollar payloads personalizados o utilizar herramientas como Metasploit para crear payloads que puedan ser utilizados para la elevación de privilegios.

    3. **Ejecución del Exploit**:
        - Implementar el exploit identificado o el payload desarrollado para aprovechar la vulnerabilidad y elevar los privilegios en el sistema.


3. **Verificación**:

   Para verificar si la elevación de privilegios ha sido exitosa, se pueden realizar varias acciones. Esto puede incluir verificar los registros de acceso al sistema para ver si se han realizado cambios en los privilegios de usuario, comprobando la existencia de nuevas cuentas de usuario con privilegios elevados, o intentando acceder a recursos restringidos para confirmar el nivel de acceso obtenido. También se puede utilizar la información obtenida durante la explotación para confirmar que se ha obtenido acceso con los privilegios deseados.

    1. **Confirmación de Privilegios Elevados**:
        - Verificar que la elevación de privilegios ha sido exitosa mediante la obtención de acceso a recursos restringidos que solo están disponibles para usuarios con privilegios elevados.

    2. **Revisión de Logs**:
        - Analizar nuevamente los registros de eventos del sistema para confirmar la actividad relacionada con la elevación de privilegios y asegurarse de que no haya sido detectada.
4. **Comunicación**

    1. **Identificación y Notificación Inicial**:
    - Notificar al equipo de respuesta a incidentes (IR) y al equipo de seguridad de la información (IS) sobre la identificación de la vulnerabilidad y la escalada de privilegios para activar el protocolo de respuesta a incidentes.

    2. **Comunicación Interna**:
    - Informar al personal interno sobre la vulnerabilidad identificada y las medidas tomadas para mitigarla, proporcionando instrucciones claras sobre cómo proceder y reportar cualquier actividad sospechosa.

    3. **Coordinación con Asesores Externos**:
    - Consultar con asesores legales y de seguridad externos para determinar la gravedad del incidente y las obligaciones legales o de cumplimiento, como la notificación a las autoridades o afectados.

    4. **Comunicación Externa**:
    - Desarrollar y distribuir comunicados para informar a clientes, socios y, si es necesario, al público sobre la vulnerabilidad identificada, las acciones tomadas para mitigarla y las medidas recomendadas para protegerse.

4. **Remediación**

    1. **Restauración de Sistemas y Servicios**:
        - Evaluar el alcance del daño causado por la escalada de privilegios y restaurar los sistemas afectados desde copias de seguridad limpias y seguras. Asegurarse de que todos los sistemas restaurados sean sometidos a una revisión exhaustiva de seguridad antes de reintegrarlos a la red.

    2. **Análisis Forense y Eliminación de Malware**:
        - Realizar un análisis forense para comprender cómo ocurrió la escalada de privilegios, qué vulnerabilidades fueron explotadas y si hay alguna presencia maliciosa persistente en la red. Utilizar esta información para eliminar completamente el malware o las herramientas utilizadas por los atacantes.

        Herramientas útiles:
            - Plataformas de análisis forense digital, como EnCase Forensic, Autopsy.
            - Antivirus avanzados y herramientas de eliminación de malware, como Malwarebytes, Kaspersky Virus Removal Tool.
            - Software de análisis de logs, como Splunk, ELK Stack.

    3. **Reforzamiento de las Defensas**:
        - Basado en los hallazgos del análisis forense, reforzar las defensas para cerrar las vulnerabilidades explotadas durante la escalada de    privilegios. Esto puede incluir la implementación de nuevas herramientas de seguridad, actualización de políticas y el reforzamiento de la seguridad física y de red.

    4. **Educación y Concienciación sobre Seguridad**:
        - Desarrollar y entregar programas de capacitación y concienciación para educar a los empleados sobre los riesgos de la escalada de privilegios, cómo identificarla y las acciones a tomar en caso de sospecha. Incluir simulaciones de ataques para evaluar y mejorar la respuesta de los empleados.
### Mitre Ataque y Defensa

### Matriz de Tácticas y Técnicas de Mitre

- **Táctica: Ejecución**
  - Técnica: Ejecución de Código en un Proceso Hijacked (T1055)
    - Descripción: Los atacantes pueden aprovechar procesos legítimos para ejecutar código malicioso con privilegios elevados.
    - Defensa: Implementar controles de ejecución de aplicaciones para prevenir la ejecución de código no autorizado en procesos legítimos.

- **Táctica: Persistencia**
  - Técnica: Creación de Tarea Programada (T1053)
    - Descripción: Los atacantes pueden establecer tareas programadas para ejecutar código malicioso de forma periódica con privilegios elevados.
    - Defensa: Monitorear y revisar regularmente las tareas programadas en el sistema para detectar actividades maliciosas y eliminarlas.

- **Táctica: Defensa y Evasión**
  - Técnica: Uso de Lenguajes de Script para Automatización (T1064)
    - Descripción: Los atacantes pueden utilizar scripts para automatizar el proceso de escalada de privilegios y evadir la detección de seguridad.
    - Defensa: Implementar restricciones de ejecución de scripts y firmar scripts autorizados para evitar la ejecución de scripts maliciosos.

#### Incorporación de Mitre al Playbook

- **Detección de Técnicas de Mitre:**
  - Descripción: Integrar la detección de técnicas de Mitre en las herramientas de monitoreo de seguridad para identificar posibles ataques basados en tácticas y técnicas conocidas.
  - Acción: Configurar reglas y alertas en las soluciones de seguridad para detectar actividades maliciosas que coincidan con las tácticas y técnicas de Mitre.
  - Responsable: Equipo de Seguridad de la Información, Equipo de Respuesta a Incidentes (ERI).

- **Respuesta a Técnicas de Mitre:**
  - Descripción: Desarrollar procedimientos de respuesta específicos para abordar las técnicas de Mitre utilizadas por los atacantes en escaladas de privilegios.
  - Acción: Definir pasos claros y acciones a tomar para mitigar las amenazas identificadas basadas en las tácticas y técnicas de Mitre.
  - Responsable: Equipo de Respuesta a Incidentes (ERI), Equipo de Seguridad de la Información.

5. **Mitigación**:

   Para mitigar la vulnerabilidad y prevenir futuras elevaciones de privilegios, se deben seguir las mejores prácticas de seguridad, que incluyen:

   - Mantener el sistema y el software actualizados con los últimos parches de seguridad.
   - Configurar adecuadamente los permisos de archivos y directorios para limitar el acceso a recursos sensibles.
   - Utilizar listas de control de acceso (ACL) para controlar quién puede acceder a qué recursos.
   - Implementar medidas de seguridad adicionales, como firewalls, sistemas de detección de intrusiones (IDS) y sistemas de prevención de intrusiones (IPS).
   - Realizar auditorías de seguridad regulares para identificar y remediar vulnerabilidades antes de que puedan ser explotadas.

    1. **Aplicación de Parches y Actualizaciones**:
        - Mantener el sistema y el software actualizados con los últimos parches de seguridad para corregir las vulnerabilidades conocidas que podrían ser explotadas para la elevación de privilegios.

    2. **Configuración de Permisos y Privilegios**:
        - Revisar y ajustar los permisos de archivos y directorios para limitar el acceso solo a usuarios autorizados y reducir el riesgo de explotación de vulnerabilidades.

    3. **Implementación de Principio de Menor Privilegio**:
        - Seguir el principio de menor privilegio asignando a los usuarios solo los privilegios necesarios para realizar sus funciones, lo que reduce el impacto potencial de la elevación de privilegios.

### Herramientas recomendadas

- Nessus
- OpenVAS
- Nmap
- Metasploit
- Exploit Database (Exploit-DB)

### Referencias

- [Nessus](https://www.tenable.com/products/nessus)
- [OpenVAS](https://www.openvas.org/)
- [Nmap](https://nmap.org/)
- [Metasploit](https://www.metasploit.com/)
- [Exploit Database](https://www.exploit-db.com/)


## Ciberresiliencia

### Páginas de Error Personalizadas
Implementaremos páginas de error personalizadas para comunicar de manera efectiva con nuestros usuarios cuando enfrenten interrupciones en el servicio. Estas páginas mostrarán mensajes claros y amigables, informando a los usuarios que somos conscientes del problema y estamos trabajando activamente para solucionarlo. Además, incluiremos información útil, como enlaces a nuestras redes sociales y formas de contacto, para que los usuarios puedan seguir recibiendo actualizaciones sobre el estado del servicio.

### Chats de Respuesta Alternativos
Para asegurarnos de que siempre estemos accesibles a nuestros clientes, incluso durante interrupciones del servicio, estableceremos sistemas de chat de respuesta alternativos. Estos sistemas operarán a través de plataformas de terceros confiables, permitiéndonos mantener una comunicación fluida y directa con nuestros usuarios. A través de estos chats, podremos ofrecer soporte en tiempo real, responder preguntas y proporcionar actualizaciones sobre la resolución de incidentes.

### Hosting de Emergencia
Nos asociaremos con proveedores de hosting de emergencia para garantizar que podamos reactivar rápidamente una versión operativa de nuestro sitio web en caso de un fallo crítico. Este plan de contingencia nos permitirá mantener una presencia en línea y seguir ofreciendo servicios esenciales mientras trabajamos en resolver cualquier problema con nuestra infraestructura principal. Esta solución de hosting de emergencia estará pre-configurada para activarse con mínima intervención manual y máxima rapidez.

### Automatización de Respuestas
Desarrollaremos y pondremos en práctica scripts de automatización diseñados para ejecutar respuestas rápidas ante fallos detectados. Esto incluirá la activación automática de nuestras páginas de error personalizadas, el despliegue de nuestro sitio en el hosting de emergencia, y la notificación instantánea a nuestro equipo técnico y a nuestros usuarios a través de los canales de comunicación establecidos. La automatización garantizará que podamos reaccionar de manera inmediata y eficiente, reduciendo el tiempo de inactividad y mejorando nuestra capacidad de recuperación.

### Simulacros
Realizaremos simulacros de fallo regularmente para probar y mejorar nuestra capacidad de respuesta ante incidentes reales. Estos ejercicios nos permitirán evaluar la efectividad de nuestras páginas de error personalizadas, la fiabilidad de nuestro hosting de emergencia, la precisión de nuestros scripts de automatización, y nuestra habilidad para comunicarnos efectivamente con los usuarios a través de chats alternativos. Los simulacros nos ayudarán a identificar áreas de mejora, garantizando que nuestro plan de respuesta sea tan robusto y eficiente como sea posible.

## Playbook: Compromiso de identidad y acceso


### Investigar

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


### Remediar

#### Planificación de Eventos de Remediación

- **Coordinador de Respuesta a Incidentes**: Encargado de la planificación y ejecución de la remediación.
- **Acciones**:
  - Programar eventos de remediación coordinando equipos de TI, seguridad, y operaciones.
  - Considerar interrupciones de servicio y comunicarlas proactivamente.
  - Priorizar acciones basadas en el impacto y la severidad del compromiso.

### Contención

#### Pasos y Herramientas

#### Aislamiento de Sistemas y Cuentas Comprometidas

- **Herramientas**: Cortafuegos, sistemas de detección de intrusos, herramientas de gestión de identidad y acceso.
- **Equipo**: Operaciones de TI
- **Acciones**: Desconexión de sistemas afectados, revocación de accesos sospechosos.

#### Implementación de Controles de Acceso Temporales

- **Herramientas**: Sistemas de gestión de identidades, autenticación multifactor.
- **Equipo**: Seguridad de TI
- **Acciones**: Establecimiento de controles de acceso más estrictos, actualización de políticas de seguridad.

**Relación de matrices de ataque MITRE ATT&CK** <br>
- T1489 - **Service Stop:** Aunque no mencionado previamente, esta técnica puede ser relevante cuando se considera la desconexión de sistemas afectados o la desactivación de servicios comprometidos como parte del proceso de aislamiento.
- T1548 - **Abuse Elevation Control Mechanism:** Aunque no mencionado previamente, esta técnica resalta la importancia de implementar y fortalecer controles como la autenticación multifactor (MFA) para prevenir la elevación indebida de privilegios por parte de atacantes.

**Relación de matrices de defensa RE&CT**
- La desconexión de sistemas afectados y la revocación de accesos sospechosos son acciones directas bajo la estrategia Contain en RE&CT. Implementar un aislamiento efectivo es crucial para prevenir la propagación del ataque y la explotación adicional de recursos de la red.
-El objetivo es reforzar las defensas y mejorar la resiliencia organizacional frente a futuros ataques. La implementación de MFA y la revisión de políticas de acceso son ejemplos de cómo se puede endurecer la seguridad tras un incidente.

### Erradicar

#### Pasos para Eliminar la Amenaza

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

### Recuperación

### Pasos para la Restauración

#### Restauración de Operaciones Normales

- **Herramientas**: Sistemas de gestión de cambios, herramientas de monitorización.
- **Equipo**: TI y Operaciones
- **Acciones**: Restauración gradual de sistemas y accesos, monitoreo intensivo para detectar anomalías.

**Relación de matrices de ataque MITRE ATT&CK** <br>
-  T1486 - Data Encrypted for Impact, relacionado con ransomware que cifra datos críticos, puede ser relevante aquí, ya que la restauración de datos desde copias de seguridad seguras es una contramedida directa a este tipo de ataque.
- T1490 - Inhibit System Recovery: Esta técnica refleja los esfuerzos de los atacantes por impedir la recuperación del sistema, ya sea mediante la eliminación de copias de seguridad, la corrupción de sistemas de recuperación, o la modificación de configuraciones del sistema para obstaculizar los esfuerzos de restauración.
  
**Relación de matrices de defensa RE&CT**
- La acción Recover en RE&CT, que se centra en la recuperación tras un incidente. Esto incluye la restauración gradual de sistemas y accesos, utilizando sistemas de gestión de cambios para implementar la restauración y herramientas de monitorización.
- RE&CT: Learn es relevante aquí para integrar lecciones aprendidas durante el incidente en prácticas y políticas futuras, asegurando una mejora continua.

### Recursos

- **Financieros y de Personal**: Asignación de presupuesto para herramientas de seguridad adicionales, contratación de expertos en seguridad externos si es necesario.
- **Logísticos**: Planificación de recursos para la restauración de operaciones, incluyendo hardware y software.

#### Información adicional

1. <a name="identity-and-access-playbook-ref-1"></a>[Marcos para la gestión de identidad y acceso](https://www.nist.gov/)
2. <a name="ransomware-playbook-ref-2"></a>[Prácticas recomendadas de gestión de identidad y acceso](https://www.strongdm.com/)
## Playbook de Ataques a Dispositivos IoT (IoT Device Attacks)

### Investigación

Los dispositivos IoT son vulnerables a una variedad de ataques debido a su diseño y configuración inherentemente débiles. Es importante comprender los diferentes tipos de ataques que pueden afectar a los dispositivos IoT, como ataques de denegación de servicio (DoS), manipulación de firmware y secuestro de dispositivos, y cómo pueden ser mitigados.

### Identificación

- **Análisis de Tráfico**: Monitorice el tráfico de red en busca de patrones sospechosos, como flujos de datos anómalos o intentos de comunicación con direcciones IP no autorizadas.
- **Auditoría de Dispositivos**: Realice auditorías regulares de dispositivos IoT para identificar vulnerabilidades de seguridad, incluyendo configuraciones predeterminadas débiles y puertos abiertos no seguros.
- **Análisis de Firmware**: Analice el firmware de los dispositivos en busca de vulnerabilidades conocidas y firmas maliciosas.

### Evaluación de Vulnerabilidades

Realice un análisis de vulnerabilidades en los dispositivos IoT para determinar si existen vulnerabilidades conocidas en el firmware o en la configuración. Utilice herramientas como Nessus o OpenVAS para escanear los dispositivos y obtener informes detallados sobre las vulnerabilidades encontradas. Tenga en cuenta que no es necesario tener conocimientos avanzados sobre cómo modificar el firmware, pero es importante identificar si existen vulnerabilidades conocidas que podrían ser explotadas por atacantes.

### Explotación

La explotación de dispositivos IoT es una preocupación creciente debido a la proliferación de estos dispositivos en el hogar y en entornos empresariales. Los atacantes pueden aprovechar vulnerabilidades en el firmware, protocolos de comunicación débiles y configuraciones inseguras para comprometer la seguridad de estos dispositivos y realizar acciones maliciosas. A continuación, se presentan ejemplos de cómo los dispositivos IoT pueden ser explotados en manos de atacantes:

- **Ataque de Denegación de Servicio (DoS)**:
  - Ejemplo 1: Lance un ataque de inundación de paquetes contra el dispositivo IoT para saturar su capacidad de procesamiento y dejarlo inaccesible.
- **Manipulación de Firmware**:
  - Ejemplo 2: Modifique el firmware del dispositivo IoT para incluir un backdoor que permita el acceso remoto no autorizado.
- **Secuestro de Dispositivos**:
  - Ejemplo 3: Intercepte el tráfico de red entre un dispositivo IoT y su servidor para secuestrar la comunicación y realizar acciones maliciosas.



### Comunicación

1. **Identificación y Notificación Inicial:**
   - Quién Participa: Equipo de Respuesta a Incidentes (ERI), Equipo de Seguridad de la Información, Equipo de TI.
   - Procedimiento: En cuanto se detecte un incidente en dispositivos IoT, el equipo de Respuesta a Incidentes (ERI) debe ser notificado de inmediato para iniciar la investigación y tomar medidas correctivas.
   - Herramientas: Sistemas de ticketing para incidentes, canales de comunicación internos (por ejemplo, Slack, Microsoft Teams).

2. **Comunicación Interna:**
   - Quién Participa: ERI, Equipo de Desarrollo de Productos, Ingenieros de IoT, Alta Dirección.
   - Procedimiento: Informar internamente sobre el incidente a todos los equipos relevantes, proporcionando detalles sobre la naturaleza del incidente, los dispositivos afectados y las medidas inmediatas que se están tomando para mitigar el riesgo.
   - Herramientas: Correo electrónico interno, reuniones de equipo, paneles de control de incidentes.

3. **Coordinación con Asesores Externos:**
   - Quién Participa: ERI, Proveedores de Dispositivos IoT, Asesores de Seguridad Externos.
   - Procedimiento: Consultar con expertos externos en seguridad de IoT y proveedores de dispositivos para comprender la naturaleza y el alcance del incidente, así como para identificar soluciones y mitigaciones efectivas.
   - Herramientas: Plataformas de comunicación segura, sistemas de gestión de relaciones con proveedores.

4. **Comunicación Externa:**
   - Quién Participa: Departamento de Comunicaciones, Alta Dirección, Asesores Legales.
   - Procedimiento: Desarrollar y distribuir comunicados externos para informar a los clientes, socios y partes interesadas sobre el incidente, las medidas tomadas para abordarlo y las recomendaciones para proteger sus dispositivos.


### Verificación

1. **Recepción del Informe de Incidente:**
   - Descripción: Confirmar la recepción del informe de incidente por parte del equipo de Respuesta a Incidentes (ERI).
   - Acción: Registrar la recepción del informe en el sistema de seguimiento de tickets o mediante una respuesta formal de confirmación.
   - Responsable: Equipo de Respuesta a Incidentes (ERI).

2. **Comprensión de Acciones a Tomar:**
   - Descripción: Verificar que los equipos internos comprendan las acciones a tomar para mitigar el incidente.
   - Acción: Realizar reuniones de seguimiento con los equipos relevantes para confirmar la comprensión de las medidas a implementar.
   - Responsable: Equipo de Respuesta a Incidentes (ERI), Equipos Internos.

3. **Implementación de Medidas Recomendadas:**
   - Descripción: Verificar la implementación de las medidas recomendadas por los asesores externos.
   - Acción: Obtener confirmación por escrito de los asesores externos sobre la implementación de las medidas recomendadas.
   - Responsable: Equipo de Respuesta a Incidentes (ERI), Asesores Externos.

4. **Seguimiento de la Respuesta Externa:**
   - Descripción: Monitorear la respuesta externa al incidente para garantizar una comunicación efectiva.
   - Acción: Realizar seguimiento continuo de la cobertura mediática y recopilar feedback de los clientes.
   - Responsable: Departamento de Comunicaciones, Alta Dirección.

### Mitre Ataque y Defensa

#### Matriz de Tácticas y Técnicas de Mitre

- **Táctica: Ejecución**
  - Técnica: Modificación de Firmware (T1566)
    - Descripción: Los atacantes pueden modificar el firmware de los dispositivos IoT para incluir puertas traseras o funcionalidades maliciosas.
    - Defensa: Implementar medidas de seguridad en el proceso de actualización de firmware, como la verificación de integridad y la autenticación de origen.

- **Táctica: Persistencia**
  - Técnica: Manipulación de Configuración de Dispositivos (T1601)
    - Descripción: Los atacantes pueden modificar la configuración de los dispositivos IoT para mantener el acceso persistente.
    - Defensa: Monitorear continuamente la configuración de los dispositivos IoT y detectar cambios inusuales que puedan indicar una manipulación por parte de un atacante.

- **Táctica: Defensa y Evasión**
  - Técnica: Ofuscación de Comunicaciones (T1573)
    - Descripción: Los atacantes pueden utilizar técnicas de ofuscación para ocultar la comunicación maliciosa entre los dispositivos IoT y los servidores de comando y control.
    - Defensa: Implementar sistemas de detección de anomalías en el tráfico de red para identificar patrones de comunicación sospechosos y técnicas de ofuscación.

#### Incorporación de Mitre 

- **Detección de Técnicas de Mitre:**
  - Descripción: Integrar la detección de técnicas de Mitre en las herramientas de monitoreo de seguridad para identificar posibles ataques basados en tácticas y técnicas conocidas.
  - Acción: Configurar reglas y alertas en las soluciones de seguridad para detectar actividades maliciosas que coincidan con las tácticas y técnicas de Mitre.
  - Responsable: Equipo de Seguridad de la Información, Equipo de Respuesta a Incidentes (ERI).

- **Respuesta a Técnicas de Mitre:**
  - Descripción: Desarrollar procedimientos de respuesta específicos para abordar las técnicas de Mitre utilizadas por los atacantes en dispositivos IoT.
  - Acción: Definir pasos claros y acciones a tomar para mitigar las amenazas identificadas basadas en las tácticas y técnicas de Mitre.
  - Responsable: Equipo de Respuesta a Incidentes (ERI), Equipo de Seguridad de la Información.

### Mitigación

- Implemente medidas de seguridad como la segmentación de red para aislar dispositivos IoT y proteger la infraestructura crítica.
- Actualice regularmente el firmware de los dispositivos IoT para corregir vulnerabilidades conocidas y mejorar la seguridad.
- Utilice autenticación fuerte y cifrado de extremo a extremo para proteger la comunicación entre dispositivos IoT y servidores.

### Remediación

- Realice auditorías de seguridad regulares en dispositivos IoT para identificar y corregir vulnerabilidades de seguridad.
- Proporcione capacitación y concienciación sobre seguridad a los usuarios y propietarios de dispositivos IoT para promover prácticas seguras.
- Establezca un proceso de respuesta a incidentes para manejar de manera efectiva los ataques a dispositivos IoT y minimizar el impacto en la organización.

### Recuperacion
- **Auditorías de Seguridad Post-Ataque:** Realice auditorías de seguridad exhaustivas en los dispositivos IoT afectados para identificar el alcance completo del ataque, las vulnerabilidades explotadas y las áreas de mejora de seguridad.

- **Restauración de Configuraciones Seguras**: Restablezca las configuraciones de fábrica seguras en los dispositivos afectados para eliminar cualquier configuración maliciosa o comprometida que pueda haber sido implementada durante el ataque.

- **Análisis Forense:** Realice un análisis forense detallado para comprender cómo ocurrió el ataque, qué datos se vieron comprometidos y qué medidas correctivas deben implementarse para evitar futuros incidentes similares.

- **Mejoras en la Seguridad:** Implemente medidas de seguridad adicionales, como parches de seguridad, actualizaciones de firmware y mejoras en la configuración de red, para fortalecer la seguridad de los dispositivos IoT y prevenir futuros ataques.

- **Revisión de Políticas y Procedimientos:** Revise y actualice las políticas y procedimientos de seguridad para garantizar que estén alineados con las lecciones aprendidas del incidente y para mejorar la capacidad de respuesta a futuros ataques.

- **Capacitación del Personal:** Proporcione capacitación adicional al personal sobre prácticas de seguridad actualizadas y procedimientos de respuesta a incidentes para mejorar la preparación y la capacidad de recuperación ante futuros ataques.

## Playbook: Phishing

**Investigar, remediar (contener, erradicar), y comunicar en paralelo!**

Asigna pasos a individuos o equipos para que trabajen simultáneamente, cuando sea posible; este playbook no es meramente secuencial. Utilice su mejor criterio.

### Investigación

#### **Ámbito del ataque** <br>
Objetivo: Determinar la extensión y el impacto del ataque de phishing para contenerlo y remediarlo de manera eficiente.
* Notificación Inicial: Registrar cómo se detectó el incidente, quién lo reportó, y la evidencia inicial proporcionada.
* Usuarios Afectados: Utilizar herramientas de análisis de logs y seguridad de correo electrónico para identificar a todos los usuarios que recibieron el mensaje de phishing.
* Acciones de los Usuarios: Comunicarse directamente con los posibles usuarios afectados para entender si interactuaron con el mensaje (descarga de archivos, clic en enlaces, suministro de información).
* Búsqueda de Actividad Relacionada: Revisar redes sociales, correos electrónicos sospechosos, y notificaciones de actividades inusuales que puedan estar relacionadas con el ataque.
* Clasificación del Ataque: Basándose en la información recopilada, determinar el tipo de phishing (general, spear, whaling, smishing/vishing) y la gravedad.

#### **Analizar el mensaje** utilizando un dispositivo seguro. <br>
Objetivo: Inspeccionar el correo electrónico de phishing de manera segura para recopilar datos sin comprometer la seguridad de la red o los datos sensibles.

Herramientas:
* Entornos Aislados: Máquinas virtuales dedicadas o entornos sandbox.
* Herramientas Forenses de Correo Electrónico: MailXaminer, The Sleuth Kit para analizar cabeceras y contenido.
* Decodificadores de URL: Para revelar redirecciones ocultas sin acceder a ellas.

Procedimiento:
* Preparación del Entorno Seguro: Iniciar una máquina virtual o entorno sandbox que no tenga acceso a la red corporativa o datos sensibles.

Inspección del Correo Electrónico:
* Cabeceras: Analizar las cabeceras del correo para determinar la ruta del mensaje, servidores involucrados y posibles falsificaciones.
* Cuerpo y Asunto: Observar el tono, errores gramaticales y tácticas de engaño.
* Adjuntos: Identificar nombres de archivos, tipos y tamaños sin abrirlos.
* Enlaces: Copiar los enlaces sin hacer clic en ellos para su análisis posterior.

#### **Analizar los enlaces y los archivos adjuntos**
Objetivo: Evaluar los enlaces y archivos adjuntos para determinar la naturaleza y el riesgo del contenido sin comprometer la seguridad.
* VirusTotal: Para análisis de URLs y archivos sospechosos.
* Sandbox de Malware: Como Cuckoo Sandbox, para observar el comportamiento de los archivos en un entorno controlado.
* Herramientas OSINT: Para investigar dominios y enlaces, como WHOIS, nslookup
* Analizadores de URL: Para descomponer y analizar el verdadero destino de un enlace.

Enlaces:
   - Utilizar decodificadores de URL para visualizar el verdadero destino.
   - Ingresar los enlaces en VirusTotal para verificar si son conocidos por distribuir malware o por ser parte de campañas de phishing.
   - Realizar búsquedas OSINT para identificar la propiedad del dominio y su reputación.

Archivos Adjuntos:
   - Subir los archivos a un sandbox de malware para analizar su comportamiento sin riesgo.
   - Usar VirusTotal para escanear los archivos en busca de firmas de malware conocido.
   - Investigar metadatos y propiedades del archivo para pistas sobre su origen y propósito.
    
#### **Tipos de ataque.**
1.  Phishing General: Ataques no personalizados enviados a gran escala, buscando engañar a los usuarios para obtener información sensible.
2.  Spear Phishing: Ataques dirigidos a individuos o empresas específicas, a menudo utilizando información personalizada para aumentar la credibilidad.
3.  Whaling: Una forma de spear phishing dirigida a altos ejecutivos, buscando acceso a información corporativa crítica o transferencias financieras fraudulentas.
4.  Smishing y Vishing: Phishing realizado a través de SMS (smishing) o llamadas telefónicas (vishing), buscando engañar a las víctimas para que revelen información personal o financiera.
 
**Relación de matrices de ataque MITRE ATT&CK** <br>
- T1566.001 - Spear Phishing Attachment y T1566.002 - Spear Phishing Link: Estas técnicas son fundamentales para comprender y clasificar los tipos de ataques de phishing, permitiendo una respuesta más enfocada y eficaz.

**Relación de matrices de defensa RE&CT**
- Identify: Clasificar el tipo de ataque de phishing ayuda a identificar el nivel de sofisticación y los objetivos posibles del atacante.
- Protect: Desarrollar estrategias específicas de protección contra los tipos identificados de ataques de phishing.

### Remediar

* **Planificar eventos de remediación** en los que estos pasos se pongan en marcha juntos (o de forma coordinada), con los equipos adecuados listos para responder a cualquier interrupción.
* **Equipo de Gestión de Crisis:** Supervisa la coordinación y ejecución de la remediación.
* **Seguridad TI y Soporte TI:** Implementación de acciones de contención y erradicación.

### Contener

1. **Aislamiento y Gestión de Cuentas Comprometidas:**
* Acciones Inmediatas:
   - Identificación y Aislamiento: Rápidamente identificar cuentas afectadas y restringir su acceso para prevenir la propagación de la amenaza. Esto puede incluir desactivación temporal o restricciones de acceso.
   - Cambio de Credenciales: Forzar un cambio de contraseña para todas las cuentas sospechosas de estar comprometidas, aplicando complejidad y unicidad en las nuevas contraseñas.
* Herramientas y Procedimientos:
   - Utilizar soluciones de gestión de identidades y accesos (IAM) para cambiar contraseñas y ajustar permisos de forma masiva.
   - Implementar soluciones de autenticación multifactor (MFA) para añadir una capa adicional de seguridad a las cuentas en riesgo.

2. **Reforzamiento de la Seguridad de Acceso:**
* Autenticación Multifactor (MFA):
   - Implementación Acelerada: Para cuentas aún sin MFA, implementar rápidamente esta capa de seguridad para evitar accesos no autorizados.
* Controles de Acceso Granulares:
   - Restricción de Privilegios: Reducir los privilegios de acceso al mínimo necesario hasta que la investigación esté completa, especialmente para cuentas con acceso a datos críticos.

3. **Bloqueo y Neutralización de Amenazas:**
* Bloqueo de Dominios y Enlaces Maliciosos:
   - Implementar bloqueos a nivel de DNS, firewalls, y proxies para prevenir el acceso a dominios asociados al ataque de phishing.
* Filtrado de Correos Electrónicos:
   - Ajustar las políticas de filtrado de correos para interceptar y bloquear mensajes con características similares a las identificadas en el ataque.

4. **Conservación de Evidencia y Análisis Forense:**
* Retención Forense:
   - Realizar copias forenses de correos electrónicos de phishing y otros artefactos relevantes para la investigación.
* Purga y Aislamiento de Mensajes:
   - Eliminar o aislar correos de phishing de las bandejas de entrada de los usuarios para prevenir interacciones accidentales.

5. **Gestión de Compromisos y Alertas de Seguridad:**
* Aumento de la Vigilancia:
   - Elevar el nivel de alerta y monitoreo de la seguridad, enfocándose en indicadores de compromiso específicos del incidente.
* Asistencia Externa:
   - Considerar el apoyo de expertos en seguridad cibernética para una evaluación más profunda y apoyo en la remediación.

**Relación de matrices de ataque MITRE ATT&CK** <br>
- T1102 (Web Service): El uso de servicios web para alojar phishing y malware. Capturar y analizar estos correos proporciona inteligencia sobre la infraestructura del atacante.
- T1070 (Indicator Removal on Host): Entender cómo los atacantes pueden intentar eliminar rastros de su actividad es crucial para la retención forense.

**Relación de matrices de defensa RE&CT**
- Investigate: Recopilar y analizar evidencia para entender la extensión del compromiso.
- Learn: Aplicar lecciones aprendidas para mejorar las respuestas futuras.

### Comunicar

1. **Identificación y Notificación Inicial:**
   - Quién Participa: Equipo de Respuesta a Incidentes (ERI), Departamento de Seguridad de la Información, Equipo de TI.
   - Procedimiento: Tan pronto como se identifique un incidente de phishing, el ERI debe ser notificado para activar el protocolo de respuesta a incidentes.
   - Herramientas: Sistemas de ticketing para incidentes, plataformas de comunicación interna (por ejemplo, Slack, Microsoft Teams).
     
2. **Comunicación Interna:**
   - Quién Participa: ERI, Departamento de Comunicaciones, Recursos Humanos, Alta Dirección.
   - Procedimiento: Informar al personal interno sobre el incidente con instrucciones claras sobre cómo proceder, especialmente aquellos en departamentos afectados. Esto puede incluir la suspensión temporal de ciertos sistemas o el cambio de contraseñas.
   - Herramientas: Correo electrónico interno, intranet, herramientas de gestión de crisis (por ejemplo, Everbridge).

3. **Coordinación con Asesores Externos:**
   - Quién Participa: ERI, Asesores Legales Externos, Proveedores de Seguridad Externos.
   - Procedimiento: Consultar con asesores legales y de seguridad externos para determinar la gravedad del incidente y las obligaciones legales o de cumplimiento, como la notificación a las autoridades o afectados.
   - Herramientas: Plataformas de comunicación segura, sistemas de gestión de relaciones con proveedores.
   
4. **Comunicación Externa:**
   - Quién Participa: Departamento de Comunicaciones, Alta Dirección, Asesores Legales.
   - Procedimiento: Desarrollar y distribuir comunicados para informar a clientes, socios y, si es necesario, al público sobre el incidente, lo que se está haciendo para resolverlo, y cómo afecta a las partes interesadas. Se deben seguir las directrices legales y de cumplimiento para la comunicación de incidentes de seguridad.
   - Herramientas: Herramientas de gestión de relaciones públicas (PR), plataformas de redes sociales, sitio web corporativo.


**Relación de matrices de ataque MITRE ATT&CK** <br>
- T1556 (Modify Authentication Process): Informar a los empleados sobre los cambios en los procesos de autenticación como respuesta al incidente puede ayudar a prevenir el abuso de credenciales modificadas o robadas.
- T1530 (Data from Cloud Storage Object): Si el ataque de phishing resultó en acceso no autorizado a datos almacenados en la nube, la comunicación externa debe gestionarse cuidadosamente para informar a los afectados de acuerdo con las leyes de protección de datos aplicables, sin comprometer la investigación en curso.
  
**Relación de matrices de defensa RE&CT**
- Inform: Comunicar de manera efectiva dentro de la organización sobre el incidente y proporcionar instrucciones claras ayuda a contener la propagación del ataque de phishing y protege a la organización de un mayor compromiso.
- Coordinate: La colaboración con asesores legales y de seguridad externos asegura que la respuesta al incidente cumpla con las obligaciones legales y de cumplimiento, abordando preocupaciones como el acceso no autorizado a datos (T1530 - Data from Cloud Storage Object).

### Recuperación

1. Restauración de Sistemas y Servicios:
   - Procedimiento: Evaluar el daño y determinar los sistemas y servicios afectados. Restaurar los datos desde copias de seguridad limpias y seguras. Asegurar que todos los sistemas restaurados sean sometidos a una exhaustiva revisión de seguridad antes de reintegrarlos a la red.
   - Herramientas: Software de respaldo y recuperación de datos, herramientas de gestión de parches para aplicar las últimas actualizaciones de seguridad.
     
2. Análisis Forense y Eliminación de Malware:
   - Procedimiento: Realizar un análisis forense para entender cómo ocurrió el ataque, qué vulnerabilidades fueron explotadas, y si queda alguna presencia maliciosa en la red. Usar esta información para eliminar completamente el malware o las herramientas utilizadas por los atacantes.
   - Herramientas: Plataformas de análisis forense digital, antivirus avanzados y herramientas de eliminación de malware, software de análisis de logs.
     
3. Reforzamiento de las Defensas:
   - Procedimiento: Basado en los hallazgos del análisis forense, reforzar las defensas para cerrar las vulnerabilidades explotadas durante el ataque. Esto puede incluir la implementación de nuevas herramientas de seguridad, actualización de políticas, y el reforzamiento de la seguridad física y de red.
   - Herramientas: Sistemas de detección y prevención de intrusiones (IDS/IPS), firewalls avanzados, soluciones de seguridad para el correo electrónico, herramientas de gestión de vulnerabilidades.
     
4. Educación y Concienciación sobre Seguridad:
   - Procedimiento: Desarrollar y entregar programas de capacitación y concienciación para educar a los empleados sobre las tácticas de phishing, cómo identificarlas y las acciones a tomar en caso de sospecha. Incluir simulaciones de phishing para evaluar y mejorar la respuesta de los empleados.
   - Herramientas: Plataformas de entrenamiento en concienciación de seguridad, herramientas de simulación de phishing, materiales educativos y cursos en línea.

**Relación de matrices de ataque MITRE ATT&CK** <br>
- T1485 (Data Destruction): Vigilar por cualquier intento de borrar o corromper datos como parte del ataque de phishing.
- T1490 (Inhibit System Recovery): Asegurar que los atacantes no hayan implementado técnicas para prevenir la recuperación del sistema

**Relación de matrices de defensa RE&CT**
- Recover: Procesos de restauración de sistemas y servicios a estados operativos normales.
- Learn: Analizar el incidente para extraer lecciones aprendidas y aplicar mejoras continuas en la respuesta a incidentes.

### Recursos

##### Referencia: Acciones del usuario ante la sospecha de un ataque de phishing

1. Identificación y No Interacción:
   - Reconocer Señales de Alerta: Los correos electrónicos de phishing a menudo contienen señales reveladoras, como solicitudes urgentes, ofertas demasiado buenas para ser verdad, errores ortográficos, y direcciones de correo electrónico que no coinciden con el nombre del remitente o la organización que afirman representar.
   - Evitar Acciones Precipitadas: No haga clic en enlaces, no descargue archivos adjuntos, y no responda al mensaje. Si el correo parece provenir de una entidad conocida, como un banco o una empresa de servicios, contacte directamente a la entidad usando información de contacto confiable para verificar la comunicación.

2. Reporte Inmediato:
   - Utilizar Canales Establecidos: Reportar el incidente lo antes posible a través de los canales designados por su organización. Esto puede ser una dirección de correo electrónico específica para reportar phishing, una herramienta interna, o incluso un número de teléfono de ayuda.
   - Proporcionar Detalles Clave: Incluya tanta información como sea posible al reportar, como el remitente del correo, cualquier enlace incluido (sin hacer clic en ellos), la fecha y hora del mensaje, y por qué sospecha que es un intento de phishing.

3. Documentación del Incidente:
   - Capturas de Pantalla: Tome capturas de pantalla del correo electrónico sospechoso, incluidos los encabezados completos del mensaje, si es posible. Esto proporcionará evidencia crucial para la investigación posterior.
   - Registro de Acciones: Si accidentalmente interactuó con el correo (por ejemplo, haciendo clic en un enlace o descargando un archivo), documente cada paso que tomó después de la interacción.

#### Información adicional

1. <a name="phishing-playbook-ref-1"></a>[Protección contra Phishing](https://learn.microsoft.com/es-es/microsoft-365/security/office-365-security/anti-phishing-protection-about?view=o365-worldwide)
1. <a name="phisphing-playbook-ref-2"></a>[Formación en concienciación sobre seguridad y simulaciones de phishing](https://www.knowbe4.com/phishing)
1. <a name="phishing-playbook-ref-3"></a>[Los ejemplos más comunes de correos de Phishing](https://blog.usecure.io/es/the-most-common-examples-of-a-phishing-email) 
1. <a name="phishing-playbook-ref-4"></a>[Mejores prácticas contra el Phishing](https://www.delfossistemas.com/mejores-practicas-contra-el-phishing/)

## Playbook: Ransomware

**Investigar, remediar (contener, erradicar) y comunicar en paralelo. La contención es fundamental en los incidentes de ransomware, priorice en consecuencia.**

### Investigación

**Determinar el tipo de ransomware:**
- Equipo asignado: Equipo de Análisis de Malware.
- Estrategia: Utilizar herramientas avanzadas de análisis de malware para identificar la familia, variante o tipo específico de ransomware involucrado en el incidente. Analizar firmas, comportamiento y características únicas del malware.

**Analizar mensajes relacionados:**
- Equipo asignado: Equipo de Análisis de Mensajes.
- Estrategia: Revisar detenidamente todos los mensajes relacionados con el ransomware, incluyendo interfaces gráficas, archivos de texto/html, mensajes de voz, etc. Identificar patrones de lenguaje, contactos de correo electrónico, instrucciones de rescate y cualquier otra información relevante.

**Examinar archivos afectados:**
- Equipo asignado: Equipo de Análisis de Archivos.
- Estrategia: Investigar a fondo los archivos afectados por el ransomware. Analizar el esquema de cambio de nombre de los archivos encriptados, tipos de archivos afectados, iconos de archivos, etc. Determinar la extensión de la encriptación y evaluar la posibilidad de recuperación de datos.

- Comprobad:
  * Corrupción de archivos frente a encriptación
  * Tipos de archivos y ubicaciones
  * Usuario/grupo propietario de los archivos que son afectados
  * Icono de los archivos encriptados
  * Marcadores de archivos
 
**Determinar el alcance:**
- Equipo asignado: Equipo de Investigación de Alcance.
- Estrategia: Identificar el alcance total del incidente de ransomware. Determinar qué sistemas están afectados, identificar indicadores de compromiso (IOC), evaluar la sensibilidad de los datos comprometidos y encontrar el vector de infección utilizado por el atacante.

1. Evaluación del Impacto: Priorización y Justificación de Recursos
**Evaluación del Impacto Operacional y Económico:**
- Estima las pérdidas económicas potenciales y el riesgo financiero.
- Identifica operaciones críticas afectadas y misiones comprometidas.
- Calcula el costo de la interrupción del negocio, incluyendo la pérdida de productividad y el impacto en las relaciones con clientes y socios.

**Evaluación del Impacto en los Datos:**
- Valora la criticidad de los datos afectados para las operaciones de la empresa o la misión.
- Determina la sensibilidad de los datos comprometidos (por ejemplo, información confidencial, secretos comerciales).
- Analiza las implicaciones legales y de cumplimiento asociadas con los datos afectados (por ejemplo, GDPR para datos personales, HIPAA para información de salud).

2. Identificación del Vector de Infección:
Para localizar cómo se introdujo el ransomware, consulta las tácticas de "Acceso Inicial" en el marco de MITRE ATT&CK. Es crucial revisar las siguientes fuentes de información:

**Adjuntos de Correo Electrónico:**
- Examina los registros de correo electrónico para identificar mensajes sospechosos.
- Utiliza dispositivos y servicios de seguridad de correo electrónico para detectar amenazas.
- Emplea herramientas de descubrimiento electrónico para buscar pruebas de phishing o malware en comunicaciones.

**Protocolo de Escritorio Remoto (RDP) Inseguro:**
- Revisa los resultados de escaneos de vulnerabilidades que puedan indicar exposiciones de RDP.
- Verifica las configuraciones de firewall para detectar reglas permisivas que puedan haber sido explotadas.

**Auto-propagación (Gusano o Virus):**
- Analiza la telemetría del host y los datos del Endpoint Detection and Response (EDR) para rastrear movimientos laterales o signos de auto-propagación.
- Consulta los registros del sistema y realiza análisis forenses para identificar mecanismos de propagación.

**Relación de matrices de ataque MITRE ATT&CK** <br>
- MITRE ATT&CK: T1140 - Deobfuscate/Decode Files or Information puede ser relevante para comprender los mensajes codificados o ofuscados por el ransomware, incluyendo las notas de rescate o las instrucciones de pago.
- Para Adjuntos de Correo Electrónico, T1566 - Spearphishing Attachment es relevante, indicando el uso de correos electrónicos maliciosos como vector de infección.
- En el caso de RDP Inseguro, T1133 - External Remote Services muestra cómo los servicios remotos expuestos pueden ser explotados para ganar acceso.

**Relación de matrices de defensa RE&CT**
- Attribution se enfoca en identificar patrones de lenguaje, contactos de correo electrónico y otras pistas dentro de los mensajes relacionados que pueden ayudar a atribuir el ataque a ciertos actores de amenazas o campañas específicas.
- Detect y Prevent son las acciones correspondientes, centradas en la detección temprana de vectores de infección y la implementación de medidas preventivas como la segmentación de red, la mejora de la seguridad del correo electrónico y la restricción de accesos remotos no seguros.

### Remediar

**Planificar eventos de remediación** en los que estos pasos se lancen juntos (o de forma coordinada), con los equipos apropiados listos para responder a cualquier interrupción.
**Considere el momento y las compensaciones** de las acciones de reparación: su respuesta tiene consecuencias.

### Contención

**Poner en cuarentena sistemas infectados:**
- Equipo asignado: Equipo de Seguridad de Red.
- Estrategia: Implementar medidas de cuarentena para aislar los sistemas infectados y evitar la propagación del ransomware a través de la red. Desconectar los sistemas comprometidos de la red corporativa y bloquear el tráfico malicioso.

**Bloquear dominios y direcciones de comando y control:**
- Equipo asignado: Equipo de Seguridad de Red.
- Estrategia: Utilizar firewalls, sistemas de detección de intrusiones y listas negras de dominios para bloquear el acceso a los servidores de comando y control utilizados por el ransomware. Prevenir cualquier comunicación saliente hacia direcciones maliciosas.

**Erradicación:** 
- Reconstruir sistemas infectados
- Equipo asignado: Equipo de Infraestructura de TI.
- Estrategia: Restaurar los sistemas afectados desde copias de seguridad verificadas y limpias. Reinstalar sistemas operativos y aplicaciones si es necesario. Implementar medidas de seguridad adicionales para prevenir futuros ataques.

**Relación de matrices de ataque MITRE ATT&CK** <br>
- T1562.004 - Impair Defenses: Disable or Modify System Firewall: Los atacantes podrían intentar deshabilitar los firewalls. La contención efectiva puede requerir asegurar y posiblemente modificar la configuración del firewall para aislar sistemas infectados.
- T1571 - Non-Standard Port: Para la contención, es crucial bloquear el tráfico malicioso, lo que puede incluir el tráfico a través de puertos no estándar utilizados por el ransomware.

**Relación de matrices de defensa RE&CT**
- Aislar: Implementar medidas de cuarentena para aislar los sistemas infectados es clave para prevenir la propagación. Esto puede incluir desconectar física o lógicamente los sistemas de la red.
- Bloquear Comunicaciones: Utilizar firewalls y otros dispositivos de seguridad para bloquear el tráfico malicioso hacia y desde los sistemas comprometidos.

### Erradicar

**Reconstrucción de Sistemas Infectados:**
- Acción: Reconstruir los sistemas afectados utilizando fuentes confiables y limpias.
- Responsable: Equipo de Infraestructura de TI.
- Descripción: Restaurar los sistemas comprometidos utilizando imágenes o medios de instalación confiables y verificados.

**Restauración desde Copias de Seguridad:**
- Acción: Restaurar los sistemas desde copias de seguridad conocidas y sin compromisos.
- Responsable: Equipo de Gestión de Respaldo y Recuperación.
- Descripción: Utilizar copias de seguridad verificadas y limpias para restaurar los datos y sistemas afectados por el ransomware.

**Actualización y Activación de Protección de Puntos Finales:**
- Acción: Confirmar y activar la protección de puntos finales en todos los sistemas.
- Responsable: Equipo de Seguridad de TI.
- Descripción: Verificar que las soluciones de seguridad, como antivirus (AV), Next-Generation Antivirus (NGAV), y Detección y Respuesta de Endpoint (EDR), estén actualizadas y activadas en todos los sistemas afectados.

**Despliegue de Parches:**
- Acción: Desplegar parches en todos los sistemas, priorizando según la criticidad.
- Responsable: Equipo de Gestión de Parches.
- Descripción: Asegurar que todos los sistemas estén actualizados con los últimos parches de seguridad para cerrar posibles vulnerabilidades explotadas por el ransomware.

**Despliegue de Firmas Personalizadas:**
- Acción: Implementar firmas personalizadas en las herramientas de seguridad basadas en IOC descubiertos.
- Responsable: Equipo de Seguridad de Red y Endpoint.
- Descripción: Desarrollar y desplegar firmas específicas para detectar y prevenir futuros ataques de ransomware basándose en los indicadores de compromiso (IOC) identificados durante la investigación.

**Vigilancia de Reinfección:**
- Acción: Monitorear y aumentar la prioridad de las alarmas relacionadas con posibles reinfecciones.
- Responsable: Equipo de Monitoreo de Seguridad.
- Descripción: Mantener una vigilancia continua sobre los sistemas y redes para detectar cualquier signo de actividad maliciosa relacionada con el incidente de ransomware. Incrementar la prioridad de las alertas para una respuesta más rápida ante posibles intentos de reinfección.

**Relación de matrices de ataque MITRE ATT&CK** <br>
- T1490 - Inhibit System Recovery: La restauración de sistemas desde copias de seguridad es una táctica directa para contrarrestar los intentos de los atacantes de prevenir la recuperación del sistema.
- T1562.001 - Impair Defenses: Disable or Modify Tools: La actualización y activación de la protección de puntos finales es una medida para contrarrestar esta técnica, asegurando que las defensas estén operativas y actualizadas

**Relación de matrices de defensa RE&CT**
- Restore (Restaurar): La restauración de sistemas a partir de copias de seguridad se alinea con la acción de Recover en RE&CT, donde el enfoque está en recuperar los sistemas y datos afectados para volver a un estado operativo normal.
- RE&CT: Harden (Endurecer): La actualización de soluciones de seguridad y la implementación de protecciones adecuadas pueden considerarse como acciones de Harden, donde se refuerzan las defensas para prevenir reinfecciones o nuevos ataques.

### Comunicar

**No pagar el rescate y activar un plan de continuidad de negocio:**
- Equipo asignado: Equipo de Gestión de Crisis.
- Estrategia: Comunicar claramente la política de la organización de no pagar rescates y activar un plan de continuidad de negocio para mitigar el impacto del ransomware en las operaciones comerciales. Informar a todas las partes interesadas sobre los pasos a seguir y las medidas de contingencia implementadas.

**Recuperación de datos y consideraciones legales:**
- Equipo asignado: Equipo de Gestión Legal y de Cumplimiento.
- Estrategia: Coordinar la recuperación de datos de las copias de seguridad verificadas y limpias. Evaluar las implicaciones legales, regulatorias y financieras del incidente de ransomware. Colaborar con las autoridades pertinentes y cumplir con los requisitos de notificación de violación de datos según sea necesario.

**Relación de matrices de ataque MITRE ATT&CK** <br>
- T1562.001 - **Impair Defenses: Disable or Modify Tools:** Aunque esta técnica se centra en cómo los atacantes pueden intentar deshabilitar las defensas, la acción de evaluar las implicaciones legales y cumplir con los requisitos regulatorios refuerza indirectamente la necesidad de tener defensas robustas y procedimientos de cumplimiento en su lugar.

**Relación de matrices de defensa RE&CT**
- **RE&CT: Harden (Endurecer):** La coordinación de la recuperación de datos y la evaluación de implicaciones legales también se ven como parte de este proceso. Aquí, el enfoque se amplía para incluir la protección legal y regulatoria de la organización, asegurando que las respuestas al incidente no solo sean técnicamente sólidas sino también legalmente defensibles.

### Recursos

#### Referencia: Acciones de los usuarios ante la sospecha de ransomware

1. **Mantén la Serenidad:** Respire hondo y mantén la calma para pensar con claridad.
   
2. **Aísla tu Equipo:** Desconecta inmediatamente tu computadora de cualquier red para evitar la propagación del ransomware.

3. **Documenta Evidencias:** Utiliza tu teléfono móvil para tomar fotografías de tu pantalla, capturando cualquier mensaje sospechoso, archivos que parezcan estar cifrados, y errores del sistema que observes.

4. **Registra Detalles del Incidente:** Aprovecha la grabadora de voz de tu móvil o usa papel y lápiz para anotar todos los detalles relevantes sobre el incidente.
Esto incluye:
 * Las irregularidades que notaste.
 * Razones por las que te pareció un problema.
 * Actividades que estabas realizando al momento del descubrimiento.
 * Momento exacto o aproximado del primer indicio y frecuencia de los mismos desde entonces.
 * Ubicación y red en uso al momento del incidente (por ejemplo, en casa, en la oficina, usando red alámbrica o inalámbrica, con o sin VPN).
 * Sistemas afectados (por ejemplo, sistema operativo y nombre de host).
 * Cuenta de usuario afectada.
 * Tipo de datos a los que comúnmente se accede.
 * Personas con las que se ha discutido el incidente y los detalles compartidos.

5. **Comunícate con el Soporte Técnico:** Informa al help desk de la situación. Utiliza el enlace provisto para contactar al recurso correspondiente y ofrece toda la información posible para asistir en la resolución del problema.

6. **Paciencia y Colaboración:** La respuesta y solución pueden requerir tiempo y ser complejas. Tu paciencia y cooperación son cruciales para proteger los activos y la seguridad de la organización. Agradecemos tu apoyo.

#### Información adicional

1. <a name="ransomware-playbook-ref-2"></a>[No More Ransom!](https://www.nomoreransom.org/es/index.html)
1. <a name="ransomware-playbook-ref-3"></a>[Identificación de Ransomware](https://latam.kaspersky.com/resource-center/threats/ransomware-attacks-and-types)
1. <a name="ransomware-playbook-ref-4"></a>[MITRE ATT&CK Matrix](https://attack.mitre.org)
# Roles

A continuación se presentan las descripciones, los deberes y la formación para cada uno de los roles definidos en la respuesta a un incidente.

## Estructura de los roles

* Equipo de Mando
  * [Incident Commander](#rol-incident-commander)
  * [Incident Commander-Adjunto](#rol-delegado-del-incident-commander-subdelegado)
  * [Escriba](#rol-escriba)
* Equipo de enlace
  * Enlace Interno [Enlace](#rol-enlace)
  * Enlace externo
* Equipo de Operaciones
  * [Expertos en la materia](#rol-experto-en-la-materia-subject-matter-expert-sme) (SMEs) para Sistemas
  * SMEs para equipos/unidades de negocio
  * SMEs para las funciones ejecutivas (_p.ej._, Legal, RRHH, Finanzas)
En el caso de incidentes complejos de mayor envergadura, la estructura de funciones puede ajustarse para tener en cuenta la creación de subequipos. Para más información, lea cómo gestionamos los [Incidentes Complejos](/before/complex_incidents.md).

Esta es una **estructura flexible**: cada rol no será ocupado por una persona diferente para cada incidente. Por ejemplo, en un incidente pequeño, el adjunto podría actuar como escribiente y enlace interno. La estructura es flexible y se adapta al incidente.

## Tiempos de Guerra vs. Tiempos de Paz

En las llamadas de respuesta a Incidentes ("tiempos de guerra"), una estructura organizativa diferente anula las operaciones normales ("tiempos de paz"):

* El Comandante del incidente está al mando. Independientemente de su rango en tiempos de paz, ahora es la persona de mayor rango en la llamada, superior al director general o CEO.
* Los primeros intervinientes (las personas que actúan como primeros intervinientes de un equipo/servicio) son las personas de mayor rango de ese servicio.
* Las decisiones serán tomadas por el IC tras considerar la información presentada. Una vez tomada la decisión, es definitiva.
* El IC puede tomar decisiones más arriesgadas que las que normalmente se considerarían en tiempos de paz.
* El IC puede ir en contra de una decisión consensuada. Si se hace una encuesta, y 9/10 personas están de acuerdo pero 1 está en desacuerdo. El IC puede elegir la opción del desacuerdo a pesar del voto de la mayoría. Aunque no esté de acuerdo, la decisión del IC es definitiva. Durante la convocatoria no es el momento de discutir con ellos.
* El IC puede utilizar un lenguaje o comportarse de una manera que usted considere grosera. Esto es tiempo de guerra, y necesitan hacer lo que sea necesario para resolver la situación, por lo que a veces se producen groserías. Esto no es personal, y es algo que debes estar preparado para experimentar si nunca has estado en una situación de guerra.
* Es posible que el IC te pida que abandones la llamada, o incluso que te eche a la fuerza de una llamada. Esto queda a discreción del IC si considera que no estás aportando nada útil. De nuevo, esto no es personal y debes recordar que los tiempo de guerra son diferentes a los tiempo de paz.

## Roles: Todos los participantes

### Descripción

Todos los participantes en la respuesta a un incidente tienen la responsabilidad de ayudar a resolver el incidente de acuerdo con el plan de respuesta a incidentes, bajo la autoridad del Incident Commander.

### Deberes

#### Exhibir la etiqueta de la llamada

* Participar tanto en la llamada como en el chat.
* Mantener el ruido de fondo al mínimo.
* Mantener el micrófono silenciado hasta que tenga algo que decir.
* Identifícarse cuando entre en la llamada; diga su nombre y su función (por ejemplo, "Soy el SME del equipo x").
* Hablar con claridad.
* Ser directo y objetivo.
* Mantener las conversaciones/debates breves y al grano.
* Comunicar cualquier preocupación al Incident Commander (IC) en la llamada.
* Respetar las limitaciones de tiempo dadas por el Incident Commander.
* Si te unes a un solo canal (llamada o chat), no participar activamente, ya que provoca una comunicación inconexa.
* **Utilizar una terminología clara y evitar usar acrónimos o abreviaturas. La claridad y la precisión son más importantes que la brevedad.**

##### Referencia: Procedimiento común de voz

El [procedimiento de voz] estándar de la radio (https://en.wikipedia.org/wiki/Voice_procedure#Words_in_voice_procedure) **no es obligatorio**, sin embargo, es posible que escuche ciertos términos (o que tenga que utilizarlos usted mismo). Las frases comunes incluyen:

* **Ack/Rog:** "He recibido y entendido"
* **Say Again:** "Repita su último mensaje"
* **Standby:** "Por favor, espere un momento para la siguiente respuesta"
* **Wilco:** "Cumpliré"

**No** invente nuevas abreviaturas; favorezca ser explícito sobre lo implícito.

#### Seguir al Incident Commander

El Incident Commander (IC) es el líder del proceso de respuesta al incidente.

* Siga las instrucciones del Incident Commander.
* No realice ninguna acción a menos que el Incident Commander se lo indique.
* El jefe normalmente sondeará si hay objeciones fuertes antes de asignar una acción importante. Plantee sus objeciones si las tiene.
* Una vez que el jefe haya tomado una decisión, sígala (incluso si no está de acuerdo).
* Responde a cualquier pregunta que te haga el jefe de forma clara y concisa. Responder "no sé" es aceptable. No adivine.
* El jefe puede pedirte que investigues algo y que le contestes en X minutos. Esté preparado con una respuesta dentro de ese tiempo. Pedir más tiempo es aceptable, pero proporcione al jefe una estimación.

### Capacitación

Lee y entiende el plan de respuesta a incidentes, incluyendo los roles y los libros de jugadas.
## Rol: Incident Commander

### Descripcion
El Incident Commander(IC) actua como la única fuente de lo que realmente está ocurriendo y va a ocurrir durante un incidente grave. El IC es el individuo con mayor rango en cualquier llamada de incidente, sin importar el rango en el dia a dia. Ellos son los que toman decisiones durante un incidente; delegan tareas y prestan atencion a expertos en la materia que están tratando para resolver el incidente. Las decisiones tomadas por el Incident commander las decisivas.

Tu trabajo como Incident commander evaluar la situación, proveer un guiado claro y coordinado, contratar otros trabajadores para recolectar contexto/detalles.**No realizar investigaciones o remedios**, delega estos trabajos.

### Deberes

Resuelve el incidente lo más rápido y seguro posible usando el plan de respuesta de incidentes como plantilla de trabajo: guia al equipo de investigacion, remedio, comunicación. Utiliza al adjunto para que te ayude, y delegue a relevantes enlaces y expertos a tu discreción.

1. Ayuda a prepararos para los incidentes,
    * Establecer canales de comunicación para incidentes.
    * Redirige a las personas hacia estos canales de comunicación cuando acurra algún incidente grave.
    * Entrena a miembros del equipo sobre como comunicarte durante incidentes y entrena a otros Incident Commanders.
1. Dirige los incidentes hacia una solución,
    * Lleva a todos al mismo canal de comunicación.
    * Recolecta información de los miembros del equipo por sus servicios de estatus.
    * Recolecta propuestas de reparación de acciones, después recomienda acciones de reparación para que se lleven a cabo.
    * Delega todas la acciones de reparación, el Incident Commander no es un resolvedor.
    * Es la única fuente de autoridad en el estado del sistema.
1. Facilita las llamadas y reuniones,
    * Gana consenso (Realiza encuestas durante las llamadas)
    * Proporciona actualizaciones de estatus
    * Reduce el alcance (despedir a los asistentes cuando sea posible)
    * Spin off sub-equipos
    * Transfiere el control cuando sea necesario
    * Firmar las llamadas
    * Mantener el orden
    * Obtén respuestas directas
    * Manejar las caídas de ejecutivos como
        * Anular al Incident Commander
        * Desmotivación
        * Petición de información
        * Cuestionar la severidad
    * Manejar respuestas perturbadoras o beligerantes
1. Post Mortem,
    * Crear la plantilla inicial justo después del incidente para que las personas puedan escribir sus opiniones mientras están frescas.
    * Asignar el post-mortem después de que el evento termine, esto puede darse después de terminar la llamada.
    * Trabaja con los gerentes o jefes de equipo para organizar acciones preventivas.

El Incident Commander utiliza métodos y lenguajes adicionales:

* Siempre anuncie cuando se una a la llamada si es el IC de guardia.
* **No** permita que las discusiones se salgan de control. Mantenga las conversaciones cortas.
* Tenga en cuenta las objeciones de los demás, pero tu decision es la definitiva.
* Si alguien está interrumpiendo activamente tu decision, expúlsalo.
* Anuncia el final de la llamada.
* Después de un incidente, comuníquese con otros Incident Commander sobre cualquier acción que considere necesaria.

**Utilice una terminología clara y evite las siglas o abreviaturas. La claridad y la precisión son más importantes que la brevedad.**

### Prácticas

* Lea el plan de respuesta a incidentes, incluidos todos los roles y manuales.
* Participar en un ejercicio de respuesta a incidentes.
* Seguir a un Incident Commander actual sin participar activamente, manteniendo sus preguntas hasta el final.
* Tomar la iniciativa de un Incident Commander. Responda a incidentes con el IC actual allí para hacerse cargo si es necesario.
* _OPCIONAL:_ facilitar las prácticas
* _OPCIONAL:_ recurre a [Incident Responders as Facilitators (and Therapists)](#FIX) y al [PagerDuty Incident Commander training](https://response.pagerduty.com/training/incident_commander/) para mas ideas y discussiones.

#### pre-requisitos

No hay requisitos previos de antigüedad o unidad de negocios para convertirse en Incident Commander, es un rol abierto a cualquier persona con la capacitación y la capacidad. Antes de que pueda ser un Incident Commander, se espera que cumpla con los siguientes criterios:

* Excelentes **habilidades de comunicación** verbal y escrita.
* **Conocimiento de alto nivel** de la infraestructura y las funciones comerciales.
* Excelente pensamiento crítico, juicio y toma de decisiones.
* Flexibilidad y capacidad para **escuchar comentarios de expertos**, modificando los planes según sea necesario.
* **Participó en al menos dos respuestas a incidentes**.
* Capacidad para **tomar el mando** y **disposición para expulsar a las personas de una llamada** para eliminar las distracciones, incluso si se trata del director ejecutivo.

¡No se requieren conocimientos técnicos profundos! Los Incident Commander no requieren un conocimiento técnico profundo de nuestros sistemas. Su trabajo como Incident Commander es coordinar la respuesta, no realizar cambios técnicos. No crea que no puede ser un Incident Commander solo porque no está en el departamento de ingeniería.

#### Graduación

Al finalizar el entrenamiento, agréguese a la lista de Incident Commander.

## Rol: adjunto del Incident Commander (adjunto)

### Descripción

Un adjunto del Incident Commander (adjunto) es un papel de apoyo directo al Incident Commander (IC). El adjunto permite que el IC se centre en el problema que tiene entre manos, en lugar de preocuparse por documentar los pasos o controlar los tiempos. El adjunto apoya al IC y lo mantiene centrado en el incidente.  Como adjunto, se espera que asuma el mando del IC si éste lo solicita.

### Funciones

1. 1. Plantear al Incident Commander cuestiones que, de otro modo, no se abordarían (vigilar los temporizadores que se han puesto en marcha, retomar los elementos que se han perdido de una lista, etc.).
1. 1. Ser un Incident Commander "de reserva", en caso de que el jefe principal tenga que hacer la transición a un SME, o tenga que alejarse de la función de IC.
1. 1. Gestionar la llamada del incidente y estar preparado para retirar a las personas de la llamada si así lo indica el Incident Commander.
1. Supervisar el estado del incidente y notificar al IC si el nivel de gravedad del incidente aumenta.
1. Supervise los temporizadores:
    * controlar el tiempo que ha durado el incidente
    * Notificar al IC cada X minutos para que pueda tomar medidas (por ejemplo, "IC, el incidente está ahora en la marca de 10 minutos").
1. Supervisar los plazos de las tareas (_p.ej._, "IC, avisa de que el temporizador de la investigación de [TEAM] se ha agotado").

### Formación

* Leer y comprender el plan de respuesta a incidentes, incluyendo los roles y los libros de jugadas.

#### Requisitos previos

* Estar entrenado como [Incident Commander](#role-incident-commander-ic).

Traducción realizada con la versión gratuita del traductor www.DeepL.com/Translator

## Rol: Escriba

### Descripción

Un escriba documenta la línea de tiempo de un incidente a medida que avanza, y se asegura de que todas las decisiones y datos importantes se capturen para su posterior revisión.  El escriba debe centrarse en el archivo del incidente, así como en los elementos de seguimiento para una acción posterior.

### Funciones

1. Asegurarse de que la llamada del incidente se está grabando.
1. 2. Anotar en el chat y en la línea de tiempo del expediente: los datos, eventos y acciones importantes, a medida que se producen. Específicamente:
    * Acciones clave a medida que se llevan a cabo
    * Informes de estado cuando el IC los proporcione
    * Cualquier llamada clave durante la llamada o en la revisión final
1. Actualice el chat indicando quién es el IC, quién es el adjunto y que usted es el escribiente (si no lo ha hecho ya).

Escribir es más un arte que una ciencia. El objetivo es mantener un registro preciso de los eventos importantes que ocurrieron, Usa tu juicio y experiencia. Pero aquí hay algunas cosas generales que definitivamente querrás capturar como escribiente.

* El resultado de cualquier decisión de la votación.
### Cualquier elemento de seguimiento que se llame "Deberíamos hacer esto..", "¿Por qué no se hizo esto?", etc.

### Formación

Lea y comprenda el plan de respuesta a incidentes, incluyendo los roles y los libros de jugadas.

#### Requisitos previos

* Excelentes habilidades de **comunicación verbal y escrita**.
* Cualquiera puede actuar como escribiente durante un incidente, y son elegidos por el Incident Commander al inicio de la llamada.
* Normalmente, el ayudante actuará como escribiente.

#### Proceso de formación

* Lea el plan de respuesta a incidentes, incluyendo todos los roles y libros de jugadas.
* _OPCIONAL:_ Paralizar las acciones de un escriba durante un incidente o ejercicio, y buscar la opinión del escriba real y del Incident Commander.


## Rol: Experto en la materia {Subject Matter Expert (SME)}

### Descripción

Un experto en la materia (SME) es un experto en el dominio o responsable designado de un equipo, componente o servicio (un "área"). Está ahí para apoyar al Incident Commander en la identificación de la causa del incidente, sugiriendo y evaluando las acciones de investigación, remediación y comunicación, y realizando el seguimiento de las mismas según se le encomiende.

### Funciones

1. Diagnosticar problemas comunes dentro de su área de experiencia.
1. Solucionar rápidamente los problemas detectados durante un incidente.
1. Comunicación concisa:
    * Estado: ¿Cuál es el estado actual de su área? ¿Está buen estado o no?
    * Acciones: ¿Qué medidas hay que tomar si su zona no se encuentra en un buen estado?
    * Necesidades: ¿Qué apoyo necesita para realizar una acción?
1. Participar en las fases de investigación, remediación y/o comunicación de la respuesta.
1. Anunciar todas las sugerencias al comandante del incidente, es su decisión cómo proceder, no siga ninguna acción a menos que se le indique.

Si está de guardia para cualquier equipo, puede ser llamado para un incidente y se espera que responda como experto en la materia (SME) para su equipo, componente o servicio. Cualquiera que se considere un "experto en la materia" puede actuar como SME para un incidente. Por lo general, el principal de guardia del equipo actuará como SME para ese equipo.


#### Prepárese para el periodo de guardia

1. Esté preparado, habiéndose familiarizado ya con nuestras políticas y procedimientos de respuesta a incidentes.
1. Asegúrese de que ha configurado sus métodos de alerta de acuerdo con nuestro procedimiento de guardia.
1. Compruebe que puede unirse a la llamada de incidentes. Es posible que tenga que instalar un plugin para el navegador.
1. Tenga en cuenta su próxima vez de guardia y organice los cambios en función de los viajes, las vacaciones, las citas, etc.
1. Si usted es el Incident Commander, asegúrese de no estar de guardia con su equipo al mismo tiempo que está de guardia como Incident Commander.

#### Durante el periodo de guardia

1. Tenga su ordenador portátil e Internet con usted en todo momento durante su período de guardia (oficina, casa, un MiFi, un teléfono con un plan de conexión, etc).
1. Si tiene citas importantes, debe conseguir que otra persona de su equipo cubra esa franja horaria con antelación.
1. Cuando recibas una alerta de incidente, se espera que te unas a la llamada de incidente y chatees lo antes posible (en cuestión de minutos).
1. El Incident Commander le hará preguntas o le dará acciones. Responde a las preguntas de forma concisa y sigue todas las acciones que se te den (incluso si no estás de acuerdo con ellas).
1. Si no estás seguro de algo, haz venir a otros miembros de tu equipo que puedan ayudarte. **Nunca dudes en escalar**, si es necesario.  
1. No culpes. Este proceso de respuesta a incidentes no tiene ninguna culpa: culpar es contraproducente y distrae del problema en cuestión. La revisión posterior a la acción identificará los puntos en los que todos podemos mejorar.

### Formación

* Lea y comprenda el plan de respuesta a incidentes, incluidas las funciones y las guías de actuación.

## Rol: Enlace

### Descripción

Los enlaces interactuan con otros equipos o partes interesadas fuera del equipo de respuesta a incidentes. A menudo incluyen:

* Enlace externo: responsable de interactuar con clientes, ya sea directamente o por vía pública.
* Enlace interno: responsable de interactuar con las partes interesadas internas. Tanto si se trata de notificar un incidente al equipo interno como al movilizar respuestas adicionales dentro de la organización.

### Deberes

#### Enlace con el exterior o con el cliente

1. Subir cualquier mensaje de cara al público con respecto al incidente (Twitter, etc).
1. Notificar al IC de cualquier cliente o medios de comunicación que informen de los efectos del incidente.
1. Proporcionar a los clientes el mensaje externo del post-mortem una vez que se haya completado.
1. Contactar o interactuar con las partes interesadas externas, como proveedores, socios, fuerzas de seguridad, _etc._
1. **No** sentirse responsable de la creación de cada mensaje: trabajar con el Incident Commander y otras partes interesadas.
1. Según proceda, mantener a los clientes informados durante un incidente.
1. Actuar como voz de nuestros clientes ante el Incident Commander, ya que esto es útil para la toma de decisiones del IC.
1. Obtener la aprobación del mensaje después de haber elaborado el mensaje público: copiar el mensaje en el chat y esperar la confirmación verbal/escrita del IC antes de continuar.

##### Pistas para mensajes públicos

* Preparar de antemano un mensaje por defecto que pueda utilizarse para la actualización inicial si se desconoce el alcance del problema.
* Sé honesto. No mientas o supongas.
* Describa nuestros progresos en la resolución del incidente.
  * _"Somos conscientes de un incidente..."_
  * _"Estamos investigando los retrasos en las notificaciones..."_
  * _"Se ha aplicado una corrección y se está desplegando actualmente..."_
  * _"El problema ha sido resuelto..."_
* Explique claramente cómo afecta el incidente a los clientes. Esta es la principal información que les interesa a los clientes.
* Proporcionar soluciones que los clientes puedan utilizar hasta que se resuelva la incidencia.
* No calcule los tiempos de resolución.
* Proporcionar el nivel de detalle adecuado.

#### Enlace interno

1. Página de SMEs u otro personal de guardia según las instrucciones del Incident Commander.
1. Notificar o movilizar a otros equipos de la organización (por ejemplo, Finanzas, Legal, Marketing), según las instrucciones del Incident Commander.
1. Seguir y anticiparse a los SMEs en la convocatoria.
1. Interactuar con las partes interesadas y proporcionar actualizaciones de estado cuando sea necesario.
1. Interactuar con las partes interesadas internas para responder a sus preguntas, para mantener la llamada principal libre de distracciones.
1. Proporcionar actualizaciones periódicas de la situación al equipo ejecutivo, ofreciendo un resumen ejecutivo de la situación actual.

### Formación

Leer y comprender el plan de respuesta a incidentes, incluyendo los roles y las guías.

#### Prerequisitos

* Excelentes **habilidades de comunicación** verbal y escrita.
* _OPCIONAL:_ Formación en atención al cliente.
* _OPCIONAL:_ Comunicación corporativa o formación en marketing.

# Realizar una revisión posterior a la acción (Conduct an After Action Review, AAR)

1. Programe una reunión de revisión posterior a la acción (AAR) dentro de 5 días laborales e invite a los asistentes que figuran en ir.ciberseguros.es/aar/attendees. Incluya siempre a los siguientes:
    * El Incident Commander.
    * Los propietarios de los servicios implicados en el incidente.
    * Ingeniero(s)/responsable(s) clave(s) implicado(s) en el incidente.
1. Designe a un propietario del AAR que investigue el incidente antes de la reunión para prepararlo, estudiando el proceso del incidente en sí, incluyendo la revisión de notas e informes.

## Realización de la reunión AAR

Documente las respuestas a las siguientes preguntas clave:

1. **¿Qué ocurrió?** Cree una línea de tiempo, apoyada con datos u otros artefactos. **Evitar las culpas. Busca los hechos.**
1. **¿Qué se suponía que iba a ocurrir?**
    * Detallar las desviaciones del proceso, el procedimiento o las mejores prácticas, incluidas las evaluaciones de los SME.
    * Identifique las formas en que el incidente podría haberse detectado antes o haberse respondido con mayor eficacia.
1. **¿Cuáles fueron las causas fundamentales?** Encuentre la raíz de lo que ocurrió y de lo que debería haber ocurrido.
1. **¿Cómo podemos mejorar?**  Capture los elementos de acción con asignados y fechas de vencimiento. Considerar:
    * Detener: ¿Qué debemos dejar de hacer?
    * Empezar: ¿Qué deberíamos empezar a hacer?
    * Continuar: ¿Qué debemos seguir haciendo?

## Comunicar el estado y los resultados del AAR

El propietario del informe, en coordinación con el enlace interno, comunicará el estado del informe (véase más abajo).

### Descripciones de estado

| Estado          | Descripción                                                                                                                                                                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Borrador**    | La investigación de la AAR sigue en curso                                                                                                                                                                                                                                                                                |
| **En revisión** | La investigación AAR se ha completado, y está lista para ser revisada durante la reunión AAR.                                                                                                                                                                                                                            |
| **Revisado**    | La reunión de AAR ha terminado y el contenido ha sido revisado y acordado. <br/>Si hay "Mensajes externos" adicionales, el equipo de comunicación tomará medidas para prepararlos.                                                                                                                                            |
| **Cerrado**     | No es necesario realizar más acciones en el AAR (los problemas pendientes se rastrean en los tickets).<br>Si no hay "Mensajes Externos", pase directamente a esto una vez que la reunión haya terminado.<br/>Si hay "Mensajes Externos" adicionales, el equipo de comunicaciones actualizará el AAR Cerrado una vez enviado. |

Comunicar internamente los resultados del AAR y finalizar la documentación del AAR.

# Acerca de

Esta plantilla ha sido creada por el equipo de [Counteractive Security](https://www.counteractive.net), para ayudar a todas las organizaciones a comenzar de forma concisa, directa, especifica, flexible y gratuita un plan de respuesta de incidentes. crea un plan [que utilizaras](https://www.counteractive.net/posts/an-ir-plan-you-will-use/) para responder de manera eficiente, minimizando los costes e impactos, para volver a trabajar lo mas rapido posible.


## Licencia

Esta plantilla esta proporcionado bajo la licencia de apache, version 2.0. puedes ver el codigo fuente en https://github.com/counteractive.


## Instrucciones

Personaliza esta plantilla para tu organizacion. Las instrucciones estan disponibles en el [README](https://github.com/counteractive) del projecto. Para asistencia profesional con respuestas de incidentes, o con customizacion, implementacion, o testeo de tu plan, porfavor contacta con nosotros por [email](mailto:support@counteractive.net) o [telefono](tel:+18889255765).


## Referencias y material adicional

* [NIST Computer Security Incident Handling Guide](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf) (NIST)
* [CERT Societe Generale Incident Response Methodologies](https://github.com/certsocietegenerale/IRM/tree/master/EN)
* [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)
* [Incident Handler's Handbook](https://www.sans.org/reading-room/whitepapers/incident/incident-handlers-handbook-33901) (SANS)
* [Responding to IT Security Incidents](https://technet.microsoft.com/en-us/library/cc700825.aspx) (Microsoft)
* [Defining Incident Management Processes for CSIRTs: A Work in Progress](http://resources.sei.cmu.edu/library/asset-view.cfm?assetid=7153) (CMU)
* [Creating and Managing Computer Security Incident Handling Teams (CSIRTS)](https://www.first.org/conference/2008/papers/killcrece-georgia-slides.pdf) (CERT)
* [Incident Management for Operations](http://shop.oreilly.com/product/0636920036159.do) (Rob Schnepp, Ron Vidal, Chris Hawley)
* [_Incident Response & Computer Forensics, Third Edition_](http://a.co/cUkFzMh) (Jason Luttgens. Matthew Pepe. Kevin Mandia)
* [_Incident Response_](http://shop.oreilly.com/product/9780596001308.do) (Kenneth R. van Wyk, Richard Forno)
* [The Checklist Manifesto](http://atulgawande.com/book/the-checklist-manifesto/) (Atul Gawande)
* [The Field Guide to Understanding Human Error](https://www.amazon.com/Field-Guide-Understanding-Human-Error/dp/0754648265) (Sidney Dekker)
* [Normal Accidents: Living with High-Risk Technologies](https://www.amazon.com/Normal-Accidents-Living-High-Risk-Technologies/dp/0691004129) (Charles Perrow)
* [Site Reliability Engineering](https://landing.google.com/sre/book.html) (Google)
* [Debriefing Facilitation Guide](http://extfiles.etsy.com/DebriefingFacilitationGuide.pdf) (Etsy)
* [Every Minute Counts: Leading Heroku's Incident Response](https://www.heavybit.com/library/video/every-minute-counts-coordinating-herokus-incident-response/) (Blake Gentry)
* [Three Analytical Traps in Accident Investigation](https://www.youtube.com/watch?v=TqaFT-0cY7U) (Dr. Johan Bergström)
* [US National Incident Management System (NIMS)](https://www.fema.gov/national-incident-management-system) (FEMA)
* [Informed's NIMS Incident Command System Field Guide](https://www.amazon.com/gp/product/1284038408) (Michael J. Ward)
* [Advanced PostMortem Fu and Human Error 101 (Velocity 2011)](http://www.slideshare.net/jallspaw/advanced-postmortem-fu-and-human-error-101-velocity-2011)
* [Blame. Language. Sharing.](http://fractio.nl/2015/10/30/blame-language-sharing/)

