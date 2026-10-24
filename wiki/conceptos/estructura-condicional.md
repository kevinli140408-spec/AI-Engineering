---
titulo: "Estructura de Control Condicional"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-09-09
tags: [estructuras-de-control, condicional, python, operadores-logicos, match-case]
fuentes: [algoritmos-secuenciales-mm, control-flujo-ciclos-mm, guia-estudio-algoritmia-mm, joyanes-aguilar-fundamentos-de-programacion, introduccion-a-la-programacion-con-python-3, programacion1-introduccion-thompson]
---

# Estructura de Control Condicional

Verifica una **condición lógica** antes de decidir qué secuencia de acciones ejecutar: "Si la condición se cumple, ejecuta el bloque verdadero; sino, ejecuta el bloque falso."

## Condición lógica
Expresión que al evaluarse da **verdadero o falso**, construida con operadores relacionales que comparan dos datos.

| Operador | Descripción |
|----------|-------------|
| `<` `<=` `>` `>=` | Menor, menor-igual, mayor, mayor-igual |
| `==` | Igual |
| `!=` | Distinto |

## Sintaxis en Python

```python
if numA > 4:
    print("mayor a 4")
elif numA < 4:
    print("menor a 4")
else:
    print("es igual a 4")
```

El bloque `else` **no es obligatorio**. La indentación delimita los bloques (no hay llaves ni palabras `begin/end`).

## Operadores lógicos (condiciones compuestas)

| Operador | Regla | Resultado V solo cuando... |
|----------|-------|------------------------------|
| `and` | Ambas condiciones deben ser V | Todas las condiciones unidas son V |
| `or` | Al menos una condición debe ser V | Al menos una condición es V |

### Tabla de verdad `and`
| A | B | A and B |
|---|---|---------|
| V | V | V |
| V | F | F |
| F | V | F |
| F | F | F |

### Tabla de verdad `or`
| A | B | A or B |
|---|---|--------|
| V | V | V |
| V | F | V |
| F | V | V |
| F | F | F |

## Comparación triple
Python permite encadenar comparaciones: `1 <= nota <= 10` equivale a `nota >= 1 and nota <= 10`.

## Operador condicional (ternario)
Permite elegir entre dos valores en una sola expresión, sin escribir un bloque `if/else` completo:

```python
<var> = <valor1> if <condición> else <valor2>
a = b if b >= 0 else -b   # valor absoluto de b
```

## Instrucción `match`-`case` (Python 3.10+)
Desde la versión 3.10 (4 de octubre de 2021), Python incorpora `match`-`case`, similar al `switch`-`case` de C, C++, C# o Java. En algunos casos reemplaza al `if`-`elif`-`else`, aportando mayor claridad — es el equivalente directo de la **alternativa múltiple** (`según_sea`/`switch`) descrita más abajo en pseudocódigo algorítmico.

```python
match <variable>:
    case <valor1>:
        ...
    case <valor2>:
        ...
    case _:
        ...
```

El contenido de `<variable>` se compara contra cada `case` en orden, buscando una coincidencia; `case _:` es el caso por defecto (opcional), equivalente al `otros`/`default` del pseudocódigo.

- El pipe `|` funciona como `or` dentro de un `case`: `case 1 | 2 | 3:` coincide con cualquiera de esos valores.
- Agregar una cláusula `if` a un `case` funciona como `and` (un *guard*): `case 4 | 5 if deuda == 1:` solo coincide si además se cumple la condición.

```python
match nota:
    case 1 | 2 | 3:
        print("Aplazado")
    case 4 | 5 | 6 | 7 | 8 | 9 | 10 if deuda == 1:
        print("Aprobado")
    case 4 | 5 | 6 | 7 | 8 | 9 | 10 if deuda == 2:
        print("Aprobación pendiente por deuda")
    case _:
        print("Nota inválida")
```

## Variantes en pseudocódigo algorítmico (Joyanes Aguilar)
- **Alternativa simple** (`si-entonces`/`if-then`): ejecuta una acción solo si la condición es verdadera; si es falsa, no hace nada (equivale a un `if` de Python sin `else`).
- **Alternativa doble** (`si-entonces-si_no`/`if-then-else`): equivale al `if/else` de Python.
- **Alternativa múltiple** (`según_sea`/`switch`-`case`): evalúa una expresión que puede tomar *n* valores discretos y ejecuta la acción asociada a cada caso, con una rama `otros`/`default` opcional — más legible que encadenar muchos `si` cuando hay más de 2-3 alternativas. Python no tiene `switch` nativo; se simula con `elif` encadenados (o `match-case` desde Python 3.10).
- **Estructuras anidadas (en escalera)**: un `si` dentro de otro `si`, tantas veces como sea necesario — equivalente a los `elif` encadenados de Python, pero requiere indentación explícita y cierre (`fin_si`) por cada nivel.
- **La sentencia `ir_a` (`goto`)**: bifurcación incondicional a una etiqueta. Históricamente controvertida (criticada por [[conceptos/algoritmo-de-dijkstra|Dijkstra]]); los lenguajes estructurados modernos la evitan casi por completo — Python ni siquiera la implementa.

## Evaluación con cortocircuito (short-circuit)
Python evalúa expresiones lógicas solo hasta donde hace falta para conocer el resultado ([[fuentes/introduccion-a-la-programacion-con-python-3]]): en `a or b`, si `a` es `True`, `b` ni siquiera se evalúa (el resultado ya es `True`); en `a and b`, si `a` es `False`, `b` no se evalúa. Esto permite un patrón muy común para evitar errores: `if a != 0 and 1/a > 1:` nunca provoca división por cero, porque si `a == 0` la primera condición ya es falsa y Python no llega a evaluar `1/a`.

### Negaciones y leyes de De Morgan
Las negaciones combinadas con `and`/`or` son una fuente frecuente de errores para quienes empiezan a programar. La negación de `a and b` **no** es `not a and not b`, sino `not a or not b` (y viceversa) — ver la formalización completa en [[conceptos/metodo-demostrativo]] (leyes de De Morgan, abreviadas `DM`).

## Referencias

- [[fuentes/algoritmos-secuenciales-mm]]
- [[fuentes/control-flujo-ciclos-mm]]
- [[fuentes/guia-estudio-algoritmia-mm]]
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[fuentes/programacion1-introduccion-thompson]]
- [[conceptos/estructura-secuencial]]
- [[conceptos/estructura-iterativa]]
- [[conceptos/algoritmo-de-dijkstra]]
- [[conceptos/metodo-demostrativo]]
