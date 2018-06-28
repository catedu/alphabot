#Configurar mis programas en Python para que funcionen en Alphabot
####Configurar motores
Evidentemente los sensores, motores, etc... estarán conectados en algún pin de la GPIO (¿qué es eso? Pues eso es que no te has leido [esto](https://catedu.gitbooks.io/raspberry-muy-basico/content/2-gpio.html)).

| Interfaces | Pines GPIO de la Raspberry Pi |
|------------|--------------|
|   IN1      | P12          |
|   IN2      | P13          |
|   ENA      | P6           |
|   IN3      | P20          |
|   IN4      | P21          |
|   ENB      | P26          |

Donde el significado de los interfaces es:

|IN1| IN2| IN3| IN4| Descripción|
|---|----|----|----|------------|
|1 |0 |0 |1 |Motores hacia delante|
|0 |1 |1 |0 |Motores hacia atrás|
|0 |0 |0 |1 |Giro derecha|
|1 |0 |0 |0 |Giro izquierda|
|0 |0 |0 |0 |Stop|



