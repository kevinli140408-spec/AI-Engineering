---
titulo: "Estructura de Control Condicional"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [estructuras-de-control, condicional, python, operadores-logicos]
fuentes: [algoritmos-secuenciales-mm, control-flujo-ciclos-mm, guia-estudio-algoritmia-mm, joyanes-aguilar-fundamentos-de-programacion]
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

## Variantes en pseudocódigo algorítmico (Joyanes Aguilar)
- **Alternativa simple** (`si-entonces`/`if-then`): ejecuta una acción solo si la condición es verdadera; si es falsa, no hace nada (equivale a un `if` de Python sin `else`).
- **Alternativa doble** (`si-entonces-si_no`/`if-then-else`): equivale al `if/else` de Python.
- **Alternativa múltiple** (`según_sea`/`switch`-`case`): evalúa una expresión que puede tomar *n* valores discretos y ejecuta la acción asociada a cada caso, con una rama `otros`/`default` opcional — más legible que encadenar muchos `si` cuando hay más de 2-3 alternativas. Python no tiene `switch` nativo; se simula con `elif` encadenados (o `match-case` desde Python 3.10).
- **Estructuras anidadas (en escalera)**: un `si` dentro de otro `si`, tantas veces como sea necesario — equivalente a los `elif` encadenados de Python, pero requiere indentación explícita y cierre (`fin_si`) por cada nivel.
- **La sentencia `ir_a` (`goto`)**: bifurcación incondicional a una etiqueta. Históricamente controvertida (criticada por [[conceptos/algoritmo-de-dijkstra|Dijkstra]]); los lenguajes estructurados modernos la evitan casi por completo — Python ni siquiera la implementa.

## Referencias

- [[fuentes/algoritmos-secuenciales-mm]]
- [[fuentes/control-flujo-ciclos-mm]]
- [[fuentes/guia-estudio-algoritmia-mm]]
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/estructura-secuencial]]
- [[conceptos/estructura-iterativa]]
- [[conceptos/algoritmo-de-dijkstra]]
