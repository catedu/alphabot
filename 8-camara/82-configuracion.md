#Configuración
Lo primero que tienes que hacer es activar la cámara y Remote GPIO: Entra en la configuración y actívalo. Mira [el capítulo 8.1 de Raspberry básico ](https://catedu.gitbooks.io/raspberry-muy-basico/content/8-vnc/81-vnc-server.html)donde activamos VNC Server, y verás que también están la opciónes de **activar la cámara y Rempote GPIO**.

![](/assets/configuracionRaspberry.jpg)

Si estás utilizando la Raspberry pero no de forma gráfica sino textual con SSH el comando a utilizar es 
**sudo raspi-config**
entra en la opción 5

![](/assets/2019-01-30 07_31_50-pi@raspberrypi_ ~.jpg)

Y activas la cámara y Remote SSH

![](/assets/2019-01-30 07_32_26-pi@raspberrypi_ ~.jpg)

>Si no activas Remote GPIO te saldrá un error tipo ERR_CONTENT_LENGTH_MISMATCH cuando quieras ver WebIOPi


