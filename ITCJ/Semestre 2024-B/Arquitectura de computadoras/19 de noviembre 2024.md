Siguiendo [[15 de noviembre 2024]]...
Subtema AdC.
Mes: [[Noviembre]]
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
