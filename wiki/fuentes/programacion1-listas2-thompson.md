---
titulo: "Programación I — Clase 4: Listas (Segunda Parte)"
tipo: fuente
creado: 2026-09-09
actualizado: 2026-09-09
tags: [python, listas, matrices, lambda, comprension-de-listas]
---

# Programación I — Clase 4: Listas (Segunda Parte)

Fuente: diapositivas de la materia "Algoritmos y Estructuras de Datos I / Programación I", [[entidades/ricardo-thompson|Lic. Ricardo Thompson]].

## Resumen
Segunda parte de [[conceptos/listas-python|listas]]: rebanadas (slicing) en profundidad, comparación de listas, semántica de copia (referencia vs. copia superficial), `for`/`enumerate()`, la instrucción `pass`, funciones de orden superior (`map`, `filter`), listas por comprensión, y matrices como lista de listas (cinco formas de construcción).

## Contenido principal
- Rebanadas: sintaxis de dos/tres subíndices, extremos implícitos, incremento (incluido negativo para invertir), rebanadas con variables, rebanada nula para insertar.
- Comparación de listas elemento a elemento (`>`, `<`).
- Copia de listas: por qué `lista2 = lista1` comparte referencia (verificable con `id()`), y las cuatro formas de copia superficial (rebanada, `list()`, concatenación con `[]`, `.copy()`).
- `for` directo sobre elementos vs. `enumerate()` para obtener también el subíndice (como tupla desempaquetada).
- Instrucción `pass` como marcador de posición, y su uso indebido.
- Funciones de orden superior `map()` y `filter()`, equivalencia con bucles `for` explícitos.
- Listas por comprensión, con y sin filtro `if`.
- Matrices como lista de listas: por qué Python no tiene matrices nativas, cinco alternativas de construcción (estática, dinámica con bucles, con replicación, con comprensión, con comprensión anidada), y funciones de relleno/impresión con doble `for` (con y sin subíndices).

## Contraste con el resto de la wiki
Gran parte de esta clase profundiza contenido que ya estaba cubierto de forma más teórica en [[conceptos/mutabilidad-y-referencias]] y [[conceptos/arrays-vectores-matrices]] (aliasing, referencias, matrices como lista de listas) — se actualizaron esas páginas con las 4 formas concretas de copia superficial y las 5 alternativas de construcción de matrices. Lo genuinamente nuevo: **slicing extendido** (incremento, rebanada nula para insertar), **`enumerate()`**, **`pass`**, **`map`/`filter`** y **listas por comprensión** — ninguno documentado hasta ahora.

## Referencias

- [[entidades/ricardo-thompson]]
- [[entidades/python]]
- [[conceptos/listas-python]]
- [[conceptos/mutabilidad-y-referencias]]
- [[conceptos/arrays-vectores-matrices]]
