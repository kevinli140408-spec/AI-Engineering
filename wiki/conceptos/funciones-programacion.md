---
titulo: "Funciones (Programación Modular)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [funciones, programacion-modular, python, modulos]
fuentes: [funciones-existentes-mm, funciones-listas-mm, joyanes-aguilar-fundamentos-de-programacion]
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
- [[conceptos/listas-python]]
- [[conceptos/algoritmo]]
- [[conceptos/recursividad]]
