#Fichero VARIABLES.py

Debido a que vamos a utilizar varias variables que serán comunes a varias librerías que también vamos a crear, vamos a crear un fichero común a todos, de momento será este:

```cpp+lineNumbers:true
import RPi.GPIO as GPIO

IN1=12
IN2=13
ENA=6
IN3=20
IN4=21
ENB=26

##############CONFIGURACION GPIO ENTRADAS SALIDAS ####
GPIO.setmode(GPIO.BCM)
GPIO.setwarnings(False)
GPIO.setup(IN1,GPIO.OUT)
GPIO.setup(IN2,GPIO.OUT)
GPIO.setup(IN3,GPIO.OUT)
GPIO.setup(IN4,GPIO.OUT)
GPIO.setup(ENA,GPIO.OUT)
GPIO.setup(ENB,GPIO.OUT)

########################### VELOCIDAD DE LOS MOTORES
PWMA = GPIO.PWM(ENA,500)
PWMB = GPIO.PWM(ENB,500)
```