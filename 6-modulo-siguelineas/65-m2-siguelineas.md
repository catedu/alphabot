#M2 Sigue líneas
Vamos a realizar un programa que siga la línea:
* Pero AL REVÉS!!! ¿por qué marcha atrás? mira al final de la página.

Fijaremos de antemano una velocidad pequeña de 25 y un incremento de velocidad en los motors de 10 cuando no está centrado. Veamoslo con un vídeo:

{% youtube %}https://www.youtube.com/watch?v=rsdQ9fGOl-I&feature=youtu.be{% endyoutube %}



###Solución
La solución es fácil con la librería TLC1543.py donde la función **SENSORLINEA(cual)** nos da el valor que lee los sensores IR. Recuerda que TLC1543.py en la misma carpeta que vamos a crear este programa y las incorporamos en el programa con **import**.
* También incorporamos las variables definidas en **VARIABLES.py**
 
¿Te atreves?

%accordion%Solución%accordion%

* Leemos la lectura de los 5 sensores
* Ajustamos la velocidad de los motores según si hay lectura de línea negra y donde
* La potencia PWM no puede pasar de 0 a 100 por eso limitamos los valores
* Si no hay linea negra que vuelva hasta que recupera la línea negra:

Fichero [Siguelineas.py](https://github.com/JavierQuintana/AlphabotPython/)

```cpp+lineNumbers:true
import RPi.GPIO as GPIO
import time

import TLC1543

from VARIABLES import *
from random import randint

x=[0,0,0,0,0]
vel=25
blanco=14
incremento=10
tiempo = 0.2


##hacia DELANTE        
GPIO.output(IN1,GPIO.LOW)
GPIO.output(IN2,GPIO.HIGH)
GPIO.output(IN3,GPIO.HIGH)
GPIO.output(IN4,GPIO.LOW)

while True:
    lineanegra=0
    #Leemos los siguelíneas
    for i in range(5):
        x[i]=TLC1543.SENSORLINEA(i)
        if (x[i]<blanco):
            lineanegra=1
    #Decidimos velocidades 
    if (lineanegra):  ##ha encontrado línea negra
        ##hacia DELANTE        
        GPIO.output(IN1,GPIO.LOW)
        GPIO.output(IN2,GPIO.HIGH)
        GPIO.output(IN3,GPIO.HIGH)
        GPIO.output(IN4,GPIO.LOW)
        velA=vel
        velB=vel        
        if (x[1]<blanco):
            velA=velA+incremento
            velB=velB-incremento
        if (x[3]<blanco):
            velA=velA-incremento
            velB=velB+incremento    
        if (x[0]<blanco):
            velA=velA+incremento
            velB=velB-incremento 
        if (x[4]<blanco):
            velA=velA-incremento
            velB=velB+incremento
        if (velA<10):
            velA=10
        if (velA>90):
            velA=90
        if (velB<10):
            velB=10
        if (velB>90):
            velB=90
        ##activamos motores
        print ('con linea negra SENSORES=',x[0],'-',x[1],'-',x[2],'-',x[3],'-',x[4],'-VELA=',velA,'VELB=',velB);
        PWMA.start(velA)
        PWMB.start(velB)
        #time.sleep(tiempo)
    else:           ##no tiene linea negra pues marcha atrás y que lo busque
        GPIO.output(IN1,GPIO.HIGH)
        GPIO.output(IN2,GPIO.LOW)
        GPIO.output(IN3,GPIO.LOW)
        GPIO.output(IN4,GPIO.HIGH)
        while (lineanegra==0):
            velA=randint(vel-incremento,vel+incremento)
            velB=vel-(velA-vel)  #el opuesto
            print ('SIN linea negra VELA=',velA,'VELB=',velB);
            PWMA.start(velA)
            PWMB.start(velB)
            time.sleep(tiempo)
            for i in range(5):
                x[i]=TLC1543.SENSORLINEA(i)
                if (x[i]<blanco):
                    lineanegra=1        
         
           
    
   
    
```
%/accordion%

#¿Por qué este ejercicio ALPHABOT va al revés?
Por que los sensores siguelineas por la parte de atrás y funcionando ALPHABOT hacia delante **SE PRODUCE UNA REALIMENTACIÓN POSITIVA** es decir, cuando detecta que hay que girar, gira, pero la cola se mueve demasiado deprisa que produce que pierda la línea