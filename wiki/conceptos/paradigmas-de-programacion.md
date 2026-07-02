---
titulo: "Paradigmas de Programación"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [paradigmas, programacion, poo, historia-lenguajes]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Paradigmas de Programación

Un **paradigma de programación** es un enfoque fundamental para construir soluciones de software; determina cómo se estructura un [[conceptos/algoritmo|algoritmo]] al expresarlo en un [[conceptos/lenguajes-de-programacion|lenguaje de programación]].

## Imperativo (procedimental)
Enfoque tradicional: una secuencia de instrucciones/órdenes que manipulan datos para producir resultados, ejecutadas una por una salvo saltos de control. Lenguajes: FORTRAN, COBOL, Pascal, BASIC, [[entidades/lenguaje-c|C]], Ada.

## Declarativo
El programador describe **qué** problema resolver, no **cómo** resolverlo paso a paso; se basa en lógica formal y cálculo de predicados de primer orden. Lenguaje por excelencia: Prolog.

## Orientado a objetos (POO)
Modela el problema como objetos que combinan datos y operaciones, por analogía con el mundo real. Sus tres propiedades clave: **encapsulamiento, herencia y polimorfismo**. Se origina en los Tipos Abstractos de Datos (TAD) — tema que retoma el libro en los capítulos 15-17 (pendientes de ingesta). Lenguajes: Smalltalk, [[entidades/lenguaje-c|C++]], Java, C#.

## Funcional
Basado en funciones matemáticas puras, sin estado mutable. Lenguajes: Lisp, Haskell.

## Línea histórica de lenguajes
| Década | Lenguajes |
|---|---|
| 1950s | FORTRAN (1954), ALGOL 58, LISP (1958), COBOL (1959) |
| 1960s | BASIC (1964), Simula 67, LOGO |
| 1970s | Pascal (1970), C (1971), Smalltalk (1969-72), Modula-2 |
| 1980s | Ada (1979), C++ (1983), Eiffel, Perl |
| 1990s | Java (1995/97) |
| 2000s | C# (2000) |

[[entidades/python|Python]] (1991) es **multiparadigma**: combina imperativo, orientado a objetos y funcional.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/lenguajes-de-programacion]]
- [[conceptos/algoritmo]]
- [[entidades/lenguaje-c]]
