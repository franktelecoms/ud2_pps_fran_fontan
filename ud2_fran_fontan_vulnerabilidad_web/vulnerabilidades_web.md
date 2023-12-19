# Puesta en producción segura  . Vulnerabilidades web.













	        **Francisco josé Fontán Forno**













INDICE:




1.INTRODUCCION


2.CONCEPTOS, FINALIDAD DE LA SEGURIDAD 


3.ANALISIS DE VULNERABILIDAD


4.TOP 10 DE VULNERAVILIDADES DE OWASP


5.REQUISITOS DE VERIFICACION DETALLADA DEL ANALISIS DE VULNERABILIDAD


6.TRES CASOS DE VULNERABILIDAD WEB Y SU REPERCUSION



7.CASO PRACTICO









#INTRODUCCION



Esta practica tiene como objetivo analizar vulnerabilidades en la red de una organización en este caso centrándose en la lista de riesgos a nivel SOFTWARE en 
entornos web


Para la revisión de este tipo de vulnerabilidades  nos basamos en el proyecto estándar de verificacián de seguridad de aplicaciones ***ASVS*** y su verificación 
de admisión .


Nos basaremos en la herramienta ***OWASP ZAP*** para realizar el análisis de la red. Al ser una herramienta automática, para el desarrollo del análisis tan solo 
tendremos que indicar la situación del software, en este caso de nuestra web de empresa, y se procederá al análisis de las vulnerabilidades elegidas.


Una vez realizado el análisis  se producirá un informe con los fallos a corregir y correlativamente las posibles amenazas que podremos evitar


Como resultado tendremos una evaluación del análisis de riesgos y  el nivel de nuestra web corporativa intentando conseguir el ***nivel 1***


Este análisis y el resultado obtenido es totalmente valido como auditoria de seguridad, por lo que nuestros técnicos o contratas de seguridad de información y IOT pueden basarse en el mismo para mejorar el nivel de seguridad de nuestra web contra futuros ataques y proteger la información sensible de nuestra base de datos







#CONCEPTOS, FINALIDAD DE LA SEGURIDAD 



La seguridad tiene por objeto la protección de la información y de los sistemas  en la que se encuentra integrada que permiten el acceso. Y el uso y representación 
de la misma 


La seguridad de la información  tienen unos objetivos comunes de confidencialidad integridad  y disponibilidad de la información independientemente de su forma que 
puedan tener audio vídeo impresiones. A través de  programas, controles, políticas consigue llegar a estos objetivos. 


La seguridad informática protege los activos como información, equipos y usuarios a través de técnicas de seguridad física y lógica de ese activo mas valorado que es
 la información.  Estas técnicas son plausibles a través de programas aplicaciones, barreras y procedimientos y medios .


Como buenas practicas serian las siguientes

Restringir el acceso al mínimo para protección de archivos e información

Programas y herramientas de uso legal y actualizados

Asegurar los medios o canales de transmisión de dicha información

Actualizar las contraseñas periódicamente y realizar análisis de vulnerabilidades. 








##ANALISIS DE VULNERABILIDAD


***ASVS*** standar verification security aplication

Para analizar nuestra web utilizaremos como referencia el sistema ASVS que consiste en implantar un marco de seguridad y controles para que podamos diseñar, 
desarrollar y testear (cheklist) nuestra aplicación web con garantías y también alinear las herramientas y ofertas de proveedores con nuestras necesidades



Dentro de nuestras expectativas realizaremos este proceso para llegar a conseguir  un nivel de seguridad N1 (vulnerabilidades del ***OSWAP10***, aseguradas 
automáticamente y para ataques oportunistas) puesto que el N2 y El N3  todavía no son aplicables hasta poseer datos mas sensibles, teniendo que retocar el código 
manualmente para implementarlas, y no  encontrándose en peligro ninguna información que pueda hacer tambalear nuestra empresa. 

En nuestra web aun no hemos implementado  catálogos, ni información sensible de contactos, ni puntos de venta con sus correspondientes datos sensibles de pago,
 por lo que nos basamos en el nivel 1 sin necesidad de abrir nuestro código fuente (necesario en N2 y N3) 

Aplicamos el test de penetración  para tener un informe de los fallos a corregir y defectos de seguridad, aunque también reflejamos por otros medios como markdown 
imágenes de los mismos

Es una guía de arquitectura detallada. Los estándares SABSA o TOGAF los desechamos en favor de este sistema mas completo y ser mas detallado



Checklist que reemplaza a terceros

Guía de pruebas unitaria y de autoverificación

Nos capacita para tener un software seguro, no como otro tipo de estandar que son guías

Dentro de los tres proyectos **OSWAP ASVS**
SKF(aplicaciones), ZAP(web) y CORNUCOPIA(metodologías requisitos seguridad), nos decantamos por la segunda al ser nuestro nivel de negocio




TOP 10 DE VULNERAVILIDADES DE OWASP

1.A01 - Pérdida de Control de Acceso
2.A02 - Fallas Criptográficas
3.A03 - Inyección
4.A04 - Diseño Inseguro
5.A05 - Configuración de Seguridad Incorrecta
6.A06 - Componentes Vulnerables y desactualizados
7.A07 - Fallas de Identificación y autenticación
8.A08 - Fallas en el Software y en la Integridad de los Datos
9.A09 - Fallas en el Registro y monitoréo
10.A10 - Falsificación de Solicitudes del Lado del Servidor

En el análisis de nuestra web nos centramos principalmente en la comunicación con el servidor, en este caso es un alojamiento HTTP en la red. Por lo que las fallas 
son principalmente de configuración en el servidor 
En este caso A05 y A06







REQUISITOS DE VERIFICACION DETALLADA DEL ANALISIS DE VULNERABILIDAD



V11 requisitos de verificación de seguridad HTTP

Servidor con configuración preestablecida y dura

Respuesta HTTP con caracteres seguros

A11.1 solicitudes GET POST resto bloqueadas si no se utilizan

A11.2 cabecera HTTP caracteres seguros(utf8) 

A11.5  respuesta HTTP no tenga información de versiones

A11.6  respuestas de API son content type nosniff y disposition attachment y api. Json

A11.7politica de seguridad de contenido (CSPv2) 
mitiga inyecciones DOM XSS JSON JSCRIP

A11.8encabezado X-XSS protection 1mode block









TRES CASOS DE VULNERABILIDAD WEB EN PROCESOS DE AUTENTICACION Y SU REPERCUSION


Hackeo a la CNV

Son ocho carpetas hackedas con datos de bancos, agentes de bolsa, operadores, inversores, tramites administración, operaciones sensibles. Unos 500000 archivos. 
Los hackers secuestraron 1.5 terabites
Hay un documento de una campaña premoritorio de lo sucedido que dice "cuida tus claves" 


Hackeo web Menéame

Los atacantes no tenían accesos directos a las contraseñas por que estaban cifradas, pero a través de las contraseñas débiles de los usuarios consiguieron entrar en muchas de ellas, que han afectado al 40% de las cuentas a través de fuerza bruta. Son unos 110000 usuarios y los datos están a la venta

hackeo de Fotolog,8bit, MyFitnessPal, Dubsmash, MyHeritage y otros más.

620 millones de usuarios y contraseñas

CASO PRACTICO

En el caso practico crearemos una pagina web con un sistema de autenticación simple y aplicaremos el análisis concerniente al  OWASP ASVS apartado V2 verificación de autenticación. 
Asi como los subapartado correspondiente. 