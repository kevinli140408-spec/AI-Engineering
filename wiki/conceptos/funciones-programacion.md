---
titulo: "Funciones (Programación Modular)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-09-09
tags: [funciones, programacion-modular, python, modulos, lambda]
fuentes: [funciones-existentes-mm, funciones-listas-mm, joyanes-aguilar-fundamentos-de-programacion, introduccion-a-la-programacion-con-python-3, programacion1-funciones-thompson]
---

# Funciones (Programación Modular)

La **programación modular** divide un problema complejo en subproblemas más pequeños ("divide y vencerás"), cada uno resuelto mediante una **función**.

## Esquema de una función
```
ENTRADA (parámetros) → PROCESO → SALIDA (return)
```

## Ventajas
- Facilita diseño y pruebas de partes pequeñas.
- Permite reutilización (usar la función varias veces).
- Permite trabajo en equipo (varios desarrolladores en paralelo).
- Permite ignorar *cómo* se resuelve una tarea, sabiendo solo *qué* hace.

## Sintaxis en Python
```python
def calcularPromedio(a, b):
    prom = (a + b) / 2
    return prom

# Programa principal
resultado = calcularPromedio(x, y)   # llamada con parámetros reales
```

Los **parámetros reales** (en la llamada) deben coincidir en **cantidad y orden** con los **parámetros formales** (en la definición). Las funciones pueden usar **variables locales**.

## Clasificación por entrada/salida

| Entrada | Ejemplo |
|---------|---------|
| Sin parámetros | `leerNumero()` |
| Un parámetro | `duplicar(n)` |
| Varios parámetros | `calcularPromedio(a, b)` |

| Salida | Ejemplo |
|--------|---------|
| Devuelve un valor | `calcularPromedio(a, b)` |
| Devuelve V/F | `esPrimo(n)` |
| Devuelve varios valores | `convertirHoraMinSeg(seg)` |
| No devuelve (retorna `None`) | `mostrarMensaje(msj)` |

## Funciones existentes (bibliotecas / módulos)
Funciones ya programadas, agrupadas en **módulos** que se importan con `import`.

| Módulo | Uso | Ejemplo |
|--------|-----|---------|
| `random` | Números al azar | `random.randint(1, 10)` |
| `math` | Funciones matemáticas | `math.sqrt(nro)` |
| `time` | Fecha y hora | `time.ctime()` |

Funciones **incorporadas (built-in)**: `print()`, `input()`, `int()`/`float()`/`str()`, `abs()`, `len()` — no requieren `import`.

### Formas de importar ([[fuentes/introduccion-a-la-programacion-con-python-3]])
- `from math import sin, cos` — importa funciones puntuales; se usan sin prefijo (`sin(x)`). Mejora la legibilidad porque se sabe de qué módulo proviene cada identificador.
- `from math import *` — importa todo el contenido del módulo. Cómodo, pero riesgoso: si el programa ya tenía una variable con el mismo nombre que una función del módulo (p. ej. `pow`), esta la sobrescribe silenciosamente y produce errores difíciles de rastrear.
- `import math` — importa el módulo completo bajo su propio espacio de nombres; se accede con prefijo (`math.sqrt(x)`). Evita por completo el problema de colisión de nombres.

Además de `math` (funciones trigonométricas, `exp`, `log`, `sqrt`, `ceil`, `floor`, constantes `pi`/`e`), el módulo `sys` da acceso a información del sistema: `sys.exit()` (aborta el intérprete), `sys.version` (versión de Python en uso), `sys.platform` (sistema operativo). Un módulo propio no es más que un fichero `.py` con funciones y/o constantes definidas dentro, que se importa igual que uno de la biblioteca estándar — agrupar así funciones reutilizables por ámbito de aplicación evita reescribir el mismo código en cada programa nuevo.

## Cadena de documentación (docstring)
Texto opcional, entre triple comilla (`"""..."""`), ubicado como primera línea del cuerpo de la función. Explica **qué** hace la función (no **cómo** lo hace) y aparece en la consola al invocar `help(<nombre>)`.

```python
def calcularFactorial(n):
    """ Devuelve el factorial de un número entero positivo """
    fact = 1
    for i in range(1, n + 1):
        fact = fact * i
    return fact
```

## Retorno de múltiples valores
A diferencia de otros lenguajes (que solo permiten devolver un valor por parámetros de salida), Python permite que un `return` entregue **varios valores separados por coma**; al llamarla, se desempaquetan directamente en varias variables:

```python
def leerFecha():
    dia = int(input("Dia? "))
    mes = int(input("Mes? "))
    anio = int(input("Año? "))
    return dia, mes, anio

d, m, a = leerFecha()
```

## Parámetros por omisión (valores por defecto)
Un parámetro puede tener un valor por defecto en el encabezado; si la llamada lo omite, se usa ese valor:

```python
def calcularRaiz(radicando, indice=2):
    return radicando ** (1 / indice)

calcularRaiz(16)        # índice=2 (raíz cuadrada)
calcularRaiz(27, 3)     # raíz cúbica
```

## Parámetros por nombre (keyword arguments)
Los parámetros también pueden pasarse indicando su nombre en la llamada, en vez de depender solo del orden posicional; deben ir **después** de los parámetros posicionales:

```python
calcularRaiz(indice=5, radicando=32)
calcularRaiz(27, indice=3)
```

## Funciones lambda
Funciones pequeñas, anónimas y de una sola línea, incorporadas a Python por compatibilidad con Lisp. Se escriben en el lugar donde se necesitan, y pueden usarse en cualquier contexto donde se admita una función (particularmente útiles combinadas con `map()`, `filter()`, `sort()` sobre [[conceptos/listas-python|listas]]):

```python
<var> = lambda <parámetros> : <valor de retorno>

cuadrado = lambda x: x**2
print(cuadrado(3))              # 9

raiz = lambda x, y=2: x**(1/y)  # admite valores por omisión
print(raiz(81))                 # 9.0
```

## Buenas prácticas de diseño (estilo)
- El nombre de una función debe ser significativo, idealmente un verbo en infinitivo que describa su tarea (evitar nombres genéricos como `funcion`).
- Cada función debe resolver **un subproblema completo**, no una tarea elemental (p. ej. leer un número); evitar funciones que solo lean o impriman si su responsabilidad principal es otra.
- No debería salirse de una función (`return`) desde el interior de un ciclo, salvo caso excepcional justificado.

## Funciones que modifican una lista
Si una función modifica el contenido de una [[conceptos/listas-python|lista]] recibida por parámetro, **no es necesario retornarla**: las listas se modifican "in place" (la lista original cambia).

```python
def duplicar(lista):
    for i in range(len(lista)):
        lista[i] = lista[i] * 2
```

## Funciones vs. procedimientos (pseudocódigo algorítmico, Joyanes Aguilar)
En lenguaje algorítmico se distinguen dos tipos de subprogramas (Python no hace esta distinción — toda función `def` puede o no devolver valor):
- **Función** (`función...fin_función`): siempre devuelve **exactamente un valor** mediante `devolver` (`return`). Cabecera: `<tipo_resultado> función <nombre>(lista_parámetros)`.
- **Procedimiento** (`procedimiento...fin_procedimiento`): no está asociado a ningún valor de retorno; puede entregar 0, 1 o varios resultados a través de su lista de parámetros. Se invoca con `llamar_a <nombre>(parámetros)`.

## Ámbito: variables locales y globales
- **Variable local**: declarada dentro de un subprograma; solo existe y es accesible mientras este se ejecuta.
- **Variable global**: declarada en el programa principal; accesible desde todos los subprogramas.
- **Efectos laterales**: cuando un subprograma modifica algo fuera de su ámbito (típicamente una variable global) sin pasar por su lista de parámetros. Se consideran mala práctica — dificultan la independencia y depuración de los módulos. Regla general: toda comunicación entre un subprograma y el resto del programa debería pasar por parámetros, no por variables globales.

### La palabra clave `global` en Python
Python decide si una variable usada dentro de una función es local o global con una regla simple: si en algún punto del cuerpo de la función se le **asigna** un valor, Python la trata como local — aunque exista una variable global con el mismo nombre ([[fuentes/introduccion-a-la-programacion-con-python-3]]). Esto provoca `UnboundLocalError` si se intenta leer esa variable antes de asignarle un valor dentro de la función, incluso si "obviamente" ya tiene un valor global. Para forzar que una función **modifique** (no solo lea) una variable global, hay que declararlo explícitamente al principio de la función: `global nombre_variable`. Sin esta declaración, Python simplemente crea una variable local nueva con el mismo nombre, que desaparece al terminar la función, dejando la global original intacta.

## Paso de parámetros: valor vs. referencia
- **Por valor**: el parámetro formal recibe una *copia* del valor del parámetro actual; los cambios dentro del subprograma no afectan a la variable original. Es el comportamiento de los tipos simples (int, float, bool) en Python.
- **Por referencia** (parámetro variable): se pasa la dirección de memoria del parámetro actual; los cambios dentro del subprograma sí modifican la variable original al volver. Corresponde al comportamiento de los objetos mutables en Python (p. ej. una [[conceptos/listas-python|lista]] modificada "in place" dentro de una función — ver sección anterior).

## Sobrecarga de funciones (C++/Java)
Definir varias funciones con el **mismo nombre** pero distinta lista de parámetros (cantidad o tipo); el compilador elige cuál ejecutar según los argumentos de la llamada. C y Pascal no la soportan; C++ y Java sí. Python tampoco la soporta de forma nativa (se simula con parámetros opcionales o `*args`).

## Recursividad
Una función puede llamarse a sí misma — ver página dedicada [[conceptos/recursividad]].

## Referencias

- [[fuentes/funciones-existentes-mm]]
- [[fuentes/funciones-listas-mm]]
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[fuentes/programacion1-funciones-thompson]]
- [[conceptos/listas-python]]
- [[conceptos/algoritmo]]
- [[conceptos/recursividad]]
- [[conceptos/mutabilidad-y-referencias]]
