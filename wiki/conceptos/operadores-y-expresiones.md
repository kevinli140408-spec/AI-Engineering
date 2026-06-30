---
titulo: "Operadores y Expresiones"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [operadores, expresiones, tipos-de-datos, precedencia]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Operadores y Expresiones

Una **expresión** combina constantes, [[conceptos/variable-programacion|variables]], operadores y funciones para producir un valor. Según el tipo de resultado, se clasifican en aritméticas, relacionales, lógicas y de carácter.

## Tipos de datos básicos (pseudocódigo algorítmico)
| Tipo | Descripción | Ejemplo |
|---|---|---|
| Entero | Subconjunto finito de los números enteros, sin parte decimal | `-15`, `1340` |
| Real | Números con parte decimal, en notación de coma flotante | `3.7452` |
| Lógico (booleano) | Solo `verdadero`/`falso` | — |
| Carácter / cadena | Un carácter o una sucesión delimitada por apóstrofos | `'A'`, `'Hola Mortimer'` |

Una **constante** no cambia durante la ejecución; una **variable**, sí — ver [[conceptos/variable-programacion]] para la versión en Python de estos conceptos.

## Operadores aritméticos
`+ - * / ^` (potencia), `div`/`mod` (división entera y resto). Ejemplo: `19 div 6 = 3`, `19 mod 6 = 1`.

## Operadores relacionales
`< > = <= >= <>` — comparan dos expresiones y devuelven un valor lógico.

## Operadores lógicos
`no`/`!` (negación), `y`/`&&` (conjunción), `o`/`||` (disyunción) — se evalúan con tablas de verdad.

## Precedencia de operadores
| Prioridad | Pascal | C/C++/Java/C# |
|---|---|---|
| Más alta | `no` | `++`, `--`, `!` |
| ↓ | `*, /, div, mod, y` | `*, /, %` |
| ↓ | `+, -, o` | `+, -` |
| Más baja | `<, >, =, <=, >=, <>` | comparación → `&&` → `\|\|` → asignación |

Los paréntesis siempre tienen prioridad máxima. Operadores de igual prioridad se evalúan de izquierda a derecha (asociatividad).

## Funciones internas
Operaciones predefinidas del lenguaje: `raiz2`/`sqrt` (raíz cuadrada), `cuadrado`/`sqr`, `abs`, `trunc`, `redondeo`/`round`, `seno`/`sin`, `cos`, `ln`, `log10`, `exp`.

## Asignación
`variable ← expresión` (en C/C++/Java/C#: `=`). Es **destructiva**: el valor anterior se pierde. Existen formas múltiples (`a += 8` equivale a `a ← a + 8`) y la conversión de tipo falla si los tipos son incompatibles (p. ej. asignar texto a una variable numérica).

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/variable-programacion]]
- [[conceptos/algoritmo]]
