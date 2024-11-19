Siguiendo [[14 de noviembre 2024]]...
Subtema AdC.
Mes: [[Noviembre]]

Siguiendo de [[14 de noviembre 2024#Redes de medio compartido]]

### Cable Coaxial
Tipo bastante cable que se utiliza para transmitir señales de electricidad de alta frecuencia.

Se compone de un núcleo desarrollado con hilo de cobre que está envuelto por un elemento aislador , unas piezas de metal trenzado y una cubierta de plástico.

### Fibra Óptica
Se forma al juntar cientos o miles de cables tan delgados como un cabello humano de fibra de vidrio transparente.

Los datos se transforman en pulsos de luz emitida por un láser del tamaño de la cabeza de un alfiler y se transmiten a una alta velocidad.

## Redes Conmutadas
Acción de establecer una vía, un camino de extremo a extremo entre dos puntos, un emisor y un receptor a través de nodos o equipos de transmisión. La conmutación permite la entrega de la señal desde el origen al destino.

### ¿Cómo funcionan?
Las comunicación entre un host origen y un host destino se realiza mediante la transmisión de datos a través de una red de nodos de comunicación intermedios.

Cada nodo intermedio almacena los datos temporalmente antes de enviarlos.

Los dispositivos finales son computadoras, terminales, teléfonos, etc.

Son las rede de área extensa.

![[Pasted image 20241115112048.png]]

### Una transmisión de este tipo tiene 3 fases
1. Establecimiento de la conexión.
2. Transferencia de la información.
3. Liberación de la conexión.

### Las redes conmutadas se dividen en dos
1. Conmutación de paquetes.
2. Conmutación de circuitos.

#### Conmutación de paquetes
Los datos o la información que se transmite es ensamblada previamente en paquetes.

Cada uno de los paquetes se transmite de manera individual y va a poder seguir rutas distintas para llegar al destino. Al llegar, los paquetes son re-ensamblados de nuevo.

##### ¿Qué son los paquetes de datos?
Son divisiones de la información que queremos enviar en pequeñas "partes" (paquetes).

Cada paquete contiene una porción de la información real que se quieren transmitir otros datos necesarios para el control de la transmisión y las direcciones IP de los ordenadores de destino y partida.

Son transportados en Mb/s.

Nos permite transportar cualquier tipo de información
#### Conmutación de circuitos
Es un tipo de comunicación que se establece o se crea a través de un canal dedicado que se conoce como circuito, el tiempo que dura la sesión.

En cuanto la sesión se finaliza (una llamada telefónica) el canal se libera y puede ser usado por otros usuarios.

Los nodos intermediarios no tratan los datos de ninguna forma, sólo se encargan de encaminarlos a su destino.

#### Ventajas de la conmutación de paquetes
- Los paquetes forman una fila y se transmiten lo más rápido posible.
- Permite la conversión en la velocidad de datos.
- La red puede seguir aceptando datos, aunque la transmisión sea lenta.
- Existe la posibilidad de manejar prioridades (si un grupo de información es más importante que los otros será transmitido antes).

#### Ventajas de la conmutación de circuitos
- El ancho de banda es definido y se mantiene constante durante la comunicación.
- El circuito es fijo, no se pierde tiempo en el encantamiento de la información.
- La transformación se realiza en tiempo real, siendo útil para la comunicación de voz y video.
