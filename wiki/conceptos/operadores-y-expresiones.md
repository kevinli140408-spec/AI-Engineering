---
titulo: "Operadores y Expresiones"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-07-01
tags: [operadores, expresiones, tipos-de-datos, precedencia]
fuentes: [joyanes-aguilar-fundamentos-de-programacion, introduccion-a-la-programacion-con-python-3]
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

## Precedencia y asociatividad de operadores en Python
Python define árboles sintácticos (operadores como nodos internos, operandos como hojas) para determinar el orden real de evaluación de una expresión — la evaluación "fluye" de las hojas hacia la raíz. Tabla completa de precedencia (1 = mayor prioridad), según [[fuentes/introduccion-a-la-programacion-con-python-3]]:

| Nivel | Operador | Aridad | Asociatividad |
|---|---|---|---|
| 1 | `**` (potencia) | Binario | Por la derecha |
| 2 | `+x` (identidad), `-x` (cambio de signo) | Unario | — |
| 3 | `* / // %` | Binario | Por la izquierda |
| 4 | `+ -` | Binario | Por la izquierda |
| 5 | `== != < <= > >=` | Binario | — (ver comparadores encadenados) |
| 6 | `not` | Unario | — |
| 7 | `and` | Binario | Por la izquierda |
| 8 | `or` | Binario | Por la izquierda |

Nota: `**` es asociativa **por la derecha** (`2**3**2` = `2**(3**2)` = 512, no `(2**3)**2` = 64), a diferencia de la mayoría de los demás operadores binarios, que son por la izquierda.

### La rareza de los comparadores encadenados
A diferencia de C/C++ (donde `2 < 3 < 4` se evalúa como `(2 < 3) < 4` → `1 < 4` → verdadero, un resultado que puede ser ilógico) y de Pascal (que directamente prohíbe encadenar comparadores por error de tipos), Python trata una cadena de comparadores como una conjunción implícita: `2 < 3 < 4` equivale a `2 < 3 and 3 < 4`. Esto permite expresar condiciones complejas de forma compacta y coincide con la lectura matemática habitual, pero también admite construcciones más extrañas como `2 < 3 > 1`.

### Operadores a nivel de bits
Para manipular directamente las secuencias de bits que codifican los enteros (ver [[conceptos/representacion-de-la-informacion]]): `&` (y bit a bit), `|` (o bit a bit), `^` (o exclusiva bit a bit), `~` (inversión de bits, unario), `<<`/`>>` (desplazamiento de bits a izquierda/derecha). Todos tienen su forma compacta con asignación (`&=`, `|=`, etc.), igual que los operadores aritméticos (`+=`, `-=`, `*=`, `/=`, `//=`, `%=`, `**=`).

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[conceptos/variable-programacion]]
- [[conceptos/algoritmo]]
- [[conceptos/representacion-de-la-informacion]]
