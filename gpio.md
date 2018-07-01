#GPIO y PYTHON

##GPIO
Vamos a recordar lo que vimos [aquí](https://catedu.gitbooks.io/raspberry-muy-basico/content/2-gpio.html), dos cosas: 
* Estos son los pines GPIO con la numeración BCM:

![](https://docs.microsoft.com/en-us/windows/iot-core/media/pinmappingsrpi/rp2_pinout.png)

* Y sobre todo  **RECUERDA** : Están diseñados para 3.3V sólo proporcionan 3mA cada pin luego NO conectes diréctamente componentes de 5V ni  que consuman más corriente o de lo contrario ESTROPEARÁS LA RASPBERRY DE FORMA IRREVERSIBLE, o sea, directamente sólo LEDs, todo lo demás a través de chips drivers. 

##Librería RPI.GPIO
Necesitamos una librería GPIO que Raspbian lo tiene por defecto, pero por si acaso ejecuta estas instrucciones:
>sudo apt-get install python-dev
>sudo apt-get install pyton-rpi.gpio

Normalmente te dirá que las tienes instaladas en su última versión.

##GPIO.setmode
Hay dos formas de utilizar la numeración de las GPIO, respetando la misma numeración que los pines de la placa, entonces la instrucción que tenemos que poner en nuestros programas es:
**GPIO.setmode(GPIO.BOARD)**
o utilización de la numeración BCM:
**GPIO.setmode(GPIO.BCM)**
nosotros elegiremos esta última por ser más sencilla, aunque tiene la desventaja de que si cambian en el futuro la numeraciones en los


##Ejemplo de utilización de la librería RPI.GPIO

El siguiente ejemplo enciende un LED puesto en el GPIO 4 (pin 7) durante 2 segundos

```cpp+lineNumbers:true
import RPi.GPIO as GPIO
import time
GPIO.setmode(GPIO.BCM)
GPIO.setup(4, GPIO.OUT) ## GPIO 7 como salida
GPIO.output(4,True) ##encendemos
time.sleep(2)        ## espera 2 segundos
GPIO.output(4,False)  ##APAGAMOS
```

