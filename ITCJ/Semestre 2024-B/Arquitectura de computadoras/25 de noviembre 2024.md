Siguiendo [[19 de noviembre 2024]]...
Subtema AdC.
Mes: [[Noviembre]]

Seguimiento de: [[21 de noviembre 2024#Sistema de clústers#¿Qué es un clúster?]]

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
Este tipo de clúster está diseñado para mantener uno o varios servicios disponibles, incluso a costa de rendimiento ya que su foco principal es que el servicio jamás tenga interrupciones, como es el caso de una base datos.

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