#¿Qué vamos a hacer?

Manejar la cámara web es fácil si queremos que salga por la salida HDMI de la Raspberry, simplemente ejecutando el siguiente código Python sale, en este caso durante 10 segundos **Pero no sale por VNC ni por SSH**:
```cpp+lineNumbers:true
from picamera import PiCamera
from time import sleep
camera = PiCamera()
camera.start_preview()
sleep(10)
camera.stop_preview()
```
Pero nosotros necesitamos que retransmita las imágenes, pues el robot se mueve, no tiene instalado un monitor, luego los pasos son los siguientes:

1. Instalar un programa servidor via web (tipo como el Apache pero adaptado a IO para la Raspberry) se llama **WEBIOPI.**
1. Instalar el programa que se ejecutará sobre el anterior y que nos retransmitirá el streaming **MJPG-STREAMER.**

