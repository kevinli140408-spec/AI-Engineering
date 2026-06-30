---
titulo: "Lenguajes de Programación"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [lenguajes-de-programacion, compiladores, paradigmas]
fuentes: [pensamiento-computacional-mm, guia-estudio-algoritmia-mm]
---

# Lenguajes de Programación

Conjunto de palabras, símbolos y reglas sintácticas mediante los cuales se indica a la computadora los pasos a seguir para resolver un problema (el [[conceptos/algoritmo]]).

## Niveles

| Nivel | Descripción | Ejemplo |
|-------|-------------|---------|
| **Máquina** | Código binario (0 y 1); el único que entiende directamente el procesador | `10110000 01100001` |
| **Bajo nivel** | Representación simbólica del lenguaje máquina (mnemónicos) | Ensamblador (MOV, ADD, JMP) |
| **Medio nivel** | Cercano al hardware (punteros, memoria) y al humano | C |
| **Alto nivel** | Cercano al humano, estructurado, portable | [[entidades/python\|Python]] |

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

## Paradigmas de programación

| Paradigma | Características | Lenguajes |
|-----------|-----------------|-----------|
| Procedimental (imperativo) | Secuencia de instrucciones y procedimientos | C, Pascal, COBOL, FORTRAN |
| Declarativo | Indica qué resultado se desea, no los pasos | Prolog |
| Orientado a objetos | Clases y objetos, encapsulamiento | Java, C++, C# |
| Funcional | Funciones matemáticas puras, sin estado mutable | Lisp, Haskell |

Python es **multiparadigma**: soporta imperativo, orientado a objetos y funcional.

## Referencias

- [[fuentes/pensamiento-computacional-mm]]
- [[fuentes/guia-estudio-algoritmia-mm]]
- [[entidades/python]]
- [[conceptos/algoritmo]]
