Materia: Arquitectura de computadoras [[Arquitectura de computadoras]]
Siguiendo [[6 de septiembre 2024]]...

## Manejo de entrada y salida
El procesador controla en parte o completamente las actividades de todos los dispositivos que están integrados o conectados al motherboard de la PC.

Este control proviene de la capacidad del CPU para comunicar sus comandos, sus peticiones y los datos directamente a cada dispositivo mediante vías de comunicación privadas que son creadas específicamente para cada uno de ellos.

Además, los dispositivos también necesitan obtener la atención de vez en cuando para requerir una acción o servicio del CPU.

Pero esto añade complejidad al motherboard y limita a la PC solamente a aceptar el número de dispositivos que tengan línea dedicada...

### Obtención de la atención del CPU
Cuando un dispositivo necesita la atención del CPU para que realice alguna operación, primero debe obtener la atención del mismo.

Con la rapidez que todo está sucediendo dentro de la PC, cuando un dispositivo necesita el CPU, lo necesita al instante.

Para esto, los dispositivos tienen que generar un código de interrupción conocido como IRQ.

### Comunicandose con los dispositivos
Tan pronto como el CPU termina la tarea que se le requirió, le comunica al dispositivo con que la tarea ya está hecha.

Hacer esto debe tener significado, no solamente apagar la luz de requisición de servicio encendida por el dispositivo.

Cada dispositivo conectado a la PC tiene asignado su propio buzón (mailbox) de dos vías.

Estos buzones trabajan casí como un sistema de correo privado dentro de la PC.

Los dispositivos obtienen datos y mensajes de sus propios buzones y también pasan mensajes y datos a otros dispositivos a través de estos buzones.

Después de terminar una tarea específic requerida por un dispositivo, cualquier dato o instrucción que necesite ser comunicada al mismo es colocada en el buzón asignado a él.

## Recursos del sistema en la PC
Son un set de tres mecanismos utilizados en la PC y el CPU para comunicarse.

1. **Interrupt Request (IRQ)**: Es el mecanismo usado por los dispositivos para requerir los servicios del CPU. Existen 16 IRQ's. Solamente 10 utilizan para dispositivos y el resto se reservan para uso del sistema.
2. **Input/Outputm (I/O) Address**
3. **Direct Memory Access (DMA)**

## Dispositivos lógicos
Un dispositivo lógico es el hardware y sus circuitos, por ejemplo un puerto.

Un dispositivo lógico es aquel que **se le asigna un nombre** que se puede usar en lugar de su dirección real.

**Ejemplo**: El primer puerto serie en una PC debe tener una dirección de 32 bits. Esto sería el nombre físico, pero resulta más cómodo utilizar el nombre lógico como COM1, es más práctico.

La rutina **POST** se encarga de asignar los nombres lógicos de los dispositivos durante la secuencia de arranque del sistema. El **BIOS** localiza cada dispositivos físico utilizando su **I/O address** y después se le asigna el nombre lógico.