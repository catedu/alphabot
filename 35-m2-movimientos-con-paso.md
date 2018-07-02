#Movimientos con paso y teclas

Vamos a hacer un programa para utilizar la librería anterior MOVIMIENTOSPASO.py y gobernado por el teclado:

* PARAR = tecla ESPACIO
* ADELANTE=FORDWARD = f
* ATRAS=BACKWARD = b
* DERECHA=RIGHT = r
* IZQUIERDA=LEFT = l

Fijaremos de antemano las velocidades y el paso a 50 y 10 por ejemplo.
####Solución
* Ponemos las librerías fichero [MOVIMIENTOS.py](/24-libreria-movimientospy.md) y [MOVIMIENTOSPASO.py](/34-movimientospasopy.md) en la misma carpeta que vamos a crear este programa y las incorporamos en el programa con **import**.
* Vamos llamando a las distintas funciones de movimientos según la tecla pulsada, fijamos la velocidad al 50%, por pantalla va saliendo el estado de los contadores.
* Todo dentro de un bucle de manera que si pulsamos la tecla espacio sale del buble no sin antes parar el robot.
%accordion%Solución%accordion%

Fichero [M2-Movimientos-Teclas.py](/Movimientos-tecla)
```cpp+lineNumbers:true
import RPi.GPIO as GPIO
import time

import MOVIMIENTOS
import MOVIMIENTOSPASO

velR=50
numR=10
velL=50

numL=10

print ('TECLAS ¡en minúscula!:\nPARAR = tecla ESPACIO\nADELANTE=FORDWARD = f\nATRAS=BACKWARD = b\nDERECHA=RIGHT = r\nIZQUIERDA=LEFT = l')
tecla='x' 
while tecla!=' ':
    tecla = input('\nPresiona una tecla y después enter : ')
    if tecla != ' ':
        print ('\nHas presionado ', tecla)
        if tecla=='f':
            print ('\nadelante')
            MOVIMIENTOSPASO.BOTH(velR,numR,velL,numL)
        if tecla=='b':
            print ('\natrás')
            MOVIMIENTOSPASO.BOTH(velR,-numR,velL,-numL)
        if tecla=='r':
            print ('\nderecha')
            MOVIMIENTOSPASO.BOTH(velR,-numR,velL,numL)
        if tecla=='l':
            print ('\nizquierda')
            MOVIMIENTOSPASO.BOTH(velR,numR,velL,-numL)

    else:
        print ('\nFin, has apretado STOP')
        MOVIMIENTOS.STOP()
```


