Materia: Arquitectura de computadoras [[Arquitectura de computadoras]]
Siguiendo [[5 de septiembre 2024]]...

## BIOS
B -> Basic
I -> Input
O -> Output
S -> System

Es lo primero que vemos cuando encendemos la computadora.

Es un software especial que sirve de interfaz entre los componentes principales del hardware y el sistema operativo.

Usualmente se encuentra guardado en un chip de memoria flash en el motherboard y tiene su propia bateria.

Es un software que desempeña diferentes roles, pero el más importante es cargar el sistema operativo.

Cuando encendemos la computadora y el procesador intenta ejecutar la primera instrucción, necesita traerla de algún lado... No puede obtenerla del sistema operativo porque éste se encuentra en el disco duro y el procesador no puede accesarlo ahí sin instrucciones. El BIOS contiene estas instrucciones

### Algunas tareas comunes que el BIOS realiza son:
Un test de encendido (POST -> Power On Self Test) para todos los componentes del hardware y asegurarse que todos están funcionando correctamente.

Activación de otros BIOS en las diferentes tarjetas (o dispositivos) instalados en la computadora.

Provee un set de rutinas de bajo nivel que el sistema operativo utiliza para interactuar diferentes dispositivos de hardware (estas son las rutinas que le dan a la BIOS su nombre).
Estos dispositivos son el teclado, la pantalla, los puertos, etc.

Maneja una colección de configuraciones para el disco duro, el reloj, etc. Estas configuraciones dependen del fabricante.

## Secuencia de arranque del sistema
1. Cuando se enciende la computadora, la fuente de poder se incializa. Tan pronto como está lista para proveer electricidad confiable al resto del equipo, transmite una señal al chipset del motherboard y se conoce como "buen voltaje" (good power). El chipset envía un comando de reinicio del sistema.
2. El comando de reinicio (reset) de sistema enviado por el chipset del motherboard ocasiona que el CPU lee la primera instrucción de lo que se conoce como el **jumpaddress** -> El jumpadress siempre está localizado en una localidad preestablecida, típicamente en la dirección **FFFF0h** en la memoria del sistema. La dirección jump contiene la dirección física del programa del boot en el BIOS que se encuentra en la ROM.
3. El CPU ejecuta la primera instrucción que copia el BIOS en la memoria RAM y comienza a ejecutarse.
4.  Enseguida el BIOS lleva a cabo el proceso de POST que verifica y prueba la configuración del hardware almacenada en la información de configuración del BIOS. Si el POST detecta algún problema emite código de pitido, las cuales son diferentes dependiendo del hardware que esté fallando.
5. Si el POST no encuentra ningún problema, continua el proceso de arranque (BOOT). En éste punto la BIOS (que está arrancando la PC) busca el BIOS del adaptador de vídeo y lo inicia. Los dispositivos periféricos tienen su propios BIOS. En éste punto, sin tomar en cuenta el ruido de los manejadores de disco y un pitido simple que indica que todo está bien, es cuando nos damos cuenta (externamente) que la PC está arrancando.
6. Puede aparecer información en la pantalla del adaptador de video e información del BIOS del sistema.
7. Cualquier rutina de BIOS de dispositivo comienza en éste punto.
8. Enseguida el BIOS comienza una serie de pruebas en el sistema sobre la pantalla para desplegar mensajes de error.
9. Con los BIOS de los dispositivos cargados, el BIOS del sistema checa que los dispositivos listados en la configuración **CMOS** estén presentes y funcionando, incluyendo la velocidad, métodos de acceso y otros parámetros. En ésta secuencia se asignan los nombres lógicos a los puertos (COM1, COM2, etc.) Sólo falta una cosa...
10. El BIOS debe encontrar el SO para iniciar su ejecución. En la CMOS se incluye el parámetro que indica en dónde buscar y en qué orden, Esta secuencia puede ser cambiada. El BOOT irá buscando en el orden que se encuentre la lista de dispositivos en la CMOS y si no se encuentra desplegará el siguiente mensaje -> **No boot device avalible**.
11. Después de esto, la computadora está lista para utilizarse...

![[Pasted image 20240906110736.png]]

### Jumpadress
El programa del BIOS es cargado a un área reservada de memoria del sistema, normalmente los últimos 64KB (direcciones de memoria **F000h a FFFFh**) el primer MB de memoria.

Los fabricantes de procesadores y BIOS han establecido está localidad en la memoria como default, lo que significa que los procesadores **siempre** buscan el inicio del BIOS en está dirección de memoria.

## CMOS
**Complementary Metal-Oxide-Semiconductor (CMOS)** utiliza un conjunto de transistores para conseguir mantener un mínimo de corriente al motherboard cuando se apaga.

Este elemento soluciona un problema: **la desconfiguración de la BIOS al apagar la PC**.

### Suele haber confusion con la bateria CMOS y la memoria CMOS
La primera es una simple pila que está conectada a la placa base para suministrar un poco energía a ésta cuando la PC está apagada. Se conoce como una **batería CR2032** y tiene una vida útil de hasta 10 años. Los síntomas de una batería agotada son:
- Pérdida de configuración de la BIOS.
- Fecha desactualizada.
- Pantalla que diga  -> **"CMOS BATTERY LOW"**.

La segunda es una especie de pequeña memoria que almacena las configuraciones de la BIOS de nuestro motherboard. Sirve para mantener los valores de hora y fecha correctos. De lo contrario, si apagamos la PC, la encendemos y accedemos a la BIOS está desconfigurada.

Tiene muy poco consumo de energía para mantener los datos. Funciona estando la PC apagada y lo hace gracias a la pila CMOS. Puede mantener los datos de configuración por años.

También se le conoce como NVRAM (non volatile RAM).

## Cold warm vs. Warm Boot
La secuencia de arranque utilizada cuando se enciende la computaora desde cero (sin haber estado encendia) recibe el nombre **cold boot**.
La computadora inicia de un estado frío (o completamente apagada).

Un arranque en tibio (warm boot) sucede cuando la PC está encendida y se reinicia (por decisión del usuario).

Un arranque en frío lleva a cabo la sencuencia de boot completa (incluye el POST) y un arranque en tibio no.