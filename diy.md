#DIY Do It Yourself

Este robot es delicado y difícil de montar, intentamos  con este manual ayudarte a montarlo si te convence comprarlo pero nosotros no somos comerciales de este robot. O sea, ésto mejor que no:

![](/assets/2018-06-30 07_45_40-Documento1 - Microsoft Word.png)

_Nomenclatura:_
* Parte delantera: La que tiene la cámara. 
* Parte trasera la que tiene el siguelíneas.

##El Paquete de piezas
Encontramos todas estas piezas, destacamos:
* Placa de raspberry con microSD, pincho adaptador y fuente de alimentación (no fotografiado)
* Tornillería abundante algunos tornillos son minúsculos.

![](/assets/PICT0025.JPG)

Vamos a por ello (Advertencia: empieza si tienes tiempo por delante):

![](/assets/ikea-noche.png)

###Los motores

Ponemos primero los dos soportes:

![](/assets/PICT0028.JPG)

Atornillamos el motor con los tornillos largos

![](/assets/PICT0029.JPG)

conectamos el motor

![](/assets/PICT0033.JPG)

repetimos los mismos pasos con el otro motor.

###Medidor de velocidad
Ponemos la rueda de agujeros para el medidor de velocidad:

![](/assets/PICT0030.JPG)

Tiene que ir en este agujero **van muy ajustados** luego no es necesario atornillarlos. ACONSEJAMOS NO METERLOS AÚN sino después de colocar el brazo robótico

![](/assets/PICT0031.JPG)

conectamos el sensor:

![](/assets/PICT0034.JPG)

con la placa

![](/assets/PICT0035.JPG)

###Sensor de siguelíneas

Hay tres tipos de barras, elegimos 2 de las **medianas** _(no sé para que sirven las pequeñas)_

![](/assets/PICT0036.JPG)

atornillamos en la parte trasera del robot

![](/assets/PICT0037.JPG)

Conectamos

![](/assets/PICT0038.JPG)

y atornillamos

![](/assets/PICT0039.JPG)

###Sensor distancia IR

Colocamos un tornillo de plástico que servirá de arandela aislante pues si no se hace, al atornillar hace un cortocircuito y el sensor no funciona bien:

![](/assets/PICT0040.JPG)

utilizando los tornillos un poco más largos:

![](/assets/PICT0045.JPG)

Atornillamos en la parte delantera en los agujeros extremos :

![](/assets/PICT0041.JPG)

![](/assets/PICT0042.JPG)

Conectamos

![](/assets/PICT0043.JPG)

Y por abajo también:

![](/assets/PICT0044.JPG)

###Arduino
Si decidimos conectar un Arduino ahora es el momento:

![](/assets/PICT0046.JPG)

##Raspberry

Antes de colocarlo, tenemos que poner el cable de la cámara, levantamos el plástico negro sin arrancarlo:

![](/assets/PICT0047.JPG)

Y colocamos el cable, con el lado azul tal como está en la foto y volvemos a apretar el plástico negro para que fije el cable a la Raspberry:

![](/assets/PICT0049.JPG)

Pasamos el cable por la ranura de la placa del robot para que salga al exterior:

![](/assets/PICT0050.JPG)

Ahora ya podemos colocar la Raspberry en el zócalo de los GPIO:

![](/assets/PICT0051.JPG)

Aprovechamos y ponemos las barras largas para proteger los distintos elementos _(Fe de erratas: Las 2 barras de la parte delantera tienen que ir más separados, a los agujeros cerca de las tuercas)._

![](/assets/PICT0053.JPG)

##Brazo robótico
Esta parte es la más difícil !!!

<iframe src="https://giphy.com/embed/3o7abrH8o4HMgEAV9e" width="480" height="241" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/starwars-3o7abrH8o4HMgEAV9e">via GIPHY</a></p>

De momento algo sencillote: Conectar los servos

![](/assets/PICT0052.JPG)

El servo de abajo tiene que colocarse en esta pieza

![](/assets/PICT0054.JPG)

entra ajustado pero entra:

![](/assets/PICT0055.JPG)

colocamos la otra pieza:

![](/assets/PICT0056.JPG)

Utilizamos los tornillos largos pero no los más largos y estrechos sino este:

![](/assets/PICT0057.JPG)

Atornillamos:

![](/assets/PICT0058.JPG)

Para el servo de arriba utilizamos un tornillo de punta

![](/assets/PICT0060.JPG)

Lo atornillamos

![](/assets/PICT0061.JPG)

Y lo colocamos con la otra pieza:

![](/assets/PICT0062.JPG)

**CHAPUZA** ahora vemos que la pieza de brazo del servo no se ajusta al hueco

![](/assets/PICT0065.JPG)

La palabra "chapuza" no está en el diccionario de los chinos ni tampoco tienen estos cuchillos albaceteños:

![](/assets/PICT0067.JPG)

Pero los españoles estamos entrenados a resolver estas situaciones:

![](/assets/PICT0068.JPG)

El tornillo es uno en punta con arandela soldada:

![](/assets/PICT0064.JPG)

**CHAPUZA2** la parte que tiene que unir el servo de abajo con la plataforma de la placa tiene que ser con un brazo de servo QUE NO ENTRA:

![](/assets/PICT0066.JPG)

Pero los maños no nos rendimos:

![](/assets/PICT0069.JPG)

Esto no sé si está en los libros de ingeniería !!

![](/assets/PICT0070.JPG)

Aún así hay que rebajar un poco más en los lados para que entre bien el brazo del servo blanco, puedes ver en la foto como con el cuchillo se ha rebajado un poco más a los lados para que la pieza blanca esté lo más prieta a la negra:.

![](/assets/PICT0072.JPG)

Bien atornillado por la parte reversa:

![](/assets/PICT0071.JPG)

Utilizando los tornillos finos y cortos:

![](/assets/PICT0059.JPG)

Es un buen momento para colocar la cámara. Levantamos la pieza negra sin arrancarla:

![](/assets/PICT0073.JPG)

Ponemos el cable con el lado azul como en la foto y volvemos a colocar la pieza negra:

![](/assets/PICT0074.JPG)

**CHAPUZA3** No, no entra, se queda torcido, no queda estético pero está bien sujeto:

![](/assets/PICT0075.JPG)

Ahora viene el **PUNTO DÉBIL DE ESTE ROBOT** la unión del brazo robótico con la placa. Ponemos el servo de abajo con la plataforma:

![](/assets/PICT0076.JPG)

Utilizaremos un tornillo con arandela soldada:

![](/assets/PICT0077.JPG)

Y bien apretado pero sin reventar el servo, ojo:

![](/assets/PICT0079.JPG)

Ahora utilizaremos los tornillos más largos con tuerca que lo utilizaremos de arandela de plástico y tuerca

![](/assets/PICT0080.JPG)

**CHAPUZA4**: ¿Por qué utilizar la arandela de plástico? porque si no se utiliza, las tuercas hacen cortocircuitos con las soldaduras de la placa, luego necesitamos levantar un poco la plataforma del brazo robótico de la placa:

![](/assets/PICT0081.JPG)

Atornillamos los 4 (por eso decíamos que no había que poner los sensores de velocidad aún):

![](/assets/PICT0082.JPG)

Y ponemos las 4 tuercas por la parte de atras bien prietas:

![](/assets/PICT0083.JPG)

Ahora ya podemos colocar los sensores de velocidad, que no hace falta atornillarlos pues entran muy ajustados y prietos:

![](/assets/PICT0084.JPG)

![](/assets/PICT0031.JPG)

Tiene que quedar que vean bien los agujeros de las ruedas:

![](/assets/PICT0032.JPG)

###Ruedas

Ponemos la rueda loca en la parte trasera:

![](/assets/PICT0086.JPG)

Atornillamos

![](/assets/PICT0087.JPG)

Ponemos las ruedas traseras, las pilas:

![](/assets/PICT0088.JPG)

Y fin !!

![](http://www.reparacionxpress.com/images/mireforma6.jpg)
