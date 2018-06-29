#M1 Mi primer baile

Vamos a realizar un sencillo programa para romper el hielo, unos movimientos delante, atrás, derecha, izquierda y paro utilizando la librería anterior:

{% youtube %}https://www.youtube.com/watch?v=WAycuDaKB0Q{% endyoutube%}

##Solución
```cpp+lineNumbers:true
import RPi.GPIO as GPIO
import time

import MOVIMIENTOS

MOVIMIENTOS.FORDWARD(50)
time.sleep(1)
MOVIMIENTOS.BACKWARD(50)
time.sleep(1)
MOVIMIENTOS.LEFT(50)
time.sleep(1)
MOVIMIENTOS.RIGHT(50)
time.sleep(1)
MOVIMIENTOS.STOP()
```