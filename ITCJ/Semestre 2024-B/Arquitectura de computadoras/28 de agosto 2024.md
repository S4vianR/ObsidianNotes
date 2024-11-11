Materia: Arquitectura de computadoras [[Arquitectura de computadoras]]
Siguiendo [[27 de agosto 2024]]... 
Subtema AdC.
## Instrucciones Set Architecture
La arquitectura del set de instrucciones (ISA) determina el formato de las instrucciones, los tipos de datos que puede operar, las distintas formas de obtener datos de memoria (que son llamadas "modo de direccionamiento") y la forma en que se atienden eventos externos (interruptores).

Cada instrucción implica "algo que hacer", que en lenguaje técnico es llamado **código de operación**.

## Funciones básicas de una computadora
- Procesamiento de datos.
- Almacenamiento de datos.
- Transferencia de datos.
- Control.

## Estructura de una computadora
Hay cuatro componentes principales:
1. CPU (UC, ALU, Registros).
2. Memoria principal.
3. E/S.
4. Bus del sistema.
![[Pasted image 20240828111936.png]]

# Modelos de arquitecturas
1. Clásicas.
2. Segmentadas.
3. Multi-procesamiento.

## Arquitectura clásica
<marquee
		 bgcolor="green"
		 direction="left"
		 ><b>Arquitectura Princeton / Mauchly-Eckert (Von Neumann)</b>-> Modelo de programa almacenado.
</marquee>
El modelo clásico de arquitectura de computadoras fue diseñado por John Von Neumann y consta de los siguientes elementos:
- Dispositivos de entrada.
- Dispositivos de procesos.
- Dispositivos de almacenamiento.
- Dispositivos de salida.

Una característica importante de este modelo es que tanto los datos como los programas se almacenan en la memoria antes de ser utilizados.

### Características
- Los datos y las instrucciones se almacenan en una sola memoria de lectura-escritura.
- Los contenidos de esta memoria se direccionan indicando su posición, sin considerar el tipo de dato contenido en la misma.
- La ejecución se produce siguiendo una secuencia de instrucción tras instrucción.

### Principal desventaja
La principal desventaja de esta arquitectura es que el bus de datos y direcciones único se convierte en cuello de botella (bottleneck) por el cual debe pasar toda la información que se lee o que se escribe a la memoria, obligando a que todos los accesos a esta, sean secuenciales. Esto limita el grado de paralelismo (acciones que se pueden realizar al mismo tiempo). Este efecto se conoce como el **cuello de botella de Von Neumann**.

### Arquitectura Harvard
Al igual que en la arquitectura Von Neumann el programa se almacena como un código numérico en la memoria, pero no en el mismo espacio de memoria i en el mismo formato que los datos.

El hecho de tener un bus separado para el programa y otro para los datos permite que se lea el código de operación de una instrucción, al mismo tiempo que se lee de la memoria de datos los utilizados de la instrucción previa.

![[Pasted image 20240828114241.png]]

## Arquitectura segmentada
Estas arquitecturas, también llamadas con segmentación del cauce (pipeline), buscan mejorar el desempeño realizando paralelamente varias etapas del ciclo de instrucción al mismo tiempo.

El procesador se divide en varias unidades funcionales independientes y se dividen entre ellas el procesamiento de las instrucciones.

Se toma el mismo número de ciclos de reloj (el mismo tiempo) pero como se trabaja en varias instrucciones al mismo tiempo, el número promedio de instrucciones por segundo se multiplica.

Ciclo de ejecución de instrucciones.
1. Fetch.
2. Decode.
3. Execute.
4. Prepare to fetch.

Program counter (PC).



