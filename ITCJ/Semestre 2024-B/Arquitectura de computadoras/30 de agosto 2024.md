Materia: Arquitectura de computadoras [[Arquitectura de computadoras]]
Siguiendo [[29 de agosto 2024]]... 
# Introducción a la lógica digital
Cuatro componentes primarios son utilizados virtualmente en cada circuito electrónico dentro de la computadora. Cada uno de estos componentes provee específicamente diferentes funciones para cada circuito.

Estos componentes son:
1. Resistencias.
2. Capacitores.
3. Diodos.
4. Transistores.

## Los componentes electrónicos de la PC
- Una **resistencia** reduce el flujo de corriente eléctrica en un circuito.
- Un **capacitor** es utilizado para almacenar cargas eléctricas.
- Un **diodo** fuerza el flujo de electricidad en un solo sentido.
- Un **transistor** almacena un dígito binario simple (bit).

Otro componente electrónico básico es la compuerta lógica. Está formada por una combinación de resistencias, capacitores, diodos y transistores.

![[Pasted image 20240830111723.png]]

## Lógica digital
Todo lo que una computadora hace para nosotros está controlado por el microprocesador. 

Lo que vemos como un procesador de palabras, un juego de computadora, un navegador, el correo electrónico o cualquier otro software que se ejecute en nuestro PC, en realidad son cientos o miles de instrucciones que el microprocesador ejecuta una por una para llevar a cabo esas acciones.

El procesador es una pieza de circuitería electrónica que utiliza lógica digital para realizar las instrucciones del software.

## Lógica de estados
La electricidad en la computadora está o no presente.

Los datos son almacenados en la computadora mediante cargas eléctricas que existe o no (representadas por 1 y 0).

El transistor es el componente que puede manejar dos cargas con diferentes niveles de voltaje. Un voltaje alto representa un valor y voltaje bajo representa otro valor.

La computadora solamente tiene dos estados eléctricos donde almacenan datos, así que los datos deben de ser muy simples para poder ser manejados. Con datos más complejos se utilizan transistores agrupados para representar esos datos.

## Datos binarios
Los dos niveles de voltaje en una computadora pueden representar los dos valores binarios, el voltaje más bajo equivale a un 0 y el voltaje más alto equivale a un 1.

Cuando un transistor maneja un valor binario por medio de voltaje, este valor se convierte en un dígito binario o bit.

## Grupos de bits
Para poder almacenar datos con longitud mayor a un bit, los bits deben agruparse.

Todos estos grupos tienen nombre y cada grupo es capaz de almacenar un valor binario diferente según el tamaño del grupo.

Algunos de estos elementos que están relacionados con la lógica de la computadora son:
1. Bit.
2. Byte.
3. Nybble.
4. Machine word (tamaño de palabra) -> es la cantidad de bits que un procesador puede manejar en un pulso de reloj.

## Operaciones lógicas primarias
Los procesadores usan los números binarios para direccionamiento, aritmética y para hacer comparaciones (=,<,>,<=,>=,<> or !=) -> Comparadores relacionales.

Las comparaciones lógicas y las operaciones de cambio de datos que lleva a cabo el procesador lo hace utilizando tres funciones:
- AND.
- OR.
- XOR (OR Exclusivo).

Estas tres funciones binarias son parte de la:
- **ALGEBRA DE BOOLE**.
![[Pasted image 20240830114139.png]]
![[Pasted image 20240830114214.png]]
![[Pasted image 20240830113923.png]]

## El procesador (CPU)
Tiene 3 sets esenciales de transistores que trabajan juntos para procesar datos digitales:
- La unidad de control (CU).
- La unidad aritmética y lógica (ALU).
- Los registros.

 La ejecución de instrucciones es un proceso fundamental en el funcionamiento de un CPU. Aquí te explico cómo se ejecutan las instrucciones y cómo se utilizan la Unidad de Control (CU) y la Unidad Aritmético-Lógica (ALU):

**Ejecución de Instrucciones**
La ejecución de instrucciones se realiza en varias etapas:

1. **Fetch** (Recuperación): El CPU recupera la instrucción desde la memoria principal.
2. **Decode** (Decodificación): El CPU decodifica la instrucción, es decir, determina qué operación se debe realizar.
3. **Fetch de operandos**: El CPU recupera los operandos necesarios para la instrucción.
4. **Ejecución**: El CPU ejecuta la instrucción utilizando la ALU.
5. **Almacenamiento de resultados**: El CPU almacena los resultados de la instrucción en la memoria principal o en los registros.

**Unidad de Control (CU)**
La Unidad de Control (CU) es responsable de controlar el flujo de datos y de instrucciones dentro del CPU. La CU se encarga de:

- Recuperar instrucciones desde la memoria principal.
- Decodificar instrucciones.
- Generar señales de control para la ALU y otros componentes del CPU.
- Manejar el flujo de datos entre la ALU, los registros y la memoria principal.

**Unidad Aritmético-Lógica (ALU)**
La Unidad Aritmético-Lógica (ALU) es responsable de realizar operaciones aritméticas y lógicas. La ALU se encarga de:

- Realizar operaciones aritméticas como suma, resta, multiplicación y división.
- Realizar operaciones lógicas como AND, OR y NOT.
- Realizar operaciones de comparación como igualdad y desigualdad.

**Ejemplo de Ejecución de Instrucción**
Supongamos que el CPU debe ejecutar la instrucción `A = B + C`, donde `A`, `B` y `C` son registros.

1. La CU recupera la instrucción desde la memoria principal.
2. La CU decodifica la instrucción y determina que se debe realizar una suma.
3. La CU recupera los operandos `B` y `C` desde los registros.
4. La ALU realiza la suma de `B` y `C`.
5. La ALU almacena el resultado en el registro `A`..

![[Pasted image 20240830114927.png]]
