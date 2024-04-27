# Atención y Seguimiento de Incidentes Usando Let's Defend

Nuestros playbooks de referencia:
Deepfakes
Bruteforce -- listo
Code-injection  -- listo
Cryptojacking
Ddos
Defacement
Elevation-privilege -- listo
Identity and access
Iot device attacks
Man in the middle
Phishing
Ransomware


## Índice

## Incidente 1: SOC239 - Remote Code Execution Detected in Splunk Enterprise

1.a Trabaja una memoria del trabajo realizado en la resolución de los incidentes. Tipo según taxonomía, Criticidad, Descripción del incidente para entender que ha sucedido. Utiliza imágenes y cualquier tipo de explicación y diagrama que permita aclarar tu trabajo. 

### Clasificación según taxonomía

Acceso no autorizado

### Criticidad

Alta

### Descripción del incidente

Se detectó una carga XSLT maliciosa en Splunk Enterprise con el potencial de desencadenar la ejecución remota de código.

1.b ¿Cuál es el proceso de investigación seguido para investigar el incidente y que evidencias han sido clave para la resolución del incidente?

### Acciones tomadas para su resolución

Lo primero que haremos será crear el playbook y examinar el nombre de la regla, donde veremos que esta relacionada con el CVE-2023-46213, el cual es una ejecución remota de código.
Tendremos que ver entre que dos dispositivos se está produciendo el tráfico.

En la siguiente ventana de Collect Data tenemos que recopilar información sobre direcciones ip, nombre de host...

Y podemos recopilar la siguiente información:

Dirección IP de origen: 180.101.88.240

Dirección IP de destino: 172.16.20.13

Puerto de origen: 54321

Puerto de destino: 8000

Si nos vamos a Virustotal e introducimos la ip 180.101.88.240 nos da que es malicioso

![img01](img/img01.png)

A continuación nos vamos a la página abuseipdb y aquí vemos que la dirección IP pertenece a una empresa China llamada Telecom.

![img02](img/img02.png)

A continuación Lets defend nos pregunta si el trafico es malicioso y le decimos que si, ya que con Virustotal y abuseipdb vemos que efectivamente eran maliciosos.


![img03](img/img03.png)

Ahora nos pregunta el tipo de ataque que es, si investigamos encontraremos un archivo shell.zip si lo descomprimimos hay dos archivos un .sh (script) y un archivo .xsl, podemos analizar el contenido de estos para ver realmente el código que se está ejecutando y parece que quiere crear un documento y abrir una reverse shell, por lo tanto deducimos que el tipo de ataque es un XML Injection.

Si buscamos en la parte de la bandeja de entrafa e intentamos buscar la ip de origen o destino no vemos nada relevante por lo tanto deducimos que el ataque no esta planeado.

![img04](img/img04.png)

Ante esta pregunta hemos ivenstigado y la dirección de origen 180.101.88.240 de la alerta pertenece a la red externa de la empresa china, pero la dirección de destino que es esta: 172.16.20.13  pertenece a la empresa Splunk. Por eso seleccionaremos la opción de Internet → Red de empresa.

![img05](img/img05.png)

Nos preguntan si el ataque fue exitoso, y si lo fue porque la acción del dispositivo está permitida.

La siguiente parte es el apartado de contención, Como se muestra aquí abajo debemos aislar el dispositivo así restringimos al atacante y contenemos el dispositivo:

![img06](img/img06.png)

Como se muestra aquí abajo Debemos aislar el dispositivo así restringimos al atacante y contenemos el dispositivo:

A cotinuación ponemos los artifacts que veamos importantes y nos quedaría así:

![img07](img/img07.png)

Por ultimo nos pregutan si hay que escalarlo al nivel 2 y diremos que si:

![img08](img/img08.png)

Y ya habríamos terminado el playbook.

### ¿Es necesario realizar alguna acción específica para el restablecimiento de los servicios afectados?

No, no es necesario.

### Documentar acciones y proponer mejoras para futuras respuestas.


### Desarrollar estrategias preventivas para evitar la repetición de incidentes similares


## Preguntas


2.a Durante la resolución del incidente ¿has tenido que realizar algún tipo de actuación para el restableciciomiento de servicios afectados por el incidente, con el objetivo de volver a la normalidad?

No, no he tenido que hacer ninguna acción para el restablecimiento de los servicios afectados.

3.a Tras trabajar en la resolución del incidente ¿Que acciones/actuaciones destacadas se han realizado para solucionar el incidente? 

Hacerrr

3.b Realizar un proceso de análisis de las actuaciones llevadas a cabo y obtener un registro de lecciones aprendidas, para finalmente concluir en las posibles mejoras que podrías plantear para tu plan/playbooks desarrollado en la práctica anterior.

Hacerrr

4.a Seguro que en el proceso de análisis para obtener un registro de lecciones aprendidas anterior, has pensado como evitar que una situación similar se vuelva a repetir. ¿Que actuaciones has decidido para evitar que se pueda dar una situación similar?

Hacerrr

## Incidente 2: 	SOC176 - RDP Brute Force Detected

1.a Trabaja una memoria del trabajo realizado en la resolución de los incidentes. Tipo según taxonomía, Criticidad, Descripción del incidente para entender que ha sucedido. Utiliza imágenes y cualquier tipo de explicación y diagrama que permita aclarar tu trabajo. 

### Clasificación según taxonomía

Fuerza Bruta

### Criticidad

Media

### Descripción del incidente

Error de inicio de sesión desde una única fuente con diferentes cuentas no existentes.

1.b ¿Cuál es el proceso de investigación seguido para investigar el incidente y que evidencias han sido clave para la resolución del incidente? 

### Acciones tomadas para su resolución

Lo primero que haremos será crear el playbook y detectar los detalles más importantes del incidente:

Direccion Ip de origen: 218.92.0.56

Direccón Ip de destino: 172.16.17.148

Nombre de host: Matthew

Protocolo: RDP

![img09](img/img09.png)

Aquí elegiremos la opción de ip de origen externa, ya que si la ponemos en virustotal y AbuseIPDB nos darán información de que la ip es maliciosa y externa:

![img10](img/img10.png)

Seleccionamos maliciosa también ya que hemos visto que es maliciosa

![img11](img/img11.png)

Si nos vamos a los logs y filtramos por esta dirección ip maliciosa, podemos ver que se realizó un ataque de fuerza bruta en el servicio RDP de este host Matthew.

![img12](img/img12.png)

Seleccionamos que si hay una respuesta de la ip del atacante a un puerto SSH o RDP porque el puerto que vemos en la imagen de arriba corresponde a rdp (3389)

![img13](img/img13.png)

En la siguiente opción marcamos no, ya que si vemos los registros, todos los registros de la ip del atacante solo val al host de Matthew.

![img14](img/img14.png)

Si miramos los logs, vemos que el ataque de fuerza bruta fue exitosos y el atacante obtuvo acceso al sistema:

![img15](img/img15.png)


Así que seleccionamos que sí:

![img16](img/img16.png)

Deberiamos aislar el equipo de Matthew, para ello nos vamos a Endpoint Security y le damos a la opción de contener/aislar:

![img17](img/img17.png)

A contunuación seleccionamos los artifacts más importantes:

![img18](img/img18.png)

Y ya hemos terminado el playbook.


### ¿Es necesario realizar alguna acción específica para el restablecimiento de los servicios afectados?


### Documentar acciones y proponer mejoras para futuras respuestas.


### Desarrollar estrategias preventivas para evitar la repetición de incidentes similares


## Preguntas

2.a Durante la resolución del incidente ¿has tenido que realizar algún tipo de actuación para el restableciciomiento de servicios afectados por el incidente, con el objetivo de volver a la normalidad?

HACER

3.a Tras trabajar en la resolución del incidente ¿Que acciones/actuaciones destacadas se han realizado para solucionar el incidente? 

HACER

3.b Realizar un proceso de análisis de las actuaciones llevadas a cabo y obtener un registro de lecciones aprendidas, para finalmente concluir en las posibles mejoras que podrías plantear para tu plan/playbooks desarrollado en la práctica anterior.

HACER

4.a Seguro que en el proceso de análisis para obtener un registro de lecciones aprendidas anterior, has pensado como evitar que una situación similar se vuelva a repetir. ¿Que actuaciones has decidido para evitar que se pueda dar una situación similar?

HACER


## Incidente 3: SOC227 - Microsoft SharePoint Server Elevation of Privilege

1.a Trabaja una memoria del trabajo realizado en la resolución de los incidentes. Tipo según taxonomía, Criticidad, Descripción del incidente para entender que ha sucedido. Utiliza imágenes y cualquier tipo de explicación y diagrama que permita aclarar tu trabajo. 

### Clasificación según taxonomía

Ataque Web

### Criticidad

Critica

### Descripción del incidente

Esta actividad puede ser indicativa de un intento de explotar la vulnerabilidad CVE-2023-29357, que podría conducir a un acceso no autorizado y a una escalada de privilegios dentro del servidor de SharePoint.

1.b ¿Cuál es el proceso de investigación seguido para investigar el incidente y que evidencias han sido clave para la resolución del incidente? 

### Acciones tomadas para su resolución

Lo primero que haremos será seleccionar el incidente, asignarnoslo y luego empezar el playbook y detectaremos las direcciones ip y los detalles más importantes del incidente:

Direccion Ip de origen: 39.91.166.222

Direccón Ip de destino: 172.16.17.233

Nombre de host: MS-SharePointServer

URL: /_api/web/siteusers

Lo primero que haremos como siempre meter la ip de origen en Virustotal y abuselPDB y nos dará que la ip es maliciosa:

![img19](img/img19.png)

Ahora nos preguntan si el trafico es malicioso y por lo que hemos visto en Virustotal, los logs y abuselPDB decimos que si es maliciosa:

![img20](img/img20.png)

Aún no estamos seguros del tipo de ataque, así que seleccionamos other (otro) en la siguiente pestaña.

Para saber si el incidente fue creado por un test de penetración nos iremos a buscar en la parte de correos y bandeja de entradas y vemos que nada coincide con las ips e información que tenemos, así que no es planeado.

![img21](img/img21.png)

La dirección de origen de la alerta pertenece a la red externa de la empresa, pero la dirección de destino pertenece a MS-SharePointServer. Así que el flujo que seleccionamos es Internet → Red de empresa.

![img22](img/img22.png)

Para ver si el ataque fue exitoso o no, tendremos que ver los logs y los raw y veremos que el atacante accedió a las urls de /currentuser y /siteusers:

![img23](img/img23.png)

Para la parte de contención nos iremos a la ip 172.16.17.233 y lo contendremos:

![img24](img/img24.png)

Ahora añadimos los artifacts más importantes:

![img25](img/img25.png)

Y por ultimo si necesitamos escalar a nivel 2 para alguien más especializado.

![img26](img/img26.png)

### ¿Es necesario realizar alguna acción específica para el restablecimiento de los servicios afectados?


### Documentar acciones y proponer mejoras para futuras respuestas.


### Desarrollar estrategias preventivas para evitar la repetición de incidentes similares


## Preguntas

2.a Durante la resolución del incidente ¿has tenido que realizar algún tipo de actuación para el restableciciomiento de servicios afectados por el incidente, con el objetivo de volver a la normalidad?

3.a Tras trabajar en la resolución del incidente ¿Que acciones/actuaciones destacadas se han realizado para solucionar el incidente? 

3.b Realizar un proceso de análisis de las actuaciones llevadas a cabo y obtener un registro de lecciones aprendidas, para finalmente concluir en las posibles mejoras que podrías plantear para tu plan/playbooks desarrollado en la práctica anterior.

4.a Seguro que en el proceso de análisis para obtener un registro de lecciones aprendidas anterior, has pensado como evitar que una situación similar se vuelva a repetir. ¿Que actuaciones has decidido para evitar que se pueda dar una situación similar?


## Incidente 4: SOC251 - Quishing Detected (QR Code Phishing)

1.a Trabaja una memoria del trabajo realizado en la resolución de los incidentes. Tipo según taxonomía, Criticidad, Descripción del incidente para entender que ha sucedido. Utiliza imágenes y cualquier tipo de explicación y diagrama que permita aclarar tu trabajo. 

### Clasificación según taxonomía

Intercambio

### Criticidad

Media

### Descripción del incidente

Se trata de un codigo QR que no es legitimo y tiene un phishing.

1.b ¿Cuál es el proceso de investigación seguido para investigar el incidente y que evidencias han sido clave para la resolución del incidente? 

### Acciones tomadas para su resolución

Lo primero que haremos será seleccionar el incidente, asignarnoslo y luego empezar el playbook y detectaremos las direcciones ip y los detalles más importantes del incidente:

Direccion SMTP: 158.69.201.47

Correo de origen: security@microsecmfa.com

Dirección de destinos : Claire@letsdefend.io

Luego tendremos que irnos a virustotal e introducir la ip 158.69.201.47 y vemos que es maliciosa y que saltan varios antivirus:

![img27](img/img27.png)

Ahora haremos una busqueda por el correo security@microsecmfa.com y nos saldrá un mensaje con un qr de microsoft:

![img28](img/img28.png)

A continuación nos descargamos la imagen del QR y lo metemos en cyberchef y nos dará la siguiente dirección: https://ipfs.io/ipfs/Qmbr8wmr41C35c3K2GfiP2F8YGzLhYpKpb4K66KU6mLmL4#

Si buscamos esa url en virustotal nos sale que es maliciosa y que lo más probable es que sea phishing.

![img29](img/img29.png)

Ahora que sabemos que es malicioso ese correo, lo eliminamos en Let's Defend.

Ahora tenemos que verificar si el usuario accedió a esa URL del QR, para ello nos vamos a Endpoint Security y vemos la ip de Claire y activamos la contención:

![img30](img/img30.png)

Aquí elegiremos la opción de Phishing for Information.

![img31](img/img31.png)

Vemos que el remitente de correo electronico y la URL del código QR es externa, por lo tanto la opción correcta es externa.

![img32](img/img32.png)

En virustotal hemos visto que la ip es maliciosa, así que la ip del atacante si es sospechosa:

![img33](img/img33.png)

Comprobamos si alguien más recibió el correo electronico con el phishing, pero vemos que solo lo recibió Claire, así que no hay mas de un usuario afectado.

![img34](img/img34.png)

Ya hemos contenido al host, haremos esto para evitar más amenazas, ya que no podemos comprobar al 100% si el usuario llegó a acceder a la URL maliciosa.

![img35](img/img35.png)

Y estos serían los artifacts a poner:

![img36](img/img36.png)

Y ya habriamos terminado el playbook.



### ¿Es necesario realizar alguna acción específica para el restablecimiento de los servicios afectados?


### Documentar acciones y proponer mejoras para futuras respuestas.


### Desarrollar estrategias preventivas para evitar la repetición de incidentes similares




## Preguntas

2.a Durante la resolución del incidente ¿has tenido que realizar algún tipo de actuación para el restableciciomiento de servicios afectados por el incidente, con el objetivo de volver a la normalidad?

3.a Tras trabajar en la resolución del incidente ¿Que acciones/actuaciones destacadas se han realizado para solucionar el incidente? 

3.b Realizar un proceso de análisis de las actuaciones llevadas a cabo y obtener un registro de lecciones aprendidas, para finalmente concluir en las posibles mejoras que podrías plantear para tu plan/playbooks desarrollado en la práctica anterior.

4.a Seguro que en el proceso de análisis para obtener un registro de lecciones aprendidas anterior, has pensado como evitar que una situación similar se vuelva a repetir. ¿Que actuaciones has decidido para evitar que se pueda dar una situación similar?


## Incidente 5


## Incidente 6


## Incidente 7


## Incidente 8


## Incidente 9



## Incidente 10


## Incidente 11
