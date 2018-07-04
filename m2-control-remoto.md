#M2 CONTROL REMOTO

```cpp+lineNumbers:true
import RPi.GPIO as GPIO
import time
from VARIABLES import *
import MOVIMIENTOS
import MOVIMIENTOSPASO
import NEC

#key=''

while True:
		key = NEC.getkey()
		if(key != None):
			if key == "repeat":
				n = 0				 
			if key == 0x18:
				MOVIMIENTOS.FORDWARD(50)
				print("forward")
			if key == 0x08:
				MOVIMIENTOS.LEFT(50)
				print("left")
			if key == 0x1c:
				MOVIMIENTOS.STOP()
				print("stop")
			if key == 0x5a:
				MOVIMIENTOS.RIGHT(50)
				print("right")
			if key == 0x52:
				MOVIMIENTOS.BACKWARD(50)		
				print("backward")

		else:
			n += 1
			if n > 20000:
				n = 0
				MOVIMIENTOS.STOP()
				
```