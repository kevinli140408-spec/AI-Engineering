---
titulo: "Guía de Estudio — Parcial de Programación I, Clases 1-6 (Thompson)"
tipo: analisis
creado: 2026-09-16
actualizado: 2026-09-16
tags: [python, programacion, guia-de-estudio, parcial, listas, cadenas, funciones]
fuentes: [programacion1-introduccion-thompson, programacion1-funciones-thompson, programacion1-listas1-thompson, programacion1-listas2-thompson, programacion1-cadenas1-thompson, programacion1-cadenas2-thompson]
---

# Guía de Estudio — Programación I (Thompson), Clases 1 a 6

> **Alcance**: Clase 1 (Introducción) → Clase 6 (Cadenas 2ª parte). **No incluye** expresiones regulares (6b) ni temas posteriores. Documento autocontenido de estudio; consolida las páginas de conceptos de la wiki (excepción deliberada al límite de 500 palabras).
> **Reglas de oro de la cátedra**: una función = una tarea · nunca salir de una función desde dentro de un ciclo · el ciclo infinito es error grave · los nombres de funciones van en verbo infinitivo.

---

## Bloque 1 — Introducción a Python ([[conceptos/variable-programacion]], [[conceptos/lenguajes-de-programacion]])

**Python**: lenguaje de alto nivel, **interpretado** (línea por línea, vs. compilación: fuente → compilador → objeto → enlazador → ejecutable), multiparadigma, portable y **case-sensitive**. Comentarios con `#`.

### Variables

- Nombre + tipo + dirección de memoria RAM (volátil). **Tipado dinámico**: el tipo se deduce al asignar.
- Reglas de nombres: letras, dígitos y `_`; no empezar con número; no usar palabras reservadas; evitar `l`, `O`, `I` solas.
- Tipos: `int`, `float`, `str`, `bool` (`True`/`False`), `None`. Conversión: `int()`, `float()`, `str()`.
- **`input()` siempre devuelve string** → convertir: `edad = int(input("Edad: "))`.
- La asignación **no es una ecuación**: `x = x + 1` evalúa primero la derecha con el valor actual y sobrescribe. `=` asigna; `==` compara.
- Asignación múltiple y extendida: `a, b = 1, 2` · `+=`, `-=`, `*=`, etc.
- Constantes: por convención en MAYÚSCULAS.

### Formato con `%` (estilo antiguo)

```python
print("Cantidad: %6d" % cant)     # ancho 6, alinea a la derecha
print("Precio: %7.2f" % precio)   # ancho 7, 2 decimales
print("%04d" % 3)                 # 0003 (relleno con ceros)
print("X = %4d Y = %4d" % (x, y)) # varias variables entre paréntesis
```

`%d` entero · `%f` real · `%s` cadena (admite ancho: `"%10s"`). Primer número = ancho total; tras el punto = decimales; `0` inicial = relleno con ceros.

### Operadores aritméticos (orden de evaluación)

1. Potenciación `**` → 2. Menos unario `-x` → 3. `*` `/` `//` `%` → 4. `+` `-`

### Condicional ([[conceptos/estructura-condicional]])

```python
if numA > 4:      print("mayor")
elif numA < 4:    print("menor")
else:             print("igual")
```

- Relacionales: `< <= > >= == !=` · Lógicos: `and` (todas V), `or` (al menos una V).
- **Cortocircuito**: `if a != 0 and 1/a > 1:` nunca divide por cero.
- Comparación triple: `1 <= nota <= 10`.
- **Ternario**: `a = b if b >= 0 else -b`.

### `match`-`case` (Python 3.10+)

```python
match nota:
    case 1 | 2 | 3:                              # | funciona como "or"
        print("Aplazado")
    case 4 | 5 | 6 | 7 | 8 | 9 | 10 if deuda == 1:  # guarda "if" como "and"
        print("Aprobado")
    case _:                                      # caso por defecto (opcional)
        print("Nota inválida")
```

### Iterativa ([[conceptos/estructura-iterativa]])

- **`while`**: ciclos condicionales (cantidad desconocida, valor centinela); admite `break`, `continue`, `else`.
- **`for` con `range()`**: ciclos exactos. `range(n)` = 0..n−1 · `range(m,n)` = m..n−1 · `range(m,n,p)` con paso (puede ser negativo). El extremo final **nunca se incluye** (cuidado con el error off-by-one).
- **Contador**: se incrementa en cantidad fija (`cont += 1`). **Acumulador**: en cantidad variable (`suma += valor`). Ambos requieren inicialización.
- **Ciclo infinito**: la condición nunca se vuelve falsa porque nada cambia dentro del ciclo — error lógico grave.

---

## Bloque 2 — Funciones ([[conceptos/funciones-programacion]])

```python
def calcularFactorial(n):
    """ Devuelve el factorial de un entero positivo """   # docstring → help()
    fact = 1
    for i in range(1, n + 1):
        fact = fact * i
    return fact
```

- Ventajas: modularidad, evitar repetición, portabilidad. Nombre = **verbo en infinitivo**.
- **Parámetros formales** (definición) vs. **reales** (llamada): deben coincidir en cantidad y orden.
- **Docstring**: primera línea del cuerpo, `"""..."""`, explica *qué* hace (no *cómo*); visible con `help(nombre)`.

### Mutables vs. inmutables como parámetros (⭐ pregunta típica)

- **Mutables** (listas, conjuntos, diccionarios): la función **modifica el original** — no hace falta `return`.
- **Inmutables** (números, strings, tuplas): la función **no afecta** al original.

```python
def agregarTotal(lista):      # SÍ modifica la lista original
    lista.append(sum(lista))

def duplicar(x):              # NO modifica la variable original
    x = x * 2
```

### Retorno múltiple, omisión y nombre

```python
def leerFecha():
    return dia, mes, anio          # retorno múltiple
d, m, a = leerFecha()              # desempaquetado

def calcularRaiz(radicando, indice=2):   # parámetro por omisión
    return radicando ** (1 / indice)

calcularRaiz(16)                   # 4.0 (usa indice=2)
calcularRaiz(27, 3)                # raíz cúbica
calcularRaiz(indice=5, radicando=32)  # por nombre (keyword); van después de los posicionales
```

### Lambdas

Funciones anónimas de una línea (origen: Lisp). Útiles con `map`/`filter`/`sort`:

```python
cuadrado = lambda x: x**2          # cuadrado(3) → 9
raiz = lambda x, y=2: x**(1/y)     # admite valores por omisión
```

### Módulos

`import math` → `math.sqrt(x)` · módulos vistos: `random`, `math`, `time`, `os`, `tkinter`, `sqlite3`. Built-in sin import: `print`, `input`, `int`, `float`, `str`, `abs`, `len`.

---

## Bloque 3 — Listas, primera parte ([[conceptos/listas-python]])

Secuencia **ordenada, mutable, iterable**, subíndices desde **0** (también negativos: `lista[-1]` = último), admite tipos mixtos.

```python
lista = [3, 25, 18]
lista.append(20)        # agrega al final
lista.insert(1, 15)     # inserta en posición
lista[2] = 25           # modifica (mutabilidad)
lista.pop(3)            # elimina por índice (retorna el valor)
lista.remove(25)        # elimina por valor (primera aparición)
```

- **Empaquetar**: `numeros = [n1, n2, n3]` · **Desempaquetar**: `d1, d2, d3 = dias` (cantidades deben coincidir) · `print(*lista)` imprime desempaquetado.
- **Concatenación** `+` y **replicación** `*`: `[0] * 5` → `[0,0,0,0,0]`.
- **Funciones**: `len()`, `sum()`, `max()`/`min()` (sobre lista o argumentos sueltos), `list(iterable)` · operadores `in` / `not in`.
- **Métodos**: `append`, `insert`, `extend` (agrega varios; ≠ `append` que agrega uno), `pop`, `remove`, `index(elem, ini, fin)`, `count` (0 si no está), `clear`, `reverse`.

### `sort()` vs. `sorted()` (⭐)

- `lista.sort()`: ordena **in situ**. · `sorted(iterable)`: devuelve **lista nueva**, acepta cualquier iterable.
- Ambos admiten `reverse=True` y `key=`:

```python
nombres.sort(key=lambda x: x[-1])        # por última letra
numeros.sort(key=abs)                    # con función incorporada
numeros.sort(key=lambda x: [x % 2, x])   # dos criterios: pares primero, luego valor
```

### Módulo `random`

`random.random()` → real en [0,1) · `random.randint(a, b)` · `random.choice(secuencia)` · `random.shuffle(lista)` (mezcla in situ).

---

## Bloque 4 — Listas, segunda parte

### Slicing (rebanadas) en profundidad

```python
lista[1:4]     # índices 1 a 3 (el 4 NO se incluye)
lista[:2]      # desde el inicio
lista[2:]      # hasta el final
lista[::2]     # con paso 2
lista[::-1]    # invertida (paso negativo)
lista[2:2] = ['X', 'Y']   # rebanada nula: INSERTA en la posición 2
```

### Comparación de listas

Elemento a elemento (lexicográfico): `[2,3] > [1,4]` → `True` (el primer elemento decide); con prefijo común, la más larga es mayor.

### Copia de listas (⭐ pregunta típica)

`lista2 = lista1` **solo copia la referencia** — ambas apuntan al mismo objeto (verificable con `id()`); modificar una modifica la "otra". Las 4 formas de **copia superficial** independiente:

1. Rebanada completa: `lista1[:]`
2. `list(lista1)`
3. Concatenación: `lista1 + []`
4. `lista1.copy()`

`==` compara **valores**; `is` compara **identidad** (mismo objeto en memoria). Dos listas pueden ser `==` sin ser `is`.

### La trampa de la matriz con `*`

```python
fila = [0] * 3
M = [fila] * 2      # ¡las 2 filas son la MISMA lista!
M[0][0] = 9         # → [[9,0,0], [9,0,0]]  (se modifican "ambas")
```

Formas seguras: construir cada fila nueva en un bucle, o `[[0] * columnas for f in range(filas)]`.

### `enumerate`, `pass`, matrices

- `for i, valor in enumerate(lista):` → pares (subíndice, elemento) desempaquetados.
- `pass`: marcador de posición para bloques sintácticamente obligatorios; abusarlo es mala práctica.
- **Matrices** = lista de listas, `matriz[fila][columna]`; 5 formas de construcción (estática, bucles anidados, replicación en bucle, replicación+comprensión, comprensión anidada). Recorrido con doble `for`; tamaño: `len(matriz)` filas, `len(matriz[0])` columnas.

### `map`, `filter` y comprensión (⭐)

```python
raices  = list(map(lambda x: x**0.5, numeros))       # aplica a cada elemento
impares = list(filter(lambda x: x % 2 != 0, numeros)) # conserva si devuelve True

cuadrados  = [x**2 for x in range(6)]                 # [0, 1, 4, 9, 16, 25]
cubospares = [i**3 for i in range(11) if i**3 % 2 == 0]  # comprensión con filtro
```

Una comprensión suele reemplazar a un `map`/`filter` con menos código.

---

## Bloque 5 — Cadenas, primera parte ([[conceptos/cadenas-de-caracteres]])

- Python 3 usa **UTF-8** (admite `ñ`, tildes; Python 2 usaba ASCII).
- Comillas simples/dobles intercambiables (`"Mc. Donald's"`); `\` al fin de línea continúa la cadena sin salto; triple comilla `"""..."""` = multilínea con formato preservado.
- **Escapes**: `\n`, `\t`, `\'`, `\"`, `\\`, `\a` · **cadenas crudas**: `r"..."` (desactivan escapes).

### Similitudes con listas

Indexado desde 0 (y negativo), slicing, `+` (concatenar), `*` (replicar: `"*" * 10`), `len()`, `in`/`not in`, `max()`/`min()`, `.index()`, `.count()`, iterables (`for letra in cad:`).

### Diferencia clave: INMUTABILIDAD (⭐)

- `cadena[0] = 'x'` → **`TypeError`**. No existe `reverse()`.
- Invertir: `cadena[::-1]`.
- **Copia**: siempre copia la referencia (`b = a`, `c = a[:]`, `d = str(a)` → todas el mismo `id()`); sin riesgo justamente porque son inmutables (contraste con listas).

### Comparación y conversión

- Comparación alfabética carácter a carácter por código Unicode: `'GARCIA' < 'GOMEZ'` (A < O); `'LUIS ' > 'LUIS'` (prefijo común → la más larga gana).
- `str()` / `int()` / `float()` · concatenar número exige conversión: `"Edad: " + str(edad)`.
- `chr(codigo)` ↔ `ord(caracter)`: `ord('A')` → 65, `chr(66)` → `'B'`.

### `split` / `join` / `replace`

```python
"16/1/2026".split("/")      # ['16', '1', '2026']
"-".join(["a", "b", "c"])   # 'a-b-c'
texto.replace("feo", "lindo")
```

---

## Bloque 6 — Cadenas, segunda parte

### Métodos interrogativos `is*` (sin parámetros, devuelven booleano)

`isalpha()` (¿solo letras?) · `isdigit()` (¿solo dígitos?) · `isalnum()` · `isupper()` / `islower()`

Ejemplo de la cátedra: `limpiarpalabra()` separa prefijo/palabra/sufijo de puntuación usando `isalpha()` en un `while`.

### Transformación, alineación, recorte, búsqueda

| Grupo | Métodos |
|---|---|
| Mayúsculas | `upper()`, `lower()`, `capitalize()` (1ª letra), `title()` (1ª de cada palabra) |
| Alineación | `center(ancho, relleno)`, `ljust()`, `rjust()`, `zfill(ancho)` (`"3".zfill(5)` → `"00003"`) |
| Recorte | `lstrip([cars])`, `rstrip([cars])`, `strip([cars])` (por defecto quitan espacios) |
| Búsqueda | `find()` / `rfind()`: como `index()` pero devuelven **−1** en vez de error |

### f-strings en profundidad (⭐ — Python 3.6, 2016)

Marcadores `{}` admiten variables, expresiones y llamadas a métodos:

```python
print(f"Sucedió el {dia} de {mes}.")
print(f"{2 * 37}")          # 74
print(f"{mes.lower()}")
```

Mini-sintaxis de formato tras `:` (la misma que `.format()`):

```python
num, pal = 15, "Hola"
f"*{num:5}*"      # *   15*    ancho 5 (números a la derecha por defecto)
f"*{num:05}*"     # *00015*    relleno con ceros
f"*{num:<8}*"     # *15      * alineado a la izquierda
f"*{pal:>8}*"     # *    Hola* a la derecha (cadenas van a la izquierda por defecto)
f"*{pal:^8}*"     # *  Hola  * centrado
f"*{pal:=^8}*"    # *==Hola==* relleno personalizado + alineación
f"{3.1416:8.2f}"  # "    3.14" ancho 8, 2 decimales, punto fijo
```

---

## Ejercicios resueltos

### E1 — Formato con `%`
**¿Qué imprime `print("Precio: %7.2f" % 12.5)` y `print("%04d" % 3)`?**
→ `Precio:   12.50` (ancho total 7, 2 decimales, relleno con espacios) y `0003` (ancho 4, relleno con ceros).

### E2 — Precedencia
**Evaluar `-3**2`, `10 // 3`, `10 % 3`:**
→ `**` se evalúa antes que el menos unario: `-(3²)` = **−9** · `10//3` = **3** (división entera) · `10%3` = **1** (resto).

### E3 — Traza de `match`-`case`
Con el `match nota` del Bloque 1: **nota=5, deuda=1** → `Aprobado` (coincide `4|...|10` y la guarda `deuda==1`). **nota=5, deuda=2** → `Aprobación pendiente por deuda`. **nota=11** → no coincide ningún caso → `Nota inválida`.

### E4 — `range()`
**¿Qué genera `range(1, 10, 2)`? ¿Y `range(5, 0, -1)`?**
→ `1, 3, 5, 7, 9` (el 10 se excluye) y `5, 4, 3, 2, 1` (paso negativo; el 0 se excluye). `range(a, b)` produce exactamente `b−a` elementos — el clásico error off-by-one es olvidar que `b` queda afuera.

### E5 — Parámetro mutable vs. inmutable
```python
def modificar(lista, x):
    lista.append(99)
    x = x + 1
nums, n = [1, 2], 5
modificar(nums, n)
print(nums, n)
```
→ **`[1, 2, 99] 5`**. La lista (mutable) se modifica in place; el entero (inmutable) no — la reasignación de `x` crea una variable local.

### E6 — Retorno múltiple y parámetros por omisión
```python
def calcularRaiz(radicando, indice=2):
    return radicando ** (1 / indice)
print(calcularRaiz(16))                    # 4.0 — usa indice=2
print(calcularRaiz(indice=2, radicando=25))  # 5.0 — por nombre, el orden no importa
```
Regla: los argumentos por nombre van **después** de los posicionales (`calcularRaiz(27, indice=3)` ✓; `calcularRaiz(radicando=27, 3)` ✗).

### E7 — `sort` con `key`
```python
nombres = ["Andrés", "Ariel", "Juan"]
nombres.sort(key=lambda x: x[-1])
```
→ `["Ariel", "Juan", "Andrés"]` (por última letra: `l` < `n` < `s`).
**Dos criterios**: `[5,2,3,8,1,4]` con `key=lambda x: [x%2, x]` → `[2, 4, 8, 1, 3, 5]` (pares primero, cada grupo ascendente).

### E8 — Slicing
Con `lista = [10, 20, 30, 40, 50]`:
- `lista[1:4]` → `[20, 30, 40]` · `lista[::2]` → `[10, 30, 50]` · `lista[::-1]` → `[50, 40, 30, 20, 10]`
- `lista[2:2] = ['X']` → **inserta**: `[10, 20, 'X', 30, 40, 50]`

### E9 — Copia y referencias
```python
a = [1, 2, 3]
b = a          # referencia
c = a[:]       # copia superficial
b.append(4)
```
→ `a = [1,2,3,4]` (b y a son el mismo objeto), `c = [1,2,3]` (independiente). `a is b` → `True` · `a is c` → `False` · `a == b` → `True`.

### E10 — La trampa de la matriz
```python
fila = [0] * 3
M = [fila] * 2
M[0][0] = 9
print(M)
```
→ **`[[9, 0, 0], [9, 0, 0]]`** — las dos filas son la misma lista (aliasing). Forma segura: `M = [[0]*3 for f in range(2)]` (crea una lista **nueva** por iteración).

### E11 — `map`/`filter`/comprensión
Con `numeros = [1, 2, 3, 4, 5, 6]`:
- `list(filter(lambda x: x%2 != 0, numeros))` → `[1, 3, 5]`
- `list(map(lambda x: x**2, numeros))` → `[1, 4, 9, 16, 25, 36]`
- Equivalente combinado en comprensión: `[x**2 for x in numeros if x%2 != 0]` → `[1, 9, 25]`

### E12 — Inmutabilidad y comparación de cadenas
- `cad = "hola"; cad[0] = "H"` → **`TypeError`** (inmutable; correcto: `cad = "H" + cad[1:]`).
- `"programacion"[::-1]` → `"noicamargorp"`.
- `'GARCIA' < 'GOMEZ'` → `True` (compara por código: A < O) · `'LUIS ' > 'LUIS'` → `True`.

### E13 — Siglas (comprensión + `join` + `isupper`)
```python
frase = "Organizacion de las Naciones Unidas"
sigla = "".join([p[0] for p in frase.split() if p[0].isupper()])
```
→ `"ONU"`: `split()` separa en palabras, la comprensión toma la inicial solo si es mayúscula, `join` las une sin separador.

### E14 — f-strings
Con `num, pal = 15, "Hola"`:
- `f"*{num:05}*"` → `*00015*` · `f"*{pal:^8}*"` → `*  Hola  *` · `f"*{pal:=^8}*"` → `*==Hola==*`
- `f"{3.1416:8.2f}"` → `"    3.14"` (ancho 8, 2 decimales)
- `"banana".find("na")` → `2` · `"banana".rfind("na")` → `4` · `"banana".find("xy")` → `-1` (no lanza error, a diferencia de `index`).

---

## Checklist final antes del parcial

- [ ] Sé que `input()` siempre devuelve string y cuándo convertir con `int()`/`float()`
- [ ] Domino `%d`/`%f`/`%s` con ancho y decimales, y la mini-sintaxis completa de f-strings
- [ ] Escribo un `match`-`case` con `|` (or) y guarda `if` (and)
- [ ] Distingo ciclo exacto (`for`+`range`, extremo final excluido) de condicional (`while`+centinela)
- [ ] Explico por qué una lista pasada a una función se modifica sin `return` y un `int` no
- [ ] Uso parámetros por omisión, por nombre, retorno múltiple y lambdas
- [ ] Conozco `sort` vs. `sorted` y ordeno con `key=lambda` (incluso por dos criterios)
- [ ] Predigo cualquier slicing, incluyendo `[::-1]` y la rebanada nula que inserta
- [ ] Sé las 4 formas de copia superficial y la diferencia `==` / `is` / `id()`
- [ ] Evito (y detecto) la trampa `[fila]*n` al crear matrices
- [ ] Convierto entre `map`/`filter` y listas por comprensión
- [ ] Sé que las cadenas son inmutables, cómo invertirlas y cómo se comparan
- [ ] Manejo `split`/`join`/`replace`, `chr`/`ord`, los métodos `is*`, `strip` y `find` (−1, no error)

## Referencias

- Fuentes: [[fuentes/programacion1-introduccion-thompson]] · [[fuentes/programacion1-funciones-thompson]] · [[fuentes/programacion1-listas1-thompson]] · [[fuentes/programacion1-listas2-thompson]] · [[fuentes/programacion1-cadenas1-thompson]] · [[fuentes/programacion1-cadenas2-thompson]]
- Mapa del curso: [[analisis/estructura-curso-programacion1-thompson]]
- Conceptos: [[conceptos/variable-programacion]] · [[conceptos/estructura-condicional]] · [[conceptos/estructura-iterativa]] · [[conceptos/funciones-programacion]] · [[conceptos/listas-python]] · [[conceptos/mutabilidad-y-referencias]] · [[conceptos/arrays-vectores-matrices]] · [[conceptos/cadenas-de-caracteres]]
- Entidades: [[entidades/ricardo-thompson]] · [[entidades/python]]
