#Posibilidad sensor Ultrasonidos
Se puede conseguir más precisión añadiendo un tercer sensor y mucho más preciso: El sensor de Ultrasonidos. 

![](https://catedu.gitbooks.io/programa-arduino-mediante-codigo/content/img/Captura_de_pantalla_2015-04-01_a_las_22.40.00.png)

Mira en [esta página](https://catedu.gitbooks.io/programa-arduino-mediante-codigo/content/sensor_de_ultrasonidos.html) para saber cómo se utiliza con el Arduino.

Básicamente se emite un pulso por el pint Trigger, él emite una señal de 40kHz y según el eco recibido saca por Output un pulso cuyo ancho es proporcional a la distancia:

![](/assets/ultrasonidos.jpg)

En Alphabot se conectaría los cables en el conector blanco de abajo y el ultrasonidos con unos tornillos en los dos agujeros de la parte delantera:

![](/assets/conexionUS.jpg)

Para sujetar el sensor ultrasonidos al chasis habría que comprar un soporte:

![](/assets/soporteus.png)

Los dos elementos: Sensor ultrasonidos como el HC-SR04 y el soporte son **muy comunes y muy baratos**

ATENCIÓN: El kit de CATEDU no lo proporciona en parte debido a que molesta para el movimiento de la cámara.