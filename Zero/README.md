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

### 20181007-2130

Logre terminar el concepto del Eje Y con un rango de trabajo de 355mm. Por lo cual el area de trabajo efectvo maxima sera de 353x355mm.

Si las varillas son lo suficientemente fuertes para soportar el peso de la herramientas más el eje z entonces se conseguiran grandes resultados.

Existe un punto flojo en la union de la cupla. Debido a que la cupla es flexible, no lograra generar suficiente resistencia al peso. Una opción fue reforzar la cupla introduciendola dentro de dos estructuras laterales, pero esto puede llegar a afectar el giro a menos que se consigan dos rulemanes. Si se consiguen dos rulemanes con un radio de 18mm en el interior, el problema se trasladara a la inserción y sujeción del ruleman. Debido a que el lateral principal tiene calados para que los SCU8 ingresen, esto puede llegar a entorpecer el sector de un ruleman tan grande. Una opción poco rudimentaria consiste en engrasar todo. Cosa que en realidad tengo pensado realizar en todos los ejes con movimiento.

Más adelante hara falta crear soportes diagonales, tanto el los laterales exteriores que conforman el eje y como en las esquinas de la caja grande que determina la forma principal del CNC.

Otro ajuste al diseño del eje Y se debera realizar cuando termine con el eje z y decida que herramienta poseera el mayor area de trabajo. Este ajuste consiste en retirar los laterales una distancia x, recorriendo el eje x con la intención de que el centro de la herramienta coincida con el centro del area de trabajo.

Ahora el siguiente desafio sera diseñar el eje z, y planear la forma en que se pueden insertar las herramientas de manera efectiva. Esto me recuerda que sera necesario ir pensando cuales son los accesorios y cables que debera integrar cada herramienta... filamentos para el extrusor, resorte para el torno...

### 20181009-1630
Estuve investigando sobre distintas alternativas para implementar el carro y el ejez. La forma que se presenta en la mayoria de los casos es un ejez con un solo estatico en la zona superior. El resulta en una caja alta que es sostenida por dos varillas de acero por las que el carro puede descender. Sin bien este metodo funciona bien para el ruteado o corte laser, no es ideal para la impresion 3d.

La altura obtenida por este sistema es alrededor de 1/3 del largo tornillo thsl. Osea dque de 40cm se obtiene una altura practica de un poco mas de 10cm. Esto se debe a que el carro tiene un final de carrera con una pieza grande, fija y estatica. Esta pieza es la que marca la altura de la pieza a trabajar.

Si bien es una forma robusta para evitar el minimo de brivación del cabelaz de la herramienta, es ineficiente para la impresión 3d. Por esa razon se me ocurrio invertir la posición del motor del ejez. En lugar de ubicarlo en la parte superior de forma estatica, pense en ubicarlo en la zona inferior, de manera movil, coincidiendo con la herramienta.

De esta forma, al desplazar el cabezal tambien lo hace el motor. El soporte del tornillo THSL se encuentra fijo en el carro del ejey por lo que el desplazamiento logra obtener el maximo potencial del largo del tornillo thsl. Da como resultado aproximadamente los 40cm de movimiento. Esto resulta impresionante para una impresora 3d.

De poderse construir el ejez la impresora adquiriria un area de trabajo efectivo de 350x355x400. Sin embargo, este concepto no resulta del todo eficiente. El concepto se puede ver con más detalle en la carpeta de ConceptTest/EjeZ Invertido

Un problema es el peso. Al trasladar el motor paso a paso a la zona inferior junto a la herramienta, se le suma al carro el peso del motor. Esto significa un mayor ezfuerso, algo que estaría al limite de las capacidades de un NEMA17. El cambio del motor conlleva tambien a un incremento de su peso. El problema aun persistiría. Una solución potencial es la de unir al carro del ejez un contrapeso.

Investigando un poco encontre que se trata de una solución común para disminuir el efecto del peso del carro sobre el motor del ejez. Sin embargo, los diseños montados trasladan por alguna razon ese peso a los otros dos ejes. Esto se podría anular montando las poleas necesarias sobre la estructura base, por lo que el ezfuerso aplicado no se repercute en los otros ejes.

Sin embargo existe un problema mayor si pensamos en el uso del cnc como ruteador. La traslasión de las brocas ejerce una fuerza de resistencia que depende del material a fresar. Esta fuerza es variable, por lo que se producen vibraciones que oscilan entre la fuerza aplicada a las resistencias estaticas y resistencias dinamicas. Esta vibración es incrementada por el largo de los 40cm que tendria el ejez. Esa distancia entre el punto que soporte el carro y la herramienta se traduce en oscilaciones lo suficientemente altas como para estropear el trabajo.

Por esta razon, si bien es una buena forma de aprovechar los materiales para el montaje de una impresora 3d, estoy descartandolo para el uso de las otras piezas.

Como alternativas me queda o montar un carro convencional sacrificando altura para las piezas de la impresora o comprar más materiales y montar un cnc con dos motores para el ejez. De esta forma la estructura cambiaria drasticamente. Pero estaría preparada para soportar herramientas de gran peso, y no jugaría tanto con los limites de potencia.

Estoy evaluando realizar la compra de un eje más con los respectivos soportes, tornillos y un motor nema17 más. De ser posible, tambien compraría otro paquete igual para montar el segundo ejeX.

Tengo que avanzar en el concepto de esta nueva estructura cnc que se aleja del plan original de realizar la cnc del profe garcia de manera más eficiente. Esto creo que ya fue logrado al superar los obstaculo que se presentaban con una base de trabajo reducida, ampliando el area de trabajo de 10x10 a 35x35. La limitación de altura efectiva que tiene el cnc del profe garcia, es una desventaja demasiado grande como para trasladarla a una inversión que debe resultar practica y de servicio profesional.

Teniendo en cuenta esto, descarto el modelo aplicado por el profe garcia y comienzo a trabajar en un modelo de cnc mucho mas robusto, eficiente y con miras a trabajar los equipos de manera profesional. Para esto voy a considerar algunos puntos.

* Voy a reemplazar las varillas del eje y de 8mm por varillas de 10mm.
* Voy a reemplazar el tornillo thsl de 8mm del eje y por uno de 10mm (si consigo el resto de las piezas.
* Junto a esto tambien voy a reemplazar los soportes de carril.
* Voy a tratar de equipar un segundo eje x clonado.
* La cnc tendra dos ejesy clonados.
* Voy a preparar las dimensiones de los espacios para poder montar motores tipo NEMA23, con lo cual deberia ser capaz de mecanisar aluminio.
* Voy a preparar el cnc para que puedan colocarse dos contrapesos sobre los ejesy, de esta forma podría ayudar en futuras ocasiones a compensar problemas con el trabajo del motor.

Luego de esta actualización voy a proceder a realizar algunos cambios en los ficheros, para preparar el trabajo del segundo concepto.

### 20181012-1630

Para comenzar el nuevo concepto elabore una copia completa del proyecto del modelo 0. Esto me permite modificar las  piezas mas basicas de ser necesario sin alterar el modelo anterior para ubicar futuras referencias. El nuevo concepto se encuentra en la carpeta modelo 1.

Estuve trabajando sobre el eje Z con dos motores. Analice varias alternativas para ubicar el motor Y. Ninguna de las opciones parece completamente eficiente, todas las opciones presentan grandes desventajas que generar distintas fuerzas de torsion sobre las varillas de acero. De todas las opciones decidi emplear una solución que mantiene el centro de gravedad lo más cerca posible del motor ZLeft. De esta forma toda la fuerza del motor se transfiere al motorY, acompañado del motorZRight para compensar la fricción por desbalance y el peso de la herramienta.

Las distancias necesarias para aprovechar al maximo el tornillo de 40cm implicaba realizar figuras y calados que podrían debilitar la estructura del arco. Por lo que decidi sacrificar recorrido en el eje Y para ganar robustes. Sin embargo, como mucho se redujo a area efectiva de 332, lo cual sige siendo significativamente superior al de la mayoria de los modelos.

Durante el proceso de diseño me di cuenta que muchas de las medidas que estaba realizando se encuenran en la decima de milimetro, dimensiones que resultan impracticables. Así que antes de continuar con el modelado del arco que sostiene el carro principal realize una revisión de todas las piezas manufacturadas. Busque reducir los cortes a unidades enteras de milimetro, algo mucho más accecible. Sin embargo, tuve problemas con los agujeros y sus centrados, ya que dependen directamente de piezas fabricadas cuyas medidas si se extienden a la decima de milimetro. 

Por suerte solo se indican medidas de medio milimetro, por lo que es posible compensar esta dimensión con margenes de error. Aún así el ajuste fue complicado.

Revisar las dimensiones tambien causo que modificara las relaciones entre piezas. Por lo que mecanicamente, en teoria, deberia estar mucho mejor planteado.

Otras mejoras son la preparación para montar hasta tres tornillos sobre el ejeX, claro que la modalidad sería un motorX o dos clonados. Esto previene algunas mejoras potenciales a futuro.

Una ves terminada la revisión recaulcule el recorrido efectivo del ejeX en 354mm. Debido a que debo enzanblar el arco superior las piezas del ejeY aún no estan suficientemente fijas como para determinar el area efectiva, pero es posible que alcance un numero similar. Respecto a la altura, no busco ningun valor específico, el diseño de la estructura tomara el recorrido máximo de una u otra forma. Ademas por como se observa la altura alcanzada sera más que superadora.

Realice algunos cambios de nombres en los archivos para que se puedan encontrar mas facil. Pero tambien quedaron algunos archivos huerfanos que espero detectar y eliminar una vez que termine el concepto.

### 20181012-1840

Termine de realizar los calculos para ubicar el arco. Surgieron varios inconvenientes.

Por un lado las varillas de acero del ejez alcanzan los 500mm es decir exactamente la mitad de 1metro, pero como dispongo de varillas de 1mt el corte no producira los 500mm sino menos. Esto impide alcanzar el maximo potencial del tornillo Z. Debido a que debo administrar cuidadosamente el dinero para comprar solo lo que es necesario para construir el segundo ejeZ, debo limitar la altura maxima a un poco mas de 290mm. La diferencia de altura dependera de la herramienta. Esta altura se correspondería con la altura de la impresión, dando un espacio efectivo de impresión de 354x334x290. En cualquier caso, es un area de trabajo de impresion mayor del estandar que es 220x220x200 y mucho mayor que las medidas 120x120x120 alcanzadas con el modelo del profe garcía y similares que utilizan los mismos materiales.

Otro problema es que no logro desaserme por completo de dimensiones que rondan la decima de milimetro. Esto puede verse al completar el relleno del lateral para dar soporte al arco principal. Esto significa que para lograr solventar estos problemas, es obligatorio que exista una secuencia de ensanblado que priorize las piezas cruciales con la maxima precisión dejando como dependientes las piezas con mayor tolerancia.

Otro problema surgio al momento de montar el extrusor en el concepto. La impresión sera la modalidad que posea la mayor area por lo que monte el extrusor para realizar calibraciones sobre al arco principal. Esta medida dio un numero redondo, pero al desplazar el extrusor, noto que colisiona con parte de la estructura de la columna Z derecha. Si omito esto, el area efectiva se ve reducida en aproximadamente 25 a 30mm. Por otro lado, el centro quedara desubicado.

Una solución inmediata implica cortar la pieza para permitir que el extrusor circule sin problemas. Esta maniobra puede debilitar la estructura haciendola suceptible a vibraciones cuando se encuentra en la modalidad router. Otra opción es alejar el extrusor de la base de herramientas, pero esto genera una torsión sobre el eje que se trasnmite a todo el arco.

Por ahora continuare con el resto de la estructura y luego modelare el resto de las herramientas potenciales y procedere a tomar alguna decisión.