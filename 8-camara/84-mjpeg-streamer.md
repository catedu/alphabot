#MJPEG-Streamer
Es una aplicación que simplemente captura imágenes (frames) en JPEG y transmitirlas vía HTTP. [Su página oficial de instalación.](https://snapcraft.io/mjpg-streamer)
##Instalación desde GitHub
Actualmente está un poco parado el proyecto,tal y como dice [aquí](https://sourceforge.net/p/mjpg-streamer/wiki/Home/) pero se puede instalar desde este Github que sigue vivo y que tiene las instrucciones para su instalación.
https://github.com/jacksonliam/mjpg-streamer
##Instalación desde Waveshare
Tiene algunos pasos algo complejos:

**1.- Añadimos la siguiente línea en el archivo modules que está en la carpeta etc**
>bcm2835-v4l2 

![](/assets/mjpeg1.png.jpg)

Si estas en una terminal, puedes ejecutar un editor de texto
> **sudo nano /etc/modules **

añadir
>bcm2835-v4l2 

Grabar con Ctrl+O con el mismo nombre (sobrescribiendo) y salir con Ctrl+X

![](/assets/sudonanomodules.jpg)

**2.- Reiniciamos para que cargue el módulo señalado**

**3.- Instalamos estas librerías:**

>sudo apt-get install libv4l-dev libjpeg8-dev

>sudo apt-get install subversion

**4.-En la página https://www.waveshare.com/wiki/AlphaBot tienes Software demo y también el software WepIOPi y MJPEG-Streamer:**

![](/assets/descargawiki.jpg)

Se descargará un fichero comprimido que lo descomprimiremos en la Raspberry 

**5.-Entrar en el directorio donde esta mjpeg-streamer, abrimos una terminal con el botón derecho en esa carpeta:**

![](/assets/mjpeg2.jpg)

**6.-Compilamos la librería:**
>make USE_LIBV4L2=true clear all

Si sale bien, saldrá el mensaje : _ No rule to make target 'clear'. Stop._ .
Si sale mal, tienes que entrar en el fichero que está en _mjpg-streamer/plugins/input_uvc/input_uvc.c_ y cambiar donde pone V4L2_PIX_FMT_MJPEG por V4L2_PIX_FMT_YUYV 



