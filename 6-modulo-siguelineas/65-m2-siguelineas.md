#M2 Sigue líneas



###Solución
La solución es fácil con la librería TLC1543.py donde la función **SENSORLINEA(cual)** nos da el valor que lee los sensores IR. Recuerda que TLC1543.py en la misma carpeta que vamos a crear este programa y las incorporamos en el programa con **import**.
* También incorporamos las variables definidas en **VARIABLES.py**
* Hay que ajustar la velocidad de los motores según la diferencia de lecturas con respecto al valor central 
¿Te atreves?

%accordion%Solución%accordion%

Fichero [M2-Siguelineas.py](https://github.com/JavierQuintana/AlphabotPython/)

```cpp+lineNumbers:true



import RPi.GPIO as GPIO
import time

import TLC1543


x=[0,0,0,0,0]
vel=50

error=10
incremento=20

##motores hacia delante
GPIO.output(IN1,GPIO.HIGH)
GPIO.output(IN2,GPIO.LOW)
GPIO.output(IN3,GPIO.LOW)
GPIO.output(IN4,GPIO.HIGH)
   

while True:
    #Leemos los siguelíneas    
    for i in range(5):
        x[i]=TLC1543.SENSORLINEA(i)
    #Decidimos velocidades según diferencias con respecto al valor central
    velA=vel+(x[0]-x[2])
    velA=vel+(x[1]-x[2])
    velB=vel+(x[3]-x[2])
    velA=vel+(x[4]-x[2]) 
    ##hacia delante
    PWMA.start(velA)
    PWMB.start(velB)
    
```
%/accordion%