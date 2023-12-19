# Práctica vulnerabilidad web


###Creacion de web explicación
Para esta practica hemos hecho una *web* muy simple con un campo de *texto* para una *password*. 

Al introducir la password enlazamos con una nueva página (datos administrativos o mantenimiento)

Esta página ha sido colgada en el servidor con la siguiente url

>[http://rockinpaula.great-site.net](http://rockinpaula.great-site.net)

La página consiste en un simple script y html, en el que si nombras la **pagina siguiente como clave** enlaza a la misma. La contraseña no aparece dentro del codigo.

###Herramientas

Se ha utilizado las siguientes herramientas

1. Editor de texto para html
2. Owasp zap
3. Alojamiento 

###Analisis de la web 

Procedemos a realizar el analisis de la web con un ataque de la herramienta owasp zap. 

Una vez realizado el mismo nos arroja un informe sobre las vulnerabilidades encontradas 

Este análisis recoje entre otros los top 10 de riesgos clasificados por la organización

###Informe de vulnerabilidades


![owa10](owasp10.jpg)
![owa11](owasp11.jpg)
![owa12](owasp12.jpg)
![owa13](owasp13.jpg)
![owa14](owasp14.jpg)



**Metadatos de la Nube Potencialmente Expuestos**

Alto 1 (16,7 %)


Es una conexion http por lo que la mejor opcion es optar por un
alojamiento https 

**Cabecera Content Security Policy (CSP) no configurada**

Medio 2 (33,3 %)


Habilitar CSP, necesitas configurar tu servidor web para que devuelva la cabecera HTTP 
Csp


**Falta de cabecera Anti- Clickjacking**

Medio 2 (33,3 %)

La cabecera X-Frame-Options sirve para prevenir que la página pueda ser abierta en un frame, o   iframe,ataquesclickjacking
Podemos denegar el enmarcado (deny) 


**X-Content-Type-Options Header Missing**

Bajo 3 (50,0 %)

añadir cabecera'X-Content-Type-Options'  a la respuesta de la web a traves de ajustes del servidor


**ModernWebApplication**

Informativo 2 (33,3 %)




**User Agent Fuzzer**

Informativo 18 (300,0 %)


Manipulacion la cadena del agente de usuario. Esta vulnerabilidad puede provocar acceso no autorizado, filtraciones de datos y otras

Chequeamos y validamos un agwnte de usuario sano. 


Tota l6