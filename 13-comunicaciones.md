#Configuración

1. Tienes que instalar el sistema operativo Raspbian en la micro tarjeta SD (que ya tiene **Python**) para ello tienes que seguir los pasos de los apuntes de [**los apuntes Raspberry muy básico**](https://catedu.gitbooks.io/raspberry-muy-basico/content/). Concrétamente el [capítulo 3](https://catedu.gitbooks.io/raspberry-muy-basico/content/3-raspbian.html).
1. Una vez instalado tienes que conectar la Raspberry a la wifi, para ello sigue los pasos marcados en el [capítulo 4](https://catedu.gitbooks.io/raspberry-muy-basico/content/4-primera-comunicacion.html).
1. Recomendable pero no obligatorio, es aprender a configurar el sistema operativo, [comunicarte con él via texto por SSH](https://catedu.gitbooks.io/raspberry-muy-basico/content/5-ssh.html), [cambiar el usuario, contraseña](https://catedu.gitbooks.io/raspberry-muy-basico/content/6-cambiar-usuario-y-contrasena.html), esto sí que es obligatorio: [tienes que aprender a apagar](https://catedu.gitbooks.io/raspberry-muy-basico/content/7-apagar.html) ;).
1. Luego tienes que comunicarte en este curso VIA GRÁFICAMENTE por VNC lo tienes explicado en [el capítulo 8](https://catedu.gitbooks.io/raspberry-muy-basico/content/8-vnc.html).

##Cómo ejecuto un programa
Vía [VNC de forma gráfica](https://catedu.gitbooks.io/raspberry-muy-basico/content/8-vnc.html), creas un fichero con extensión .py le das dos cliks y ya está !! Se abre el editor de Python para que escribas tus programas. (pues Raspbian tiene Python de forma nativa). Se ejecuta con el botón Play (redondo verde de la figura) y se para con el rojo. Esta será la forma de trabajar en este curso.

![](/assets/play)

UNA VEZ REALIZADO ESTOS PASOS YA PODEMOS PASAR A REALIZAR NUESTRO PRIMER PROGRAMA.

>Nota: También se puede hacer de forma textual con el [protocolo SSH](https://catedu.gitbooks.io/raspberry-muy-basico/content/5-ssh.html) ejecutando la orden  python. 
>Por ejemplo: Tenemos un programa llamado miprograma.py en la carpeta Aphpabot de la Raspberry luego las instrucciones serían en el terminal ssh:
>cd ~/AlphaBot/  
>sudo python miprograma.py 

##Curiosidad ¿se puede hacer desde Internet?
Totos estos pasos se entiende que lo haces desde **LA RED LOCAL** accediendo a la Raspberry por una IP fija tal y como hemos explicado pero también lo podemos hacer desde Internet [siguiendo estos pasos](https://catedu.gitbooks.io/raspberry-muy-basico/content/11-conectando-desde-internet.html).

O sea: ¿que puedo manejar mi Alphabot desde cualquier lugar del mundo? Si


