#Posibilidad sensor Ultrasonidos
Se puede conseguir más precisión añadiendo un tercer sensor y mucho más preciso: El sensor de Ultrasonidos. 

![](https://catedu.gitbooks.io/programa-arduino-mediante-codigo/content/img/Captura_de_pantalla_2015-04-01_a_las_22.40.00.png)

Mira en [esta página](https://catedu.gitbooks.io/programa-arduino-mediante-codigo/content/sensor_de_ultrasonidos.html) para saber cómo se utiliza con el Arduino.

Básicamente se emite un pulso por el pin **Trigger**, él emite una señal de 40kHz y según el eco recibido saca por **Output** un pulso cuyo ancho es proporcional a la distancia:

![](/assets/ultrasonidos.jpg)

En Alphabot se conectaría los cables en el conector blanco de abajo y el ultrasonidos con unos tornillos en los dos agujeros de la parte delantera:

![](/assets/conexionUS.jpg)

Para sujetar el sensor ultrasonidos al chasis habría que comprar un soporte:

![](/assets/soporteus.png)

Los dos elementos: Sensor ultrasonidos como el HC-SR04 y el soporte son **muy comunes y muy baratos**

### ATENCIÓN: 
El kit de CATEDU no lo proporciona en parte debido a que molesta para el movimiento de la cámara, habría que hacer alguna chapa o algo para adelantar y alejar el sensor de ultrasonidos del brazo de robot.
También por otra razón: la parte didáctica de evitar obstáculos está satisfecho con los sensores de infrarrojos.
###Bueno, si aún así me decido ponerlo ¿cómo se programa?
Muy fácil, el conector blanco de abajo está conectado con los siguientes GPIO:
* Echo en el GPIO 5
* Trigger en el GPIO 17

Por lo tanto, viendo la teoría, una posible función en código Python para utilizarlo sería:

* Emitir un pulso alto por TRIG durante 15 microsegundos.
* Esperar el pulso alto de ECHO
* Cronometrar el pulso alto de ECHO
* La distancia será velocidad por tiempo o sea: la diferencia el tiempo del pulso ECHO multiplicado por la velocidad del sonido y dividido por 2 pues es el recorrido del sonido ida y vuelta.

```cpp+lineNumbers:true
TRIG = 17
ECHO = 5

GPIO.setup(TRIG,GPIO.OUT,initial=GPIO.LOW)
GPIO.setup(ECHO,GPIO.IN)

def Distance():
	GPIO.output(TRIG,GPIO.HIGH)
	time.sleep(0.000015)
	GPIO.output(TRIG,GPIO.LOW)
	while not GPIO.input(ECHO):
		pass
	t1 = time.time()
	while GPIO.input(ECHO):
		pass
	t2 = time.time()
	return (t2-t1)*34000/2
```