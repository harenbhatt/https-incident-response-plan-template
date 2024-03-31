# Plan de respuesta a incidentes para Netmancer Incorporated

Autor: GRUPO 3, grupo3@g.educaand.es

Revisión 1, Publicado 31 de Marzo de 2024

Este plan de respuesta a incidentes está basado en el plan conciso, directivo, específico, flexible y gratuito disponible en [Github](https://github.com/counteractive/incident-response-plan-template) de Counteractive Security y discutido en [www.counteractive.net](https://www.counteractive.net/blog/an-ir-plan-you-will-use/)


Fue revisado por última vez el 31 de Marzo de 2024. Fue probado por última vez en 31 de Marzo de 2024.

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

El procedimiento de nomenclatura de los incidentes será el siguiente:

Consistirá en un número, que empezará con el 0 siendo el primer incidente que se registre, seguido de un guión y la fecha en el siguiente formato: DDMAAAA, construyendo el mes en base a sus tres primeras letras en español. Por ejemplo, para el 3 incidente, sucedido el 2 de Mayo de 2024 tendríamos el código: 

- **2-02MAY2024**

## Reunir el equipo de respuesta

1. Llame al Incident Commander de turno/de guardia. El Incident Commander debe estar disponible al 100% durante su turno de guardia mediante el canal oficial de Discord y su teléfono móvil. También es considerable el tener un dispositivo de radiofrecuencia que garantice que las comunicaciones se puedan establecer.
2. **No** discuta el incidente fuera del equipo de respuesta a menos que el Incident Commander lo autorice
3. Inicie y/o únase al chat de respuesta en https://discordapp.com/channels/1160937443617411112/1160937444200415276. Si se utiliza una aplicación de mensajería instánea para la comunicación, será "Signal" debido a sus niveles de privacidad y encriptación.
4. Iniciar y/o unirse a la llamada de respuesta en 956 24 33 17 y/o https://discordapp.com/channels/1160937443617411112/1160937444200415276.
5. Preferible usar la llamada de voz, el chat y el intercambio seguro de archivos sobre cualquier otro método.
6. **No** utilizar el correo electrónico principal si es posible.  Si el correo electrónico es necesario, utilícelo con moderación o use 11001828.edu@juntadeandalucia.es.  Encripte los correos electrónicos cuando cualquier participante esté fuera del dominio https://iesrafaelalberti.es.
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
Url del Incident Commander          | https://iesrafaelalberti.es/te-informamos/
Lista del Incident Commander        | https://iesrafaelalberti.es/te-informamos/
Lista del equipo de seguridad       | https://iesrafaelalberti.es/te-informamos/
Lista del equipo SME                | https://iesrafaelalberti.es/te-informamos/
Lista de ejecutivos                 | https://iesrafaelalberti.es/te-informamos/


## Establecer el ritmo de batalla

### Realizar la primera llamada de respuesta

1. Realice la llamada inicial utilizando la [estructura de llamada de respuesta inicial](#referencia-estructura-de-la-llamada-de-respuesta-inicial)
2. Siga las instrucciones del Incident Commander.  Si el Incident Commander de turno/de guardia no se une a la llamada **dentro de 60 minutos** y usted es un Incident Commander capacitado, tome el mando de la llamada.
3. Siga las [instrucciones correspondientes a su función](#roles).
4. Siga la llamada y el chat, y comente según corresponda.  Si no es un SME, comunique las aportaciones a través del SME de su equipo si es posible.
5. **Mantenga la llamada y el chat activos durante todo el incidente para una comunicación basada en eventos.**
6. Programe actualizaciones **cada 3 horas** sobre la comunicación activa.

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

* Llevar a cabo actualizaciones programadas utilizando la [estructura de llamada de actualización](#referencia-estructura-de-la-llamada-de-actualización-de-la-respuesta) cada 3 horas en el puente activo.
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

1. Cree un nuevo archivo de incidentes en https://netmancer.es/src/incidents utilizando el [nombre del incidente](#nombre-del-incidente).  Utilice este archivo para el almacenamiento seguro de documentación, pruebas, artefactos, _etc._.
    * Proporcionar un almacenamiento digital seguro.
    * Proporcionar un intercambio de archivos seguro.
    * Obtener almacenamiento físico.
    * Compartir la ubicación del archivo del incidente en la llamada y el chat.
1. Documente el impacto funcional y de la información, si se conoce (véase [Evaluar](#evaluar)). 
2. Documentar el vector, si se conoce (_por ejemplo_ web, correo electrónico, medios extraíbles).
3. Documente el resumen del incidente: un breve resumen del vector, el impacto, la investigación y la situación de la reparación, si se conoce.
4. Documente la línea de tiempo del incidente, incluyendo la actividad del atacante y la actividad de la respuesta.
5. Documente los pasos de investigación, reparación y comunicación.  Documente las actividades de forma independiente para que puedan combinarse y reutilizarse, si es posible.
6. Registre la información significativa, como:
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
Lista de información crítica        | https://netmancer.es/src/critical_info_list
Lista de activos críticos           | https://netmancer.es/src/critical_asset_list
Base de datos de gestión de activos | https://netmancer.es/src/assets
Mapa de red                         | https://netmancer.es/network/network_map
Consola SIEM                        | https://netmancer.es/siem/console
Agregador de registros              | https://netmancer.es/elk/console_log

La información crítica sobre los riesgos y sus activos relacionados puede encontrarse en el directorio /documentosEmpresa/plan_director_de_seguridad_hoja_para_el_analisis_de_riesgos.xlsm

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

## Recogida de pruebas

* Priorizar en base al plan de investigación
* Recoger datos de respuesta en vivo utilizando [netman](https://netmancer.es/response_tool/netman) para la memoria y [netman](https://netmancer.es/response_tool/netman) para el disco.
* Recoger los registros relevantes de los sistemas (si no forman parte de la respuesta en vivo), agregadores, SIEM o consolas de dispositivos.
* Recoger la imagen de la memoria, si es necesario y si no forma parte de la respuesta en vivo, utilizando [volatility](https://github.com/volatilityfoundation/volatility).
* Recoger la imagen del disco, si es necesario, utilizando [FTK_imager](https://www.exterro.com/digital-forensics-software/ftk-imager).
* Recoger y almacenar las pruebas de acuerdo con la política, y con la cadena de custodia adecuada.
  - **Herramientas y Procedimientos:**
    - Utilizar [volatility](https://github.com/volatilityfoundation/volatility) para la recogida de memoria, siguiendo los procedimientos específicos de adquisición de evidencia.
    - Utilizar [FTK_imager](https://www.exterro.com/digital-forensics-software/ftk-imager) para la recogida de imágenes de disco, asegurando la integridad de los datos y el cumplimiento de la cadena de custodia.
    - Mantener registros detallados de todas las acciones realizadas durante la recogida de pruebas.
* Considere la posibilidad de recopilar los siguientes artefactos como evidencia, ya sea en tiempo real (_por ejemplo_, a través de EDR o un SIEM) o bajo demanda:
    - Registros de eventos del sistema y de seguridad.
    - Registros de firewall y registros de proxy.
    - Registros de acceso y autenticación.
    - Copias de seguridad de archivos relevantes.
    - Capturas de pantalla de actividades sospechosas.
    - Copias de registros de chat o mensajes.
    - Correos electrónicos relevantes.
    - Archivos de configuración del sistema.
    - Archivos de registro de aplicaciones relevantes.

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

* Aumento repentino en el tráfico del sitio web, especialmente en páginas de pago o de acceso a cuentas.
* Cambios significativos en las tasas de conversión o abandono en el proceso de compra.
* Número de intentos de inicio de sesión fallidos en la plataforma de ecommerce.
* Cambios en el patrón de comportamiento de los usuarios, como la navegación rápida entre productos o la repetición de ciertas acciones.
* Incremento en el número de solicitudes de reembolso o cancelaciones de pedidos.
* Aparición de productos o categorías de productos no autorizados en el sitio web.
* Detección de enlaces o archivos maliciosos en el sitio web.
* Cambios en los precios de los productos sin autorización.
* Aumento en el número de quejas o reclamaciones de clientes sobre transacciones fraudulentas.
* Detección de accesos no autorizados o intentos de acceso a áreas protegidas del sitio web.
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

1. Revise el archivo del incidente en https://netmancer.es/src/incidents utilizando el [nombre del incidente](#nombre-del-incidente)
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

* Tras el cierre del incidente, capture la información en el [archivo del incidente](#crear-archivo-del-incidente) para su distribución utilizando el formato en https://netmancer.es/reports/template.  **Si los informes de vector, impacto, resumen, línea de tiempo y actividad están completos, esto puede ser totalmente automatizado.**
* Distribuir el informe de incidentes a lo siguiente: https://netmancer.es/reports/recipients.

## Comunicar al exterior

### Notificar a los reguladores

* **No** notifique ni ponga al día al personal que no ha respondido hasta que el Incident Commander lo autorice.
* Notificar a los organismos reguladores (por ejemplo, HIPAA/HITRUST, PCI DSS, SOX) si es necesario y de acuerdo con la política.
* Coordinar los requisitos, el formato y los plazos con el leaglteam@netmancer.es.

### Notificar a los clientes

* **No** notifique o actualice al personal que no responde hasta que el Incident Commander lo autorice.
* Coordine las notificaciones a los clientes con comunications@netmancer.es.
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
* Coordinar con executive@netmancer.es y leaglteam@netmancer.es antes de interactuar con las fuerzas del orden.
* Póngase en contacto con las fuerzas del orden locales en Detective Ramón García. policia@policialocal.es.
* Póngase en contacto con el FBI en https://www.fbi.gov/contact-us o a través del [Internet Crime Complaint Center (IC3)](https://www.ic3.gov).
* Póngase en contacto con los operadores de los sistemas utilizados en el ataque, sus sistemas también pueden haber sido comprometidos.

### Contactar con el servicio de asistencia de respuesta externa

* Póngase en contacto con [AT&amp;T USM Anywhere]https://cybersecurity.att.com/products/usm-anywhere para que le ayude a evaluar el riesgo, la gestión de incidentes, la respuesta a los mismos y el apoyo posterior al incidente.
* Póngase en contacto con https://www.softr.io/ para que le ayude con las relaciones públicas y la comunicación externa.
* Póngase en contacto con https://www.reale.es/ para obtener ayuda con el seguro cibernético.

### Compartir Inteligencia

* Comparta los IOCs con [Infragard](https://www.infragard.org/) si procede.
* Comparta los IOCs con su [ISAC](https://en.wikipedia.org/wiki/Information_Sharing_and_Analysis_Center) de servicio a través de https://isacspain.com/, si procede.

# Recuperación

**La recuperación suele estar dirigida por las unidades de negocio y los propietarios de los sistemas.  Tome medidas de recuperación sólo en colaboración con las partes interesadas pertinentes.**

1. Poner en marcha un plan de continuidad de negocio/recuperación de desastres: Por ejemplo, considerar la migración a ubicaciones operativas alternativas, sitios de conmutación por error, sistemas de copia de seguridad.
   - **Herramientas y Procedimientos:**
     - Utilizar Bacula para restaurar los datos desde las copias de seguridad.
     - Coordinar con los equipos de operaciones para configurar y poner en funcionamiento los sistemas alternativos o de respaldo.
     - Comunicar con claridad los pasos a seguir a todo el personal involucrado en la recuperación.

2. Integrar las acciones de seguridad con los esfuerzos de recuperación de la organización.
   - **Herramientas y Procedimientos:**
     - Coordinar con el equipo de seguridad para garantizar que todas las medidas de seguridad adecuadas se implementen durante el proceso de recuperación.
     - Realizar análisis de vulnerabilidades y pruebas de seguridad antes de poner en línea los sistemas recuperados.
     - Implementar medidas de monitoreo y detección de intrusiones para identificar posibles actividades maliciosas durante el proceso de recuperación.# Playbook

Los siguientes playbooks capturan los pasos comunes de [investigación](#investigate), [remediación](#remediate) y [comunicación](#communicate) para determinados tipos de incidentes.

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
## Playbook: Creacción o modificación de procesos para escalado.

### Investigar

1. Identificar el origen del ataque.
2. Identificar la vía del ataque.
3. Recopilar evidencias forenses con las herramientas suministradas por la empresa.
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
## Playbook: Ataque de Denegación de Servicio Distribuido (DDoS)

**Investigar, mitigar y comunicar en paralelo!**
Asigne los pasos a individuos o equipos para que trabajen simultáneamente; este playbook no es puramente secuencial (Exceptuando la fase "Mitigar" que SIEMPRE debe ser la primera). 

Utilice su mejor criterio.


### Mitigar

1. Implementar filtros de tráfico y reglas de firewall.
    * Bloquee las direcciones IP de origen conocidas del ataque.
    * Considerar bloqueo de IP de un país concreto en caso de que todas las peticiones vengan de un lugar concreto, puede ocurrir.
    * Configure reglas de firewall para filtrar el tráfico malicioso.
2. Escalar la infraestructura.
    * Aumente la capacidad de ancho de banda y los recursos de servidor para absorber el tráfico adicional.
    * Considerar conectar servidores adicionales disponibles para ganar tiempo.
    * Utilice servicios de CDN (Content Delivery Network) para distribuir el tráfico y mitigar el impacto del ataque.

### Comunicar

1. 1. Notificar a la dirección y al equipo de gestión de crisis.
1. 2. Documentar el incidente según el procedimiento establecido.
2. Comunicarse con los equipos de operaciones y desarrollo.
    1. Informar sobre las medidas de mitigación implementadas y las posibles interrupciones del servicio.
    2. Coordinar con los equipos de TI para garantizar la disponibilidad continua de los servicios críticos.
3. Comunicarse con los proveedores de servicios de red.
    1. Notificar a los proveedores de servicios de red sobre el ataque y solicitar asistencia adicional si es necesario.
    2. Coordinar con los proveedores de servicios de mitigación de DDoS para optimizar la respuesta al ataque.
4. Actualizar a los clientes y usuarios.
    1. Informar sobre posibles interrupciones del servicio y tiempo estimado de recuperación.
    2. Proporcionar actualizaciones periódicas sobre el estado del incidente y las medidas de mitigación.
5. Configurar la alerta de respuesta de emergencia.
    * Establezca alertas automáticas para notificar al equipo de seguridad sobre futuros picos inusuales de tráfico.
    * Automatice la respuesta de mitigación para que se active automáticamente ante futuros ataques.

### Investigar

1. Identificar y confirmar el ataque DDoS en curso.
    * Supervise el tráfico de red y analice los patrones de tráfico anómalos que puedan indicar un ataque DDoS en curso.
    * Utilice herramientas de monitoreo de red como Wireshark, Nagios, o soluciones específicas contra DDoS.
2. Determine el tipo de ataque DDoS.
    * Ataque de inundación SYN
    * Ataque de inundación UDP
    * Ataque de inundación HTTP
    * Otros tipos de ataques conocidos.
3. Evaluar la gravedad y el impacto del ataque.
    * Analice la magnitud del tráfico malicioso en comparación con el tráfico normal.
    * Determine si los servicios críticos están siendo afectados y en qué medida.
4. Identificar el origen y las fuentes del ataque.
    * Rastree las direcciones IP de origen del tráfico malicioso.
    * Utilice herramientas de geolocalización para identificar la ubicación aproximada de los atacantes.
    * Recopile información sobre la infraestructura utilizada por los atacantes.
5. Recuperar y conseguir toda la información relativa a los sistemas para ser investigados utilizando técnicas forenses, las cuales nos ayudarán a aprender más sobre el escenario.

### Evaluar y recuperar
1. Determinar el alcance del daño a los sistemas.
    - Daños financieros
    - Daños de imagen
    - Daños físicos en por ejemplo hardware
2. Restablecer sistemas y servicios al estado habitual de los mismos
    - Añadir configuraciones extras derivadas del ataque para el futuro
    - Desactivar las medidas aplicadas en la fase de mitigación


### Aprender

1. Configurar la alerta de respuesta de emergencia.
    * Establezca alertas automáticas para notificar al equipo de seguridad sobre futuros picos inusuales de tráfico.
    * Automatice la respuesta de mitigación para que se active automáticamente ante futuros ataques.
2. Mantener equipos y servicios para un posible nuevo escenario con necesidad de escalada de recursos.



### Recursos

#### Herramientas de Mitigación de DDoS

- Cloudflare
- Akamai
- AWS Shield
- Arbor Networks
- Radware
- F5 Networks

#### Herramientas de Monitoreo de Red

- Wireshark
- Nagios
- SolarWinds
- Cisco NetFlow
- Zabbix

#### Referencia: Artículos y Recursos

1. [Guía sobre DDoS](https://www.cloudflare.com/learning/ddos/what-is-a-ddos-attack/) de Cloudflare.
2. [Cómo protegerse contra ataques DDoS](https://aws.amazon.com/es/shield/) con AWS Shield.
3. [Cómo detectar y mitigar ataques DDoS](https://www.akamai.com/es/es/) con Akamai.
## Playbook: Ataque de Denegación de Servicio (DoS)

**Investigar, remediar (contener, erradicar) y comunicar en paralelo!**
Asigne los pasos a individuos o equipos para que trabajen simultáneamente; este playbook no es puramente secuencial. Utilice su mejor criterio.

### Investigar

1. Confirmar el ataque de Denegación de Servicio (DoS).
    * Verificar la degradación del rendimiento del sistema o la indisponibilidad de los servicios.
    * Analizar los registros del servidor en busca de tráfico anormal o patrones de ataque.
2. Identificar posibles fuentes del ataque.
    * Analizar el tráfico de red para identificar direcciones IP sospechosas o rangos de direcciones asociados con el ataque.
    * Diferenciar entre un ataque de Denegación de Servicio distribuido (DDoS) y un ataque DoS convencional.
        * Para ataques DDoS: Investigar la posibilidad de que el ataque provenga de una botnet o de dispositivos comprometidos distribuidos geográficamente.
        * Para ataques DoS convencionales: Investigar si el ataque se origina desde una sola fuente o un conjunto limitado de direcciones IP.
    * Considerar la posibilidad de que el ataque sea perpetrado por un atacante interno o externo.
3. Recopilar evidencia para la investigación.
    * Capturar registros de tráfico y paquetes de red para su análisis posterior.
    * Registrar cualquier actividad sospechosa observada durante el ataque, como intentos de autenticación fallidos o solicitudes de recursos específicos.

### Remediar

**Planificar la remediación** en la que estos pasos se pongan en marcha juntos (o de forma coordinada), con los equipos adecuados listos para responder a cualquier interrupción.

#### Contención

1. Mitigar el ataque en curso.
    * Identificar y bloquear las fuentes de tráfico malicioso utilizando reglas de firewall, listas de bloqueo IP u otras medidas de filtrado.
    * Utilizar servicios de mitigación de DDoS si están disponibles para desviar el tráfico no deseado.

#### Erradicación

1. Identificar la causa raíz del ataque.
    * Analizar los registros de tráfico para determinar el tipo y la fuente del ataque.
    * Investigar posibles vulnerabilidades en el sistema que podrían haber sido explotadas por los atacantes.

### Comunicar

**Comunicarse con las partes interesadas** para informar sobre el incidente y las acciones tomadas para mitigarlo.

1. Notificar a la dirección y al equipo de gestión de crisis.
    * Informar sobre la naturaleza y el alcance del ataque de Denegación de Servicio.
    * Proporcionar actualizaciones regulares sobre la remediación y las medidas de mitigación implementadas.

### Recursos

#### Herramientas y Tecnologías de Mitigación

- Firewalls con capacidades de filtrado avanzado.
- Servicios de mitigación de DDoS proporcionados por proveedores de seguridad.
- Sistemas de detección y prevención de intrusiones (IDS/IPS) para identificar y bloquear el tráfico malicioso.
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
## Playbook: Limpieza de disco

### Investigar

1. Identificar el origen del ataque en caso de que haya sido un malware.
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
## Playbook: Brute Force

### Investigar

- Monitorizar altos volúmenes de fallos de autenticación. Esto implica supervisar los registros de eventos de autenticación en busca de un número inusualmente alto de intentos fallidos de inicio de sesión. Estos intentos pueden indicar diferentes tipos de ataques dirigidos a comprometer las credenciales de usuario.
    - *Password guessing:* Intento de adivinar la contraseña correcta probando diferentes combinaciones de contraseñas comunes o predecibles.
    - *Password Cracking:* Intento de descifrar contraseñas utilizando técnicas como fuerza bruta o ataques de diccionario. Este tipo de ataques suelen producir un número elevado de errores de autenticación.
    - *Password Spraying:* Intenta de inicio de sesión en múltiples cuentas con un conjunto limitado de contraseñas comunes. Este tipo de ataque deja un rastro de múltiples intentos fallidos de inicio de sesión en diversas cuentas.
    - *Credential Stuffing:* Intento de inicio de sesión en una cuenta con credenciales filtradas de otros sitios web o servicios ajenos a la compañía.
- Investigar y eliminar todas las alertas asociadas con los activos afectados. Esto puede implicar la identificación de los sistemas afectados, el análisis de los registros de eventos relacionados y la recopilación de evidencia para una investigación más detallada.
- Verificar regularmente los registros del firewall, IDS (Sistema de Detección de Intrusiones), IPS (Sistema de Prevención de Intrusiones) y SIEM (Sistemas de gestión de información y eventos de seguridad) en busca de actividad inusual.    
- Examinar los comandos y argumentos ejecutados que pueden utilizar técnicas de fuerza bruta para obtener acceso a cuentas cuando se desconocen las contraseñas o cuando se obtienen hashes de contraseñas.

### Remediar

- Restablecer proactivamente las cuentas que se sabe que forman parte de credenciales vulneradas, ya sea inmediatamente o después de detectar intentos de fuerza bruta.
- Implementar la autenticación multifactor. Cuando sea posible, habilitar también la autenticación multifactor en servicios externos.
- Cambiar las contraseñas que hayan sido vulneradas por los atacantes.
    - Consultar las directrices del NIST al crear políticas de contraseñas.
    - En base a estas directrices anteriormente mencionadas, capacitar e instar a los empleados para usar contraseñas que cumplan con estas normas.

#### Contener

- Establecer políticas de bloqueo de cuentas después de una cierta cantidad de intentos fallidos de inicio de sesión para evitar que se adivinen las contraseñas. 
    - Una política demasiado estricta puede crear una condición de denegación de servicio y dejar los entornos inutilizables, bloqueando todas las cuentas utilizadas en la fuerza bruta. Utilice políticas de acceso condicional para bloquear inicios de sesión desde dispositivos no compatibles o desde rangos IP de organización fuera de los definidos.

### Comunicar

- Informar a todos los equipos relevantes dentro de la organización sobre el incidente de fuerza bruta detectado, lo que incluye equipos de seguridad, TI, gestión de riesgos y cualquier otro departamento relevante.
- Si los usuarios fueron afectados por el intento de fuerza bruta (por ejemplo, si sus cuentas fueron objeto de ataques de contraseñas), es importante comunicarse con ellos de manera transparente. Proporcionar orientación sobre cómo proteger sus cuentas, como cambiar sus contraseñas y habilitar la autenticación de dos factores si está disponible.
- Informar a la dirección sobre el incidente de fuerza bruta. 

### Recuperación

- Si se considera conveniente, debido a la intrusión de un/os posible/s atacante/s en la/s cuenta/s vulnerada/s, restaurar hasta el Punto de Recuperación Objetivo (RPO) dentro del Tiempo de Recuperación Objetivo (RTO).
    - El RPO es el punto en el tiempo al que una organización está dispuesta a recuperarse después de un desastre. 
    - El RTO es la cantidad de tiempo que una organización está dispuesta a tolerar para que sus servicios vuelvan a estar disponibles después de un desastre.
- Restaurar los sistemas vulnerados hasta su último backup limpio.
- Antes de restaurar cualquier sistema desde una copia de seguridad, es esencial inspeccionar las copias de seguridad en busca de IOC (Indicadores de Compromiso) que puedan indicar que las copias de seguridad también están comprometidas. Esto ayuda a evitar la restauración de sistemas comprometidos y a garantizar la integridad de los datos restaurados.
- Identificar y abordar cualquier daño colateral para minimizar cualquier impacto adicional en la organización.
- Resolver cualquier incidente de seguridad relacionado tales como posibles vulnerabilidades que hayan podido ser explotadas por los atacantes. 

### Recursos

#### Referencia: Artículos y Recursos

- [MITRE ATT&CK](https://attack.mitre.org/techniques/T1110/)
- [CIRT Playbook Battle Cards](https://github.com/guardsight/gsvsoc_cirt-playbook-battle-cards/blob/master/Markdown/GSPBC-1048%20-%20Credential%20Access%20-%20Brute%20Force.md)
- [RE&CT](https://atc-project.github.io/atc-react/)
- [Directrices del NIST para crear políticas de contraseñas](https://pages.nist.gov/800-63-3/sp800-63b.html)
## Playbook: Credentials from Password Stores

### Investigar

- Monitorizar búsquedas en la memoria de palabras clave comunes, tales como password, pwd, login, store, secure, credentials, etc. 
- Supervisar los comandos y argumentos ejecutados que pueden buscar ubicaciones de almacenamiento de contraseñas comunes para obtener credenciales de usuario, así como procesos a los que se accede, procesos recién ejecutados, llamadas API o archivos accedidos con este fin.
- Tener en cuenta el posible uso de herramientas automatizadas que escanean la memoria en busca de contraseñas.
- Prevenir el almacenamiento de contraseñas en texto plano.
- Supervisar cualquier actividad anómala en torno a todas las aplicaciones de almacenamiento de contraseñas autorizadas.
- Vigilar el uso de aplicaciones de almacenamiento de contraseñas no autorizadas.
- Controlar el acceso a los archivos de la BBDD de almacenamiento de contraseñas del navegador web.

### Remediar
 
- Limitar la cantidad de cuentas y servicios con permiso para consultar información de los almacenes de contraseñas solo a aquellos necesarios. Asegurar que las cuentas y servicios con permisos para consultar almacenes de contraseñas solo tengan acceso a los secretos que necesiten.
- La contraseña para el llavero de inicio de sesión del usuario puede ser cambiada desde la contraseña de inicio de sesión del usuario. Esto aumenta la complejidad para un atacante porque necesitarían conocer una contraseña adicional.
- Realizar escaneos en puntos finales (*endpoints*, o más concretamente, dispositivos finales de una red tales como ordenadores de sobremesa, teléfonos móviles, tablets, portátiles, etc) con antivirus (AV)(***Endpoint/AV Scan***).
- Restablecer cualquier contraseña comprometida, así como las contraseñas de cualquier cuenta comprometida.
- Inspeccionar los backups en busca de IOCs (Indicadores de Compromiso) consistentes con el perfil del ataque previo a la recuperación del sistema.
- Eliminar todas las instancias de credenciales que se almacenaron de forma insegura.

#### Contener

- Utilice software de detección y respuesta de endpoints (EDR) para finalizar los procesos infractores.
- Se debe aislar al equipo o sistema afectado de la red, a fin de evitar que el malware se propague por esta. Esto debe mantenerse hasta que el incidente de seguridad se dé por finalizado y solucionado.
- Identificar y bloquear de inmediato las cuentas de usuario comprometidas que hayan sido utilizadas para acceder o almacenar credenciales en ubicaciones no autorizadas.
- Revisar los permisos de acceso a los almacenes de contraseñas y otras ubicaciones sensibles para asegurar que solo los usuarios autorizados tengan acceso y que los privilegios se ajusten a los principios de menor privilegio.
- Reforzar los controles de acceso mediante la implementación de autenticación de múltiples factores (MFA) o autenticación de un solo uso (OTP) en los sistemas de almacenamiento de contraseñas y otros sistemas críticos.
- Capacitar a los empleados para no usar contraseñas inseguras, no almacenarlas en texto plano, no compartir las contraseñas con nadie, etc.

### Comunicar

- Informar a todos los empleados relevantes sobre el incidente de compromiso de credenciales y las acciones tomadas para contener y remediar la situación.
- Informar a la alta dirección de la organización sobre el incidente, destacando los posibles impactos en la seguridad y en las operaciones del negocio, así como las medidas tomadas para mitigar los riesgos asociados.
- Si el incidente de compromiso de credenciales afecta a socios comerciales, clientes u otras partes externas, es importante comunicarse con ellos de manera transparente y oportuna. Esto puede implicar informarles sobre el incidente, los riesgos potenciales y las medidas que están siendo tomadas para abordar la situación.

### Recuperación

- Restaurar hasta el Punto de Recuperación Objetivo (RPO) dentro del Tiempo de Recuperación Objetivo (RTO).
    - El RPO es el punto en el tiempo al que una organización está dispuesta a recuperarse después de un desastre. 
    -   El RTO es la cantidad de tiempo que una organización está dispuesta a tolerar para que sus servicios vuelvan a estar disponibles después de un desastre. 
- Identificar y abordar cualquier daño colateral para minimizar cualquier impacto adicional en la organización.
- Resolver cualquier incidente de seguridad relacionado tales como posibles vulnerabilidades que hayan podido ser explotadas por los atacantes.
- Después de abordar cualquier daño colateral y resolver cualquier incidente de seguridad relacionado, se deben restaurar los sistemas afectados a su última copia de seguridad limpia. Esto implica volver a un estado conocido y seguro antes del incidente, utilizando copias de seguridad verificadas para garantizar la integridad y la seguridad de los datos y sistemas restaurados.

### Recursos

#### Referencia: Artículos y Recursos

- [MITRE ATT&CK](https://attack.mitre.org/techniques/T1555/)
- [CIRT Playbook Battle Cards](https://github.com/guardsight/gsvsoc_cirt-playbook-battle-cards/blob/master/Markdown/GSPBC-1035%20-%20Credential%20Access%20-%20Credentials%20from%20Password%20Stores.md)
- [RE&CT](https://atc-project.github.io/atc-react/)## Playbook: Defacement de Sitio Web

**Investigar, remediar (contener, erradicar) y comunicar en paralelo!**
Asigne los pasos a individuos o equipos para que trabajen simultáneamente; este playbook no es puramente secuencial. Utilice su mejor criterio.

### Investigar

1. Identificar y confirmar la desfiguración del sitio web.
    * Verifique la autenticidad del incidente visitando el sitio web afectado y corroborando el cambio no autorizado.
    * Determine si la desfiguración es global o si se limita a ciertas páginas o secciones del sitio.
2. Recopilar información sobre el incidente.
    * Capture capturas de pantalla de la desfiguración y registre cualquier mensaje o contenido malicioso.
    * Examine los registros del servidor web y de aplicaciones para identificar el momento y la fuente del ataque.
3. Evaluar el impacto del incidente.
    * Determine si la desfiguración afecta la funcionalidad del sitio web o simplemente su apariencia.
    * Evalúe el impacto en la reputación de la marca y la confianza del cliente.
4. Identificar la causa raíz del incidente.
    * Investigue cómo los atacantes pudieron comprometer la seguridad del sitio web y realizar la desfiguración.
    * Analice las vulnerabilidades de seguridad del sitio web y los posibles vectores de ataque utilizados.

### Remediar

**Planificar la remediación** en la que estos pasos se pongan en marcha juntos (o de forma coordinada), con los equipos adecuados listos para responder a cualquier interrupción.

#### Contención

1. Retirar la desfiguración del sitio web.
    * Restaure el contenido original y legítimo del sitio web desde una copia de seguridad o desde una versión no afectada.
    * Elimine cualquier archivo malicioso o modificado por los atacantes.
2. Reforzar la seguridad del sitio web.
    * Actualice todas las aplicaciones, plugins y sistemas de gestión de contenido (CMS) a las versiones más recientes.
    * Cambie todas las contraseñas de acceso y aplique una política de contraseñas fuerte.
    * Implemente medidas adicionales de seguridad, como firewalls de aplicaciones web (WAF) y monitoreo de seguridad continuo.

#### Erradicación

1. Investigar la causa raíz del incidente.
    * Realice una revisión exhaustiva de la seguridad del sitio web para identificar las vulnerabilidades explotadas.
    * Corrija las vulnerabilidades identificadas y aplique parches de seguridad según sea necesario.
2. Implementar controles de seguridad adicionales.
    * Configure copias de seguridad regulares y automatizadas del sitio web y su contenido.
    * Establezca alertas de seguridad para detectar y responder rápidamente a futuros incidentes de desfiguración.

### Comunicar

**Comunicarse con las partes interesadas** para informar sobre el incidente y las acciones tomadas para mitigarlo.

1. Notificar a la dirección y al equipo de gestión de crisis.
    * Informe a los ejecutivos y a los responsables de la toma de decisiones sobre la naturaleza y el alcance del incidente.
    * Proporcione actualizaciones regulares sobre el progreso de la remediación y las medidas de seguridad implementadas.
2. Comunicarse con los usuarios y clientes.
    * Notifique a los usuarios sobre el incidente y explique las medidas tomadas para restaurar la seguridad del sitio web.
    * Proporcione canales de comunicación para que los usuarios puedan informar sobre cualquier problema adicional o inquietud.
3. Coordinar con las autoridades y reguladores pertinentes.
    * Notifique a las autoridades de protección de datos y cumpla con cualquier requisito de notificación obligatoria.
    * Colabore con las autoridades en la investigación del incidente y en la identificación de los responsables.

### Recursos

#### Herramientas y Tecnologías de Seguridad

- Firewalls de Aplicaciones Web (WAF)
- Sistemas de Gestión de Contenido (CMS) seguros
- Escáneres de Vulnerabilidades Web (Nessus, Acunetix)
- Herramientas de Monitoreo de Seguridad de Sitios Web (Sucuri, Wordfence)

#### Referencia: Artículos y Recursos

1. [OWASP Top 10](https://owasp.org/www-project-top-ten/) - Lista de las principales vulnerabilidades de seguridad en aplicaciones web.
2. [Sucuri Blog](https://sucuri.net/blog/) - Recursos y guías sobre seguridad web y protección contra desfiguraciones.
3. [Wordfence](https://www.wordfence.com/blog/) - Blog con consejos y mejores prácticas para la seguridad de WordPress y otros CMS.
## Playbook: Phishing

### Investigar

- Examinar los registros, mensajes y/u otros artefactos de aplicaciones de terceros que puedan enviar mensajes de phishing para obtener acceso a los sistemas de las víctimas. El filtrado basado en DKIM+SPF o análisis de encabezados puede ayudar a detectar cuándo el remitente del correo electrónico es falso. La inspección de URL dentro del correo electrónico (incluida la expansión de enlaces acortados) puede ayudar a detectar enlaces que conducen a sitios maliciosos conocidos.
    - DMARC, DKIM y SPF son tres métodos de autenticación del correo electrónico . Juntos, ayudan a evitar que los spammers, phishers, y otras partes no autorizadas envíen correos electrónicos en nombre de un dominio que no poseen.
- Supervisar los registros de llamadas desde dispositivos corporativos para identificar patrones de posible phishing de voz, como llamadas hacia o desde números de teléfono maliciosos conocidos. Correlacionar estos registros con eventos del sistema.
- Revisar los archivos recién creados a partir de mensajes de phishing para obtener acceso a los sistemas de las víctimas.
- Monitorizar y analizar patrones de tráfico SSL/TLS e inspeccionar de paquetes asociados a protocolos que no siguen los estándares de protocolo y flujos de tráfico esperados (por ejemplo, paquetes extraños que no pertenecen a flujos establecidos, patrones de tráfico anómalos o gratuitos, sintaxis anómala o estructura).
    - Los certificados de SSL/TLS permiten a los navegadores web identificar y establecer conexiones de red cifradas con sitios web mediante el protocolo de capa de conexión segura/seguridad de la capa de transporte (SSL/TLS).
- Evaluar los datos de la red para detectar flujos de datos poco comunes. Los procesos que utilizan la red y que normalmente no tienen comunicación de red o que nunca antes se han visto son sospechosos.   
- Se debe poner especial atención a emails con archivos adjuntos sospechosos o de procedencia dudosa, a emails múltiples enviados desde fuentes desconocidas, emails con errores tipográficos en el nombre del dominio o aquellos que no cumplen con los métodos DKIM o SPF.
    - Revisar enlaces, archivos adjuntos y/o hashes en [VirusTotal](https://www.virustotal.com/gui/home/upload) o en sandboxes de malware tales como [Cuckoo Sandbox](https://github.com/cuckoosandbox), [Hybrid Analysis](https://www.hybrid-analysis.com/), [Joe Sandbox](https://www.joesecurity.org/) o [VMRay](https://www.vmray.com/).
    - También se recomienda analizar el mensaje, haciendo uso de un dispositivo seguro. Este no debe tener acceso a datos sensibles, credenciales o información importante en general. Se deben analizar los puntos siguientes:
        - Receptor del mensaje y objetivo del mismo.
        - Dirección de correo electrónico del remitente.
        - Asunto y cuerpo del mensaje.
        - Archivos adjuntos. Estos sólo deberían abrirse en máquinas virtuales aisladas de la red corporativa, y analizados por el equipo IT.
        - Enlaces, dominios o nombres de host. En este caso se sigue el mismo principio que con los archivos adjuntos, los enlaces no deben abrirse, con la excepción de hacerlo en un entorno controlado por el equipo IT.
        - Metadatos del correo electrónico. 

### Remediar

- Para bloquear la actividad se pueden utilizar sistemas de prevención de intrusiones (IPS) o sistemas de detección de intrusiones (IDS) en la red y sistemas diseñados para escanear y eliminar enlaces o archivos adjuntos de correo electrónico maliciosos.
- Determinar si ciertos sitios web o tipos de archivos adjuntos (por ejemplo: .scr, .exe, .pif, .cpl, etc.) que pueden usarse para phishing son necesarios para las operaciones comerciales y considerar bloquear el acceso si la actividad no se puede monitorizar o bien si plantea un riesgo importante.
- Cerrar el vector de ataque. Esto puede suponer desconectar al equipo afectado de la red, a fin de evitar la posible propagación del malware.
- Realizar escaneos en puntos finales (*endpoints*, o más concretamente, dispositivos finales de una red tales como ordenadores de sobremesa, teléfonos móviles, tablets, portátiles, etc) con antivirus (AV)(***Endpoint/AV Scan***).
- Examinar los logs para identificar si existen otros usuarios afectados.
- Se puede capacitar a los usuarios para que identifiquen técnicas de ingeniería social y correos electrónicos de phishing.

#### Contener

- Contención de la cuenta afectada. Esto supone cambiar sus credenciales, utilizar autenticación multifactor (MFA) y limitar el acceso de la cuenta a cualquier servicio, sistema o información hasta que exista total certeza que es seguro hacerlo. Otra opción es bloquear la cuenta hasta que el problema haya quedado resuelto. 
- Enumerar y evaluar los posibles daños causados por el incidente. Esto nos refiere al punto anterior y a cerrar el vector de ataque, o dicho de otro modo, aislar el equipo de origen, a fin de evitar una propagación del hipotético malware.
- Bloquear la IP externa e interna del equipo de origen, cerrar toda comunicación a través de los puertos del sistema y bloquear cualquier posible comunicación del usuario afectado. También se debe bloquear el dominio del email y el correo electrónico de origen.
- Poner en cuarentena tanto el mensaje recibido como el hipotético archivo adjunto que este pueda contener. Esta cuarentena debe realizarse teniendo en cuenta el formato del archivo, su hash, su ruta y el patrón de contenido del mismo.
    - El antivirus puede poner automáticamente en cuarentena archivos sospechosos.
- Considerar llevar a cabo una actualización del software que pudiera presentar posibles vulnerabilidades. Tras una investigación, se debería detectar la hipotética vulnerabilidad o falla de seguridad que el malware pudo haber apovechado.   

### Comunicar

- Informar a otros usuarios y partes interesadas relevantes sobre el ataque de phishing y las precauciones necesarias que deben tomar.
- Emitir un reporte al proveedor de servicios de correo electrónico o a la empresa de alojamiento web que se utilizó para enviar el correo electrónico malicioso.
- Escalar el incidente al nivel apropiado de gestión, si es necesario.
- Informar el incidente a las autoridades pertinentes, como organismos reguladores o encargados de hacer cumplir la ley, si es necesario.

### Recuperación

- En caso de interrupción del negocio, poner en marcha un plan de recuperación de desastres, además de hacer uso de las copias de seguridad en caso de considerarse necesario.
- Verificar que las credenciales se han cambiado correctamente.
- Es extremadamente recomendable preparar y poner en acción un programa de formación y adiestramiento de los empleados acerca de cómo responder a amenazas informáticas, y cómo prevenirlas en la medida de lo posible. Enfocándonos al phishing, que es el tema que nos ocupa, los empleados deben centrarse en los siguiente aspectos:
    - Errores ortográficos en el mensaje, el asunto o más importante aún, en el nombre del domninio.
    - Inconsistencia entre el nombre del remitente y el correo electrónico de origen.
    - Uso de correos eletrónicos personales como Gmail, Hotmail o Yahoo para asuntos de trabajo.
    - Enlaces sospechosos. En este punto se vuelve a aplicar la regla de los errores ortográficos. También se debe prestar atención a los servicios que acortan las urls, y si esto está presente en el enlace recibido. 

### Recursos

#### Referencia: Artículos y Recursos

- [Formas de detectar un ataque de phishing](https://www.securitymetrics.com/blog/7-ways-recognize-phishing-email)
- [Ejemplos de ataques de phishing](https://www.phishing.org/phishing-examples)
- [MITRE ATT&CK](https://attack.mitre.org/techniques/T1566/)
- [CIRT Playbook Battle Cards](https://github.com/guardsight/gsvsoc_cirt-playbook-battle-cards/blob/master/Markdown/GSPBC-1002%20-%20Credential%20Access%20-%20Spearphishing%20-%20Phishing.md)
- [RE&CT](https://atc-project.github.io/atc-react/)## Playbook: Ransomware

**Investigar, remediar (contener, erradicar) y comunicar en paralelo!**
Asigne los pasos a individuos o equipos para que trabajen simultáneamente; este playbook no es puramente secuencial. Utilice su mejor criterio.

### Investigar

1. Identificar y confirmar la infección por ransomware.
    * Verifique la autenticidad del incidente investigando cualquier mensaje de rescate o signos de cifrado de archivos.
    * Determine el alcance de la infección identificando los sistemas y archivos afectados.
2. Recopilar información sobre el incidente.
    * Capture capturas de pantalla de los mensajes de rescate y registre cualquier otra actividad sospechosa.
    * Examine los registros del sistema y del servidor para identificar la fuente y el momento de la infección.
3. Evaluar el impacto del incidente.
    * Determine el impacto en la disponibilidad de los sistemas y archivos afectados.
    * Evalúe la sensibilidad de los datos cifrados y la importancia de los sistemas afectados para las operaciones comerciales.
4. Identificar la causa raíz del incidente.
    * Investigue cómo el ransomware pudo infiltrarse en la red y cifrar los archivos.
    * Analice las vulnerabilidades de seguridad explotadas y los vectores de ataque utilizados por los atacantes.

### Remediar

**Planificar la remediación** en la que estos pasos se pongan en marcha juntos (o de forma coordinada), con los equipos adecuados listos para responder a cualquier interrupción.

#### Contención

1. Detener la propagación del ransomware.
    * Aísle los sistemas comprometidos y desconéctelos de la red para evitar una mayor propagación.
    * Bloquee el tráfico malicioso y las conexiones de comando y control utilizadas por el ransomware.
2. Identificar y mitigar la amenaza.
    * Utilice herramientas de seguridad para identificar y eliminar el ransomware de los sistemas comprometidos.
    * Restaure los archivos cifrados desde copias de seguridad limpias y confiables.

#### Erradicación

1. Investigar la causa raíz del incidente.
    * Realice una revisión exhaustiva de la seguridad de la red y los sistemas para identificar las vulnerabilidades explotadas.
    * Corrija las vulnerabilidades identificadas y aplique parches de seguridad según sea necesario.
2. Implementar controles de seguridad adicionales.
    * Mejore la detección y la respuesta ante amenazas mediante la implementación de soluciones de seguridad avanzadas.
    * Realice auditorías de seguridad regulares y pruebas de penetración para identificar posibles puntos de entrada adicionales.

### Comunicar

**Comunicarse con las partes interesadas** para informar sobre el incidente y las acciones tomadas para mitigarlo.

1. Notificar a la dirección y al equipo de gestión de crisis.
    * Informe a los ejecutivos y a los responsables de la toma de decisiones sobre la naturaleza y el alcance del incidente.
    * Proporcione actualizaciones regulares sobre el progreso de la remediación y las medidas de seguridad implementadas.
2. Comunicarse con los usuarios y clientes.
    * Notifique a los usuarios sobre el incidente y las medidas tomadas para restaurar la seguridad de sus datos.
    * Proporcione orientación sobre cómo protegerse contra futuros ataques de ransomware y cómo recuperar datos cifrados.
3. Coordinar con las autoridades y reguladores pertinentes.
    * Notifique a las autoridades de protección de datos y cumpla con cualquier requisito de notificación obligatoria.
    * Colabore con las autoridades en la investigación del incidente y en la identificación de los responsables.

### Recursos

#### Herramientas y Tecnologías de Seguridad

- Soluciones de Antivirus y Antimalware
- Herramientas de Respuesta a Incidentes de Seguridad (SIEM)
- Soluciones de Copia de Seguridad y Recuperación de Datos
- Herramientas de Análisis de Malware y Sandboxing

#### Referencia: Artículos y Recursos

1. [No More Ransom Project](https://www.nomoreransom.org/) - Recursos y herramientas gratuitas para recuperar archivos cifrados por ransomware.
2. [Malwarebytes Labs](https://blog.malwarebytes.com/) - Blog con análisis de amenazas y consejos de seguridad contra ransomware y otros tipos de malware.
3. [National Cyber Security Centre (NCSC)](https://www.ncsc.gov.uk/) - Recursos y guías sobre cómo prevenir y responder a incidentes de ransomware.
## Playbook: Replication through Removable Media

### Investigar

- Supervisar las letras de unidad recién construidas o los puntos de montaje en medios extraíbles.
- Monitorizar los archivos inesperados a los que se accede en medios extraíbles.
- Vigilar los archivos recién construidos en medios extraíbles.
- Examinar los procesos recién ejecutados que se ejecutan desde medios extraíbles después de que se montan o cuando los inicia un usuario. Si se utiliza una herramienta de acceso remoto de esta manera para moverse lateralmente, es probable que se produzcan acciones adicionales después de la ejecución, como abrir conexiones de red para Comando y Control y Descubrimiento de información del sistema y de la red.

### Remediar

- Identificar y eliminar archivos maliciosos encontrados en medios extraíbles.
- Desconectar o bloquear el acceso a puertos USB y otros dispositivos de almacenamiento extraíbles en los sistemas afectados.
- Actualizar y parchear sistemas para cerrar posibles brechas de seguridad explotadas por el malware en medios extraíbles.
- Implementar políticas de seguridad claras y restricciones sobre qué dispositivos pueden conectarse y qué archivos pueden ser transferidos a través de medios extraíbles.

#### Contener

- Es importante analizar los archivos relacionados con el ataque en busca de información que pueda ayudar en la investigación. Esto puede incluir direcciones IP utilizadas por los atacantes, agentes de usuario que identifican los navegadores o herramientas utilizadas en el ataque, y detalles sobre las solicitudes de red realizadas durante el incidente.
- Fortalecer los activos críticos no afectados, con el objetivo de prevenir futuros ataques.
- En Windows 10, habilite las reglas de Reducción de superficie de ataque (ASR) para bloquear la ejecución de archivos ejecutables no firmados o que no sean de confianza (como .exe, .dll o .scr) desde unidades extraíbles USB. 
- Desactivar la ejecución automática si no es necesario.
- Aislar el sistema afectado de la red corporativa, con el objetivo que el malware presente en el dispositivo extraíble malicioso no se propague.

### Comunicar

- Notificar a los equipos pertinentes de la organización sobre el incidente de replicación a través de medios extraíbles, incluyendo detalles relevantes sobre el alcance y las medidas de contención tomadas.
- Informar a la alta dirección sobre el incidente, destacando los posibles impactos en la seguridad y las operaciones del negocio, así como las acciones tomadas para mitigar los riesgos asociados.
- Comunicar proactivamente con los usuarios afectados y otros empleados sobre el incidente, proporcionando pautas claras sobre cómo proceder y cómo protegerse de futuros incidentes similares.
- Coordinar la comunicación con partes externas relevantes, como socios comerciales o autoridades reguladoras, según sea necesario y en cumplimiento con las políticas de divulgación de la organización.

### Recuperación

- Restaurar hasta el Punto de Recuperación Objetivo (RPO) dentro del Tiempo de Recuperación Objetivo (RTO).
    - El RPO es el punto en el tiempo al que una organización está dispuesta a recuperarse después de un desastre. 
    -   El RTO es la cantidad de tiempo que una organización está dispuesta a tolerar para que sus servicios vuelvan a estar disponibles después de un desastre. 
- Restaurar los sistemas afectados a su última copia de seguridad limpia. Esto implica volver a un estado conocido y seguro antes del incidente, utilizando copias de seguridad verificadas para garantizar la integridad y la seguridad de los datos y sistemas restaurados.

### Recursos

#### Referencia: Artículos y Recursos

- [MITRE ATT&CK](https://attack.mitre.org/techniques/T1091/)
- [CIRT Playbook Battle Cards](https://github.com/guardsight/gsvsoc_cirt-playbook-battle-cards/blob/master/Markdown/GSPBC-1066%20-%20Initial%20Access%20-%20Replication%20Through%20Removable%20Media.md)
- [RE&CT](https://atc-project.github.io/atc-react/)## Playbook: Robo de Cookies de Sesión Web

**Investigar, remediar (contener, erradicar) y comunicar en paralelo!**
Asigne los pasos a individuos o equipos para que trabajen simultáneamente; este playbook no es puramente secuencial. Utilice su mejor criterio.

### Investigar

1. Identificar el incidente de robo de cookies de sesión web.
    * Recopile información sobre cómo se descubrió el incidente y qué indicadores lo señalan.
    * Confirme si se ha producido el robo de cookies de sesión y cuándo ocurrió.
2. Determinar el alcance del incidente.
    * Identifique qué sistemas o aplicaciones se ven afectados por el robo de cookies de sesión.
    * Evalúe el número de usuarios afectados y la sensibilidad de los datos comprometidos.
3. Recopilar evidencia forense.
    * Capture y preserve las cookies de sesión comprometidas para su análisis forense.
    * Registre los registros del servidor web y de aplicaciones relevantes para identificar la actividad maliciosa.
4. Identificar la causa raíz y el método de compromiso.
    * Determine cómo se llevaron a cabo el robo de cookies de sesión y la explotación de las vulnerabilidades.
    * Analice los vectores de ataque utilizados por los agresores y las posibles debilidades en la seguridad de la aplicación.
5. Evaluar el impacto del incidente.
    * Determine las posibles repercusiones para los usuarios afectados y para la seguridad de los datos de la empresa.
    * Evalúe el impacto en la confianza del cliente y la reputación de la empresa.

### Remediar

**Planificar la remediación** en la que estos pasos se pongan en marcha juntos (o de forma coordinada), con los equipos adecuados listos para responder a cualquier interrupción.

#### Contención

1. Revocar y regenerar todas las cookies de sesión comprometidas.
    * Implemente una nueva sesión de autenticación para todos los usuarios afectados.
    * Revise y actualice los mecanismos de autenticación y de gestión de sesiones para fortalecer la seguridad.
2. Restablecer las credenciales de acceso de los usuarios afectados.
    * Notifique a los usuarios sobre el incidente y solicite que cambien sus contraseñas de inmediato.
    * Implemente una política de contraseñas más robusta y fomenta el uso de autenticación de dos factores.
3. Implementar medidas de seguridad adicionales.
    * Refuerce las políticas de seguridad de la aplicación y aplique parches de seguridad según sea necesario.
    * Configure los sistemas de detección de intrusiones para monitorear la actividad maliciosa y los intentos de robo de cookies de sesión.

#### Erradicación

1. Investigar la causa raíz del incidente.
    * Realice una revisión exhaustiva de la arquitectura de seguridad de la aplicación y de las configuraciones del servidor para identificar las vulnerabilidades subyacentes.
    * Corrija cualquier brecha de seguridad identificada y fortalezca las defensas de la aplicación contra futuros ataques.
2. Realizar una revisión de seguridad completa.
    * Realice pruebas de penetración y auditorías de seguridad para identificar posibles puntos de entrada adicionales y áreas de vulnerabilidad.
    * Implemente medidas de seguridad adicionales según las recomendaciones de los auditores de seguridad.

### Comunicar

**Comunicarse con las partes interesadas** para informar sobre el incidente y las acciones tomadas para mitigarlo.

1. Notificar a la dirección y al equipo de gestión de crisis.
    * Informe a los ejecutivos y a los responsables de la toma de decisiones sobre la naturaleza y el alcance del incidente.
    * Proporcione actualizaciones regulares sobre el progreso de la remediación y las medidas de seguridad implementadas.
2. Comunicarse con los usuarios afectados.
    * Notifique a los usuarios sobre el incidente y proporcione instrucciones claras sobre cómo proteger sus cuentas y datos.
    * Ofrezca asistencia y recursos adicionales, como líneas directas de atención al cliente y sitios web de ayuda.
3. Coordinar con las autoridades y reguladores pertinentes.
    * Notifique a las autoridades de protección de datos y cumpla con cualquier requisito de notificación obligatoria.
    * Colabore con las autoridades en la investigación del incidente y en la identificación de los responsables.

### Recursos

#### Herramientas y Tecnologías de Seguridad

- Gestores de contraseñas seguras (LastPass, 1Password)
- Sistemas de autenticación de dos factores (Google Authenticator, Authy)
- Herramientas de detección de intrusiones (Snort, Suricata)
- Herramientas de análisis forense digital (Sleuth Kit, Autopsy)
- Escáneres de vulnerabilidad de aplicaciones web (Nessus, Acunetix)

#### Referencia: Artículos y Recursos

1. [OWASP Top 10](https://owasp.org/www-project-top-ten/) - Lista de las principales vulnerabilidades de seguridad en aplicaciones web.
2. [SANS Institute](https://www.sans.org/) - Recursos y formación en seguridad informática.
3. [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework) - Marco de trabajo para mejorar la seguridad cibernética de las organizaciones.
# Roles

A continuación se presentan las descripciones, los deberes y la formación para cada uno de los roles definidos en la respuesta a un incidente.

`TODO: Personalizar los roles, las descripciones, las funciones y la formación, si es necesario.`

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

1. Programe una reunión de revisión posterior a la acción (AAR) dentro de 5 días laborables e invite a los asistentes que figuran en https://netmancer.es/aar/asistentes. Incluya siempre a los siguientes:
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

