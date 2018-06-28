#M1 Mi primer baile

Vamos a realizar un sencillo programa para romper el hielo, unos movimientos delante, atrás, derecha, izquierda y paro:

{% youtube %}https://www.youtube.com/watch?v=WAycuDaKB0Q{% endyoutube%}

##Solución
```cpp+lineNumbers:true
import RPi.GPIO as GPIO
import time
###################TABLA CONEXIONES RASPBERRY ###########################
IN1=12;IN2=13;ENA=6;IN3=20;IN4=21;ENB=26
#################################CONFIGURACION GPIO ENTRASDAS SALIDAS ####
GPIO.setmode(GPIO.BCM);GPIO.setwarnings(False)
GPIO.setup(IN1,GPIO.OUT);GPIO.setup(IN2,GPIO.OUT);GPIO.setup(IN3,GPIO.OUT);GPIO.setup(IN4,GPIO.OUT)
GPIO.setup(ENA,GPIO.OUT);GPIO.setup(ENB,GPIO.OUT)
################################# POTENCIA DE LOS MOTORES
PWMA = GPIO.PWM(ENA,500);PWMB = GPIO.PWM(ENB,500)
PWMA.start(50);PWMB.start(50)
#####################################FUNCIONES#######################
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
######################################################
FORDWARD()
time.sleep(1)
BACKWARD()
time.sleep(1)
LEFT()
time.sleep(1)
RIGHT()
time.sleep(1)
STOP()



```