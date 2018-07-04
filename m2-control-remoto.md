#M2 CONTROL REMOTO

¿Qué esperas? te lo pide el cuerpo !!! vamos a hacer un control remoto del robot !!

Vamos a definir las siguientes teclas

gobernado por el teclado *numérico*:

* PARAR = tecla 5
* ADELANTE=FORDWARD = 8
* ATRAS=BACKWARD = 2
* DERECHA=RIGHT = 6
* IZQUIERDA=LEFT = 4



```cpp+lineNumbers:true

import RPi.GPIO as GPIO
import time

from VARIABLES import *

import MOVIMIENTOS
import MOVIMIENTOSPASO
import NEC

vel=50

print ('TECLAS :\nPARAR = tecla 5\nADELANTE=FORDWARD = 2\nATRAS=BACKWARD = 8\nDERECHA=RIGHT = 6\nIZQUIERDA=LEFT = 4')

key=0
while key!=28:
    key=NEC.getkey()
    if (key != None):
        if key==24:
            print ('\nadelante')
            MOVIMIENTOS.FORDWARD(vel)
        if key==82:
            print ('\natrás')
            MOVIMIENTOS.BACKWARD(vel)
        if key==90:
            print ('\nderecha')
            MOVIMIENTOS.RIGHT(vel)
        if key==8:
            print ('\nizquierda')
            MOVIMIENTOS.LEFT(vel)
        if key==28:
            print ('\nFin, has apretado STOP')
            MOVIMIENTOS.STOP()
    
        

```