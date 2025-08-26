Siguiendo [[28 de agosto 2024]]... 
Subtema AdC.
Mes: [[ITCJ/Semestre 2024-B/Arquitectura de computadoras/Agosto]]

![[Pasted image 20240829112601.png]]

## Arquitectura multiprocesamiento
Cuando se desea incrementar el desempeño  más allá de lo que permite la técnica de pipeline, se requiere utilizar más de un procesador para la ejecución del programa de aplicación.

<span style="color:#F88379">Una computador con multiprocesamiento es un sistema de dos o más procesadores</span>

### Taxonomía de Flynn
Una de las clasificaciones de computadoras que es más popular es la clasificación de Flynn. Ésta taxonomía está basada en la clasificación según el flujo de datos e instrucciones en un sistemas.

Flynn clasifica los sistemas en cuatro categorías
- SISD (Sigle Instruction stream, SIngle Data Stream).
- MISD (Multiple Instruction stream, Single Data stream).
- SIMD (Single Instruction Stream).
- MIMD (Multiple instruction streams, multiple data streams).

![[Pasted image 20240829113310.png]]

### Multiprocesamiento simétrico o multiprocesador simétrico
SMP es el acrónimo de Symmetric Multi-Processing. Hace referencia a la arquitectura en la que todos los procesadores acceden a la misma memoria compartida y periféricos de E/S conectados por un bus común.

Se conocen como simétrico ya que ningún procesador toma el papel de maestro y los demás de esclavos, sino que todos tienen derechos similares en cuanto al acceso a la memoria y periféricos y ambos son los administrados por el SO.

![[Pasted image 20240829113635.png]]

### Clúster
Son conjuntos de computadoras independientes conectadas en una LAN o por un bus de interconexión y que trabajan cooperativamente para resolver un problema.

![[Pasted image 20240829113817.png]]

### Procesadores Vectoriales
Son computadoras pensadas para aplicar un mismo algoritmo numérico a una serie de datos matriciales, en especial en la simulación de sistemas físicos complejos, tales como los simuladores para predecir el clima, explosiones atómicas, reacciones químicas complejas, etc.

La mayoría de los procesadores modernos incluye algunas instrucciones de tipo vectorial, como el conjunto de instrucciones MMX (MultiMedia eXtention) y SSE (Streaming SIMD Extensions). Estas instrucciones les permiten procesar flujos más eficientemente.

### Procesadores Digitales de Señales (DSP)
Son procesadores especializados en el procesamiento de señales tales como audio, video, radar, sonar, radio, etc. Cuentan con instrucciones de tipo vectorial que los hace muy aptos para aplicaciones.

Se utilizan en conjunto con un microcontrolador en dispositivos como reproductores de audio, reproductores DVD y BlueRay, teléfonos celularesm sistemas de entretenimiento, etc.

### Unidad de procesamiento gráfico (GPU)
Son sistemas diseñados originalmente para el procesamiento de gráficos, con múltiples procesadores vectoriales sencillos compartiendo la misma memoria, la cual tambien puede ser accedida por el CPU.

Muchas de las Supercomputadoras más rápidas utilizan estos procesadores y los fabricantes de tarjetas gráficas producen versiones de sus productores especializadas en acelerar los cálculos de propósito general.
