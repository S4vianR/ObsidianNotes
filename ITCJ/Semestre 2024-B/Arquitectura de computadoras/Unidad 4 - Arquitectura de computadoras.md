Materia: Arquitectura de computadoras [[Arquitectura de computadoras]]
Subtema AdC.
Unidad 4.
# Unidad 4
## Computación Paralela
Cuando se habla de procesamiento paralelo, la idea central es multiplicar la cantidad de "unidades de ejecución" que funcionen concurrentemente ya sea ejecutando instrucciones en paralelo o ejecutando....

Estad **unidades** pueden ser procesadores (multiprocesadores).
O **unidades** dentro de un procesador (dos unidades de coma flotante para realizar operaciones simultáneas).

### Definición
Es una forma de cómputo en la que muchas instrucciones se ejecutan simultáneamente, operando sobre el principio de problemas grandes se pueden dividir en unos más pequeños, que luego son resueltos en paralelo.

Las computadoras paralelas pueden clasificarse según el nivel de paralelismo que admite el hardware:
- **Equipos con procesadores multi-núcleo y multi-procesador**: Tienen múltiples elementos de procesamiento dentro de una sola máquina.
- **Clusters**: MPPS, y Grids que utilizan varios equipos para trabajar en la misma tarea.

## Paralelismo a nivel software
Los programas paralelos son más difíciles de escribir que los secuenciales porque la concurrencia introduce nuevos tipos de errores de software, siendo las condiciones de carrera más comunes.

### Condiciones de carrera
El término se origina por la similitud de dos procesos compitiendo en carrera por llegar antes que el otro, de manera que el estado y la salida del sistema dependerán a cuál llegó antes, pudiendo provocar inconsistencias y comportamientos impredecibles y no compatibles con un **sistema determinista**.

### Ley de Amdahl
La máxima aceleración posible de un programa como resultado de la paralelización se conoce como la Ley de Amdahl.

## Tipos de computacion paralela
### Paralelismo a nivel de bit.
Anteriormente la aceleración de la arquitectura se lograba duplicando el tamaño de palabra en la computadora. Haciendo esto, se reducía el número de instrucciones que el procesador debía ejecutar para realizar una operación.

Actualmente los procesadores de 64 bits son un estándar en la computación de propósito general.

### Paralelismo de datos (instrucción)
En pipeline, cada etapa es llevada a cabo por una unidad específica del procesador. Si por cada etapa se duplica la cantidad...

### Pipeline superescalar de 5 etapas
Un procesador superescalar con pipeline de cinco etapas, es capaz de ejecutar dos instrucciones por ciclo.

Puede tener dos instrucciones en cada etapa para un total de hasta 10 instrucciones ejecutadas simultáneamente.

### ¿Cómo funciona esto... (superescalar)?
Durante la ejecución, las múltiples instrucciones se leen y pasan a un planificador que determina cuáles se pueden ejecutar en paralelo.

El planificador requiere un flujo constante de instrucciones para analizar, y deben estar disponibles en la memoria caché.

El procesamiento paralelo a nivel instrucción se conoce como **granulado fino**, en éste el paralelismo se aplica a cada etapa de ejecución de la instrucción, y por lo general es el hardware el que detecta instrucciones y datos no dependientes...

### Dependencia de datos
Durante el pipeline puede ocurrir que el resultado de una instrucción "dependa" del resultado de la anterior razón, por la que sería necesario concluir la instrucción *n* para ejecutar la instrucción *n+1*.

Se puede anticipar la presencia de este conflicto que interfiere en la evolución del pipeline, porque está previsto y se puede resolver, ya sea retrasado la ejecución o por medio de la compilación, aplicando una técnica que produce un reordenamiento de las instrucciones sin afectar la lógica del programa. A esta técnica se le llama ***ejecución fuera de orden***.

El cambio en el orden de ejecución no afecta la lógica del programa y otorga el tiempo necesario para que si se ejecutan las tres primeras instrucciones reordenadas, al ejecutar la cuarta *M=C2* no haya espera, pues ya se calculó el valor de C sin producir retardos.

### Paralelismo a nivel proceso
Los sistemas multi-procesadores explotan el paralelismo de proceso o paralelismo de **granulado grueso**. Este paralelismo lo resuelve el compilador y las funciones del SO.

### Thread Level Paralelism (TLP)
El paralelismo a nivel de hilo de ejecución tiene como objetivo incrementar el número de programas individuales que un CPU puede ejecutar de forma simultánea.

Los hilos son rutinas concurrentes que comparten variables globales y el mismo espacio de direccionamiento.

En el diseño de chips, las dos metodologías principales usadas para logra el TLO son el multiprocesamiento a nivel chip (multi-core) y el multihilos simultáneos (CPU superescalar).

### Paralelismo a nivel arquitectura
La clasificación de Flynn ha demostrado funcionar para tipificar los sistemas y se ha venido usando desde hace mucho tiempo. Los nuevos avances en tecnología y otras tipologías han llevado a sistemas que no son tan fáciles de clasificar a entrar dentro de los 4 tipos de Flynn.

Para solucionar esto se han propuesto otras clasificaciones.

Una taxonomía ampliada que incluye alguno de los avances en arquitectura de computadoras en los últimos años (es lo mas cercano a una clasificación completa).

## Arquitectura de las computadores secuenciales
La mayoría de los sistemas secuenciales están gobernados por señales de reloj. A éstos se les llama síncronos o sincrónicos, a diferencia de los sincrónicos o asincrónicos que son aquellos, a diferencia de los asincrónicos....

Los principales sistemas secuenciales que pueden encontrarse en forma de circuito integrado o como estructuras en sistemas programados:
- **Contadores**: Generalmente se fabrican conectando varios flip-flops entre sí, Se pueden obtener como circuitos integrados completos.
- **Registros**: Los biestables de un bit pueden agruparse en bloques de 8 para construir....

### Taxonomía de Flynn
La clasificación más popular de computadoras.

Está basada en la clasificación atendiendo el flujo de datos e instrucciones en un sistema.

Un **flujo de instrucciones** es el conjunto de instrucciones secuenciales que son ejecutadas por un único procesador y un **flujo de datos** es el flujo secuencial de datos requeridos para el flujo de instrucciones.

![[Pasted image 20241113113037.png]]

#### Organización del espacio de direcciones de memoria
La memoria de acceso secuencial es memoria en la cual para acceder a un registro en particular se tienen que leer registro por registro desde el inicio hasta alcanzar el registro particular que contiene el dato que se requiere

Se clasifican en:
1. Registros de desplazamiento.
2. Dispositivos por acoplamiento de carga.
3. Memoria de burbuja.

#### Sistemas de memora-compartida multiprocesadores
**Multiprocesador**: Computadoras con varios procesadores inter-conectados que comparten un mismo sistema de memoria.

Son arquitecturas *MIMD* con memoria compartida.

Dependiendo de la forma en que se comparte la memoria se clasifican en: UMA, NUMA, COMA.

#### Redes de interconexión dinámicas o indirectas
Uno de los criterios más importantes para la clasificación de las redes es el que tiene en cuenta la situación de la red en la máquina paralela.

Esto da lugar a dos familias:
- Estáticas
- Dinámicas

##### Estáticas
Su topología queda definida de manera definitiva y estable durante la construcción de la máquina paralela. Una IP es asignada a un dispositivo y nunca se modifica.

La red simplemente une los elementos de acuerdo con una configuración.

Por la red sólo circulan los menajes entre procesadores...

##### Red estática
Una dirección IP estática es una dirección que está asignada permanentemente a una computadora localizable a través de Internet.

Una IP estática proporciona un único carril de tráfico que conduce directamente a un destino web.

Son esenciales para VPN's, configuraciones de acceso remoto y juegos online.

##### Red Dinámica
Es una red cuya topología puede variar durante el curso de la ejecución de un programa paralelo entre dos ejecuciones de progrmaas

La red está constituida por conmutadores o switches:
- Estos generan topologías fácilmente escalables.
- Permiten comunicaciones "all to all".
- Igualdad de latencia para comunicaciones
- .....

Una dirección IP dinámica es la que cambia cada cierto tiempo.

Estas IP's dinámicas se pueden encontrar en grandes empresas o servidores que reciben gran cantidad de tráfico.

La IP cambia en función de las necesidades del servidor.

### Principales topologías de red dinámicas
Buses.
Redes de líneas cruzadas o matriz de conmutación (crossbar).
Redes Multi-etapa o MIN (Multi-stage Interconnection Network):
- Omega.
- Línea Base.
- Mariposa.
- Delta.
- Clos.
- Benés.

![[Pasted image 20241114113332.png]]

![[Pasted image 20241114113423.png]]

![[Pasted image 20241114113557.png]]

## Redes de medio compartido

### Entorno de medios compartidos
El medio de comunicación es compartido por todos los elementos del proceso.

Sólo un dispositivo puede usar la red en un momento dado.

La comunicación es tipo broadcast por lo que debe haber sistemas de arbitraje para solucionar colisiones.

*Colisión significa que dos o más dispositivos están usando el bus al mismo tiempo.*

### Entorno extendido de medios compartidos
Los dispositivos de red pueden ampliar el entorno para incluir accesos múltiples o mayores distancias de cableado.

Se realiza mediante cables. Dependiendo del cable y de sus características se pueden realizar diferentes conexiones.

La conexión física entre la PC y la red se establece a través de un puerto.

Los principales medios de transmisión utilizados en las redes locales son:
- Par trenzado.
- Cable coaxial.
- Fibra óptica.

El cable más utilizado para enlazar redes distantes es el de fibra óptica. Crea enlaces muy rápidos entre servidores o interconexión de redes.
#### Par trenzado
Se utiliza para comunicar los nodos de una red

Consta de 4 pares de cables.

Existen variaciones:
- UTP (Unshielded twisted pair).
- STP (Shielded twisted pair).
- FTP (Foiled twisted pair).

### Cable Coaxial
Tipo bastante cable que se utiliza para transmitir señales de electricidad de alta frecuencia.

Se compone de un núcleo desarrollado con hilo de cobre que está envuelto por un elemento aislador , unas piezas de metal trenzado y una cubierta de plástico.

### Fibra Óptica
Se forma al juntar cientos o miles de cables tan delgados como un cabello humano de fibra de vidrio transparente.

Los datos se transforman en pulsos de luz emitida por un láser del tamaño de la cabeza de un alfiler y se transmiten a una alta velocidad.

## Redes Conmutadas
Acción de establecer una vía, un camino de extremo a extremo entre dos puntos, un emisor y un receptor a través de nodos o equipos de transmisión. La conmutación permite la entrega de la señal desde el origen al destino.

### ¿Cómo funcionan?
La comunicación entre un host origen y un host destino se realiza mediante la transmisión de datos a través de una red de nodos de comunicación intermedios.

Cada nodo intermedio almacena los datos temporalmente antes de enviarlos.

Los dispositivos finales son computadoras, terminales, teléfonos, etc.

Son las redes de área extensa.

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

## Coherencia de Caché

### Multiprocesadores
Los multiprocesadores son sistemas MIMD basados en varios procesadores funcionando de forma paralela e independiente.

La principal característica de los multiprocesadores es que la memoria está compartida, es decir, todos los procesadores comparten el mismo espacio de direccionamiento.

### El problema de la coherencia de las cachés
La memoria debe proporcionar un conjunto e direcciones para almacenar valores y cuando se lea una de estas direcciones debe devolver el último valor escrito en ella.

Una lectura devuelve el último valor escrito en esa dirección, **sin importar** el proceso que se escribió dicho valor.

Cuando dos procesos ven la memoria compartida a través de diferentes cachés, existe el peligro de que uno vea el nuevo valor en su caché mientras que el otro todavía el antiguo.

### Ejemplo del problema de la coherencia de cachés con dos procesadores

| Tiempo | Acción               | Caché A | Caché B | Memoria (X) |
| ------ | -------------------- | ------- | ------- | ----------- |
| 1      | CPU A lee X          | 1       | N/A     | 1           |
| 2      | CPU B lee X          | 1       | 1       | 1           |
| 3      | CPU A escribe 0 en X | 0       | 1       | 0           |
| 4      | CPU B lee X          | 0       | 1?      | 0           |

## Sistema de clústers

### ¿Cómo mejorar el desempeño?
Básicamente hay 3 maneras:
1. Trabajar más intensamente.
2. Trabajar más inteligentemente.
3. Solicitar ayuda.

Analogía para la computadora
1. Utilizar HW especial (reducir el tiempo de instrucción con un CPU de mayor ciclos de reloj).
2. Optimizar algoritmos y técnicas de programación.
3. Utilizar múltiples recursos de cómputo para resolver el problema, ejecutando más instrucciones en el mismo tiempo.

### ¿Qué es un clúster?
El término Clúster se aplica a los conjuntos o conglomerados de computadoras unidos entre sí normalmente por una red de alta velocidad y que se comportan como si fueran una única computadora.

Aunque algunas son máquinas muy sofisticadas, un clúster pueden ser varios sistemas de PC's trabajando en "paralelo" o al mismo tiempo en una determinada tarea.

A cada uno de los elementos del Clúster se le conoce como **nodo**.

Estos son aparatos o torres que pueden tener uno o varios procesadores, memoria RAM, interfaces de red, dispositivos de entrada y salida, y sistema operativo.

Los nodos pueden estar contenidos o inter-conectados en un solo gabinete o acoplados a través de una red LAN.

Generalmente, en los Clúster existe una máquina que funciona como **nodo-maestro** y se encarga de administrar, controlar y monitorear todas las aplicaciones y recursos del sistema, mientras el resto de los nodos está dedicado al procesamiento de datos o a ejecutar operaciones aritméticas. Se les conoce como **nodos-esclavos**.

## Clasificación de los Clúster
- HPCC - Alto rendimiento.
- HACC - Alta disponibilidad.
- HTCC - Balance de carga.

### Alto rendimiento (HPCC)
Este tipo de clúster está diseñado para obtener el máximo rendimiento de la aplicación utilizada, incluso a costa de la disponibilidad del sistema, es decir, el clúster puede sufrir caídas. Este tipo de configuración está orientada a procesos que requieran mucha capacidad de cálculo.

## Alta disponibilidad (HACC o Fail-Over)
Este tipo de clúster está diseñado para mantener uno o varios servicios disponibles, incluso a costa de rendimiento ya que su foco principal es que el servicio jamás tenga interrupciones, como es el caso de una base de datos.

## Balance de carga (HTCC o Load-Balancing)
Este tipo de clúster está diseñado para balancear la carga de trabajo entre varios servidores; esto permite tener, por ejemplo, un sitio Web sin caídas por una carga excesiva de peticiones en un momento dado. Actualmente un clúster load-balancing es un fail-over, con el extra del balanceo de la carga y con mayor número de nodos.

## Características importantes...
**Escalabilidad**: Se espera que un clúster presente una combinación de los tres servicios anteriores y además que sea escalable. Característica importante porque un clúster inicia con pocos nodos y posteriormente se añadirán más.

**Flexibilidad**: Todos los nodos pueden tener la misma configuración de HW y SO (clúster homogéneo) o tener arquitectura y SO similares, no iguales (clúster semi-homogéneo) o tener diferente HW y SO (clúster heterogeneo).

## Un clúster necesita varios componentes de HW y SW para funcionar
- Nodos (ordenadores - servidores).
- Sistemas Operativos.
- Conexiones de red.
- Middleware (capa de abstracción entre el usuario y los SO).
- Protocolos de comunicación y servicios.
- Aplicaciones paralelas.

## Programación de clúster
Todo el software ha sido escrito para una **computación de serie**:
- El programa se diseña para correr en un solo sistema con una única CPU.
- El problema es dividido en series de instrucciones.
- Las instrucciones son ejecutadas una detrás de otra.
- Sólo una instrucción puede ser ejecutada en cada instante de tiempo.

Se puede definir la **computación en paralelo** como la utilización simultánea de múltiples recursos de computación para resolver un problema:
- El programa correrá utilizando múltiples procesadores.
- El problema es dividido en partes que pueden ser resueltas concurrentemente.
- Cada parte es descompuesta en series de instrucciones.
- Las instrucciones procedentes de cada parte se ejecutan simultáneamente en diferentes procesadores.

## Algunos usos de clúster
- Análisis Estructural.
- Simulación de mecánica de fluidos.
- Predicción meteorológica.
- El estudio de cualquier fenómeno que pueda ser modelado matemáticamente.
- Alto rendimiento en bases de datos.
- Google.
- Nasa.
- NSA (National Security Agency).