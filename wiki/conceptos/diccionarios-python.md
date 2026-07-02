---
titulo: "Diccionarios en Python"
tipo: concepto
creado: 2026-07-01
actualizado: 2026-07-01
tags: [diccionarios, dict, estructuras-de-datos, python]
fuentes: [introduccion-a-la-programacion-con-python-3]
---

# Diccionarios en Python

Estructura de datos que asocia **claves** con **valores** — una correspondencia, igual que un diccionario de idioma pone en correspondencia palabras con definiciones ([[fuentes/introduccion-a-la-programacion-con-python-3]]). A diferencia de una [[conceptos/listas-python|lista]], el índice ("clave") no tiene que ser un entero consecutivo: puede ser cualquier valor **inmutable** (cadena, entero, flotante, tupla).

## Operaciones básicas
```python
d = {}                          # diccionario vacío
listin = {'Ana': '555-1234', 'Luis': '555-5678'}

listin['Ana']                   # consulta → '555-1234'
listin['Eva'] = '555-9999'      # inserta/actualiza una clave
'Ana' in listin                 # True — comprobar existencia antes de acceder
del listin['Luis']              # borra una clave
```
Acceder a una clave que no existe lanza `KeyError` — por eso conviene comprobar `clave in diccionario` antes de leer una clave "dudosa" (o usar `dict.get(clave, valor_por_defecto)`).

## Recorrido
`for clave in diccionario:` recorre las claves (no hay orden garantizado — un diccionario es, conceptualmente, un **conjunto desordenado** de pares clave-valor). A partir de cada clave se accede al valor con `diccionario[clave]`. El método `.keys()` devuelve un generador de claves (equivalente conceptual a `range` para listas); `list(diccionario.keys())` lo materializa como lista.

## Patrón común: valores acumulativos
Para modelar "una clave puede tener varios valores asociados" (p. ej. una persona con varios teléfonos), el valor de cada clave es a su vez una lista, y hay que comprobar si la clave ya existe antes de decidir si crearla o añadir a la lista existente:
```python
def añadir(listin, nombre, telefono):
    if nombre in listin:
        if telefono not in listin[nombre]:
            listin[nombre].append(telefono)
    else:
        listin[nombre] = [telefono]
```

## Cuándo usar diccionario vs. lista
Lista: colección ordenada indexada por posición (0, 1, 2, ...). Diccionario: colección indexada por una clave con significado propio (nombre, código, palabra) — mucho más natural cuando la relación entre datos no es "el n-ésimo elemento" sino "el elemento asociado a X". Ver también [[conceptos/estructuras-registros]] para el equivalente conceptual en pseudocódigo algorítmico (registro/struct con campos con nombre, aunque un registro tiene un conjunto fijo de campos y un diccionario admite claves arbitrarias en tiempo de ejecución).

## Referencias
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[conceptos/listas-python]]
- [[conceptos/mutabilidad-y-referencias]]
- [[conceptos/estructuras-registros]]
- [[conceptos/conjuntos-python]]
