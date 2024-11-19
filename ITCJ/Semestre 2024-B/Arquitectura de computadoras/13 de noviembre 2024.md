Siguiendo [[9 de noviembre 2024]]...
Subtema AdC.
Mes: [[Noviembre]]
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