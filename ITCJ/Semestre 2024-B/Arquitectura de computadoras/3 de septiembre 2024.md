Materia: Arquitectura de computadoras [[Arquitectura de computadoras]]
Siguiendo [[2 de septiembre 2024]]... 
Subtema AdC.

[[2 de septiembre 2024#El procesador (CPU)]]
## Unidad de control
- Secuenciador.
- Contador ordinal.
- Unidad de pre-carga.
- Unidad de decodificación.
- Unidad de prueba de protección.

## Unidad de ejecución
- ALU (Aritmethic Logical Unit).
- Unidad de punto flotante (FPU.
- Registro de estado -> [[3 de septiembre 2024#Registros]].
- Registro acumulador -> [[3 de septiembre 2024#Registros]].

## Unidad de administración de E/S.
- Unidad de manejo de memoria (MMU).
- Unidad de interfaz de bus (BIU).

## Registros

# Memoria
## Memoria RAM
RANDOM ACCESS MEMORY es una serie de pequeñas tarjetas o módulos insertados en ranuras de la tablilla madre (motherboard).

El CPU puede solicitar cualquier dato en la memoria RAM.

Ese dato se localiza, se abre y se despacha al procesador para que sea procesado en una fracción de segundo.

La memoria RAM es el almacenamiento temporal o volátil de la computadora, ya que piere su contenido al apagar la computadora.

### ¿Pero cómo funciona?
La memoria también es un circuito integrado hecho de millones de transistores y capacitores.

En la forma más común de memoria RAM, la DRAM, un transistor y un capacitor que se conectan para formar una celda de memoria, que representa un bit de datos.

El capacitor sostiene el bit de información (un 0 ó un 1). El transistor actúa como un switch que permite al circuito de control de chip informarle si sostiene la carga o no.

### ¿Cómo funciona el capacitor?
Es como una pequeña cubeta que es capaz de almacenar electrones.

Para almacenar un 1 en la celda de memoria, la cubeta es llenada con electrones. Para representar un 0, es vaciada.

El problema con el capacitor es que tiene una fuga... En unos cuantos milisegundos una cubeta llena se vacía.

Así que para la DRAM funcione, el CPU o el controlador de memoria se deben estar recargando todos los capacitores que estén almacenado un 1 antes de que se descarguen.

Los capacitores se deben de volver a energizar aprox. cada 15ms para quee mantengan la carga.

Para lograr esto, el controlador de memoria lee la memoria y la vuelve a escribir. Esta operación de refresco de memoria (refresh operation) sucede automáticamente y de aquí el nombre de RAM dinámica...