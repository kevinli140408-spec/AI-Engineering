---
titulo: "Estructura de Control Condicional"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [estructuras-de-control, condicional, python, operadores-logicos]
fuentes: [algoritmos-secuenciales-mm, clase-control-flujo-ciclos-mm, guia-estudio-algoritmia-mm]
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

## Referencias

- [[fuentes/algoritmos-secuenciales-mm]]
- [[fuentes/clase-control-flujo-ciclos-mm]]
- [[fuentes/guia-estudio-algoritmia-mm]]
- [[conceptos/estructura-secuencial]]
- [[conceptos/estructura-iterativa]]
