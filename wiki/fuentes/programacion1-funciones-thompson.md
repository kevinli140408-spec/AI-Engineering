---
titulo: "Programación I — Clase 2: Funciones"
tipo: fuente
creado: 2026-09-09
actualizado: 2026-09-09
tags: [python, funciones, lambda]
---

# Programación I — Clase 2: Funciones

Fuente: diapositivas de la materia "Algoritmos y Estructuras de Datos I / Programación I", [[entidades/ricardo-thompson|Lic. Ricardo Thompson]].

## Resumen
Clase dedicada a [[conceptos/funciones-programacion|funciones]] en Python: estructura (`def`, docstring, `return`), reglas de nombres, parámetros formales/reales, mutabilidad de parámetros, retorno de múltiples valores, parámetros por omisión y por nombre, funciones lambda, y módulos/paquetes.

## Contenido principal
- Ventajas de las funciones: modularidad, evitar código repetido, portabilidad entre proyectos.
- Estructura: `def nombre(parámetros):`, docstring opcional (`"""..."""`, visible con `help()`), `return`.
- Reglas de nombres y buenas prácticas: verbo en infinitivo, nombres distintos de las variables, funciones al principio del programa.
- Diseño: una función = una tarea; no mezclar entrada/salida con otra responsabilidad; nunca salir de una función desde dentro de un ciclo.
- Parámetros formales (en la definición) vs. reales (en la llamada); mutables (listas/conjuntos/diccionarios, afectan al original) vs. inmutables (numéricos/strings/tuplas, no lo afectan) — ejemplos `agregartotal(lista)` vs. `duplicar(x)`.
- Retorno de múltiples valores (`return dia, mes, año`).
- Parámetros por omisión (`indice=2`) y por nombre (`calcularraiz(indice=5, radicando=32)`).
- Funciones lambda: sintaxis, ejemplos con uno y dos parámetros, valores por omisión, origen en Lisp, utilidad futura con `map`/`filter`/`sort`.
- Módulos y paquetes: `import math`, otros módulos (`random`, `os`, `tkinter`, `sqlite3`), funciones incorporadas sin import (`abs`, `len`, `int`, `float`).

## Contraste con el resto de la wiki
[[conceptos/funciones-programacion]] ya cubría en profundidad programación modular, ámbito (`global`), paso por valor/referencia y sobrecarga. Lo nuevo que aporta esta fuente: **docstrings**, **retorno de múltiples valores**, **parámetros por omisión y por nombre**, y **funciones lambda** — ninguno documentado hasta ahora.

## Referencias

- [[entidades/ricardo-thompson]]
- [[entidades/python]]
- [[conceptos/funciones-programacion]]
- [[conceptos/listas-python]]
