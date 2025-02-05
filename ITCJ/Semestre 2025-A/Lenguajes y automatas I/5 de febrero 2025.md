Mes: [[ITCJ/Semestre 2025-A/Lenguajes y automatas I/Enero|Enero]]
Subtema LyAI.

## Actividad
Sea A={epsilon, a}, determinar A* y A⁺

A* = Union de todas las A con potencia 0 hasta infinito.
A⁺ = Union de todas las A con potencia 1 hasta infinito.

**Cerradura estrella** ={epsilon} U {epsilon, a} U {epsilon, a, aa} U {epsilon, a, aa, aaa} U... 
= {epsilon, a, aa, aaa, aAaaa, ...}

**Cerradura positiva A⁺** = {epsilon, a} U {epsilon, a, aa} U {epsilon, a, aa, aaa} U ... = {epsilon, a, aa, aaa, aaaa, ...}

Sea B = {a, ab}, determinar B* y B⁺
**Cerradura estrella** = {epsilon} U {a, ab} U {aa, aab, aba, abab} U {aaa, aaab, aaba, aababa, abaa, abaab, ababa, ababab} U ...

**Cerradura positiva** = {a, ab} U {aa, aab, aba, abab} U {aaa, aaab, aaba, aababa, abaa, abaab, ababa, ababab} U ...


