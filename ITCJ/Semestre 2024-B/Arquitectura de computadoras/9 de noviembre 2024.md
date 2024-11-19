Siguiendo [[8 de noviembre 2024]]...
Subtema AdC.
Mes: [[Noviembre]]

Siguiendo del tema: [[8 de noviembre 2024#Tipos de computacion paralela]]
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