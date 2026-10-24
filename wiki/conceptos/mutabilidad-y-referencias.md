---
titulo: "Mutabilidad, Referencias y el Operador is"
tipo: concepto
creado: 2026-07-01
actualizado: 2026-09-09
tags: [python, mutabilidad, referencias, memoria, listas]
fuentes: [introduccion-a-la-programacion-con-python-3, programacion1-listas2-thompson]
---

# Mutabilidad, Referencias y el Operador `is`

En Python, una variable no "contiene" directamente un valor: contiene una **referencia** (puntero) a una zona de memoria donde vive el valor. Esta distinción, invisible la mayor parte del tiempo, se vuelve crítica en cuanto se trabaja con listas ([[fuentes/introduccion-a-la-programacion-con-python-3]]).

## Objetos inmutables vs. mutables
- **Inmutables** (`int`, `float`, `bool`, `str`, tuplas): su valor no puede cambiar una vez creado. Python reutiliza en memoria un mismo valor inmutable para varias variables (`a = 2; b = 2` puede hacer que `a` y `b` apunten a la misma celda de memoria). "Modificar" una variable inmutable en realidad hace que su referencia apunte a una celda distinta con el nuevo valor — la celda original no cambia. Por eso `cadena[0] = 'x'` lanza `TypeError`: los índices de una cadena no se pueden reasignar.
- **Mutables** (`list`, y más adelante `dict`, objetos definidos por el usuario): su contenido puede modificarse in situ sin crear un objeto nuevo — `lista[0] = 10` cambia la celda de memoria existente.

## `==` vs. `is`
- `==` compara **valores**: dos listas son iguales si tienen la misma longitud y los mismos elementos en el mismo orden (comparación recursiva, elemento a elemento).
- `is` compara **identidad**: devuelve `True` solo si ambas variables apuntan exactamente a la **misma zona de memoria** (son el mismo objeto), no solo a valores equivalentes.

```python
a = [1, 2, 3]
b = [1, 2, 3]
c = a
a == b   # True (mismos valores)
a is b   # False (objetos distintos en memoria)
a is c   # True (c es una referencia al mismo objeto que a)
```

## La trampa clásica: aliasing al crear una matriz
Multiplicar una lista por un entero (`fila * n`) no copia los elementos internos si estos son a su vez mutables: crea `n` **referencias a la misma lista**. Es un error muy común al construir una matriz como "lista de listas":

```python
fila = [0] * 6
M = [fila] * 3     # ¡las 3 filas son la MISMA lista!
M[0][0] = 1
print(M)           # [[1,0,0,0,0,0], [1,0,0,0,0,0], [1,0,0,0,0,0]] — se modificaron las 3 filas
```

La forma correcta es asegurarse de que cada fila sea un objeto lista **distinto**, típicamente construyéndolas una a una dentro de un bucle:
```python
M = []
for _ in range(3):
    M.append([0] * 6)   # una lista nueva en cada iteración
```

## Copia superficial de listas (evitar el aliasing accidental)
Cuando el objetivo es tener una lista independiente (no solo una segunda referencia), existen varias formas equivalentes de obtener una **copia superficial** (shallow copy): rebanada completa (`lista1[:]`), la función `list(lista1)`, concatenar con una lista vacía (`lista1 + []`), o el método `lista1.copy()`. La función `id(objeto)` (equivalente a la dirección de memoria) permite verificar si dos variables comparten objeto: `id(lista1) == id(lista2)` es `True` solo si son la misma referencia.

## Relación con el paso de parámetros a funciones
Esta misma distinción explica por qué una función puede modificar una lista recibida como parámetro sin necesidad de un `return` (la función recibe una referencia al mismo objeto que existe fuera de ella), mientras que reasignar un parámetro de tipo `int`/`str` dentro de una función no afecta a la variable original — ver [[conceptos/funciones-programacion]] (paso por valor vs. por referencia).

## Objetos definidos por el usuario
El mismo fenómeno aplica a instancias de clases propias: `copia = original` copia solo la referencia, no crea un objeto independiente. Para copiar de verdad hace falta definir un método explícito que construya una instancia nueva copiando cada atributo — ver [[conceptos/programacion-orientada-a-objetos]].

## Referencias
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[fuentes/programacion1-listas2-thompson]]
- [[conceptos/listas-python]]
- [[conceptos/arrays-vectores-matrices]]
- [[conceptos/variable-programacion]]
- [[conceptos/funciones-programacion]]
- [[conceptos/programacion-orientada-a-objetos]]
