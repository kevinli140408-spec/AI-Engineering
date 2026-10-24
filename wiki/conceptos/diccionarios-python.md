---
titulo: "Diccionarios en Python"
tipo: concepto
creado: 2026-07-01
actualizado: 2026-09-09
tags: [diccionarios, dict, estructuras-de-datos, python]
fuentes: [introduccion-a-la-programacion-con-python-3, programacion1-tuplas-conjuntos-diccionarios-thompson]
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

## Diccionario por comprensión
Igual que las [[conceptos/listas-python|listas por comprensión]], pero con llaves y una expresión `clave:valor`: `{x: x**2 for x in range(1, 5)}` → `{1: 1, 2: 4, 3: 9, 4: 16}`.

## No son secuencias
Los diccionarios no están ordenados como una lista (no hay "posición 0"), por lo que no admiten slicing. Las claves deben ser únicas: asignar a una clave existente **reemplaza** su valor; asignar a una clave nueva la **crea**. Los valores pueden repetirse entre distintas claves, y pueden ser de cualquier tipo (incluidas listas u otros diccionarios); las claves, en cambio, deben ser de un tipo inmutable (número, cadena, tupla) — igual que los elementos de un [[conceptos/conjuntos-python|conjunto]].

## Métodos más usados
| Método | Función |
|---|---|
| `.get(clave, default)` | Como acceder por `[clave]`, pero devuelve `default` (u opcionalmente `None`) en vez de lanzar `KeyError` si no existe |
| `.pop(clave, default)` | Elimina `clave` y devuelve su valor; devuelve `default` si no existe (sin ese segundo argumento, lanza error) |
| `.keys()` | Secuencia de claves (se materializa con `list()`) |
| `.values()` | Secuencia de valores |
| `.items()` | Secuencia de tuplas `(clave, valor)` — ideal para `for clave, valor in d.items():` |
| `dict.fromkeys(secuencia, valor)` | Crea un diccionario nuevo a partir de cualquier iterable: cada elemento se vuelve una clave, todas con el mismo `valor` (por defecto `None`). Se invoca sobre la clase `dict`, no sobre una variable |

## El patrón "pythonizado" de conteo
Contar ocurrencias de cada palabra en una frase se resuelve típicamente comprobando la clave antes de incrementar (`if palabra not in dic: dic[palabra] = 1 else: dic[palabra] += 1`), pero `dict.get()` con valor por defecto simplifica esto a una sola línea:

```python
dic = {}
for palabra in palabras:
    dic[palabra] = dic.get(palabra, 0) + 1
```

## Aplicaciones típicas
Agenda telefónica, control de stock, usuarios y contraseñas, listas de precios — cualquier caso donde el acceso natural a un dato es "por nombre/código", no "por posición".

## Cuándo usar diccionario vs. lista
Lista: colección ordenada indexada por posición (0, 1, 2, ...). Diccionario: colección indexada por una clave con significado propio (nombre, código, palabra) — mucho más natural cuando la relación entre datos no es "el n-ésimo elemento" sino "el elemento asociado a X". Ver también [[conceptos/estructuras-registros]] para el equivalente conceptual en pseudocódigo algorítmico (registro/struct con campos con nombre, aunque un registro tiene un conjunto fijo de campos y un diccionario admite claves arbitrarias en tiempo de ejecución).

## Referencias
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[fuentes/programacion1-tuplas-conjuntos-diccionarios-thompson]]
- [[conceptos/listas-python]]
- [[conceptos/mutabilidad-y-referencias]]
- [[conceptos/estructuras-registros]]
- [[conceptos/conjuntos-python]]
- [[conceptos/tuplas-python]]
- [[conceptos/json]]
