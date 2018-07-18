##Desventajas
Encontramos algunas, por ejemplo:

* **Fallos en el diseño:**
    * Del brazo de robot, el pie no se ajusta bien a la placa y tampoco a la cámara web (en las fotos las flechas amarillas) Ver Chapuzas nº 1, 2 y 3 de [DIY](/diy.md).
    * El brazo robot está situado demasiado hacia delante, lo que dificulta la posibilidad de colocar un sensor de Ultrasonidos en la parte delantera, esto lo hablaremos en [este punto](/45-posibilidad-ultrasonidos.md).
    * El acceso a la tarjeta microSD es difícil, una manera es utilizando unas pinzas de depilar (ver foto) o desmontando la tapa inferior.
    * No se puede acceder a la alimentación por USB con la tapa inferior luego tenemos dos opciones:
        * Alimentar Alphabot con las pilas. (única opción cuando está en movimiento).
        * Desmontar la tapa inferior y alimentarlo por USB. Si elegimos esta opción hay que dejar las ruedas en alto para que los motores trabajen en vacío.

![](/assets/IMG_20180628_090440692.jpg)
![](/assets/IMG_20180628_090521449.jpg)
![](/assets/IMG_20180628_093005864.jpg)

* **La información que hay en Internet** no es muy buena, pero al menos hay una wiki más o menos útil: https://www.waveshare.com/wiki/AlphaBot

![](/assets/wikialphabot.png)

* **Las pilas son especiales** tipo 18650 no son las "_normales AA o AAA_" pero proporcionan 3.7V y más de 1.000mAh cada una lo que asegura la alimentación del robot+raspberry de forma autónoma. Se pueden encontrar en tiendas online por 10€ con cargador incluido. (ojo,hay dos versiones, elegir la de 65mm).

![](/assets/pila.png)

Para hacer pruebas y depuraciones **sin utilizar las pilas** (son un engorro) se puede utilizar la fuente de alimentación de la Raspberry (output 3.000 mA) pero para conectarlo hay que quitar la placa de abajo 

![](/assets/PICT0026.JPG)

Y por supuesto levantar el robot para que no salga disparado conectado con el cable, que los motores trabajen en vacío y entonces sí que la fuente de alimentación lo puede soportar:

![](/assets/2018-07-01 17_37_11-PhotoFiltre.jpg)

* Otro defecto es **la colocación del siguelíneas atrás del sentido de la marcha**, esto lo veremos en [el capítulo correspondiente](/6-modulo-siguelineas/65-m2-siguelineas.md) y lo solucionaremos haciendo que vaya hacia atrás, pero claro, la cámara enfoca a la parte trasera y pierde su gracia.



