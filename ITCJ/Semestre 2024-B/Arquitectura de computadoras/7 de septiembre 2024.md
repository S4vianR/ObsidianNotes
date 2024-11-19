Siguiendo [[17 de septiembre 2024]]...
Subtema AdC.
Mes: [[Septiembre]]
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