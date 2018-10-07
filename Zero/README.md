# Zero

Primer modelo de impresora, inspirado en la popular impresora del profe garcia, mejora diferentes detalles que le permiten maximisar la eficiencia de los materiales minimos para su implementación.

## Bitacora

### 20181004-0000

Creación de proyecto.
El estado del arte hasta el momento es simple. No realice ninguna clase de montaje, estan disponibles todas las piezas a excepsión de los tornillos y tuercas necesarios para sujetar las piezas.

Antes de iniciar con los cortes, debo diseñar cada elemento. Para eso voy a usar el Solidworks y subir cada etapa de diseño al repositorio. Probablemente al principio sera complicado resolver los nombres de las piezas, como así tambien la arquitectura de archivos del proyecto. Pero espero y solucionandolo con el tiempo.

Antes de empezar analize el modelo creado por el profe garcia del cual tome su lista de materiales. El diseño al parecer sencillo tiene varias desventajas.

* La base de trabajo es reducida, de unos 20cm. Sin embargo el area de trabajo eficiente es aun más reducida, siendo de aproximadamente 10cm. Esto se debe a que la plataforma no puede sobresalir por encima del marco de la base.
* El soporte que sostiene los actuadores, dremel, extrusor, laser no es facilmente desmontable. Se tiene que desatornillar los soportes de las piezas para luego insertar los nuevos soportes que mantendran firme la herramienta.
* No muestra como imprime, solo como funciona para CNC
* La electronica no esta bien resguardada
* Las mediciones y las tecnicas de producción generan demasiadaa impresición que termina afectando la performance de la impresora.

Por lo pronto me concentrare en modelar las piezas existentes, empezando por las que no se puede realizar ninguna modificación física.
Luego procedere a modelar las piezas que pueden ser alteradas hasta cierto punto.
Finalmente modelare la estructura, para determinar la cantidad y dimensiones de los cortes de madera.

### 20181004-0100

Sobre las cuplas flexibles.
Probe un montaje rapido de la tuerca THSL sobre la cupla flexible y note algunas peculiaridades.

* Los tornillos alem colisionan con una superficie irregular del tornillo producto de sus helices. Esto hace que el tornillo no quede centrado, sino que tienda a torcerce cuanto más firme se presionan los tornillos alem.
* La profundidad hasta que se introduce el tornillo en la cupla es variable. Si bien existe un limite producto del calado interno de la cupla, justo en el momento donde cambia de tamaños los ejes, la propiedad de flexión permite que el tornillo estire la cupla. Esto puede representar un problema en el ajuste de las dimensiones y los finales de carrera.
* Si se desea sujetar lo mas firme posible el tornillo THSL sobre la cupla, debe introducirce hasta el limite. Evitando que se estire la cupla. Sin embargo, esto provoca que la cupla pierda su caracteristica de flexibilidad. Por lo que lo mejor es introducirlo hasta el maximo y luego retirarlo lo suficiente hasta que la cupla vuelva a adquirir cierta flexibilidad.
* Si la cupla posee mucha flexibilidad el eje tiende a ceder ante el peso, por ejemplo de la plataforma de trabajo. Esto es un serio problema que se da independientemente de los ejes de soporte. La tracción que puede llegar a ejercer el motor sobre el tornillo debe tambien realizar un ezfuerso para corregir la torcedura de la union entre el tornillo THSL y la cupla.

La elección de la cupla flexible se presento por el comentario del profe garcia sobre las posibilidades de error y compensación de la impresora. Se supone que en caso de impresición la cupla flexible permitiria realizar un buen trabajo. Sin embargo, pienso que la utilización de la cupla flexible, aún en casos en que la estructura este bien precisa, generan siempre un error.

### 20181004-0200

Modele la cupla flexible y la tuerca THSL.
Intente de realizar los cortes por barridos adecuados. En el caso de la cupla por cuestiones de apariencia, en el caso de la tuerca para tratar de poder simular el movimiento una vez que se realiza el montaje.

Seleccione para la tuerca un cuatro elices de paso 8mm, 2 revoluciones con un calado de 1mm de altura y 0,9mm de profundidad. Es una medida empirica pero podría funcionar.

### 20181005-1500

Termine de realizar todo el modelado de las piezas principales. Las que no deberían presentarse con modificaciones y aquellas a las que no se les puede realizar modificaciones. Deje delado los ejes de acero ya que los voy a ir construyendo de las medidas necesarias.

En este punto es cuando la organización en ficheros se vuelve problematica, ya que tengo diversas piezas similares de varias dimensiones, piezas que es difil de nombrar y ensamblajes parciales.

Creo que realizare dos carpetas, una para ensamblados parciales y otra para las piezas a manufacturar

### 20181006-2000

Estuve trabajando en el primer concepto del CNC. Sigo elaborando el eje x. Realice varias modificaciones a las bases, el area de trabajo y cree las piezas principales para soportar los ejes.

Aún falta analizar muchas cosas, pero hasta el momento he logrado determinar que el area de trabajo efectivo será de 35.3 cm cuadrados. 35*35. Lo cual es una caracteristica ampliamente superadora respecto a los modelos planteados mayoriatariamente en internet.

Sin embargo, me preocupa cada vez más la precisión que se requiere para construirlo. Para evitar que los materiales cedan al peso de la estructura estoy pensando en pequeños refuerzos que lograran dotarle a los ejes de una mayor robustes. Pero en la medida en que sigo añadiendo más piezas, el porcentaje de error por impresición aumenta drasticamente.

Una posiblidad es realizar por corte laser las piezas más cruciales... O las que entren en un metro cuadrado de acrilico. Eso ademas de aumentar el precio trae consigo muchas dudas como los limites de temperatura, las tensiones en puntos criticos... etc.

Por el momento, no veo problems con el tamaño final. Será grande, pero es debido a que el area de trbajo tambien lo es.

Espero terminar pronto con el concepto del eje X y continuar con el arco de los otros dos.

### 20181007-1830

Logre terminar con el concepto del eje que desplaza el area de trabajo. La zona a cubrir por ese eje es de 353.2mm -0.1

El diseño del eje x esta pensado para que puedan montarse dos motores con sus respectivos tornillos THSL. De esta forma se podría duplicar la fuerza en caso de que el peso del area de trabajo sea demasiado para realizar el empuje.

Esta estrategia tambien significa hacer modificaciones en la electronica y fuente de alimentación.

Por otro lado extendi las piezas que soportan los ejes a una sola pieza que atraviezan todo el ancho del cnc, esto les dara una mayor robustes y ademas será más facil de calibrar y ajustar las piezas durante el montaje minimizando los errores por impresición.

Por ahora estoy intentando diseñar el concepto del arco que transmite el movimiento por el eje y. Resulta un desafio en teniendo encuenta la gran variedad de piezas y posiciones que no pueden determinarse. Si bien muchas piezas cuentan con dimensiones estaticas, su posición puede variar, y esto provoca que las dimensiones de las piezas manufacturadas se vean modificadas ante cada propuesta.

Ademas se presento un problema al que aún no le encuentro una solución optima con los materiales disponibles. Se trata de la resistencia de las varillas acero de 8mm al aplicarle una fuerza perpecdicular al eje. Una sola varilla se tuerce muy facilmente cuando se aplica una fuerza de unas pocas centimas de gramos. Esto se debe a que la distancia que manejara el eje es de practicamente unos 45cm, y el material cede. 

Este problema lo intui en el diseño del eje x que desplaza el area de trabajo, y lo resolvi añadiendo un soporte central que sostiene las varillas en caso de que se les aplique una fuerza normal al suelo. Pero en el caso del eje "y", no es posible adjuntar ninguna clase de soporte sin entorpercer el movimiento de la herramienta.

Una solución es reducir el largo, pero esto sería catastrofico, ya que habria que eliminar unos 20cm para que la resistencia de la torción soporte al menos 1kg. 20cm menos implica un área de trabajo maxima de 10x35cm. Aún así el eje Y esta atravesado por tres varillas. Dos de acero, lo que deberia duplicar la resistencia, y el tornillo THSL, que al contener las formas espiraladas multiplica enormemente la resistencia en comparación a la varilla de acero. Las tres piezas a un largo de 40cm, logran soportar cerca de unos 5kg antes de comenzar a ceder.

Otra estrategia podría ser la de realizar una suerte de riel por el que la base de la herramienta "cuelga" con un sistema de rulemanes. Esto tiene varios inconvenientes:

* Es una solución a medio camino entre el uso de varillas, y el uso de hierro estructural y rulemanes.
* Genera una superficie de contacto mayor, causando mayor resistencia.
* La calibración puede resultar costosa.
* Se requieren más materiales.
* Aún no hay evidencia de que se necesite o de que realmente solucione el problema
* La fuerza aplicada hacia abajo tendera a causar un dezplazamiento perpendicular hacia el eje del plano x. Lo que causara que la torción de la varilla inferior termine por ser causada hacia otra dirección

Otra estrategia es la de aumentar el largo de las varillas hassta cerca de unos 80cm. Utilizando el mismo sistema que en el caso de la base permitiria montar un soporte central que mantenga la recta de la varilla. Esto significa que el cnc final tendra unos 80x80cm. Las dimensiones son realmente enormes. Pero es una solución más viable que la anterior. Tambien requeriria la compra de mas varillas para montar el eje z.

Otra opción que podría ser viable es cambiar las varillas de 8mm por varillas de acero de 10mm. Tambien deberia cambiar los SC8U.

Por el momento estoy planeando dejarlo de la forma en la que esta. En teoria el eje constituido por las tres varillas deberia ser suficientemente fuerte para soportar el peso del minitorno, que es la herramienta mas pesada hasta el momento.

En caso de que falle, una forma de solución podria ser aplicar un sistema de cancelación de fuerzas con un sitema de resortes calibrados para contrarrestar el peso de la herramienta en los puntos más criticos.

Realizar un calculo infinito seria de gran utilidad para diseñar el sistema de resortes.

Como medida parcial estoy contemplando la idea de apoyar la cupla del eje Y sobre una superficie rigida. Pero debido al trabajo de giro que debe realizar, pienso que lo correcto seria montarlo sobre un ruleman.

Tengo pensado realizar una estructura encastrable para insertar o remover la herramienta. De esta forma cada herramienta ya esta fielmente montada a una estructura parcial, que luego simplemente se encastra y se asegura al CNC. De esta menra puedo lograr mantener una mejor estabilidad sobre la precición entre cambios de herramientas.

El centro de la herramienta cambiara, dependera de las dimensiones de la herramienta. Al modificarse el centro de la herramienta, tambien se modifica el area de trabajo. Aún no seleccione que herramienta tendra el area de trabajo maxima. Pero cualquier otra herramienta cuya distancia desde la base que lo soporta al punto central sea diferente, tendra un area de trabajo menor.



