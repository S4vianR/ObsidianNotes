Siguiendo [[10 de septiembre 2024]]...
Subtema AdC.
Mes: [[Septiembre]]
## Memory address
Además del I/O address, algunos dispositivos requieren un block de memoria en la parte alta de la misma para uso particular.

Estos bloques de memoria son asignados durante el proceso de arranque del sistema.

## Interrupciones

### ¿Qué son las IRQ's?
Son avisos que el hardware envía al procesador de una computadora a través de señales físicas a los circuitos de la misma CPU.

Las solicitudes de interrupciones están basadas en un sistema de prioridades de modo que el procesador pueda o no ignorarlas.
### ¿Porqué se producen?
Puede ser como una consecuencia de un evento externo al CPU.

Por el propio CPU como consecuencia de la ejecución o intento de ejecución de una instrucción.

Por cualquiera de estos motivos una interrupción debe entenderse como un suceso que se produce por "sorpresa" pero hay que tratarlo inmediatamente.

### ¿Cómo sabe el CPU cuál es la dirección de la rutina que las resuelve?
Salta a las rutinas de tratamiento de la interrupción mediante indirección.

Normalmente en la parte baja de la memoria se dispone de una tabla de vectores de interrupción.

El SO debe de encargarse en su proceso de inicialización.

### Tipos de interrupciones
Interrupciones externas:
- Interrupciones de hardware.
Interrupciones internas:
- Traps (trampas)
- Interrupciones de SO.

#### Interrupciones internas
Son asíncronas...

#### Interrupciones internas
Son síncronas porque cuando se producen están asociadas a una instrucción del propio programa.

Las trampas (traps) son provocados por el programador. Las causas suelen ser realización de operaciones no permitidas, como la división entre cero, o el desbordamiento, etc. Para provocar una trampa existe instrucciones en el código de máquina (INT).

Las excepciones se producen al realizar una operación no permitida dentro del software, se producen por un fallo al programar.

### ¿Cuál interrupción se resuelve primero?
Esto lo resuelve el PIC (Programmable Interrupt Controller).

Se establecen prioridades...

### Segun su importancia, hay que atender las interrupciones o no
1. **Las No Enmarscarables (NMI)**. Son las que siempre se atiende. Se deben a motivos cuya atención no puede postergarse en el tiempo, Ej. Un reset, un error en el bus de direccionnes (BERR), fallo en la tensión eléctrica, etc.
2. **Las Enmascarables**: Se pueden atender o no, dependiendo de lo que esté indicado en el registro de estado del procesador. Se coloca en un estado ENABLE o DISABLE en la bandera de aceptación de interrupciones.

### Atención de la interrupción
1. Se guardan en la pila de registro de estado y el contador de programa.
2. Se inhiben las instrucciones.
3. Se contesta con la señal INTA (Interrupt Acknowledge).
4. El PIC desactiva la señal de interrupción.
5. El PIC pone en el bus de datos del # de vectorV de la interrupción a trarar.
6. El CPU lee el # de vectorV.
7. El procesador debe calcular la dirección del vector de interrupción que contiene la dirección de rutina de tratamiento correspondiente, la cual se encuentra en la tabla de vectores de interrupción.
8. El CPU pone el contenido del vector del IRQ en el contador del programa. (la RTI correspondiente).
9. Toma el control de la RTI al nivel de la interrupción atendida.
10. Al finalizar la RTI, su última instrucción es del tipo "retorno de interrupción" (IRET, RTE...). Esta instrucción saca de la pila los valores guardados y con esto las interrupciones vuelven a estar permitidas.
11. Continúa la ejecución del prorgrama que fue interrumpido.

El tratamiento de las interrupciones NMI es similar a las enmascarables, con la diferencia que se atienden aún estando el CPU con las interrupciones inhibidas.

![[Pasted image 20240911114124.png]]