Mes: [[Marzo]]
Subtema LyAI.

Describir el patrón de una constante entera, que puede ser dada en hexadeimal (empieza en 0x ó 0X), decimal (empieza con dígito diferente de 0), octal (empieza con 0) ó binario (empieza con 0b ó 0B), como en C/Java y escribir código para reconocerla y encontrar su valor. Pueden tener signo. Atributo es su valor como entero.

( + U - U epsilon)(
( 0 (x U X)(0 U 1 ... U 9 U A U ... U F U a U ... U f)
(0 U 1 ... U 9 U A U ... U F U a U ... U f)\*) U
((1 U ... U 9)(0 U 1 ... U 9)\*) U
(0 (0 U 1 U ... U 7)\*) U (0(b U B)(0 U 1)\*))

## Código a hacer
Dada una cadena determinar si corresponde a un componente léxico CTE_ENTERA y determinar su atributo(valor).