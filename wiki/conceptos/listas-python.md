---
titulo: "Listas en Python"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [listas, estructuras-de-datos, python]
fuentes: [taller-listas-mm, funciones-listas-mm, listas-python-mm]
---

# Listas en Python

Estructura de datos que permite guardar **varios valores en una sola variable**. Cada valor ocupa una posición (**subíndice**), que siempre comienza en **0**. Las listas son **ordenadas, mutables (modificables), iterables** y admiten elementos duplicados y de **tipos mixtos**.

## ¿Por qué estructuras de datos?
Cuando se necesitan guardar muchos valores (ej. notas de un curso), una variable por dato no alcanza. Python ofrece: `list` (listas), `tuple` (tuplas, inmutables), `set` (conjuntos), `dict` (diccionarios). Las listas son la más versátil para empezar.

## Operaciones básicas

```python
lista = []                      # lista vacía
lista = [3, 25, 18]              # lista con elementos
lista.append(20)                 # agregar al final
lista.insert(1, 15)              # insertar en posición
lista[2] = 25                    # modificar elemento
lista.pop(3)                     # eliminar por índice (y retorna el valor)
lista.remove(25)                 # eliminar por valor (primera aparición)
len(lista)                       # cantidad de elementos
```

## Acceso y slicing

```python
lista[0]            # primer elemento
lista[-1]            # último elemento (índice negativo)
lista[1:4]           # sublista del índice 1 al 3 (4 no incluido)
lista[:2]            # primeros 2 elementos
lista[2:]            # desde el índice 2 hasta el final
lista[::2]           # con paso 2
```

`IndexError: list index out of range` ocurre al acceder a un índice fuera de rango.

## Recorrido

```python
for i in range(len(lista)):     # por subíndice
    print(lista[i])

for valor in lista:              # por elemento
    print(valor)
```

## Métodos útiles
`append()`, `insert()`, `remove()`, `pop()`, `index()`, `count()`, `reverse()`, `copy()`, `clear()`.

## Verificar existencia
```python
if "Ana" in nombres:
    print("Ana está en la lista")
```

## Listas y funciones
Una función que recibe una lista por parámetro y la modifica (agrega, elimina, duplica valores) **no necesita retornarla**: la lista original se modifica directamente (ver [[conceptos/funciones-programacion]]).

## Listas paralelas
Dos o más listas relacionadas por el mismo subíndice (ej. `legajos[i]` corresponde a `notas[i]`). Útiles para representar registros relacionados sin usar diccionarios.

## Generar listas con `random`
```python
import random
lista = []
for i in range(5):
    lista.append(random.randint(10, 99))
```

## Listas y algoritmos
Las listas son la estructura base sobre la que operan los [[conceptos/algoritmos-busqueda|algoritmos de búsqueda]] y los [[conceptos/algoritmos-ordenamiento|algoritmos de ordenamiento]].

## Referencias

- [[fuentes/taller-listas-mm]]
- [[fuentes/funciones-listas-mm]]
- [[fuentes/listas-python-mm]]
- [[conceptos/funciones-programacion]]
- [[conceptos/algoritmos-busqueda]]
- [[conceptos/algoritmos-ordenamiento]]
