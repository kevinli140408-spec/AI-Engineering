---
titulo: "Listas en Python"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-09-09
tags: [listas, estructuras-de-datos, python]
fuentes: [taller-listas-mm, funciones-listas-mm, listas-python-mm, introduccion-a-la-programacion-con-python-3, programacion1-listas1-thompson, programacion1-listas2-thompson]
---

# Listas en Python

Estructura de datos que permite guardar **varios valores en una sola variable**. Cada valor ocupa una posición (**subíndice**), que siempre comienza en **0**. Las listas son **ordenadas, mutables (modificables), iterables** y admiten elementos duplicados y de **tipos mixtos**.

## ¿Por qué estructuras de datos?
Cuando se necesitan guardar muchos valores (ej. notas de un curso), una variable por dato no alcanza. Python ofrece: `list` (listas), `tuple` (tuplas, inmutables), `set` (conjuntos — ver [[conceptos/conjuntos-python]]), `dict` (diccionarios — ver [[conceptos/diccionarios-python]]). Las listas son la más versátil para empezar.

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

### Rebanadas (slicing) en detalle
Una rebanada usa hasta tres subíndices separados por `:` (`inicio:fin:incremento`); dejar `inicio` o `fin` en blanco toma el extremo correspondiente de la lista. El tercer valor es el incremento entre elementos tomados, y puede ser **negativo** (recorre en reversa): `original[::-1]` invierte la lista sin modificar la original. Una rebanada con el mismo subíndice de inicio y fin (`lista[2:2]`) es una **rebanada nula** (vacía) — asignarle una lista la **inserta** en esa posición: `lista[2:2] = ['X', 'Y']`.

### Comparación de listas
Dos listas se comparan con `==`, `<`, `>`, etc. elemento a elemento (orden lexicográfico, igual que las [[conceptos/cadenas-de-caracteres|cadenas]]): `[2, 3] > [1, 4]` es `True` porque el primer elemento ya decide (`2 > 1`); `[2, 4, 6] > [2, 4]` es `True` porque, empatados en el prefijo común, la lista más larga es mayor.

### Copia de listas: por qué `lista2 = lista1` no alcanza
Asignar una lista a otra variable (`lista2 = lista1`) solo copia la **referencia** — ambas variables apuntan al mismo objeto en memoria (verificable con `id(objeto)`), por lo que modificar una a través de sus métodos modifica también la otra. Formas de obtener una copia independiente (shallow copy): rebanada completa (`lista1[:]`), `list(lista1)`, concatenación con una lista vacía (`lista1 + []`), o el método `lista1.copy()`. Desarrollo completo del porqué (mutabilidad y referencias compartidas) en [[conceptos/mutabilidad-y-referencias]].

### `for` con `enumerate()`
`for valor in lista:` recorre los **valores** directamente, sin necesidad de `range(len(lista))`. Cuando además se necesita el subíndice, `enumerate(lista)` devuelve pares `(subíndice, elemento)` —una **tupla**— que se desempaquetan en dos variables: `for i, valor in enumerate(lista):`.

## Recorrido

```python
for i in range(len(lista)):     # por subíndice
    print(lista[i])

for valor in lista:              # por elemento
    print(valor)
```

## Métodos útiles
`append()`, `insert()`, `remove()`, `pop()`, `index()`, `count()`, `reverse()`, `copy()`, `clear()`.

### Detalle de métodos adicionales
| Método | Función |
|---|---|
| `extend(iterable)` | Agrega **varios** elementos al final (de cualquier iterable: otra lista, un `range`, etc.) — a diferencia de `append`, que agrega un solo elemento |
| `index(elem, inicio, fin)` | Además del elemento, admite acotar el rango de búsqueda (el `fin` no se incluye) |
| `count(elem)` | Cantidad de repeticiones de un elemento; devuelve `0` si no está |
| `clear()` | Vacía la lista *in situ* (sin crear una lista nueva) |
| `reverse()` | Invierte el orden *in situ* |
| `sort(reverse=True)` | Ordena *in situ*; `reverse=True` invierte el criterio (mayor a menor) |

### Empaquetado y desempaquetado
**Empaquetar**: asignar un conjunto de variables/constantes a una lista (`numeros = [n1, n2, n3]`). **Desempaquetar**: asignar los elementos de una lista a un conjunto de variables en una sola línea (`d1, d2, d3 = dias`) — la cantidad de variables debe coincidir con la cantidad de elementos.

### Concatenación y replicación
`lista1 + lista2` concatena dos listas en una nueva; `lista * n` la replica `n` veces (`[0] * 5` → `[0, 0, 0, 0, 0]`, un modismo común para inicializar una lista de tamaño fijo).

### Funciones sobre listas (no métodos)
`len(lista)`, `sum(lista)` (solo numéricas), `max(lista)`/`min(lista)` (también aceptan varios argumentos sueltos: `max(4, 1, 7, 2)`), y `list(iterable)` (convierte cualquier iterable — `range`, string, tupla, conjunto — en una lista nueva).

### El método `sort()` y la función `sorted()`
`sort()` ordena la lista *in situ*; `sorted(iterable)` es una función (no un método) que acepta **cualquier** iterable y siempre devuelve una **lista nueva** ordenada, dejando el original intacto. Ambos aceptan `reverse=True` y el parámetro `key`:

```python
nombres = ["Andrés", "Ariel", "Juan"]
nombres.sort(key=lambda x: x[-1])   # ordena por última letra
numeros.sort(key=abs)               # con una función incorporada, sin lambda
numeros.sort(key=lambda x: [x % 2, x])  # ordenar por más de un criterio: par/impar, luego valor
```

Python garantiza **estabilidad**: ante claves iguales, conserva el orden relativo original.

## Módulo `random` aplicado a listas
Además de `random.randint()` (más arriba), el módulo ofrece:

| Función | Función |
|---|---|
| `random.random()` | Real al azar en `[0, 1)` |
| `random.choice(secuencia)` | Un elemento al azar de cualquier secuencia (lista, string, tupla, rango) |
| `random.shuffle(lista)` | Mezcla *in situ* el orden de los elementos |

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

## Funciones de orden superior: `map` y `filter`
Ambas reciben una función y un iterable, y devuelven un objeto perezoso que se materializa envolviéndolo con `list()`:

- `map(función, lista)`: aplica la función a **cada** elemento, devolviendo el resultado de aplicarla. `raices = list(map(lambda x: x**(1/2), numeros))` equivale a un `for` que hace `raices.append(x**(1/2))` por cada elemento.
- `filter(función, lista)`: conserva solo los elementos para los que la función devuelve `True`. `impares = list(filter(lambda x: x % 2 != 0, numeros))`.

Las funciones lambda son ideales como argumento de `map`/`filter`, aunque también pueden usarse funciones definidas con `def`.

## Listas por comprensión
Sintaxis matemática (heredada de la notación de conjuntos) para construir una lista en una sola línea: `[<expr> for <elem> in <secuencia>]`, opcionalmente con un `if` final para filtrar:

```python
cuadrados = [x**2 for x in range(6)]                      # [0, 1, 4, 9, 16, 25]
cubospares = [i**3 for i in range(11) if i**3 % 2 == 0]    # solo donde la condición es verdadera
```

En muchos casos una comprensión reemplaza con menos código a un `map`/`filter` equivalente.

## Instrucción `pass`
No hace nada; se usa como marcador de posición sintáctico en un bloque que Python exige que no esté vacío (una función aún no implementada, una rama de `if` deliberadamente vacía). Su abuso (usarlo para "no hacer nada" en una rama que sí debería tener lógica, en vez de resolver el problema con la condición correcta) se considera mala práctica.

## Matrices como lista de listas
Python no tiene un tipo nativo de matriz: se simula con una **lista de listas**, indexada `matriz[fila][columna]` (ambos desde 0). Formas de crearla (todas producen una matriz de 3×4 llena de ceros):

```python
matriz = [[0,0,0,0], [0,0,0,0], [0,0,0,0]]                          # 1: estática, literal

matriz = []                                                          # 2: dinámica, con bucles anidados
for f in range(filas):
    fila = []
    for c in range(columnas):
        fila.append(0)
    matriz.append(fila)

matriz = []                                                          # 3: usando replicación (* crea una lista NUEVA en cada vuelta del for)
for f in range(filas):
    matriz.append([0] * columnas)

matriz = [[0] * columnas for i in range(filas)]                      # 4: replicación + comprensión
matriz = [[0 for c in range(columnas)] for f in range(filas)]         # 5: comprensión anidada
```

Nota: las alternativas 3-5 son seguras porque `[0] * columnas` construye una lista **nueva** en cada iteración del `for` — no confundir con el error clásico `[[0]*columnas]*filas`, que sí crea referencias repetidas a la misma fila (ver [[conceptos/mutabilidad-y-referencias]]).

Recorrido típico con doble `for` anidado (filas en el externo, columnas en el interno), autodetectando el tamaño con `len(matriz)` (filas) y `len(matriz[0])` (columnas); también puede recorrerse sin subíndices con `for fila in matriz: for elemento in fila:`, útil solo para lectura (no permite modificar in situ).

## Contraste: listas dinámicas vs. arrays estáticos
La lista de Python es **dinámica** (crece/encoge en tiempo de ejecución con `append`/`insert`/`pop`/`remove`) e indexada desde 0. En pseudocódigo algorítmico clásico (lenguaje C, Pascal, etc.) la estructura equivalente es el **array**, que es de tamaño **fijo**, requiere desplazar elementos manualmente para insertar/borrar, y puede tener límites de índice arbitrarios (no necesariamente desde 0) — ver [[conceptos/arrays-vectores-matrices]].

## Comparación, identidad y mutabilidad
`==` compara listas elemento a elemento (igualdad de **valor**); `is` comprueba si dos variables apuntan al mismo objeto en memoria (igualdad de **identidad**) — dos listas pueden ser `==` sin ser `is`. Las listas son **mutables**: dos variables pueden referenciar la misma lista, y modificarla a través de una de ellas afecta a la otra (a diferencia de los tipos inmutables como `int` o `str`). Desarrollo completo, con el caso clásico del error al construir una matriz como "lista de listas", en [[conceptos/mutabilidad-y-referencias]].

## Referencias

- [[fuentes/taller-listas-mm]]
- [[fuentes/funciones-listas-mm]]
- [[fuentes/listas-python-mm]]
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[fuentes/programacion1-listas1-thompson]]
- [[fuentes/programacion1-listas2-thompson]]
- [[conceptos/funciones-programacion]]
- [[conceptos/algoritmos-busqueda]]
- [[conceptos/algoritmos-ordenamiento]]
- [[conceptos/arrays-vectores-matrices]]
- [[conceptos/mutabilidad-y-referencias]]
