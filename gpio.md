#GPIO y PYTHON

##GPIO
Vamos a recordar lo que vimos [aquí](https://catedu.gitbooks.io/raspberry-muy-basico/content/2-gpio.html), dos cosas: 
* Estos son los pines GPIO 

![](https://docs.microsoft.com/en-us/windows/iot-core/media/pinmappingsrpi/rp2_pinout.png)

* Y sobre todo Están diseñados para 3.3V sólo proporcionan 3mA cada pin luego NO conectes diréctamente componentes de 5V ni  que consuman más corriente o de lo contrario ESTROPEARÁS LA RASPBERRY DE FORMA IRREVERSIBLE, o sea, directamente sólo LEDs, todo lo demás a través de chips drivers. 

##Librería GPIO
Necesitamos una librería GPIO que Raspbian lo tiene por defecto, pero sino lo tienes, ejecuta estas instrucciones en un terminal por ejemplo por SSH:
* Descargar la librería
w_get 'http://downloads.sourceforge.net/project/raspberry-gpio-python/RPi.GPIO-0.5.4.tar.gz'_
* Descomprimir la librería:
_tar zxvf RPi.GPIO-0.5.4.tar.gz_
* Entramos en la carpeta :
_cd RPi.GPIO-0.5.4/_
* Instalamos la librería 
_sudo python setup.py install_
* Si lo anterior de da problemas es porque no tienes instalado el compando python-dev
_sudo apt-get install python-dev_

##Ejemplo de utilización de la librería GPIO

El siguiente ejemplo enciende un LED puesto en el GPIO 4 (pin 7)

import RPi.GPIO as GPIO
import time
GPIO.setmode(GPIO.BCM)
GPIO.setup(7, GPIO.OUT) ## GPIO 7 como salida

