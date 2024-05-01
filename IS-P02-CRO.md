
> [!NOTE] Aclaración
> La pregunta **1.a** se ha separado del resto de la preguntas y se ha contestado en la sección "**Memoria**". El resto de preguntas está a continuación de esta sección y comienzan siempre por tanto a partir de la cuestión **1.b**.

# 1. SOC210 - Possible Brute Force Detected on VPN
## Clasificación

| **Taxonomía**    | VPN Bruteforce attack                                                                                                       |
| ---------------- | --------------------------------------------------------------------------------------------------------------------------- |
| **Criticidad**   | Alta                                                                                                                        |
| **Descripción**  | Se ha detectado un inicio de sesión válido por VPN tras múltiples intentos fallidos provenientes de una misma dirección IP. |
| **Fecha y hora** | Apr, 13, 2024, 10:10 PM                                                                                                     |

## Memoria

En primer lugar se debe determinar si la IP es externa o interna, para ello buscamos en "**Endpoint security**" si existen instancias de esa IP en nuestra red. Comprobamos que no, por lo que deberá ser externa.

![](./img/Pasted%20image%2020240413203245.png)

Tras ello, se comprueba si la IP es sospechosa o no. Utilizamos herramientas como *VirusTotal, AbuseIPDB* o la herramienta de la plataforma *Threat Intel*. 

![](./img/Pasted%20image%2020240413203501.png)

![](./img/Pasted%20image%2020240413204016.png)

![](./img/Pasted%20image%2020240413204033.png)

De las 3, solamente *AbuseIPDB* nos marca como reportada la IP un total de **23** veces. En *VirusTotal* solo tenemos un proveedor que nos indica que es maliciosa y en nuestra base de datos de inteligencia (*Threat Intel*) no tenemos nada referente a ella.

Aunque *VirusTotal* y *Threat Intel* no nos dan indicios de que sea peligrosa, las 23 veces que ha sido reportadas son suficientes como para considerarla sospechosa, por lo que la marcaremos como tal.

Determinamos luego si la IP sospechosa hacia peticiones a los puertos de SSH o RDP, y vemos en los logs que no.

![](./img/Pasted%20image%2020240413205121.png)

Después, el playbook nos sugiere revisar logs de SSH/RDP, pero en este caso sabemos que todos los intentos de autenticación por parte de esa IP van dirigidos al puerto 443 de SSL. 

Se nos pregunta si el ataque de fuerza bruta fue exitoso, y creemos **que efectivamente sí lo fue**, por que se ha detectado un inicio de sesión válido, pero no a través de **SSH o RDP**.

![](./img/Pasted%20image%2020240413205403.png)
Tenemos un evento en el log de eventos que indica que el usuario ha conseguido acceder:

![](./img/Pasted%20image%2020240413211227.png)

Investigando los logs, se puede comprobar como esta IP ha intentado autenticarse con varios usuarios:

- sane@letsdefend.io
- mane@letsdefend.io
- zane@letsdefend.io (Éste incluso tras haberse autenticado)

Tras ver estos datos, concluimos el playbook y establecemos que esta alerta es un **Verdadero positivo** y efectivamente un atacante con la IP sospechosa se ha conseguido autenticar.
## Preguntas

- **1.b  ¿Cuál es el proceso de investigación seguido para investigar el incidente y que evidencias han sido clave para la resolución del incidente?**
El proceso de investigación seguido para investigar el incidente comenzó con la determinación de si la IP involucrada era interna o externa, utilizando la herramientas de Endpoint security para buscar instancias de la IP en la red interna. Al no encontrar ninguna instancia, se concluyó que era una IP externa. Luego, se utilizó una variedad de herramientas como VirusTotal, AbuseIPDB y Threat Intel para determinar la peligrosidad de la IP. Aunque VirusTotal y Threat Intel no mostraron indicios de riesgo, la IP fue reportada 23 veces en AbuseIPDB, lo que la marcó como sospechosa.

Se verificó si la IP sospechosa realizaba peticiones a puertos de SSH o RDP, lo cual no se evidenció en los logs. Sin embargo, se detectó un inicio de sesión válido a través del puerto 443 de SSL, lo que llevó a concluir que el ataque de fuerza bruta fue exitoso. 

La evidencia clave para la resolución del incidente fueron **los logs** que mostraban los intentos de autenticación con diferentes usuarios, confirmando que el atacante logró acceder.

- **2.a Durante la resolución del incidente ¿has tenido que realizar algún tipo de actuación para el restablecimiento de servicios afectados por el incidente, con el objetivo de volver a la normalidad?**
Durante la resolución del incidente, no se menciona específicamente ninguna acción para restablecer los servicios afectados. Probablemente, esto se deba a que el incidente no afectó directamente a los servicios, sino que se trató de un intento de acceso no autorizado.

- **3.a Tras trabajar en la resolución del incidente ¿Que acciones/actuaciones destacadas se han realizado para solucionar el incidente?**
Las acciones destacadas realizadas para solucionar el incidente incluyeron la identificación de la IP como sospechosa, la confirmación del ataque de fuerza bruta exitoso a través del puerto 443 de SSL y la recolección de evidencia a partir de los registros de eventos. Además, se concluyó que se trató de un verdadero positivo y se determinó que un atacante logró acceder a través de los intentos de autenticación exitosos.

- **3.b Realizar un proceso de análisis de las actuaciones llevadas a cabo y obtener un registro de lecciones aprendidas, para finalmente concluir en las posibles mejoras que podrías plantear para tu plan/playbooks desarrollado en la práctica anterior.**
En el proceso de análisis de las actuaciones llevadas a cabo, se podría destacar la importancia de una detección temprana de amenazas mediante herramientas de seguridad, así como la necesidad de mantener registros detallados de eventos para una investigación efectiva. Como mejora para el plan/playbooks desarrollado en la práctica anterior, se podría considerar la implementación de medidas de mitigación proactiva, como el bloqueo automático de IP sospechosas después de cierto número de intentos fallidos de autenticación.

- **4.a Seguro que en el proceso de análisis para obtener un registro de lecciones aprendidas anterior, has pensado como evitar que una situación similar se vuelva a repetir. ¿Que actuaciones has decidido para evitar que se pueda dar una situación similar**

Para evitar que una situación similar se repita, se podrían implementar las siguientes medidas:
1. Actualización regular de los sistemas y aplicaciones para cerrar posibles vulnerabilidades que puedan ser explotadas por atacantes.
2. Implementación de políticas de contraseñas robustas y la activación de la autenticación multifactor (MFA) para hacer más difícil el acceso no autorizado incluso en caso de fuerza bruta.
3. Configuración en el sistema de prevención de intrusiones (IPS) para detectar y bloquear intentos muy repetidos de autenticación.

# 2. SOC251 - Quishing Detected (QR Code Phishing)

## Clasificación

| **Taxonomía**    | Quishing (QR Code Phising)                                                     |
| ---------------- | ------------------------------------------------------------------------------ |
| **Criticidad**   | Media                                                                          |
| **Descripción**  | Se ha detectado un email sospechoso de ser *quishing* (phishing con código QR) |
| **Fecha y hora** | Jan, 01, 2024, 12:37 PM                                                        |

## Memoria

En primer lugar se nos pide analizar los logs relevantes para el caso. Comprobando el registro de logs con la herramienta "*Log Management*" encontramos el siguiente que parece contener la info necesaria:

![](./img/Pasted%20image%2020240413232809.png)

Además se revisa el correo y se encuentra el código QR malicioso. Se escanea y encontramos la siguiente URL:

```
https://ipfs.io/ipfs/Qmbr8wmr41C35c3K2GfiP2F8YGzLhYpKpb4K66KU6mLmL4#
```

Esta URL pertenece a la aplicación **InterPlanetary File System**, lo que parece una especie de protocolo de transferencia de archivos. Esto es un claro indicador de riesgo debido a la naturaleza de esta aplicación, es probable que la intención del atacante fuera acceder a los archivos de este ordenador. 

![](./img/Pasted%20image%2020240413233453.png)

De entre las opciones que se nos plantean, la aparentemente más correcta es la opción de recolectar información del host víctima.

![](./img/Pasted%20image%2020240413233607.png)

Luego se nos pregunta si la IP es externa o interna, nuevamente vamos a comprobar las IP locales para ver si coincide con la que hemos encontrado en los logs.

![](./img/Pasted%20image%2020240413233900.png)

Y parece que es externa.

Comprobamos también la IP en nuestras herramientas habituales para testear la fiabilidad de las mismas: VirusTotal, AbuseIPDB y Threat Intel.

![](./img/Pasted%20image%2020240413234312.png)
![](./img/Pasted%20image%2020240413234539.png)


Comprobamos que efectivamente esta IP es sospechosa de concretamente *phising* según las herramientas. 

Comprobamos también la cantidad de dispositivos afectados en este incidente, revisamos los logs en busca de la misma IP o de la IP de la máquina afectada:

![](./img/Pasted%20image%2020240413234821.png)
Y se revisa que la IP de la máquina afectada no haya realizado conexiones extrañas o haya enviado otros emails de phising.
Finalmente se comprueba que parece ser que es la única máquina afectada.

Se comprueba también el historial de búsqueda web del ordenador afectado y existen muchas URLs visitadas no relacionadas con el trabajo. Quizá esas búsquedas hayan causado su filtración de email y el consecutivo ataque de phishing.
 ![](./img/Pasted%20image%2020240413235451.png)

Finalmente se determina el **Verdadero positivo** que el equipo debe quedar en contención.


## Preguntas

- **1.b  ¿Cuál es el proceso de investigación seguido para investigar el incidente y que evidencias han sido clave para la resolución del incidente?**
El proceso de investigación seguido para investigar el incidente comenzó con el análisis de los logs relevantes utilizando la herramienta de "**Log Management**". 

Se identificó un código QR malicioso en un correo electrónico, el cual conducía a una URL sospechosa en el protocolo **IPFS** (InterPlanetary File System), el cual es P2P, por lo que ya había indicios de posible intención de acceso a los archivos de la víctima, esto fue una pista clave. 

Se confirmó la IP como externa. Luego, se utilizaron herramientas como VirusTotal, AbuseIPDB y Threat Intel para verificar la peligrosidad de la IP, confirmando que era sospechosa de phishing por VirusTotal. 

Se investigó la cantidad de dispositivos afectados, encontrando que solo una máquina estaba comprometida. Además, se revisó el historial de búsqueda web de la máquina afectada, encontrando URLs no relacionadas con el trabajo que podrían haber causado la filtración de email y el consecuente ataque de phishing. 

La evidencia clave para la resolución del incidente fue la identificación del código QR malicioso y la confirmación de la IP como sospechosa mediante herramientas de seguridad.

- **2.a Durante la resolución del incidente ¿has tenido que realizar algún tipo de actuación para el restablecimiento de servicios afectados por el incidente, con el objetivo de volver a la normalidad?**
Durante la resolución del incidente se aisla la máquina afectada. Esto puede deberse a que el incidente no afectó directamente a los servicios, sino que se centró en la compromisión de una máquina específica.

- **3.a Tras trabajar en la resolución del incidente ¿Que acciones/actuaciones destacadas se han realizado para solucionar el incidente?**
Tras trabajar en la resolución del incidente, se realizaron las siguientes acciones destacadas:

- Identificación del código QR malicioso y la URL sospechosa.
- Verificación del origen externo de la IP asociada al incidente.
- Confirmación de la sospecha de phishing mediante herramientas de seguridad.
- Investigación para determinar la cantidad de dispositivos afectados y encontrar que solo una máquina estaba comprometida.
- Análisis del historial de búsqueda web de la máquina afectada para identificar posibles vectores de ataque.
- Conclusión de que se trató de un verdadero positivo y la decisión de dejar al equipo en contención.

- **3.b Realizar un proceso de análisis de las actuaciones llevadas a cabo y obtener un registro de lecciones aprendidas, para finalmente concluir en las posibles mejoras que podrías plantear para tu plan/playbooks desarrollado en la práctica anterior.**
En el proceso de análisis de las actuaciones llevadas a cabo, se destaca la importancia de una respuesta rápida y precisa ante incidentes de seguridad. Se podría mejorar el proceso de detección temprana de amenazas mediante la implementación de herramientas de monitoreo más avanzadas y la capacitación continua del personal en prácticas de seguridad informática.

Además, se podría fortalecer la seguridad de la red mediante la implementación de políticas de acceso más estrictas y la actualización regular de sistemas y aplicaciones para cerrar posibles brechas de seguridad.

- **4.a Seguro que en el proceso de análisis para obtener un registro de lecciones aprendidas anterior, has pensado como evitar que una situación similar se vuelva a repetir. ¿Que actuaciones has decidido para evitar que se pueda dar una situación similar**
Para evitar que una situación similar se repita, se pueden tomar las siguientes medidas:

1. Implementación de filtros de correo electrónico más estrictos para detectar y bloquear mensajes de phishing antes de que lleguen a las bandejas de entrada de los usuarios.
2. Capacitación del personal en prácticas seguras de navegación web y en la identificación de correos electrónicos sospechosos.
3. Monitoreo continuo del tráfico de red y del comportamiento de los sistemas para detectar actividades sospechosas de manera proactiva.
4. Actualización periódica de políticas de seguridad para adaptarse a las nuevas amenazas y vulnerabilidades.

# 3. SOC202 - FakeGPT Malicious Chrome Extension

## Clasificación

| **Taxonomía**    | Data Leakage                                                                                                                                  |
| ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| **Criticidad**   | Alta                                                                                                                                          |
| **Descripción**  | Uno de los empleados ha instalado una extensión para el navegador chrome y se ha detectado un comportamiento malicioso por parte de la misma. |
| **Fecha y hora** | May, 29, 2023, 01:01 PM                                                                                                                       |

## Memoria

En un primer reconocimiento del incidente, vamos al ordenador afectado utilizando **Endpoint security** y revisamos su historial web, encontrando que a las **13:01:44** instaló efectivamente la extensión de chrome y luego el usuario buscó información en el soporte de google acerca de problemas con extensiones.

Es llamativo que su historial de terminal está vacío y que en su actividad de red se observa que a las **13:02:47** realizó conexiones a lo que parece una IP pública (**52.76.101.124**) y otras dos más. De las cuales se descarta **172.217.17.142** debido a que existen otros dos equipos que han realizado conexiones a esta IP, sin embargo,  el equipo de samuel es el único que ha realizado conexion a **18.140.6.45**.

![](./img/Pasted%20image%2020240414025456.png)

Tras revisar los logs y el endpoint afectado (equipo de *Samuel*), se determina que el malware **no** está puesto en cuarentena.

Ingresamos la URL en VirusTotal, HybridAnálisis, URLhaus y urlscan, y la única que determina que es malware es VirusTotal
![](./img/Pasted%20image%2020240414030156.png)

Buscamos también la extensión en chrome-stats 

![](./img/Pasted%20image%2020240414030302.png)

Y esta web determina que la extensión fue eliminada de la store de chrome debido a que contenía malware.

Se nos pregunta si existen indicios de un C2 (*Command and control*) al haber accedido a una dirección maliciosa. Como previamente miramos las conexiones, muy posiblemente la posible IP pública sea maliciosa, por lo que determinamos que efectivamente se ha producido. 

Por ello se determina aislar la máquina de la red inmediatamente desde "**Endpoint Security**":

![](./img/Pasted%20image%2020240414031510.png)
## Preguntas

- **1.b  ¿Cuál es el proceso de investigación seguido para investigar el incidente y que evidencias han sido clave para la resolución del incidente?**
El proceso de investigación seguido para investigar el incidente comenzó con el análisis del historial web y del historial de terminal del equipo afectado utilizando Endpoint Security. Se identificó que el usuario instaló una extensión de Chrome y buscó información sobre problemas con extensiones poco antes de que se realizaran conexiones a una IP pública sospechosa. 

Se determinó que la extensión había sido eliminada de la Chrome Web Store debido a su contenido malicioso. Además, se ingresó la URL en varias herramientas de análisis de malware, donde solo VirusTotal detectó la URL como maliciosa. Pero fue más determinante aún que la web chrome-stats determinase que efectivamente esa extensión fue incluso removida por contener malware. 

La evidencia clave para la resolución del incidente fue la detección de la instalación de la extensión maliciosa y las conexiones a la IP pública sospechosa, así como la confirmación de que la extensión había sido eliminada de la Chrome Web Store por contener malware.

- **2.a Durante la resolución del incidente ¿has tenido que realizar algún tipo de actuación para el restablecimiento de servicios afectados por el incidente, con el objetivo de volver a la normalidad?**
Durante la resolución del incidente, se realizó una acción importante para aislar la máquina afectada de la red inmediatamente utilizando Endpoint Security.

- **3.a Tras trabajar en la resolución del incidente ¿Que acciones/actuaciones destacadas se han realizado para solucionar el incidente?**
Tras trabajar en la resolución del incidente, se realizaron las siguientes acciones destacadas:

- Análisis del historial web y del historial de terminal del equipo afectado para identificar actividades sospechosas.
- Verificación de la eliminación de la extensión maliciosa de la Chrome Web Store y confirmación de su naturaleza maliciosa mediante herramientas de análisis de malware.
- Identificación de conexiones a una IP pública sospechosa, lo que sugiere la presencia de un posible C2 (Command and Control).
- Aislamiento inmediato del equipo afectado de la red para prevenir la propagación del malware.

- **3.b Realizar un proceso de análisis de las actuaciones llevadas a cabo y obtener un registro de lecciones aprendidas, para finalmente concluir en las posibles mejoras que podrías plantear para tu plan/playbooks desarrollado en la práctica anterior.**
En el proceso de análisis de las actuaciones llevadas a cabo, se destaca la importancia de una respuesta rápida y proactiva ante incidentes de seguridad. Se podría mejorar el proceso de detección temprana de malware mediante la implementación de herramientas de monitoreo más avanzadas y la automatización de la respuesta a incidentes. Además, se podría fortalecer la conciencia de seguridad del usuario final mediante la capacitación regular en prácticas seguras de navegación web y en la identificación de señales de posibles amenazas.

- **4.a Seguro que en el proceso de análisis para obtener un registro de lecciones aprendidas anterior, has pensado como evitar que una situación similar se vuelva a repetir. ¿Que actuaciones has decidido para evitar que se pueda dar una situación similar**
Se pueden tomar las siguientes medidas:

1. Implementación de políticas de seguridad más estrictas en la instalación de extensiones de navegador, con revisiones y aprobaciones previas antes de su instalación.
2. Monitoreo continuo del tráfico de red para detectar y bloquear conexiones a IP públicas sospechosas.
3. Actualización regular de herramientas de seguridad y bases de datos de amenazas para garantizar una detección efectiva de malware.
4. Reforzamiento de la educación y conciencia del usuario final sobre las amenazas de seguridad en línea y la importancia de informar cualquier actividad sospechosa a los equipos de seguridad informática.

# 4. SOC170 - Passwd Found in Requested URL - Possible LFI Attack

## Clasificación

| **Taxonomía**    | Ataque Web  (LFI ,Local File Intrusion)                                                       |
| ---------------- | --------------------------------------------------------------------------------------------- |
| **Criticidad**   | Alta                                                                                          |
| **Descripción**  | Se ha detectado una URL maliciosa que podría indicar un ataque LFI a uno de nuestros equipos. |
| **Fecha y hora** | Mar, 01, 2022, 10:10 AM                                                                       |

## Memoria
En una primera instancia se detecta una petición a la siguiente URL:

```
https://172.16.17.13/?file=../../../../etc/passwd
```

Que es claramente un intento malicioso de conseguir el archivo `/etc/passwd` de la máquina objetivo (esta misma tarde exploté una máquina utilizando esta vulnerabilidad). 

Revisando los logs, se comprueba que la respuesta del servidor fue un código 500 (error interno del servidor), por lo que es posible que este ataque fallara:

![](./img/Pasted%20image%2020240414033327.png)

Además, es de notar el tamaño de la respuesta HTTP, el cual es 0, por lo que es muy probable que efectivamente el ataque no se efectuara con éxito.

La cuestión aquí igualmente es determinar si se trata de un falso positivo o no, es posible que un **test de penetración programado** haya provocado esta incidencia.

Buscamos emails que involucren el nombre del servidor atacado o algo referente a pruebas de penetración y no encontramos nada.

![](./img/Pasted%20image%2020240414033611.png)

También debemos comprobar para verificar si es un falso positivo o no que el host contenga el nombre de alguno de los simuladores de ataque (*Verodin, AttackIQ, Picus*), sin embargo no hay rastro de ellos, por lo que se verifica como **positiva** la incidencia.

Se nos pide determinar la dirección del tráfico, y entre las tres opciones posibles la correcta es **Internet → Company Network** ya que la IP **106.55.45.162** no se encuentra en nuestra Red:

![](./img/Pasted%20image%2020240414034206.png)

Se nos pregunta si el ataque fue exitoso, pero previamente mediante el análisis de la respuesta HTTP vemos que con casi total seguridad no fue exitoso.

Se nos pregunta también si necesitamos escalar al **Tier 2**, lo cual sucede en caso de que un ataque tenga éxito o si el atacante ha llegado a comprometer una máquina (en caso de ataque con tráfico interno). Ninguno de los dos casos es cierto, por lo que **NO** escalamos.

![](./img/Pasted%20image%2020240414034510.png)

## Preguntas

- **1.b  ¿Cuál es el proceso de investigación seguido para investigar el incidente y que evidencias han sido clave para la resolución del incidente?**
El proceso de investigación seguido para investigar el incidente comenzó con la detección de una solicitud maliciosa a una URL específica que intentaba acceder al archivo `/etc/passwd` de la máquina objetivo. 

Se verificó en los logs que el servidor respondió con un código de **error interno del servidor (500)** y que el tamaño de la respuesta HTTP fue **0**, lo que sugiere que el ataque no fue exitoso. 

Se buscó evidencia adicional en correos electrónicos relacionados con pruebas de penetración o nombres de simuladores de ataque, pero no se encontró nada relevante.

Además, se verificó que la dirección IP involucrada no estaba en la red interna de la empresa. La falta de evidencia de un test de penetración programado y la ausencia de simuladores de ataque en el entorno llevaron a determinar que la incidencia era positiva y no un falso positivo.

- **2.a Durante la resolución del incidente ¿has tenido que realizar algún tipo de actuación para el restablecimiento de servicios afectados por el incidente, con el objetivo de volver a la normalidad?**
Durante la resolución del incidente, no se menciona ninguna acción específica para restablecer servicios afectados. Esto puede deberse a que el ataque no tuvo éxito y no causó ningún impacto en los servicios o sistemas. De hecho se decidió no ascender a **Tier 2**.

- **3.a Tras trabajar en la resolución del incidente ¿Que acciones/actuaciones destacadas se han realizado para solucionar el incidente?**
Tras trabajar en la resolución del incidente, las acciones destacadas que se realizaron para solucionar el incidente incluyeron:

- Investigación detallada del evento y verificación de la **respuesta del servidor HTTP**.
- Búsqueda de **evidencia adicional en correos electrónicos y en el entorno de red** para determinar la naturaleza del incidente.
- Confirmación de que el ataque no fue exitoso y determinación de que **no era necesario escalar al Tier 2.**

- **3.b Realizar un proceso de análisis de las actuaciones llevadas a cabo y obtener un registro de lecciones aprendidas, para finalmente concluir en las posibles mejoras que podrías plantear para tu plan/playbooks desarrollado en la práctica anterior.**
En el proceso de análisis de las actuaciones llevadas a cabo, se destaca la importancia de una detección temprana y una respuesta rápida a incidentes de seguridad. 

Se pudo mejorar la eficacia de la detección mediante la implementación de herramientas de monitoreo más avanzadas y la automatización de la respuesta a eventos sospechosos. 

Además, se podría fortalecer la capacitación del personal en la identificación de posibles amenazas y en la respuesta adecuada ante incidentes de seguridad.

- **4.a Seguro que en el proceso de análisis para obtener un registro de lecciones aprendidas anterior, has pensado como evitar que una situación similar se vuelva a repetir. ¿Que actuaciones has decidido para evitar que se pueda dar una situación similar**
Se pueden tomar las siguientes medidas:

1. Actualización regular de sistemas y aplicaciones para cerrar posibles vulnerabilidades que puedan ser explotadas por atacantes.
2. Fortalecimiento de las políticas de seguridad para limitar el acceso a recursos sensibles y reducir la superficie de ataque.

# 5. SOC169 - Possible IDOR Attack Detected

## Clasificación

| **Taxonomía**    | Ataque Web (Posible ataque IDOR)                                                              |
| ---------------- | --------------------------------------------------------------------------------------------- |
| **Criticidad**   | Media                                                                                         |
| **Descripción**  | Se ha detectado una URL maliciosa que podría indicar un ataque LFI a uno de nuestros equipos. |
| **Fecha y hora** | Feb, 28, 2022, 10:48 PM                                                                       |

## Memoria
Se ha recibido varias peticiones sospechosas con la URL aparentemente maliciosa y de construcción frecuente en ataques de tipo IDOR (Insecure direct object reference), en el cual se solicita un recurso específico a través de su ID o nombre, por inferencia o descubrimiento.

El equipo afectado por este incidente es el **WebServer1005** con IP **172.16.17.15**, la petición proviene de una IP **134.209.118.137** identificada como externa al no pertencer a la red local:

![](./img/Pasted%20image%2020240414041918.png)

Se pasa a comprobar esta IP con herramientas como VirusTotal, AbuseIPDB y Cisco Talos
![](./img/Pasted%20image%2020240414042314.png)

![](./img/Pasted%20image%2020240414042322.png)
![](./img/Pasted%20image%2020240414042405.png)

En este caso, el único que categoriza la IP como "*Poor*" es *Cisco Talos*, tanto VirusTotal como AbuseIPDB la verifican como una IP sin peligro. 

Para terminar de asegurarnos vamos a revisar los logs para ver en detenimiento las peticiones que se han realizado y revisandolas descubrimos que en el cuerpo de la petición POST se indica el parámetro `?user_id=1`, al revisar las demás vemos que efectivamente se observa un patrón de ataque en el que se está probando usuarios.

![](./img/Pasted%20image%2020240414043131.png)
![](./img/Pasted%20image%2020240414043151.png)

Con estos indicadores de compromiso creo que es suficiente para identificar la IP como maliciosa y confirmar el ataque IDOR. 

Además podemos confirmar también que el atacante tuvo éxito en varios intentos, ya que recibe una respuesta con un tamaño considerable y un código HTTP de respuesta 200 (éxito).

Se determina pues poner en contención al equipo desde **Endpoint Security**.

![](./img/Pasted%20image%2020240414043456.png)

Además se nos pregunta si es necesario ascender a **Tier 2** el nivel de alerta. Efectivamente, esta vez es necesario porque estamos en un escenario donde el atacante ha conseguido éxito en su intento de explotación, lo cual es suficiente para elevar el nivel de alarma.

![](./img/Pasted%20image%2020240414043628.png)
## Preguntas

- **1.b  ¿Cuál es el proceso de investigación seguido para investigar el incidente y que evidencias han sido clave para la resolución del incidente?**
El proceso de investigación seguido para investigar el incidente comenzó con la detección de varias peticiones sospechosas con una URL que se asemejaba a un ataque de tipo IDOR (Insecure Direct Object Reference). 

Se identificó que el equipo afectado era el *WebServer1005* con la IP *172.16.17.15* y que las peticiones provenían de una IP externa, *134.209.118.137*. Se verificó la reputación de la IP utilizando herramientas como VirusTotal, AbuseIPDB y Cisco Talos, donde solo Cisco Talos la categorizó como "Poor". 

Se procedió a revisar los logs para examinar en detalle las peticiones realizadas, y se descubrió un patrón de ataque en el cuerpo de las solicitudes POST que indicaban la prueba de diferentes usuarios. 

Se confirmó que el atacante había tenido éxito en varios intentos debido a los códigos HTTP y el teamño de la respuesta, lo que llevó a identificar la IP como maliciosa y confirmar el ataque **IDOR**.

- **2.a Durante la resolución del incidente ¿has tenido que realizar algún tipo de actuación para el restablecimiento de servicios afectados por el incidente, con el objetivo de volver a la normalidad?**
Durante la resolución del incidente, se tomó la acción de poner en contención al equipo afectado desde Endpoint Security para prevenir la propagación del ataque y proteger otros sistemas de la red. 

Al ser un servidor web, el servicio habrá quedado deshabilitado temporalmente hasta que se solucione el problema con el IDOR por parte del equipo de desarrollo. Hasta que la vulnerabilidad no esté parcheada es necesario mantener el servicio restringido, y cuando lo esté, deberá volver a habilitarse para la vuelta a la normalidad.

- **3.a Tras trabajar en la resolución del incidente ¿Que acciones/actuaciones destacadas se han realizado para solucionar el incidente?**
Las acciones destacadas que se realizaron para solucionarlo incluyeron:

- Identificación de la naturaleza del ataque mediante la revisión detallada de las peticiones sospechosas y los logs del servidor.
- Confirmación del éxito del ataque mediante la observación de respuestas con un tamaño considerable y códigos HTTP de respuesta 200.
- Aislamiento del equipo afectado para evitar daños adicionales desde Endpoint Security.
- Evaluación de la necesidad de escalar el nivel de alerta al Tier 2 debido al éxito del ataque.

- **3.b Realizar un proceso de análisis de las actuaciones llevadas a cabo y obtener un registro de lecciones aprendidas, para finalmente concluir en las posibles mejoras que podrías plantear para tu plan/playbooks desarrollado en la práctica anterior.**
Para nuestros playbooks mediante este y el anterior incidente se puede comprobar que, a pesar de tener nuestra empresa un servidor web y basar su lógica de negocio en él, se han elaborado muy pocos playbooks concretos para la gran cantidad de ataques web que existen, siendo tan específicos como este.

Es fundamental elaborar elaborar playbooks específicos para este tipo de vulnerabilidades que añadan acciones concretas para responder como revisar concretamente el peso de las peticiones HTTP o los códigos de respuesta, además de comprobar la dirección del tráfico, relacionarla con el nivel de alarma ( en nuestro caso NETCOM en lugar de Tier) y hacer un paso a paso detallado de cómo reaccionar ante este tipo de incidentes.

- **4.a Seguro que en el proceso de análisis para obtener un registro de lecciones aprendidas anterior, has pensado como evitar que una situación similar se vuelva a repetir. ¿Que actuaciones has decidido para evitar que se pueda dar una situación similar**
Para evitar que una situación similar se repita, se pueden tomar las siguientes medidas:

1. Implementación de controles de acceso adecuados para evitar vulnerabilidades de tipo IDOR, como validar y autorizar adecuadamente las solicitudes de recursos.
2. Monitoreo continuo de los registros de actividad del servidor y la red para detectar y responder rápidamente a actividades sospechosas.
3. Capacitación regular del personal de desarrollo en prácticas seguras y en la identificación de posibles amenazas de seguridad.
4. Implementación de políticas de seguridad que limiten el acceso a recursos sensibles y protejan contra ataques de enumeración de usuarios y otras técnicas de explotación comunes.
5. Detección de patrones en el cuerpo de solucitudes HTTP de tipo POST 
# 6. ⭐ SOC175 - PowerShell Found in Requested URL - Possible CVE-2022-41082 Exploitation

## Clasificación

| **Taxonomía**    | Ataque Web (Posible SSRF), CVE-2022-41082                                                                                                 |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| **Criticidad**   | Alta                                                                                                                                      |
| **Descripción**  | Se ha detectado la inclusión de una invocación de Powershell en una de las peticiones HTTP recibidas. Esta vulnerabilidad es una zero-day |
| **Fecha y hora** | Sep, 30, 2022, 07:19 AM                                                                                                                   |

## Memoria

Tenemos una URL que contiene lo siguiente:

```
/autodiscover/autodiscover.json?@evil.com/owa/&Email=autodiscover/autodiscover.json%3f@evil.com&Protocol=XYZ&FooProtocol=Powershell
```

Esto es un intento de activar una powershell de manera remota en la máquina. Además el incidente indica que se trata del CVE-2022-41082, que permite al atacante acceder a ubicaciones restringidas a través de un SSRF. Podemos concluir por aquí que debemos buscar indicios de SSRF en la máquina como IP internas de nuestra red que no deberían ser accesibles o usuales, muchas conexiones o conexiones extrañas.

Sin duda la URL es maliciosa por sus características, vamos a buscarla en los logs:

![](./img/Pasted%20image%2020240414050548.png)

Vemos 3 instancias de peticiones de esta IP a una de nuestras máquinas, con fecha del 30 de Septiembre de 2022 además lo que cuadra con el incidente. Si nos paramos a revisar, vemos como en las solicitudes GET parece que ha comprobado si existe "`/autodiscover/autodiscover.json`" y luego ha intentado dos veces utilizar la URL maliciosa con la powershell incorporada:
![](./img/Pasted%20image%2020240414050806.png)
![](./img/Pasted%20image%2020240414050828.png)

En estos logs además puede verse como las peticiones han sido bloquedas, por lo que es muy probable que el atacante no haya tenido éxito en sus intentos. 

Se nos pregunta si la URL es maliciosa, y con seguridad podemos afirmar que efectivamente lo es. Luego también se nos pregunta que tipo de ataque es. Como en la lista no está SSRF,  el correcto debe ser "Other". 

![](./img/Pasted%20image%2020240414051130.png)

Debemos comprobar si este incidente puede deberse a un test de penetración planeado. Nuevamente buscamos emails que incluyan el nombre del servidor afectado, palabra clave como "penetration test" o "test" a secas, y no tenemos rastro de nada de eso.
![](./img/Pasted%20image%2020240414051413.png)
![](./img/Pasted%20image%2020240414051441.png)

Determinamos que el ataque no ha sido exitoso ya que las peticiones han sido bloqueadas y que tampoco ha sido un test planeado, por lo que no estamos ante un **falso positivo**.

## Preguntas

- **1.b  ¿Cuál es el proceso de investigación seguido para investigar el incidente y que evidencias han sido clave para la resolución del incidente?**
El proceso de investigación seguido para investigar el incidente comenzó con la detección de una URL maliciosa que indicaba un intento de activar una PowerShell de manera remota en la máquina. Se identificó que se trataba del CVE-2022-41082, que explota una vulnerabilidad SSRF (Server-Side Request Forgery). 

Se procedió a buscar indicios de SSRF en la máquina, como conexiones a IP internas de la red o conexiones inusuales. Se encontraron tres instancias de solicitudes a una de nuestras máquinas desde una IP externa, coincidiendo con el incidente reportado. 

Se examinaron los logs y se observó que las solicitudes fueron bloqueadas, lo que sugiere que el atacante no tuvo éxito en sus intentos. Se determinó que la URL era maliciosa y se identificó el tipo de ataque como "Other", ya que no estaba especificado en la lista proporcionada. Se buscó evidencia de un test de penetración planeado, pero no se encontró nada relevante. 

Se concluyó que el incidente no fue un falso positivo.


- **2.a Durante la resolución del incidente ¿has tenido que realizar algún tipo de actuación para el restablecimiento de servicios afectados por el incidente, con el objetivo de volver a la normalidad?**

Durante la resolución del incidente, no se menciona ninguna acción específica para restablecer servicios afectados, ya que las solicitudes maliciosas fueron bloqueadas y no causaron daños significativos.

- **3.a Tras trabajar en la resolución del incidente ¿Que acciones/actuaciones destacadas se han realizado para solucionar el incidente?**
Tras trabajar en la resolución del incidente, se destacan las siguientes acciones/actuaciones:

- Identificación y análisis de la URL maliciosa y de las solicitudes asociadas en los logs del servidor.
- Confirmación de que las solicitudes fueron bloqueadas, lo que indicaba que el atacante no tuvo éxito en sus intentos de activar la PowerShell de manera remota.
- Determinación de que el incidente no fue un falso positivo y de que no se trató de un test de penetración planeado.

- **3.b Realizar un proceso de análisis de las actuaciones llevadas a cabo y obtener un registro de lecciones aprendidas, para finalmente concluir en las posibles mejoras que podrías plantear para tu plan/playbooks desarrollado en la práctica anterior.**
He podido darme cuenta de que en nuestros playbooks no consideramos si estamos ante un posible test de penetración o no en ningún momento, por lo que sería muy adecuado añadirlo. 

También determinar el flujo del tráfico es importante y no lo estamos haciendo tampoco, pudiendo ser de internet hacia nuestra red o desde la red interna. Éste último caso podría indicar un movimiento lateral por parte de un atacante por ejemplo.

- **4.a Seguro que en el proceso de análisis para obtener un registro de lecciones aprendidas anterior, has pensado como evitar que una situación similar se vuelva a repetir. ¿Que actuaciones has decidido para evitar que se pueda dar una situación similar**

1. Implementación de filtros y validaciones adecuadas para prevenir vulnerabilidades de SSRF y otros ataques de inyección de código.
2. Capacitación regular del personal en prácticas seguras de desarrollo de software y en la identificación de posibles amenazas de seguridad.
3. Actualización y parcheo regular de sistemas y aplicaciones para cerrar posibles brechas de seguridad y vulnerabilidades conocidas.
4. Establecer filtros de configuración en caso de test de penetración para posibles escenarios en los que intentos concretos queden marcados como tales.

# 7.⭐ SOC227 - Microsoft SharePoint Server Elevation of Privilege - Possible CVE-2023-29357 Exploitation


## Clasificación

| **Taxonomía**    | Privilege Escalation, CVE-2023-29357                                                                                                      |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| **Criticidad**   | Crítica                                                                                                                                   |
| **Descripción**  | Se ha detectado la inclusión de una invocación de Powershell en una de las peticiones HTTP recibidas. Esta vulnerabilidad es una zero-day |
| **Fecha y hora** | Oct, 06, 2023, 08:05 PM                                                                                                                   |

## Memoria

En este caso tenemos una solicitud HTTP a la URL `/_api/web/siteusers` de la máquina **MS-SharePointServer** hecho con un *user-agent* de Python, por lo que ya es bastante sospechoso. Vamos a comprobar en primer lugar como siempre de donde viene y si existen logs relativos a la URL de origen. En primer lugar vamos a mirar los logs:

![](./img/Pasted%20image%2020240414053048.png)

Vemos que existen 3 logs de solicitudes de este tipo, cada una posee un código 200 de éxito y además cada una hace una petición a un endpoint distinto, para literalmente enumerarla. Por el tamaño de la respuesta y los códigos de éxito, podemos determinar que esto es un atacante y que de hecho ha tenido éxito. 

Es muy probable que se tenga que aislar rápidamente esta máquina para prevenir daños mayores.

Aunque nuestras sospechas ya son grandes, no está de más revisar la URL en VirusTotal y AbuseIPDB:

![](./img/Pasted%20image%2020240414053425.png)

![](./img/Pasted%20image%2020240414053438.png)

Y efectivamente vemos que VirusTotal nos la marca como peligrosa, en AbuseIPDB ha sido reportada múltiples veces, pero no está marcada como de abuso. Igualmente, junto a los logs, que VirusTotal tenga registros de phishing de esta IP es suficiente para marcarla como maliciosa.

Buscando información en internet acerca del CVE-2023-29357 comprobamos que existen pruebas de concepto de este exploit con python, y el user-agent que teníamos en nuestro incidente era efectivamente python.

![](./img/Pasted%20image%2020240414053744.png)

Consiste en una cadena de vulnerabilidades, primero *bypasear* JWT y luego aprovechar una vulnerabilidad para hacer una RCE (*Remote Code Execution*). En el playbook se nos pregunta por el tipo de ataque, la opción que me parece más lógica es command injection debido a que todo desemboca en ello y que no hay una opción concreta para bypass.

![](./img/Pasted%20image%2020240414054005.png)

Debemos descartar que esté planeado, una vez más vamos a buscar en emails si existe algo relacionado con esta máquina (ya que con tests de penetración hemos comprobado en los otros incidentes que no hay nada):

![](./img/Pasted%20image%2020240414054124.png)

Y vemos que no hay nada, por lo que lo clasificamos como **No planeado**.

Finalmente pondremos el equipo comprometido en contención ya que se trata de un incidente grave. Se nos pregunta también si se debe elevar a Tier 2, y efectivamente así debe ser porque el atacante ha conseguido cumplir el requisito de vulnerar la máquina para que esta directriz se cumpla.


> [!NOTE] Nota
> En este incidente se ha dado por erróneo el "Command Injection" como tipo de ataque, para la próxima marcaré "Otro cuando tenga dudas"
> ![](./img/Pasted%20image%2020240414054623.png)

## Preguntas

- **1.b  ¿Cuál es el proceso de investigación seguido para investigar el incidente y que evidencias han sido clave para la resolución del incidente?**
El proceso de investigación comenzó con la detección de una solicitud HTTP sospechosa a la URL `/_api/web/siteusers` de la máquina **MS-SharePointServer** con un user-agent de Python. 

Se verificaron los logs, donde se encontraron tres instancias de solicitudes similares, cada una con un código 200 de éxito y peticiones a diferentes endpoints para enumerarlos. Se determinó que estas solicitudes eran maliciosas y que el atacante había tenido éxito, hallar esto fue parte clave para resolver el incidente. Se comprobó la URL en VirusTotal y AbuseIPDB, confirmando que era maliciosa. 

Se buscó información sobre el CVE-2023-29357 para entender el tipo de vulnerabilidad explotada, lo que sugirió un ataque de inyección de comandos, también fue clave investigar sobre este exploit al tener otro indicador de compromiso como era el user-agent de python. Se descartó que el incidente fuera planeado mediante la búsqueda en emails. 

Finalmente, se decidió poner en contención al equipo comprometido y elevar el incidente a Tier 2.

- **2.a Durante la resolución del incidente ¿has tenido que realizar algún tipo de actuación para el restablecimiento de servicios afectados por el incidente, con el objetivo de volver a la normalidad?**
Durante la resolución del incidente, se tomó la acción de poner en contención al equipo comprometido para prevenir daños mayores. Esto era un servidor de intercambio, por lo que se habrá interrumpido el servicio. 

Hasta que no se parchee la vulnerabilidad es necesario que el equipo quede en contención mientras sea vulnerable a este tipo de ataques críticos. Como recomendación, sería necesario restablecer esta máquina al completo, aunque tuviera que ser reemplazada con una copia de seguridad o incluso reconstruida, para evitar futuros problemas de seguridad que tengan que ver con puertas traseras o persitencia que haya logrado el atacante, habiendo probablemente ganado privilegios de administrador.

- **3.a Tras trabajar en la resolución del incidente ¿Que acciones/actuaciones destacadas se han realizado para solucionar el incidente?**
- Identificación y análisis de la solicitud HTTP sospechosa y los logs asociados.
- Verificación de la URL en VirusTotal y AbuseIPDB para confirmar su maliciosidad.
- Investigación sobre la vulnerabilidad CVE-2023-29357 para comprender la naturaleza del ataque.
- Puesta en contención del equipo comprometido y elevación del incidente a Tier 2 debido a la gravedad del ataque.

- **3.b Realizar un proceso de análisis de las actuaciones llevadas a cabo y obtener un registro de lecciones aprendidas, para finalmente concluir en las posibles mejoras que podrías plantear para tu plan/playbooks desarrollado en la práctica anterior.**
En este incidente me he podido dar cuenta de que en nuestros playbooks podrían existir medidas para restablecer servicios en caso de que hayan sido vulnerados de manera crítica como es este caso, por ejemplo no veo otra manera que no sea formatear el ordenador de asegurarse de que no existen métodos de persistencia que un atacante hábil haya podido implementar tras ganar privilegios máximos a través de una vulnerabilidad crítica. 

Los playbooks podrían cubrir aspectos como restaurar ciertas copias de seguridad, formatear equipos en ciertos casos o sustituir sus servicios en caso de ser vulnerados por algún tipo de activo que tenga como función precisamente suplir la falta de los servicios vulnerados.

- **4.a Seguro que en el proceso de análisis para obtener un registro de lecciones aprendidas anterior, has pensado como evitar que una situación similar se vuelva a repetir. ¿Que actuaciones has decidido para evitar que se pueda dar una situación similar**

1. Implementar filtros que puedan detectar posibles relaciones con CVEs existentes y automáticamente bloquear preventivamente estas peticiones.
2. Realizar más auditorías de seguridad periódicas para identificar y remediar posibles vulnerabilidades en los sistemas y aplicaciones.
4. Mantener actualizados los sistemas y aplicaciones con los últimos parches de seguridad para mitigar el riesgo de explotación de vulnerabilidades conocidas.

# 8. ⭐ SOC235 - Atlassian Confluence Broken Access Control 0-Day CVE-2023-22515


## Clasificación

| **Taxonomía**    | Ataque Web, CVE-2023-22515                                                                                                     |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **Criticidad**   | Alta                                                                                                                           |
| **Descripción**  | Se ha detectado actividad relacionada con la explotación del exploit CVE-2023-22515 a través de una solicitud HTTP sospechosa. |
| **Fecha y hora** | Nov, 08, 2023, 09:47 AM                                                                                                        |

## Memoria

En este incidente tenemos una URL probablemente maliciosa proveniente de la IP **43.130.1.222**, que ya se ha comprobado como externa. Se trata de uno de un Data Center de Confluencia en nuestra red, por lo que es probablemente un activo crítico.

Vamos a comprobar en primer lugar y como es habitual en este tipo de incidentes los logs que involucren a esta IP externa:

![](./img/Pasted%20image%2020240414060910.png)

Encontramos tres logs que contienen peticiones altamente sospechosas y críticas, siendo una de ellas a un recurso de administrador, aunque con un código 302 (Recurso movido temporalmente). Las otras dos poseen un código 200 por lo que probablemente el atacante haya tenido éxito al explotarla. El user. El user-agent es curl, por lo que podría ser un indicador de compromiso de que efectivamente es un atacante intentando explotar el CVE-2023-22515.

![](./img/Pasted%20image%2020240414061200.png)

Sí buscamos en google además, encontramos que un indicador de compromiso es efectivamente la presencia de `setup/setupadministrator.action` en los logs de atlassian-confluence:

![](./img/Pasted%20image%2020240414061351.png)

Y ese es de hecho nuestro caso:

![](./img/Pasted%20image%2020240414061431.png)

Por lo que efectivamente este ataque es **positivo** y además se ha realizado con éxito comprometiendo el servidor de confluencia servido con Atlassian.

Esta vez en el tipo de ataque marcaremos **Other** debido a que es un CVE específico:

![](./img/Pasted%20image%2020240414061555.png)

Indicaremos que el ataque se ha realizado con éxito, que se debe elevar el nivel de alerta a Tier 2 y pondremos la máquina vulnerada en contención para evitar daños mayores.
## Preguntas

- **1.b  ¿Cuál es el proceso de investigación seguido para investigar el incidente y que evidencias han sido clave para la resolución del incidente?**
El proceso de investigación comenzó con la detección de una URL maliciosa proveniente de la IP externa **43.130.1.222**, confirmada como externa. 

Se verificaron los logs relacionados con esta IP, donde se encontraron tres solicitudes sospechosas y críticas, una de ellas dirigida a un recurso de administrador con un código de respuesta 302 y las otras dos con códigos 200, lo que sugiere un posible éxito en la explotación. El user-agent utilizado fue `curl`, lo que podría indicar un intento de explotar el CVE-2023-22515. 

Se realizó una búsqueda adicional en Google para confirmar los indicadores de compromiso asociados con Atlassian-Confluence, encontrando una coincidencia con el recurso `setup/setupadministrator.action`, lo que confirmó el ataque, este fue desde mi punto de vista el punto clave. 

Se marcó el incidente como positivo y se decidió elevar el nivel de alerta a Tier 2 y poner la máquina comprometida en contención.

- **2.a Durante la resolución del incidente ¿has tenido que realizar algún tipo de actuación para el restablecimiento de servicios afectados por el incidente, con el objetivo de volver a la normalidad?**

Se contiene el equipo afectado, y se debe considerar restablecerlo con una copia de seguridad, sustituirlo o volver a levantarlo desde 0 con una configuración nueva debido a su compromiso total y la inseguridad de que el atacante haya generado persistencia en la máquina.

- **3.a Tras trabajar en la resolución del incidente ¿Que acciones/actuaciones destacadas se han realizado para solucionar el incidente?**

- Identificación y análisis de las solicitudes sospechosas en los logs, especialmente aquellas dirigidas a recursos críticos como `setup/setupadministrator.action`.
- Confirmación del ataque mediante la coincidencia con los indicadores de compromiso asociados con Atlassian-Confluence.
- Puesta en contención de la máquina comprometida para evitar daños adicionales.
- Elevación del nivel de alerta a Tier 2 para una mayor supervisión y respuesta ante posibles amenazas futuras.

- **3.b Realizar un proceso de análisis de las actuaciones llevadas a cabo y obtener un registro de lecciones aprendidas, para finalmente concluir en las posibles mejoras que podrías plantear para tu plan/playbooks desarrollado en la práctica anterior.**
En este incidente creo que se destaca un claro componente como resolutivo del incidente y es el Indicador de compromiso (IoC), es de hecho el que me ha llevado a concluir que el ataque era de hecho un ataque, ha sido exitoso y ha sido de concretamente esa vulnerabilidad. 

Es mucha información con tan solo un detalle, y en nuestros playbooks solo se mencionan de pasada. Es importante hacer hincapié en su posible detección o hallazgo a la hora de abordar un incidente.

- **4.a Seguro que en el proceso de análisis para obtener un registro de lecciones aprendidas anterior, has pensado como evitar que una situación similar se vuelva a repetir. ¿Que actuaciones has decidido para evitar que se pueda dar una situación similar**
1. Implementar sistemas de detección de intrusiones más robustos para identificar CVEs concretos y bloquear actividades maliciosas en tiempo real.
2. Realizar auditorías de seguridad periódicas en servidores críticos para identificar posibles vulnerabilidades y aplicar parches de seguridad de manera oportuna.
3. Reforzar la formación del personal en prácticas de seguridad cibernética y en la identificación de indicadores de compromiso para una detección temprana de amenazas.
4. Mejorar la configuración de seguridad en servidores, limitando el acceso a recursos críticos y estableciendo políticas de acceso basadas en el principio de privilegio mínimo.

# 9. ⭐ SOC173 - Follina 0-Day Detected


## Clasificación

| **Taxonomía**    | Malware, CVE-2022-30190                                                                                                                                   |
| ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Criticidad**   | Media                                                                                                                                                     |
| **Descripción**  | Se ha ejecutado un archivo etiquetado como malicioso después de abrir un documento perteneciente a Microsoft Office. Se identifica con el CVE-2022-30190. |
| **Fecha y hora** | Jun, 02, 2022, 03:22 PM                                                                                                                                   |

## Memoria

Tenemos una supuesta ejecución de archivo malicioso tras abrir un documento de Microsoft Office, es la información que nos aporta la incidencia. Lo primero que deberíamos comprobar es qué ha detectado el malware, si internet, el empleado mediante la observación de comportamiento o conexiones sospechosas.. etc, pero antes me interesa conocer el CVE-2022-30190 ya que en los incidentes anteriores me ha ayudado mucho conocer de qué se trata para actuar más rápidamente.

De inmediato encontramos esta información:
![](./img/Pasted%20image%2020240414193034.png)

Que nos indica efectivamente que el CVE está relacionado con abrir un documento de office y que consiste en un archivo que de primeras sale en blanco, pero por detrás está realizando conexiones a URLs maliciosas. La incidencia se reporta en 2 de Junio de 2022 a las 03:22 PM, y al revisar las conexiones de la máquina afectada (JonasPRD) vemos que no hay conexiones a esa hora exacta o, al menos, en esa ventana de tiempo:

![](./img/Pasted%20image%2020240414193540.png)

Se han revisado todas las IPs con herramientas como VirusTotal, AbuseIPDB y Cisco Talos, y dos de ellas reportan como maliciosa o al menos sospechosa la IP **99.83.154.118**, 

![](./img/Pasted%20image%2020240414193821.png)
![](./img/Pasted%20image%2020240414194142.png)

Esto ya podría ser sospechoso de intrusión. Revisamos la terminal de la máquina ya que estamos aquí y vemos que hay comandos que podemos afirmar prácticamente ya que son maliciosos.

```
C:/windows/system32/cmd.exe /c cd C:/users/public/&&for /r %temp% %i in (05-2022-0438.rar) do copy %i 1.rar /y&&findstr TVNDRgAAAA 1.rar>1.t&&certutil -decode 1.t 1.c &&expand 1.c -F:* .&&rgb.exe
```

Este comando está abriendo una cmd, yéndose a la carpeta users/public del disco C: y buscando recursivamente archivos nombrados con una fecha y los está copiand otro archivo llamado 1.rar. Busca además una cadena muy extraña, "`TVNDRgAAAA`" y redirige la salida a un archivo 1.c. Además realiza la ejecución de un .exe al final. Así que o este empleado es una especie de ciberpsicópata o estamos ante una cadena maliciosa. 

Revisando los servicios, no vemos antivirus ni otros servicios extraños realmente, solo un cmd que podría estar relacionado con el comando anterior, por lo que la primera pregunta del playbook vamos a contestar que el indicador de la amenaza es "Other", concretamente desde mi punto de vista el indicador de la amenaza es el comportamiento extraño al abrir el documento, el cual de hecho está asociado con el CVE-2022- 30190.

![](./img/Pasted%20image%2020240414195219.png)

Vamos a revisar los logs ahora para ver si el malware ha sido puesto en cuarentena:
![](./img/Pasted%20image%2020240414195431.png)
![](./img/Pasted%20image%2020240414195452.png)
![](./img/Pasted%20image%2020240414195514.png)

Pero parece que no hay rastro de que se haya puesto ninguno de los supuestos archivos en cuarentena ni que ni siquiera se hayan manipulado por el antivirus u otro software de seguridad. Se nos pide analizar el malware en busca de C2, cosa que previamente hicimos con la URL acotada en la ventana de tiempo del incidente, además de ver el comportamiento claramente relacionado con el CVE-2022-30190, por lo que marcamos maliciosa.
![](./img/Pasted%20image%2020240414195631.png)

Debemos comprobar si la URL que detectamos como maliciosa ha sido accedida por alguno de nuestros equipos para ver si ha existido C2 a través de los logs:

![](./img/Pasted%20image%2020240414195830.png)
![](./img/Pasted%20image%2020240414195903.png)

Parece que no hay registros de que haya sido accedida. Determinamos pues que es un **positivo** y que efectivamente estamos frente a malware, considero que es necesario igual que en los otros incidentes elevar a Tier 2, pero no se nos menciona en el playbook actual.


> [!WARNING] Error
> Parece que en este caso, sí que habían intentado un command and control, debería haber investigado más el funcionamiento del CVE y revisar conexiones a la máquina local, y no únicamente relacionadas con la URL maliciosa. Allí podía comprobarse una conexión desde un dominio xmlformats.com, el cual de hecho se produce a la hora del incidente. También, existía un correo malicioso que nos proporcionaba hasta el archivo en sí que contenia el malware para poder analizarlo. Los hashes no lo hemos comprobado tampoco. Este incidente... regular.
> ![](./img/Pasted%20image%2020240414201605.png)



## Preguntas

- **1.b  ¿Cuál es el proceso de investigación seguido para investigar el incidente y que evidencias han sido clave para la resolución del incidente?**
El proceso de investigación comenzó con la identificación de una posible ejecución de archivo malicioso después de abrir un documento de Microsoft Office, asociado con el CVE-2022-30190. 

Se revisaron los logs en busca de conexiones sospechosas, se analizó el comportamiento de la máquina afectada, y se verificaron las direcciones IP involucradas utilizando herramientas como VirusTotal, AbuseIPDB y Cisco Talos. Se encontró evidencia de comandos maliciosos en la terminal de la máquina afectada, lo que aumentó las sospechas de una amenaza. 

Se marcó la URL maliciosa como sospechosa y se analizó en busca de posibles actividades de Command and Control (C2) en los logs. 

Finalmente, se determinó que la amenaza era real y que sería recomendable elevar el nivel de alerta a Tier 2, aunque en el playbook no se especificaba nada. Además se determino que **no** había intento de C2, cuando en realidad si que lo hubo.

- **2.a Durante la resolución del incidente ¿has tenido que realizar algún tipo de actuación para el restablecimiento de servicios afectados por el incidente, con el objetivo de volver a la normalidad?**
En este caso esa máquina debería de ponerse en contención como se ha hecho con las anteriores incidencias, se trataba del equipo de uno de los empleados por lo que en realidad sería relativamente de restablecer mediante un formateo y restablecimiento con copia de seguridad, ya que no estaba sirviendo ningún tipo de servicio, tan solo se vería interrumpida la actividad del trabajador.

- **3.a Tras trabajar en la resolución del incidente ¿Que acciones/actuaciones destacadas se han realizado para solucionar el incidente?**
Las acciones destacadas realizadas para solucionar el incidente incluyeron la identificación y análisis de los comandos maliciosos en la terminal de la máquina afectada, la verificación de las conexiones en los logs en busca de actividades sospechosas, y la marcación de la URL maliciosa como sospechosa para un análisis adicional en busca de actividades de C2. 

También la puesta en contención de la máquina atacada y la investigación del CVE directamente relacionado con el incidente.

- **3.b Realizar un proceso de análisis de las actuaciones llevadas a cabo y obtener un registro de lecciones aprendidas, para finalmente concluir en las posibles mejoras que podrías plantear para tu plan/playbooks desarrollado en la práctica anterior.**
En este incidente he podido comprobar como una de las claves para por ejemplo resolver una incidencia de malware es reconstruir el incidente en sí, es decir, recrear los pasos que el usuario afectado ha seguido y luego calcular o deducir los que su atacante haya podido dar en base a ellos. 

Es algo que he podido observar nada más finalizar el incidente y al ver que había fallado y me había dejado varias cosas. Si hubiera seguido con más detenimiento la traza del archivo de malware, y hubiera investigado más conexiones, habría resuelto con éxito absoluto el incidente.

- **4.a Seguro que en el proceso de análisis para obtener un registro de lecciones aprendidas anterior, has pensado como evitar que una situación similar se vuelva a repetir. ¿Que actuaciones has decidido para evitar que se pueda dar una situación similar**
1. Realizar una investigación más exhaustiva sobre las vulnerabilidades asociadas con CVE específicos y comprender su funcionamiento para una mejor detección y respuesta.
2. Prestar más atención a las conexiones no solo externas si no las que hace la máquina en sí tanto al exterior como en la intranet.
3. Añadir a los playbooks una serie de preguntas o checklists como "De donde surge el archivo malicioso", o busca en más lugares donde podría ubicarse el archivo malicioso, etc.
4. Reforzar la formación y concienciación del personal en prácticas de seguridad cibernética y en la identificación de indicadores de compromiso.
5. Mejorar la coordinación entre los equipos de seguridad para una respuesta más rápida y efectiva ante incidentes de seguridad.

# 10. ⭐ SOC250 - APT35 HyperScrape Data Exfiltration Tool Detected


## Clasificación

| **Taxonomía**    | Data exfiltration tool                                                                                                                     |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| **Criticidad**   | Media                                                                                                                                      |
| **Descripción**  | Se ha detectado un patrón de comportamiento malicioso ligado a un hash identificado, lo cual nos indica una potencial intención maliciosa. |
| **Fecha y hora** | Dec, 27, 2023, 11:22 AM                                                                                                                    |

## Memoria

En esta incidencia tenemos un patrón anómalo sospechoso de ser malicioso encontrado en el endpoint "Arthur" con IP **172.16.17.72**, la alerta nos indica que se ha encontrado una herramienta de robo de información llamada *Hyperscrape*. Investigando la herramienta podemos comprobar que lo que hace es extraer información de correos personales principalmente, como Yahoo, Gmail, etc. 

Si comprobamos el hash adjunto en el incidente comprobamos que efectivamente este hash es altamente malicioso, pero no es de extrañar porque ha sido ésto lo que ha causado la alerta:

![](./img/Pasted%20image%2020240414205551.png)

El playbook nos indica que recabemos la información suficiente para comprobar si esta incidencia se ha escalado correctamente al Tier 2, y que comprobamos logs para ver si existen actividades de reconocimiento en nuestros servicios. Comprobamos los logs y encontramos tres de ellos que son realmente sospechosos, uno de ellos relacionado con la descarga de emails, por supuesto potencialmente relacionado con la herramienta de *Hyperscrape*:

![](./img/Pasted%20image%2020240414204241.png)
![](./img/Pasted%20image%2020240414204254.png)
![](./img/Pasted%20image%2020240414204310.png)
También un evento de que éxito de autenticación en una cuenta, debemos tenerlo en cuenta. 

Vamos a revisar ahora los emails de Arthur para ver si existen siquiera o el tipo de información que podrían contener. 

![](./img/Pasted%20image%2020240414204850.png)
![](./img/Pasted%20image%2020240414205907.png)

Pero parece que no hay emails, comprobemos la máquina, sus conexiones externas e internas. Concretamente vamos a revisar la de los logs. 

Parece que la IP que ha realizado la operación de descarga de archivos es una de nuestra propia red, y correponde con la máquina **Exchange Server** con IP **172.16.20.3**, además se nos indica que ha tenido éxito en la operación, por lo que el posible ataque se ha completado. ¿Podría significar esto que una de nuestras máquinas está infectada y está atacando a las demás en red interna? 

![](./img/Pasted%20image%2020240414205947.png)

Después de comprobar esto, vamos a seguir con el playbook, que nos hace la siguiente pregunta:

![](./img/Pasted%20image%2020240414210033.png)

Para la cual no estoy muy seguro, por que podría entenderse como *host information* algunos emails por tener adjuntos por ejemplo. Descartando lo anterior, que en realidad puede ser algo ambigüo, lo más lógico me parece  "**Gather Victim Identity Information**", ya que en los correos es muy probable que haya información personal principalmente. Que hubiera habido correos electrónicos almacenados del usuario habría sido bastante útil. 

Tenemos que contestar ahora si la IP del atacante era externa o interna, en los logs hemos visto que era del Exchange Server, el cual pertenece a nuestra Red Interna, pero justo para asegurar se comprueba el famoso log que nos indica un intento de autenticación exitoso y vemos que la IP que lo realiza en la máquina de Arthur **es externa**. Lo que habrá ocurrido aquí probablemente es que el servidor de intercambio esté relacionado con el flujo del correo electrónico, y que tenga que pasar por ahí, pero no quiere decir que esté infectado. Aún así, sería recomendable investigarlo y tenerlo controlado.

![](./img/Pasted%20image%2020240414211607.png)

Determinamos que es externa.

![](./img/Pasted%20image%2020240414210311.png)

Comprobamos la IP encontrada en los logs y vemos que existe una conexión al puerto 3389, frecuente para Escritorio Remoto, y hacia el ordenador de Arthur. Esto nos confirma que efectivamente ha sido vulnerado.

![](./img/Pasted%20image%2020240414211854.png)

A continuación tenemos que determinar el alcance, y efectivamente tal y como dudábamos antes, considero que el alcance es al menos dos máquinas, la de Arhur y el servidor de intercambio, el cual realiza la petición. Aunque no esté implicada, creo que debería formar parte del alcance del incidente y merece investigación. No hay indicios de que haya más máquinas implicadas.

![](./img/Pasted%20image%2020240414210416.png)

Se nos pregunta si deben poner se en contención las máquinas, a lo que respondemos afirmativamente, ya que están claramente vulneradas.

> [!WARNING] Error
> En este caso LetsDefend considera que el alcance era únicamente la máquina de Arthur, y sinceramente no entiendo por qué, ya que aunque el servidor sea un trámite está implicado en el incidente a mi modo de ver.

## Preguntas

- **1.b  ¿Cuál es el proceso de investigación seguido para investigar el incidente y que evidencias han sido clave para la resolución del incidente?**
El proceso de investigación comenzó con la detección de un patrón anómalo sospechoso de ser malicioso en el endpoint "Arthur". Se verificó la presencia de la herramienta de robo de información llamada _Hyperscrape_ y se confirmó su naturaleza maliciosa. Se analizó el hash asociado al incidente y se comprobó su alta peligrosidad. 

Luego, se examinaron los logs en busca de actividades de reconocimiento en los servicios y se encontraron eventos sospechosos relacionados con la descarga de emails y autenticación exitosa en una cuenta. 

Se revisaron los correos electrónicos de Arthur en busca de información comprometida, pero no se encontraron. 

Finalmente, se determinó que una máquina interna, el Exchange Server, estaba involucrada en la operación de descarga de archivos, lo que sugiere una posible infección interna y ataque a otras máquinas en la red.

- **2.a Durante la resolución del incidente ¿has tenido que realizar algún tipo de actuación para el restablecimiento de servicios afectados por el incidente, con el objetivo de volver a la normalidad?**
Durante la resolución del incidente, se ha puesto en contención tanto la máquina de Arthur como el servidor de intercambio.

Para restablecer los servicios afectados, se debe realizar una investigación exhaustiva para identificar el alcance completo del incidente y determinar si se han comprometido otros sistemas o recursos de la red. Una vez que se haya confirmado el alcance y se hayan tomado las medidas necesarias para contener la amenaza, se puede proceder con la limpieza y restauración de los sistemas afectados. 

Además, es importante implementar medidas de seguridad adicionales para prevenir futuros ataques similares.

- **3.a Tras trabajar en la resolución del incidente ¿Que acciones/actuaciones destacadas se han realizado para solucionar el incidente?**
Para solucionar el incidente se han buscado registros que involucren a la IP atacada perteneciente al equipo de Arthur, se han comprobado los emails, los servicios y desde donde y quién los estaba ejecutando, además de las conexiones de la máquina atacada. 

También se intenta confirmar mediante herramientas como VirusTotal la naturaleza del programa malicioso y si efectivamente se ha ejecutado.

- **3.b Realizar un proceso de análisis de las actuaciones llevadas a cabo y obtener un registro de lecciones aprendidas, para finalmente concluir en las posibles mejoras que podrías plantear para tu plan/playbooks desarrollado en la práctica anterior.**
Lo más destacado de este incidente es que no se relacione el servidor de intercambio con el incidente del robo de email, cuando es ese servidor quien realiza la operación de descarga. 

Sería interesante añadir a nuestros playbooks secciones en las que se hable de seguir posibles trazas relacionadas con la infraestructura, es decir, si existe un malware que descarga archivos por ejemplo a través de otro equipo o servidor, considerar su comprobación y examen también en el playbook para conseguir abarcar al máximo los detalles del incidente. 

- **4.a Seguro que en el proceso de análisis para obtener un registro de lecciones aprendidas anterior, has pensado como evitar que una situación similar se vuelva a repetir. ¿Que actuaciones has decidido para evitar que se pueda dar una situación similar**
Establecer más restricciones o capas de seguridad en las conexiones de tipo escritorio remoto, SSH o VPN a la empresa, estableciendo por ejemplo filtros que solo permitan a equipos concretos conectarse.

Podría establecerse una contención preventiva inmediata de manera automática si se detecta un hash que claramente es malicioso como este es el caso, así podría limitarse la ventana de tiempo útil que un atacante tendría para actuar si consigue colocar el malware en uno de nuestros equipos. Haberlo detectado y que actúe es algo evitable desde mi punto de vista.