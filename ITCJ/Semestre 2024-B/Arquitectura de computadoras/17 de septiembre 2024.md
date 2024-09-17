Materia: Arquitectura de computadoras [[Arquitectura de computadoras]]
Siguiendo [[12 de septiembre 2024]]...

La velocidad de los procesadores aumenta según la tecnología va avanzando, mientras que la velocidad de las tarjetas para expandir el hardware permanece relativamente constante. No es práctico rediseñar y reemplazar cada tarjeta cada vez que un nuevo procesador sale al mercado. Esto sería muy complicado y caro para los fabricantes.

El compromiso de la industria de mantener compatibilidad con versiones anteriores complica aún más las tareas de diseño, porque cualquier nueva tecnología tendría que ejecutar los dispositivos más antiguos y lentos.

Para resolver esto, los diseñadores dividieron el bus externo de datos en dos partes...
### Bus local
Da soporte al CPU, RAM y otros componentes del motherboard. Este bus corre a la velocidad del procesador.

### Bus de expansión
Da soporte a cualquier dispositivo que se añade al motherboard mediante las ranuras de expansión y funciona a una velocidad constante. Según el diseño de bus específico.

### Objetivos del bus del sistema
- Conectar las placas con el procesador para permitir de datos.
- Llevar voltaje a las placas (+/- 5v, +/-  12v, +/-  3.3v).
- Facilitar la instalación de tarjetas.
- Ofrecer un estándar de conexión al sistema.

## Bus local
**Bus de datos**: Lleva información (bytes) desde y hacia el procesador. Es bidireccional.
**Bus de direcciones**: Permite al procesador seleccionar posiciones de memoria para lectura o escritura. Es unidireccional porque le procesador solicita direcciones que son leídas por los periféricos.
**Bus de control**: Consiste en señales individuales con las que el procesador controla los dispositivos externos mediante las cuales "se pone de acuerdo" con ellos para realizar transferencias de información. Es bidireccional.

"PCMCIA(Personal Computer Memory Card International Association)"

## USB
Se utiliza para conectar periféricos externos como ratones, teclados, scanners, cámaras digitales, etc... a la computadora.

### Tipos de USB
- USB 1.0 -> 1.5Mbps
- USB 1.1 -> 12Mbps
- USB 2.0 -> 480Mbs
- USB 3.0 -> 4.8Gbps
- USB 3.1 (USB C) -> 10Gbps (1GB/s)
- USB 3.2 -> 20Gbps (2.5GB/s)
- USB 4.0 -> 40Gbps (4GB/s)

![[Pasted image 20240917112847.png]]

Entre más lejos del CPU, los buses son más lentos y normalmente de menos líneas de datos.