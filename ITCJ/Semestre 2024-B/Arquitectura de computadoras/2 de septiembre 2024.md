Siguiendo [[30 de agosto 2024]]... 
Subtema AdC.
Mes: [[Septiembre]]
## El procesador (CPU)
El procesamiento de datos e instrucciones es manejado en un ciclo de máquina.

El ciclo de máquina incluye cuatro pasos que realiza un procesador por cada instrucción:
1. Fetch.
2. Decodificar.
3. Ejecutar.
4. Almacenar.

![[Pasted image 20240902110536.png]]

Varias características del rendimiento del CPU determinan la eficiencia del equipo máquina básico:
1. Velocidad del reloj.
2. Tamaño de palabra.
3. Ancho de bus.
4. Pipelining.
5. Procesamiento RISC o CISC.

### Velocidad del reloj
Un reloj interno del sistema sincroniza el ciclo de máquina.

En cada pulso del reloj, el CPU ejecuta otra instrucción.

**Definición**: Velocidad de reloj es la velocidad a la que el CPU lleva a cabo sus instrucciones básicas.

Las computadoras ejecutan instrucciones muy rápido a velocidades medidas, **Hertz** (Ciclos por segundo).

La velocidad del reloj es medida en Gigahertz (billones de ciclos por segundo).

### Tamaño de palabra
Un factor importante que contribuye al poder del CPU es la cantidad de datos o instrucciones que son movidos a través del procesador en un ciclo de máquina.

**Definición**: El tamaño de palabra se refiere al grupo de bits que un procesador puede manipular como unidad en un ciclo de máquina.

![[Pasted image 20240902111945.png]]

![[Pasted image 20240902112038.png]]

<marquee > I use Arch BTW </marquee>
### Ancho de bus
Otro factor de desempeño es el ancho de bus del sistema entre el procesador y la memoria.

El bus del sistema es una ruta electrónica entre el CPU, la memoria y otros componentes del sistema.

El procesador tiene dos conexiones de bus hacia la memoria:
1. Bus de datos.
2. Bus de direcciones.

#### Bus de datos
- Es el conjunto de vías que transportan los datos actuales entre la memoria y el cpu.

#### Bus de direcciones
- Es una vía electrónica que acarrea información acerca de las localidades de memoria de los datos.
- El ancho del bus de direcciones determina cuánta memoria puede reconocer el procesador.
### Pipelining
Técnica utilizada para maximizar la velocidad de los CPU's.

El pipeline incrementa la eficiencia leyendo una instrucción, comenzando el procesamiento y leyendo otra instrucción antes de terminar la anterior.

Esta técnica redice el tiempo de inactividad (idle time) del CPU e incrementa la velocidad.

### Procesamiento (Instruction Set Architecture)
1. RISC.
2. CISC.

Investigar lo siguiente:
1. 5 ó 6 características principales de cada set de instrucciones
2. Qué fabricantes del equipo los utilizan.
3. De 3 a 4 modelos de procesadores donde se implementan.
4. Ventajas y desventajas de c/u.