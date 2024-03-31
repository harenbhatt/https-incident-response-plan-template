# Indice
1. [Introducción](#introducción)
2. [Plan de respuesta](#plan-de-respuesta)
3. [Playbooks](#playbooks)
4. [Respuesta a las preguntas](#respuesta-a-las-preguntas)
5. [Conclusiones](#conclusiones)
6. [Bibliografía](#bibliografía)

# Introducción

# Plan de respuesta

Este enlace lleva al plan de respuesta generado.

[Plan de respuesta](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/blob/2024-4.1-G3/plan.md)

# Playbooks

En este punto indicamos con enlaces los playbooks que hemos generado para nuestro plan de respuesta.

1. [playbook-Create-or-Modify-System-Procces](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/blob/2024-4.1-G3/playbooks/playbook-Create-or-Modify-System-Process.md)
2. [playbook-DDoS](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/blob/2024-4.1-G3/playbooks/playbook-DDoS.md)
3. [playbook-DoS](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/blob/2024-4.1-G3/playbooks/playbook-DoS.md)
4. [playbook-Identity-and-Access](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/blob/2024-4.1-G3/playbooks/playbook-Identity-and-Access.md)
5. [playbook-Supply-Chain](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/blob/2024-4.1-G3/playbooks/playbook-Supply-Chain.md)
6. [playbook-Wipe-Disk](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/blob/2024-4.1-G3/playbooks/playbook-Wipe-Disk.md)
7. [playbook-Credentials-from-Password-Stores](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/blob/2024-4.1-G3/playbooks/playbook-credentials%20from%20password%20stores.md)
8. [playbook-Defacement](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/blob/2024-4.1-G3/playbooks/playbook-defacement.md)
9. [playbook-Phishing](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/blob/2024-4.1-G3/playbooks/playbook-phishing.md)
10. [playbook-Ransonware](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/blob/2024-4.1-G3/playbooks/playbook-ransomware.md)
11. [playbook-Replication-Through-Removable-Media](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/blob/2024-4.1-G3/playbooks/playbook-replication%20through%20removable%20media.md)
12. [playbook-Steal-Web-Session-Cookie](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/blob/2024-4.1-G3/playbooks/playbook-steal-web-session-cookie.md)
13. [playbook-Brute-Force](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/blob/2024-4.1-G3/playbooks/playbook-brute%20force.md)

# Respuesta a las preguntas

### 1.a   ¿Que relación existe entre el trabajo que has hecho con las matrices MITRE ATT&CK y RE&CT y el plan de respuesta que estás planteando? ¿De que manera te ha ayudado el trabajo previo sobre las matrices a la hora de generar el plan? Deja evidencias del trabajo que has realizado sobre le navigator de las matrices, para obtener la información. 

La existencia y el uso de las matrices MITRE ATT&CK y RE&CT ha influido mucho en el desarrollo de nuestro plan de respuesta ya que guía y nos indica tanto los posibles caminos que debemos atender como las acciones que ejecutar. Nos ha proporcionado _raíles_ para construir el plan de una forma mucho más organizada y coherente.

Mediante la matriz MITRE ATT&CK, se puede comprender tanto el posible flujo de trabajo de nuestro posible atacante como sus técnicas concretas. 

Conociendo esto, podemos evaluar nuestra postura de seguridad al comparar las tácticas y técnicas identificadas por los adversarios con nuestros propios controles de seguridad. Esto nos permite identificar posibles brechas en nuestra defensa y áreas donde podríamos mejorar nuestra seguridad.

Por ejemplo, en este caso se ha utilizado la matriz para intentar recrear el posible flujo de ataque con respecto a un DDoS, qué sería necesario y qué no, optimizando así nuestra estrategia y respuesta al focalizarla en los puntos que vienen tan bien detalladas en la matriz.

![Alt text](/imagenes/attack.png)

Además conociendo cada parte concreta, MITRE aporta una sección personalizada de cada posible método de ataque que podemos consultar para obtener información más detallada sobre el ataque al que nos enfrentamos:

![Alt text](/imagenes/attack2.png)

Luego, con respecto a la matriz RE&CT, nos da una información mucho más directa que la matriz de ATT&CK, ya que directamente nos informa de todas las medidas que tendríamos que tomar. 

RE&CT además clasifica por fases de la respuesta, por lo que, siguiendo el ejemplo del ataque DDoS, si quisiera saber que hacer para contenerlo, nos iríamos a la fase de _Containment_ y ya tendríamos una serie de indicaciones para reaccionar directamente en esta fase:

![Alt text](/imagenes/react.png)

Esto nos ha ayudado en gran medida a diseñar nuestros playbooks por ejemplo, para tomar medidas y respuestas concretas a escenarios específicos de una manera mucho más sencilla y directa.

### 1.b   ¿Qué playbooks has identificado como necesarios en este plan de respuesta y en que te has basado para identificar esos playbooks y saber que son los necesarios? Deja algún diagrama que describa el flujo de un playbook.

En primer lugar, nos hemos basado en nuesto análisis de riesgos, el cual nos indicaba que las siguientes amenazas eran las que suponían un riesgo del mayor nivel (9).

- Corrupción de la información 
- Difusión de software dañino 
- Denegación de servicio  
- Caída del sistema por sobrecarga 
- Ingeniería social 
- Fuga de información 

Partiendo de estos riesgos, decidimos agrupar los riesgos y desarrollando playbooks que los cubran. 

Entonces, si nos dedicamos a agrupar los riesgos previos y crear un playbook que responda y responda al mismo, nos queda lo siguiente:

> [!CAUTION]
> **Denegación de servicio y Caída del sistema por sobrecarga**
>
> - DoS
> - Supply-chain

> [!CAUTION]
> **Corrupción de la información y difusión de software dañino**
>
> - Ransomware
> - Defacement (Desfiguración o modificación de la página web)
> - Create or Modify System Process

> [!CAUTION]
> **Ingeniería social y fuga de información**
> 
> - Identity-and-access
> - Phishing
> - Credentials from Password Stores
> - Replication Through Removable Media

De esta manera intentamos adecuar y acotar nuestros playbooks a la estrategia de negocio de nuestra empresa y a su ciberresiliencia, teniendo una respuesta clara a cada incidente que de verdad pudiera dañarnos gravemente. 

Además, ganamos organización y control sobre nuestro enfoque del plan teniendo ya agrupadas nuestras prioridades para maximizar la efectividad de la respuesta.

A continuación se detallará el flujo del playbook de _Distributed Denial Of Service (DDoS)_:

![Alt text](/imagenes/esquemaDDoS.png)

### 1.c   ¿Como te has asegurado que has cubierto todas las fases del plan de respuesta? ¿Qué fase consideras que está más floja en un plan? ¿Cuál de ellas consideras que está mejor trabajada en tu plan? Asegúrate de hablar de todas las fases y como las cubres. 

En nuestro plan de respuesta se da covertura completa a todas las fases, que son evaluar, iniciar la respuesta, investigar, remediar, comunicar y por último, la fase de recuperación. Si leemos el archivo during.md, vemos que, aunque todaas las fases son cubiertas con precisión y detalle, las más breves son de hecho la primera y la última, que son la fase de evaluación y la fase de recuperación. Del mismo modo, podemos aseverar que las fases intermedias, sobre todo la de investigación, son las más extensas y más trabajadas. Igualmente, si tenemos que elegir obligatoriamente una, sería sin duda la fase de investigación, la cual cubre la creación del archivo del incidente, pasa por la recogida de pruebas, los indicadores de compromiso, el análisis de las pruebas anteriormente recopiladas, así como una lista de artefactos útiles, etc.

- Fase de Evaluación
  - Toma en consideración una serie de pautas iniciales, para poder afrontar el incidente
  - Comprobar la extensión del impacto del incidente.
- Fase de Inicio de Respuesta
  - Reunión del equipo de respuesta
  - Se establece el ritmo general de la "batalla" por superar el incidente
  - Es necesario supervisar el alcance de la respuesta
- Fase de Investigación
  - Creación del archivo del incidente
  - Recopilación de pistas iniciales
  - El plan de investigación y el archivo del incidente se van actualizando a medida que se afronta el incidente
  - IOC's
  - Recogida y análisis de pruebas
- Fase de Remediación
  - Protección
  - Detección
  - Contención
  - Erradicación
- Fase de Comunicación
  - Cubre la comunicación tanto interna como con agentes externos, como clientes, socios comerciales, etc. 
- Fase de Recuperación
  - Esta fase subre tanto la recuperación del propio negocio, haciendo uso de un plan de continuidad del mismo, como la recuperación de los sistemas.

### 2.a   ¿En que consiste el Flujo de Toma de Decisiones y Escalado de tu plan de respuesta? ¿Existe un plan de comunicación, protocolos, etc? Si la respuesta es correcta, haz un resumen del plan y protocolos. Deja evidencias del flujo, mediante un diagrama.

El flujo de Toma de decisiones y escalado de nuestro plan de respuesta consiste en identificar el incidente, evaluarlo, tomar decisiones necesarias siguiendo una serie de playbooks que nos ayuden a solucionar la situación lo antes posible o escalar dicha situación en caso de que esta se complique o no pueda ser solucionada. 

Nuestros playbooks indican con quién nos debemos comunicar en caso de que ocurra un incidente. El empleado en cuestión debe dirigirse inicialmente a su superior y este debe dirigirse al equipo de IT permitiendo que puedan actuar a la mayor brevedad posible. El equipo de IT deberá comunicar dicho incidente a dirección para que estén al tanto y a las autoridades competentes si es necesario.

![Diagrama de toma de decisiones y escalado](https://github.com/IES-Rafael-Alberti/incident-response-plan-plantilla/blob/2024-4.1-G3/imagenes/Diagrama%20de%20toma%20de%20decisiones%20y%20escalado.drawio.png)

### 3.a  ¿Como te has asegurado de que tu plan tiene respuestas resilientes? ¿Porque son resilientes y en qué fases se centran?

Hemos investigado los ataques más comunes que pueden existir y que pueden vulnerar nuestra empresa, por lo tanto hemos generado una serie de playbooks que reune lo que creemos son las respuestas a los incidentes encontrados paso a paso para llegar a recuperar nuestro sistema y orden de trabajo lo más pronto posible.


Nos hemos centrado principalmente en la fase llamada remediar ya que interrumpe el proceso del atacante y nos permite ganar tiempo a nosotros frente a la vulneralidad encontrada. Esta fase indica como detectar el incidente, como contenerlo y luego erradicarlo del sistema permitiendonos llegar a la fase de recuperación lo antes posible.

# Conclusiones

# Bibliografía


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

