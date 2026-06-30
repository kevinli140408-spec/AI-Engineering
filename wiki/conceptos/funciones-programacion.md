---
titulo: "Funciones (Programación Modular)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [funciones, programacion-modular, python, modulos]
fuentes: [funciones-existentes-mm, funciones-listas-mm]
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

## Referencias

- [[fuentes/funciones-existentes-mm]]
- [[fuentes/funciones-listas-mm]]
- [[conceptos/listas-python]]
- [[conceptos/algoritmo]]
