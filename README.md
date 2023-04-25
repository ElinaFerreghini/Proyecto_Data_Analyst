<p align='center'>
<img src ="https://d31uz8lwfmyn8g.cloudfront.net/Assets/logo-henry-white-lg.png">
<p>

<h1 align='center'>
 <b>PROYECTO INDIVIDUAL Nº2</b>
</h1>
 
# <h1 align="center">**`Telecomunicaciones`**</h1>
# <h1 align="center">**Bienvenidos a mi proyecto de Data Analyst!! En el presente informe van a encontrar el contexto del trabajo, el roll a desarrollar y posteriormente las consignas junto al análisis que fui elaborando en el transcurso de éstos días a partir de información recopilada de distintos sitios de acceso público. Además, arriba se encuentran los archivos realizados previamente.**</h1>


## **Descripción del problema:**


### **Contexto**

Las telecomunicaciones se refieren a la transmisión de información a través de medios electrónicos, como la telefonía, la televisión, la radio y, más recientemente, 
el internet. Estos medios de comunicación permiten la transmisión de información entre personas, organizaciones y dispositivos a largas distancias. 
El internet, por su parte, es una red global de computadoras interconectadas que permite el intercambio de información en tiempo real. Desde su creación, ha tenido un 
impacto significativo en la vida de las personas, transformando la manera en que nos comunicamos, trabajamos, aprendemos y nos entretenemos.
La industria de las telecomunicaciones ha jugado un papel vital en nuestra sociedad, facilitando la información a escala internacional y permitiendo la comunicación 
continua incluso en medio de una pandemia mundial. La transferencia de datos y comunicación se realiza, en su mayoría, a través de internet, líneas telefónicas fijas, 
telefonía móvil y en casi cualquier lugar del mundo.
En comparación con la media mundial, Argentina está a la vanguardia en el desarrollo de las telecomunicaciones, teniendo para el 2020 un total de [62,12 millones de conexiones](https://www.datosmundial.com/america/argentina/telecomunicacion.php). 

 
### **Rol a desarrollar**

En este contexto, una empresa prestadora de servicios de telecomunicaciones le encarga a usted la realización de un análisis completo que permita reconocer el 
comportamiento de este sector a nivel nacional. Considere que la principal actividad de la empresa es brindar acceso a internet, pero también es importante considerar 
el comportamiento asociado al resto de los servicios de comunicación, con el fin de orientar a la empresa en brindar una buena calidad de sus servicios, identificar 
oportunidades de crecimiento y poder plantear soluciones personalizadas a sus posibles clientes.
Con el fin de monitorear la eficacia de los objetivos de la empresa, se le pide visualizar en un dashboard el siguiente KPI y establecer 3 KPIs adicionales producto 
de su análisis:

+ Aumentar en un 2% el acceso al servicio de internet para el próximo trimestre, cada 100 hogares, por provincia. [(Datos)](https://www.google.com/url?q=https://datosabiertos.enacom.gob.ar/visualizations/32226/penetracion-de-internet-fijo-accesos-por-cada-100-hogares/&sa=D&source=docs&ust=1671204570423891&usg=AOvVaw0YwFIM-MNjsy094L_FOFM3)


<b>YA HABIENDO COMPENDIDODO EL CONTEXTO DEL PROYECTO Y LA FUNCIÓN QUE DEBO CUMPLIR, EMPECEMOS... MANOS A LA OBRA!!</b>
</h1>

<p align='center'>
<img src ="https://media.giphy.com/media/BpGWitbFZflfSUYuZ9/giphy.gif" height=250>
<p>


`Análisis Exploratorio de los datos` 

Para llevar a cabo la propuesta realizada por Henry, comencé cargando un total de 19 archivos csv en python (los datos fueron sacados del link proporcionado). 
Utilizando la librería pandas, comencé a hacer visualizaciones de los datos para entender que información contenía cada uno y que cambios se requerían. 
Realicé algunas transformaciones, como cambios de tipo de datos, eliminación de algunas columnas, agregado de otras, correcciones en formatos, etc. Luego, usando las liberias matplotlib, pyplot y seaborn seguí en profundidad con mi análisis exploratorio de datos de cada variable de manera individual, análisis univariado y multivariado.
En el camino fui descartando información que consideraba poco útil para el enfoque de mi estudio, pero también fui sumando material para complementarlo; a continuación expongo en breves palabras la información cada contiene cada uno de los dataset que elegí:


         df1  #Acceso por cada 100 hogares distribuido por porvincias, año y trimestre
         df4  #Acceso por banda ancha y por banda angosta, por trimestre, por provincia
         df5  #Acceso por ADSL,Cablemodem,Fibra óptica,Wireless,Otro. Por trimestre, sin distincion entre provincias
         df9  #Velocidad media de bajada, por trimestre, por provincia
         df13 #Ingresos por prestación de servicios, por trimestre, en todo el país.
         df17 #Distinción de qué tipo de conecciones (ADSL	CABLEMODEM	DIALUP	FIBRAOPTICA	4G	3G	TELEFONIAFIJA	WIRELESS	SATELITAL) 
         #dispone cada localidad, distinguido por partido y provincia, además agrega latitud y longitud.
         df18 #Tipo de reclamo y cantidad de cada tipo de reclamo
         df19 #Fondos destinados, adjudicados y ejecutados por año, al crecimiento de las tecnologías de la informacion
         df20 #Ingresos por provincia


### **ATENCION! POSIBLE OUTLIER A LA VISTA!! **

 En el primer dataframe, de acceso por cada 100 hogares, la Capital Federal registraba un número mayor a 100 accesos, lo cual en principio me resultó extraño...
 Cómo va a haber más accesos por hogares que hogares en sí? Por lo que recurrí a la herramienta más usada por la mayoría de los humanos: Google. Ingresé a diarios,
 datos del Indec, entre otros y efectivamente, Capital Federal tiene más de un 100% de accesos a internet, medida que además incrementa con el correr del tiempo. 
 A partir de esto, me surgieron otras dudas: ¿Cómo llegan a pasar el 100%? ¿Tendrán establecida una máxima velocidad de carga y descarga, entonces los que estén por
 encima de esa máxima aumentan ese porcentaje? ¿Será que algunos hogares tienen más de un dispositivo covertidor de señales? En fin, esa respuesta no la encontré y
 la verdad que me intriga bastante... y ustdes, saben el por qué?????? En fin, el dato era certero, por lo que decidí dejarlo como estaba.


`KPIs`

 También se pidió en la propuesta de trabajo establecer 4 KPIs con el fin de monitorear la eficacia de los objetivos de la empresa de telecomunicaciones. El primer
 KPI ya lo daban como consigna y se trata de: Aumentar en un 2% el acceso al servicio de internet para el próximo trimestre, cada 100 hogares. Los 3
 restantes son a criterio, gusto (y por qué no ingenio??) del alumno. 
 A continuación voy a listar los KPIs y encontrar ideas para la puesta en marcha del mismo:


**KPI 1 - Aumentar en un 2% el acceso al servicio de internet para el próximo trimestre, cada 100 hogares:** se pueden utilizar diversas estrategias de marketing y de negocios para fijar esto como objetivo. Primero veamos una cosa: Cuánto creció el nivel de acceso a internet entre los últimos 2 trimestres que tenemos listados? (2 y 3 del 2022).

Vemos que para el 2do trimestre del 2022 hay un total de accesos de 1626,8 hogares con acceso a esta tecnología y para el siguiente trimestre un 1646.07. Lo que significa que ya está habiendo un crecimiento del 1.18%. Seamo ambicisos y pidamos un poquito más... 
un 2.5%? un 3%?. Veamos qué cosas podemos hacer para lograrlo:


     -Campañas de marketing digital: Se pueden desarrollar campañas publicitarias para aumentar la conciencia y la demanda del servicio de Internet. Estas campañas pueden estar dirigidas a los hogares que aún no tienen acceso al servicio de Internet, enfatizando los beneficios que pueden obtener al suscribirse al servicio. Podemos enfatizar sobre las provincias que no superan el 60% de los accesos, éstas son: Chaco, Corrientes, Formosa, Mendoza, Misiones, Salta, San Juan, Santa Cruz y Santiago del Estero. 
     Más precisamente en las provincias de Santa Cruz, San Juan y Mendoza que son además de las provincias con mejor ingresos percápita.
 
     -Ofertas promocionales: Se pueden ofrecer ofertas promocionales para incentivar a los hogares a suscribirse al servicio de Internet. Estas ofertas pueden incluir descuentos en la tarifa mensual o un período de prueba gratuito. 
 
     -Alianzas estratégicas: Se pueden establecer alianzas con empresas que tengan una base de clientes similar a la de la empresa de telecomunicaciones, para promocionar conjuntamente los servicios de Internet y lograr una mayor penetración en el mercado. Por ejemplo, con empresas de telefonía y cable.
 
     -Mejora de la infraestructura: Para aumentar la cobertura del servicio de Internet, se puede invertir en la mejora de la infraestructura de la red. Esto puede incluir la instalación de nuevas torres de antenas, la implementación de fibra óptica, y la actualización de los equipos de red para ofrecer una mejor calidad de servicio.
 
 Todas estas propuestas podemos enfatizarlas sobre las provincias que no superan el 60% de los accesos, éstas son: Chaco, Corrientes, Formosa, Mendoza, Misiones, Salta, San Juan, Santa Cruz y Santiago del Estero. Más precisamente en las provincias de Santa Cruz, San Juan y Mendoza que son además de las provincias con mejores ingresos per cápita según información del INDEC (dejando de lado las provincias con buenos ingresos pero ya con altos porcentajes de acceso a internet).
 
 Por otra parte, podemos plantear estrategias de negocio dentro de la empresa, como pueden ser:
 
     -Reducción de costos: Se pueden implementar medidas para reducir los costos de operación de la empresa, lo que podría permitir una reducción de la tarifa mensual del servicio de Internet y, por lo tanto, atraer a más hogares.

     -Ampliación de la oferta de servicios: La empresa puede ampliar su oferta de servicios para incluir paquetes que incluyan televisión y telefonía, lo que podría atraer a hogares que buscan una solución completa de telecomunicaciones.

     -Mejora de la atención al cliente: Una atención al cliente eficiente y eficaz puede ser un factor determinante en la fidelización de los clientes. Por lo tanto, la empresa puede enfocarse en mejorar la calidad de atención al cliente para aumentar la satisfacción y la retención de los clientes existentes.

**KPI 2 - Aumentar la velocidad media de descarga en provincias donde estén por debajo de los 50 Mbps, en al menos 10 Mbps, para el próximo trimestre:** esta es una 
 medida importante para evaluar el rendimiento de la  red y el impacto de cualquier mejora realizada en la infraestructura. A excepción de la Capital Federal, 
 Buenos Aires y Catamarca, el resto de las provincias no llegan a los 50 Mbps de promedio de vel en sus conexiones a internet. Es un punto a reveer, ya que, si 
 ofrecemos un servicio éste debe funcionar de manera óptima. Nadie quiere que su internet funcione lento...

 Veamos que propuestas generamos para llegar a cumplir nuestro objetivo:

      -Actualizar la infraestructura: actualizar la infraestructura en provincias donde sólo tienen las tecnologías mas antiguas para mejorar la velocidad de descarga.

     -Implementar un sistema de equilibrio de carga: Un sistema de equilibrio de carga puede distribuir la carga de internet de manera uniforme entre los usuarios, 
     lo que puede mejorar la velocidad de descarga.

     -Aumentar la capacidad de la red: hay muchas provincias con gran cantidad de acceso a internet, pero con baja velocidad de bajada, por lo que se podría considerar 
     aumentar la capacidad de la red en esas áreas para mejorar la velocidad de descarga.

     -Optimizar los equipos de red: Al monitorear el rendimiento de los equipos de red, se puede identificar y resolver problemas que puedan estar limitando la 
     velocidad.


**KPI 3 - Disminuir la cantidad de reclamos por día, en un 30% para el próximo trimestre:** en el sitio web se encuentra un gráfico sobre la cantidad y tipo de reclamo
 que recibe un trabajador de la empresa por día, los reclamos están identificados por categorías, siendo los mismos Facturación Gestiones Administrativas y
 Problemas técnicos (éste último en mayor medida), veamos qué propuestas podemos plantear:

     -Mejorar la calidad del servicio: La mejor manera de reducir los reclamos por el servicio es mejorar la calidad del servicio que se ofrece a los clientes. 
     Esto podría implicar mejorar la infraestructura, capacitar al personal y brindar un servicio al cliente excepcional.
     
     -Ofrecer opciones de autoservicio: Muchos clientes prefieren resolver problemas por sí mismos en lugar de llamar a la empresa. Ofrecer opciones de autoservicio, 
     como un centro de ayuda en línea o un chatbot, podría reducir la cantidad de llamados de reclamo.
     
     -Implementar sistemas de seguimiento de reclamos: Implementar un sistema que permita hacer seguimiento a los reclamos de los clientes podría ayudar a la empresa 
     a detectar y resolver problemas recurrentes que generan reclamos.
     
     -Realizar encuestas de satisfacción del cliente: Realizar encuestas de satisfacción del cliente permitirá a la empresa obtener información valiosa sobre la 
     experiencia de los clientes con el servicio, lo que puede ayudar a identificar áreas de mejora y reducir la cantidad de llamados de reclamo.
     
     -Brindar incentivos por no realizar reclamos: Ofrecer incentivos a los clientes por no realizar reclamos podría motivarlos a usar el servicio de manera más 
     responsable y reducir la cantidad de llamados de reclamo.
     
     -Implementar un programa de fidelización: Un programa de fidelización podría ayudar a la empresa a retener a sus clientes y reducir la cantidad de llamados
     de reclamo. Los clientes que se sienten valorados y apreciados por la empresa son menos propensos a realizar reclamos.

**KPI 4 - Disminuir el tiempo de resolución de problemas para el próximo trimestre:** Este KPI mide el tiempo promedio que tarda la empresa en resolver problemas técnicos o de servicio. Un tiempo de resolución rápido es un indicador de un servicio de atención al cliente eficiente y efectivo. Propongamos ideas:   

     -Establecer objetivos de tiempo de resolución: Es importante que la empresa defina objetivos claros para el tiempo de resolución de problemas técnicos o de servicio. Estos objetivos deben ser realistas y alcanzables, y se deben comunicar claramente a todo el personal involucrado en el proceso de atención al cliente. Por ejemplo, para una falla normal, el cliente no puede estar más de 2 días sin servicio.
     
     -Monitoreo constante: La empresa debe monitorear continuamente el tiempo que tarda en resolver los problemas técnicos o de servicio. Esto puede hacerse mediante la implementación de un software de seguimiento de tickets o una herramienta de gestión de incidencias.
     
     -Identificación de las causas de los retrasos: Si la empresa está teniendo problemas para cumplir con los objetivos de tiempo de resolución, es importante identificar las causas de los retrasos. Estos pueden incluir una falta de personal capacitado, un sistema de seguimiento de tickets ineficiente o un alto volumen de solicitudes de atención al cliente.
     
     -Comunicación con los clientes: La empresa debe comunicar con los clientes de manera clara y efectiva sobre el tiempo de resolución de los problemas técnicos o de servicio. Esto les permitirá saber qué esperar y les dará confianza en la capacidad de la empresa para resolver sus problemas de manera oportuna y eficiente.


 Con esto doy por concluído el informe. En mi repositorio encontrarán un archivo .py con el análisis exploratorio de datos, otro archivo con el dashboard y la carpeta
 con los csv que elegí luego de realizar el análisis exploratorio (incluyen datos de servicios móviles, info de indec, etc). También hay un archivo de información 
 general que me pareció muy interesante en el cual me basé para redactar el presente informe. Un placer que hayan llegado hasta aquí! 
 Desde ya muchas gracias por su atención!!!!!
 
 REFERENCIAS:
     
 https://datosabiertos.enacom.gob.ar/home
     
 https://www.indec.gob.ar/

  
