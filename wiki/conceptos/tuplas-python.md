---
titulo: "Tuplas en Python"
tipo: concepto
creado: 2026-09-09
actualizado: 2026-09-09
tags: [tuplas, tuple, python, estructuras-de-datos]
fuentes: [programacion1-tuplas-conjuntos-diccionarios-thompson]
---

# Tuplas en Python

Una **tupla** (`tuple`) es una secuencia similar a una [[conceptos/listas-python|lista]] (indexada desde 0, iterable, admite slicing), pero **inmutable**: una vez creada, no puede modificarse.

## Creación

```python
salsas = ("tártara", "criolla", "chimichurri")   # con paréntesis
salsas = "tártara", "criolla", "chimichurri"     # los paréntesis son opcionales
aderezos = ()                                     # tupla vacía
misalsa = "barbacoa",                             # tupla de un solo elemento: la coma es obligatoria
```

Sin la coma final, `misalsa = "barbacoa"` sería simplemente un string, no una tupla de un elemento.

## Inmutabilidad
Al igual que las cadenas, las tuplas carecen de `append`, `insert`, `remove`, `pop`, `sort` y de cualquier método que modifique *in situ*. Intentar asignar por subíndice (`t[0] = 4`) lanza `TypeError: 'tuple' object does not support item assignment`. Para "agregar" un elemento hay que crear una tupla nueva por concatenación: `aderezos = aderezos + ("mayonesa",)`. El operador de replicación `*` sí funciona: `(0, 1) * 3` → `(0, 1, 0, 1, 0, 1)`.

## Tipos mixtos y anidamiento
Una tupla puede combinar tipos de dato distintos y contener otras tuplas anidadas, accesibles con múltiples subíndices:

```python
alumno = (152408, "Luis Arce", "Lima 717", (1, "Mayo", 1998))
alumno[1]      # "Luis Arce"
alumno[3][1]   # "Mayo"
```

## Funciones, métodos y conversión
`len()`, `max()`, `min()`, `sum()`, el operador `in`, y los métodos `index()`/`count()` funcionan igual que en listas. `tuple(lista)` convierte una lista en tupla; `list(tupla)` hace la conversión inversa.

## Empaquetado, desempaquetado e intercambio de variables
Como con las listas, una tupla puede desempaquetarse en variables individuales (`d, m, a = leerfecha()` — ver [[conceptos/funciones-programacion]]). Esto permite el modismo clásico para **intercambiar el valor de dos variables sin usar una variable auxiliar**:

```python
a, b = b, a
```

Python evalúa primero el lado derecho como una tupla `(b, a)` y luego la desempaqueta en `a, b`.

## Cuándo usar tupla en vez de lista
Una tupla comunica intención: "esta secuencia de datos es fija y no debería cambiar" (una coordenada, un registro de fecha, una fila de datos heterogéneos). Además, al ser inmutable (y por lo tanto *hashable*), una tupla puede usarse como clave de [[conceptos/diccionarios-python|diccionario]] o como elemento de un [[conceptos/conjuntos-python|conjunto]] — algo que una lista no puede hacer.

## Referencias

- [[fuentes/programacion1-tuplas-conjuntos-diccionarios-thompson]]
- [[entidades/python]]
- [[conceptos/listas-python]]
- [[conceptos/diccionarios-python]]
- [[conceptos/conjuntos-python]]
