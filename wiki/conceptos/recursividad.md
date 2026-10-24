---
titulo: "Recursividad"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-09-09
tags: [recursividad, funciones, algoritmia]
fuentes: [joyanes-aguilar-fundamentos-de-programacion, introduccion-a-la-programacion-con-python-3, programacion1-recursividad-thompson]
---

# Recursividad

Una **función o procedimiento recursivo** es aquel que se llama a sí mismo, directa o indirectamente, durante su propia ejecución. Es una herramienta alternativa a la [[conceptos/estructura-iterativa|estructura iterativa]] para resolver problemas que se definen de forma natural en términos de versiones más simples de sí mismos.

## Recursión directa e indirecta
- **Directa**: una función `F` contiene una sentencia que invoca a `F` (los ejemplos de esta página).
- **Indirecta** (o **mutua**): `F` invoca a `G`, que a su vez invoca de nuevo a `F` — la cadena de llamadas vuelve al origen sin que ninguna función se llame literalmente a sí misma.

## Condiciones de un algoritmo recursivo correcto
1. **No hay recursión infinita**: cada llamada recursiva debe acercarse más a la condición de salida (de lo contrario, se agota la memoria de pila y el programa termina anormalmente).
2. **El caso base devuelve el valor correcto** directamente, sin recursión.
3. **Composición correcta**: si cada llamada recursiva individual devuelve un resultado correcto, el valor combinado que arma la función también debe ser correcto.

## Condición de terminación
Toda función recursiva necesita un **caso base** (condición de terminación) que detiene las llamadas; sin él, la recursión continúa indefinidamente (análogo al [[conceptos/estructura-iterativa|ciclo infinito]]) hasta agotar la memoria de pila.

## Ejemplo: factorial
```
N! = { 1                  si N = 0
     { N * (N – 1)!       si N > 0

entero función factorial(E entero: n)
inicio
  si n = 0 entonces
    devolver (1)
  si_no
    devolver (n * factorial(n - 1))
  fin_si
fin_función
```
Cada llamada se "apila" hasta llegar al caso base (`n = 0`), y luego los resultados se "desapilan" multiplicando en cadena: `factorial(3) = 3 * factorial(2) = 3 * (2 * factorial(1)) = ...`

## Ejemplo: serie de Fibonacci
```
fib(1) = 1
fib(2) = 1
fib(n) = fib(n-1) + fib(n-2)   para n > 2

entero función fibonacci(E entero: n)
inicio
  si (n = 1) o (n = 2) entonces
    devolver (1)
  si_no
    devolver (fibonacci(n-2) + fibonacci(n-1))
  fin_si
fin_función
```
Esta definición es simple de escribir pero **ineficiente**: cada llamada genera otras dos, por lo que el número de llamadas crece exponencialmente (se recalculan los mismos subproblemas muchas veces).

## Caso base y caso recursivo (terminología)
En cada función recursiva se distinguen dos ramas: el **caso recursivo** (donde ocurre la llamada a sí misma; suele ejecutarse la mayoría de las veces) y el **caso base** (la salida no recursiva; suele ser único o limitado a pocas alternativas). Si el caso base nunca se alcanza — p. ej. invocar `factorial(-1)`, donde `n` nunca llega a `0` porque decrece indefinidamente — Python agota la pila de llamadas y lanza `RecursionError: maximum recursion depth exceeded`.

## El "teorema fundamental" de recursión/iteración
Formulado explícitamente: *"Todo problema que admite una solución iterativa admite también una solución recursiva, y viceversa"*. Es la misma idea que "recursión vs. iteración" más abajo, pero como garantía general: la elección entre ambas es una decisión de diseño, no una limitación del problema.

## Ventajas y desventajas
- **Ventajas**: elegancia y simplicidad — el código puede reflejar directamente la definición matemática o conceptual del problema (ver factorial, Fibonacci).
- **Desventajas**: lentitud y mayor consumo de memoria frente a la versión iterativa equivalente (cada llamada activa un nuevo marco en la pila).

## Recomendaciones prácticas
- El caso base **nunca** debe verificarse con `while` o `for` — mezclar recursión con iteración explícita para controlar la salida contradice la lógica recursiva.
- Las variables locales de una llamada recursiva tienen alcance acotado a esa llamada; para comunicar valores entre llamadas hay que usar **parámetros adicionales** (con valor por omisión) o el **valor de retorno**, no variables compartidas.

## Recursividad sobre listas
Cualquier recorrido iterativo de una [[conceptos/listas-python|lista]] puede reescribirse recursivamente, típicamente de dos formas: con un parámetro adicional que actúa de índice, o consumiendo la lista con slicing en cada llamada.

```python
# Versión 1: índice explícito con valor por omisión
def imprimirlista(lista, inicio=0):
    if inicio < len(lista):
        print(lista[inicio], end=" ")
        imprimirlista(lista, inicio + 1)

# Versión 2: un solo parámetro, consumiendo la lista con slicing
def imprimirlista(lista):
    if len(lista) > 0:
        print(lista[0], end=" ")
        imprimirlista(lista[1:])
```

El mismo patrón aplica para agregación (buscar el máximo): cada llamada resuelve "el máximo del resto de la lista" y lo compara con su propio elemento:

```python
def buscarmayor(lista):
    if len(lista) > 1:
        actual = lista[0]
        mayor = buscarmayor(lista[1:])
        return actual if actual > mayor else mayor
    else:
        return lista[0]
```

La versión con slicing es más legible pero crea una copia parcial de la lista en cada llamada (costo adicional de memoria); la versión con índice es más eficiente para listas grandes.

## Recursión vs. iteración
- Si un problema se puede resolver con igual facilidad de ambas formas, la solución **iterativa es preferible**: se ejecuta más rápido y usa menos memoria (no acumula llamadas en la pila).
- La recursión es preferible cuando simplifica notablemente la solución o el problema es naturalmente recursivo (p. ej. recorridos de árboles, algoritmos de "divide y vencerás").

## Mecanismo interno
Las llamadas recursivas se gestionan con una estructura de [[conceptos/pilas-y-colas|pila (stack)]]: cada llamada apila su dirección de retorno y su estado (variables locales); al alcanzar el caso base, se desapilan en orden inverso. Ver [[conceptos/funciones-programacion]] para el paso de parámetros y el ámbito de las variables locales involucradas.

## Problemas clásicos resueltos con recursividad
Además de factorial y Fibonacci, el libro desarrolla varios casos de referencia: el problema de las [[conceptos/torres-de-hanoi|Torres de Hanoi]] (el ejemplo arquetípico de "divide y vencerás"), la búsqueda binaria recursiva (ver [[conceptos/algoritmos-busqueda]]), y las versiones recursivas de quicksort y mergesort (ver [[conceptos/algoritmos-ordenamiento]]).

### El algoritmo de Euclides (MCD), formulado recursivamente
```python
def mcd(a, b):
    if b == 0:
        return a
    else:
        return mcd(b, a % b)
```
Es el mismo algoritmo descrito en [[conceptos/algoritmo]] (origen histórico, Euclides, siglo III a.C.), pero expresado directamente como recursión: el caso base es `b == 0` (entonces `a` es el MCD), y el caso recursivo reduce el problema aplicando la misma operación al resto de la división entera — un ejemplo limpio de cómo un algoritmo formulado originalmente de forma iterativa admite una expresión recursiva casi idéntica a su definición matemática ([[fuentes/introduccion-a-la-programacion-con-python-3]]).

### Fractales: el copo de nieve de Von Koch
Ejemplo que combina recursividad con [[conceptos/graficos-de-tortuga|gráficos de tortuga]]: una figura fractal donde cada segmento se sustituye recursivamente por una versión más pequeña de un patrón (un "pico" triangular), hasta una profundidad de recursión dada. Ilustra que la recursividad no se limita a cálculos numéricos: también estructura de forma natural procesos gráficos autosimilares.

## Referencias

- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[fuentes/programacion1-recursividad-thompson]]
- [[conceptos/funciones-programacion]]
- [[conceptos/listas-python]]
- [[conceptos/estructura-iterativa]]
- [[conceptos/algoritmo]]
- [[conceptos/pilas-y-colas]]
- [[conceptos/torres-de-hanoi]]
- [[conceptos/algoritmos-busqueda]]
- [[conceptos/algoritmos-ordenamiento]]
- [[conceptos/graficos-de-tortuga]]
