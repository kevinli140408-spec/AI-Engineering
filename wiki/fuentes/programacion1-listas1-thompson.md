---
titulo: "Programación I — Clase 3: Listas (Primera Parte)"
tipo: fuente
creado: 2026-09-09
actualizado: 2026-09-09
tags: [python, listas, random]
---

# Programación I — Clase 3: Listas (Primera Parte)

Fuente: diapositivas de la materia "Algoritmos y Estructuras de Datos I / Programación I", [[entidades/ricardo-thompson|Lic. Ricardo Thompson]].

## Resumen
Primera parte de [[conceptos/listas-python|listas]] en Python: creación, acceso e indexado (incluyendo negativo), empaquetado/desempaquetado, concatenación y replicación, mutabilidad, funciones (`len`, `sum`, `max`, `min`, `list`), operadores `in`/`not in`, métodos de lista (`append`, `insert`, `extend`, `pop`, `remove`, `index`, `count`, `clear`, `reverse`, `sort`), la función `sorted()`, y el módulo `random` aplicado a listas.

## Contenido principal
- Qué es una lista: secuencia de elementos, equivalente flexible de los arreglos de otros lenguajes; homogénea por convención pero admite tipos mixtos y listas anidadas.
- Creación (`[ ]`), acceso por subíndice (positivo y negativo), impresión directa y con desempaquetado (`print(*lista)`).
- Empaquetado y desempaquetado de listas.
- Concatenación (`+`) y replicación (`*`); mutabilidad vía asignación por subíndice.
- Ejemplo de acumulación con lista + promedio; ejemplo de gráfico de barras con porcentajes.
- Funciones: `len()`, `sum()`, `max()`/`min()` (sobre lista o sobre argumentos sueltos), `list()` (conversión desde cualquier iterable), operadores `in`/`not in`.
- Métodos: `append`, `insert`, `extend`, `pop`, `remove`, `index` (con rango de búsqueda), `count`, `clear`, `reverse`, `sort` (con `reverse=True` y `key=`, incluyendo `key=lambda` y ordenar por más de un criterio), y la función `sorted()`.
- Módulo `random`: `random()`, `randint()`, `choice()`, `shuffle()`.

## Contraste con el resto de la wiki
[[conceptos/listas-python]] ya cubría lo esencial (creación, slicing, `append`/`insert`/`pop`/`remove`, listas paralelas, `random.randint`). Lo nuevo que aporta esta fuente: **empaquetado/desempaquetado** como término explícito, **`extend`**, **`count`**, **`clear`**, **`sort`/`sorted` con `key`** (incluyendo con lambda y ordenamiento por múltiples criterios), y el resto del módulo `random` (`random()`, `choice()`, `shuffle()`).

## Referencias

- [[entidades/ricardo-thompson]]
- [[entidades/python]]
- [[conceptos/listas-python]]
- [[conceptos/funciones-programacion]]
