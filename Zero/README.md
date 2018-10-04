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