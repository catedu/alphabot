#Cómo funciona el sensor de velocidad

Las ruedas tienen un disco con agujeros que pasan por este sensor fotoeléctrico WYC-H206:

![](/assets/esquemasensorvelocidad.jpg) 

Están conectados a los siguientes GPIO:
* Motor derecha GPIO7
* Motor izquierda GPIO8

![](/assets/motoressensorvelocidad.jpg)

Si te fijas en las resistencias, están con la configuración **PULL-UP** ([aquí para saber +](https://catedu.gitbooks.io/programa-arduino-mediante-codigo/content/resistencias_pullup_y_pulldown.html) en el curso Arduino) ¿qué significa esto? pues que van al revés, cuando el circuito está encendido ON transmite un 0 lógico, y al revés, lo puedes ver mejor en estas fotografías:

![](/assets/sensorvelocidadOFF.jpg)
![](/assets/sensorvelocidadON.jpg)
