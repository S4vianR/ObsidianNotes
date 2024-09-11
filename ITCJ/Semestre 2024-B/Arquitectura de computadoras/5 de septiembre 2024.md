Materia: Arquitectura de computadoras [[Arquitectura de computadoras]]
Siguiendo [[3 de septiembre 2024]]

## DRAM
La RAM dinámica debe ser refrescada dinámicamente todo el tiempo o pierde lo que está almacenado (los bits).

Esto hace que se pierda tiempo y hace lento el manejo de memoria.

Las celdas de memoria están grabadas en una oblea de silicio (silicon wafer) en un arreglo de columnas (bitlines) y renglones (wordlines).

La intersección de una bitline y una wordline forma una dirección de memoria.

![[Pasted image 20240905111524.png]]

La DRAM funciona enviando una carga (una señal eléctrica llamada Strobe) a través de una columna específica (CAS) para activar el transistor de cada bit en la columna.

Cuando se está escribiendo, los renglones contienen en el estado el estado del capacitor que se debe usar.

### Amplificador de sentido
El amplificador de sentido (Sense amplifier) determina el nivel de carga en el capacitor, si es mas del 50% se representa como 1, si no, como 0.

![[Pasted image 20240905111735.png]]

## Tiempo de acceso (Latencia)
Es el tiempo que transcurre desde que una dirección de memoria es visible para los circuitos de la memoria hasta que el dato está almacenado (escritura) o está disponible para ser utilizado (lectura).

### La velocidad de la RAM en el sistema es controlada por el ancho de bus y la velocidad de bus:
- El **ancho de bus** se refiere al número de bits que pueden ser enviados al CPU de manera simultanea.
- **Velodiad de bus**: se refiere a la cantidad de veces que un grupo de bits puede ser enviado c/s.
- Un **ciclo de bus** sucede cada vez que los datos viajan de la memoria al CPU.

## Memoria caché
Aún con un bus eficiente, sigue tomando tiempo transportar los datos de la RAM al CPU para que sean procesados.

La memoria caché se diseñó para aliviar el cuello de botella haciendo que los datos que el CPU utiliza más seguido, estén disponibles al instante.

Esta memoria se clasifica en L1, L2, L3 todas disponibles dentro del procesador (procesadores actuales).

En algunos procesadores con GPU integrados se utiliza un nivel de caché L4, va en un circuito fuera del CPU.

![[Pasted image 20240905113435.png]]

### ¿Cómo funciona la caché)
Un tipo particular de RAM llamada SRAM.

SRAM utiliza múltiples transistores para cada celda de memoria.

Tiene un arreglo externo de compuertas que se conoce como multivibrador biestable que cambia entre dos estados (flipflop). Esto significa que no tiene que ser continuamente refrescada como la DRAM.

Cada celda mantiene el dato mientras tenga electricidad. Esto significa que la SRAM puede funcionar extremadamente rápido.

Sin embargo la complejidad de cada celda hace que ocupe más espacio en un integrado y es más costoso.
