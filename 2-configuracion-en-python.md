#Motores
Evidentemente los sensores, motores, etc... estarán conectados en algún pin de la GPIO (¿qué es eso? Pues eso es que no te has leido [esto](https://catedu.gitbooks.io/raspberry-muy-basico/content/2-gpio.html)).

| Interfaces | Pines GPIO de la Raspberry Pi |
|------------|--------------|
|   IN1      | P12          |
|   IN2      | P13          |
|   ENA      | P6           |
|   IN3      | P20          |
|   IN4      | P21          |
|   ENB      | P26          |

Luego una de las primeras líneas que hay que poner en nuestros programas es traducir esos números a letras para que sea más facil utilizarlos en el código, y definir esos pines como pines de salida que van a gobernar a los motores:

```cpp+lineNumbers:true
###Cremos una variable GPIO definido en la librería GPIO
import RPi.GPIO as GPIO

IN1=12;IN2=13;ENA=6;IN3=20;IN4=21;ENB=26

GPIO.setmode(GPIO.BCM);GPIO.setwarnings(False)
GPIO.setup(IN1,GPIO.OUT);GPIO.setup(IN2,GPIO.OUT);GPIO.setup(IN3,GPIO.OUT);GPIO.setup(IN4,GPIO.OUT)
GPIO.setup(ENA,GPIO.OUT);GPIO.setup(ENB,GPIO.OUT)
```
##¿Qué significan IN1 IN2 IN3 IN4 ?

|IN1| IN2| IN3| IN4| Descripción|
|---|----|----|----|------------|
|1 |0 |0 |1 |Motores hacia delante|
|0 |1 |1 |0 |Motores hacia atrás|
|0 |0 |0 |1 |Giro derecha|
|1 |0 |0 |0 |Giro izquierda|
|0 |0 |0 |0 |Stop|

##¿Y qué significa ENA ENB?
ENA y ENB es la velocidad de los motores A y B respectivamente.

Su valor tiene que ser analógico pero los GPIO son digitales, así que tienen que ser señales PWM ¿que no sabes qué es eso? Pues tendrías que haber hecho nuestro curso Arduino lo dice en el [capítulo 2.4](https://catedu.gitbooks.io/programa-arduino-mediante-codigo/content/un_caso_especial_seales_pwm.html)

Para ello definimos en PYTHON una variable nueva tipo PWM que está definido en la librería GPIO y la llamaremos PeWMA para el motor A y PWMB para el motorB utilizando la función PWM de la variable GPIO que hemos definido en la instrucción _import RPi.GPIO as GPIO_

PWMA = GPIO.PWM(pin, frecuencia) pondremos para el motor A el pin ENA y frecuencia 500, y para PWMB lo mismo o sea PWMB = GPIO.PWM(ENB,500)





Luego el código que tenemos que poner al principio de nuestro programa es:

```cpp+lineNumbers:true
PWMA = GPIO.PWM(ENA,500);PWMB = GPIO.PWM(ENB,500)
PWMA.start(50);PWMB.start(50)
```
###Bueno, pero ... ¿Por qué?
Porque en el AlphaBot están conectados los pines IN1 IN2 IN3 IN4 ENA ENB en los pines de un chip L298P que hace de driver a los motores (nunca conectes un motor a un GPIO de la Raspberry[ ya lo sabes](https://catedu.gitbooks.io/raspberry-muy-basico/content/2-gpio.html))
![](/assets/2018-06-28 16_07_34-AlphaBot-User-Manual - PDF-XChange Viewer.png)
##Vale... ¿Y cómo se utiliza?
Podemos definir en nuestros programas unas funciones para simplificar código:

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





