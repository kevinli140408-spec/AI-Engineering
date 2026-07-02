---
titulo: "Lenguajes de Programación"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-07-01
tags: [lenguajes-de-programacion, compiladores, paradigmas]
fuentes: [pensamiento-computacional-mm, guia-estudio-algoritmia-mm, joyanes-aguilar-fundamentos-de-programacion, introduccion-a-la-programacion-con-python-3]
---

# Lenguajes de Programación

Conjunto de palabras, símbolos y reglas sintácticas mediante los cuales se indica a la computadora los pasos a seguir para resolver un problema (el [[conceptos/algoritmo]]).

## Niveles

| Nivel | Descripción | Ejemplo |
|-------|-------------|---------|
| **Máquina** | Código binario (0 y 1); el único que entiende directamente el procesador | `10110000 01100001` |
| **Bajo nivel** | Representación simbólica del lenguaje máquina (mnemónicos) | Ensamblador (MOV, ADD, JMP) |
| **Medio nivel** | Cercano al hardware (punteros, memoria) y al humano | C |
| **Alto nivel** | Cercano al humano, estructurado, portable | [[entidades/python|Python]] |

## Programa fuente → ejecutable

- **Código fuente**: instrucciones escritas por el programador; no es directamente ejecutable.
- **Lenguajes compilados** (C, Pascal): el código fuente se traduce a **código objeto** y luego a **programa ejecutable** mediante un compilador, antes de la ejecución.
- **Lenguajes interpretados** (Python): no generan archivos intermedios; el intérprete traduce cada instrucción durante la ejecución.
- **Java**: caso híbrido — compila a *bytecode* portable, que la JVM interpreta/ejecuta en tiempo real ("escribe una vez, ejecuta en cualquier lugar").

| Característica | Intérprete | Compilador | Ensamblador |
|---|---|---|---|
| ¿Cuándo traduce? | Durante la ejecución | Antes de ejecutar | Antes de ejecutar |
| Resultado | No genera ejecutable | Genera ejecutable | Genera objeto/ejecutable |
| Velocidad | Más lenta | Más rápida | Muy rápida |
| Ejemplo | Python, JavaScript | C, Pascal | Assembly |

## Generaciones de lenguajes
1. **Lenguaje máquina**: código binario puro, el único que entiende el procesador directamente.
2. **Ensamblador (bajo nivel)**: mnemónicos que representan instrucciones máquina (p. ej. `MOV R5, R6`); requiere un programa **ensamblador** para traducirlo.
3. **Alto nivel**: independiente de la máquina, más cercano al lenguaje humano (FORTRAN, COBOL, Pascal, C, Java...).

### ¿Por qué no lenguaje natural?
Podría pensarse en programar directamente en un idioma como el castellano o el inglés, pero esto choca con dos problemas no resueltos en la práctica ([[fuentes/introduccion-a-la-programacion-con-python-3]]): el **análisis sintáctico** (la complejidad de las construcciones del lenguaje natural dificulta entender la estructura de una frase) y el **análisis semántico** (la ambigüedad del lenguaje natural admite varios significados posibles para una misma frase, p. ej. «Trabaja en un banco»). Los lenguajes de alto nivel son la solución intermedia: menos potentes que el lenguaje natural, pero sin la complejidad de un ensamblador.

### Por qué hay tantos lenguajes ("la torre de Babel")
Fortran (1950s, "FORmula TRANslator") fue el primer lenguaje de alto nivel, orientado a traducir fórmulas matemáticas. Le siguieron lenguajes de propósito específico (Cobol para gestión empresarial, Lisp para IA) y de propósito general (Algol 60). En los años 60, al hacerse más accesible la tecnología de compiladores, hubo una explosión: ya en 1969 existían unos 120 lenguajes de programación distintos, cada uno con su propio compilador o intérprete — una situación de fragmentación ("torre de Babel") que con los años se fue decantando hacia los lenguajes más adecuados para cada tipo de tarea.

## Proceso de compilación
`programa fuente → compilador → programa objeto → enlazador (linker) → programa ejecutable`

El programa ejecutable resultante ya no necesita el compilador para correr; solo se vuelve a compilar si cambia el código fuente. Un **intérprete**, en cambio, no genera programa objeto: traduce y ejecuta instrucción por instrucción en cada corrida (por eso es más lento, pero no requiere paso de compilación previo).

**Analogía con traductores de idiomas** ([[fuentes/introduccion-a-la-programacion-con-python-3]]): un compilador es como un traductor que recibe un libro completo en un idioma y produce un nuevo libro traducido; la traducción se hace una sola vez y el libro resultante se puede leer (ejecutar) cuantas veces se quiera. Un intérprete es como un intérprete simultáneo de una conferencia: traduce sobre la marcha, frase a frase, y debe repetir el proceso completo cada vez que se "ejecuta" la conferencia. Por esto los programas interpretados suelen ser entre 2 y 100 veces más lentos que su equivalente compilado — pero a cambio ofrecen mayor flexibilidad (por ejemplo, evaluar código dinámicamente). En la práctica, la mayoría de los lenguajes "interpretados" (Python, Java) en realidad se traducen primero a un lenguaje intermedio (bytecode) que es el que se interpreta.

## Paradigmas de programación

| Paradigma | Características | Lenguajes |
|-----------|-----------------|-----------|
| Procedimental (imperativo) | Secuencia de instrucciones y procedimientos | C, Pascal, COBOL, FORTRAN |
| Declarativo | Indica qué resultado se desea, no los pasos | Prolog |
| Orientado a objetos | Clases y objetos, encapsulamiento | Java, C++, C# |
| Funcional | Funciones matemáticas puras, sin estado mutable | Lisp, Haskell |

Python es **multiparadigma**: soporta imperativo, orientado a objetos y funcional. Detalle ampliado (definiciones, origen en TAD, línea histórica 1954-2000) en [[conceptos/paradigmas-de-programacion]].

## Referencias

- [[fuentes/pensamiento-computacional-mm]]
- [[fuentes/guia-estudio-algoritmia-mm]]
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[entidades/python]]
- [[entidades/java]]
- [[conceptos/algoritmo]]
- [[conceptos/paradigmas-de-programacion]]
- [[conceptos/organizacion-de-computadoras]]
