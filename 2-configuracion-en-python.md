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

Luego una de las primeras líneas que hay que poner en nuestros programas es

```cpp+lineNumbers:true
IN1=12;IN2=13;ENA=6;IN3=20;IN4=21;ENB=26
GPIO.setmode(GPIO.BCM);GPIO.setwarnings(False)
GPIO.setup(IN1,GPIO.OUT);GPIO.setup(IN2,GPIO.OUT);GPIO.setup(IN3,GPIO.OUT);GPIO.setup(IN4,GPIO.OUT)
GPIO.setup(ENA,GPIO.OUT);GPIO.setup(ENB,GPIO.OUT)
```
Donde el significado de los interfaces es:

|IN1| IN2| IN3| IN4| Descripción|
|---|----|----|----|------------|
|1 |0 |0 |1 |Motores hacia delante|
|0 |1 |1 |0 |Motores hacia atrás|
|0 |0 |0 |1 |Giro derecha|
|1 |0 |0 |0 |Giro izquierda|
|0 |0 |0 |0 |Stop|

ENA y ENB = Potencia de los motores A y B.

Luego podemos definir en nuestros programas unas funciones para simplificar código:

```cpp+lineNumbers:true
def FORDWARD():
    GPIO.output(IN1,GPIO.HIGH);GPIO.output(IN2,GPIO.LOW);GPIO.output(IN3,GPIO.LOW);GPIO.output(IN4,GPIO.HIGH)
def BACKWARD():
    GPIO.output(IN1,GPIO.LOW);GPIO.output(IN2,GPIO.HIGH);GPIO.output(IN3,GPIO.HIGH);GPIO.output(IN4,GPIO.LOW)
def LEFT():
    GPIO.output(IN1,GPIO.LOW);GPIO.output(IN2,GPIO.LOW);GPIO.output(IN3,GPIO.LOW);GPIO.output(IN4,GPIO.HIGH)
def RIGHT():
    GPIO.output(IN1,GPIO.HIGH);GPIO.output(IN2,GPIO.LOW);GPIO.output(IN3,GPIO.LOW);GPIO.output(IN4,GPIO.LOW)
def STOP():
    GPIO.output(IN1,GPIO.LOW);GPIO.output(IN2,GPIO.LOW);GPIO.output(IN3,GPIO.LOW);GPIO.output(IN4,GPIO.LOW)
```





