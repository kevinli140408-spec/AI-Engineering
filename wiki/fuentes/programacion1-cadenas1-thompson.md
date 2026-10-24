---
titulo: "Programación I — Clase 5: Cadenas de Caracteres (Primera Parte)"
tipo: fuente
creado: 2026-09-09
actualizado: 2026-09-09
tags: [python, cadenas, strings]
---

# Programación I — Clase 5: Cadenas de Caracteres (Primera Parte)

Fuente: diapositivas de la materia "Algoritmos y Estructuras de Datos I / Programación I", [[entidades/ricardo-thompson|Lic. Ricardo Thompson]].

## Resumen
Primera parte de [[conceptos/cadenas-de-caracteres|cadenas de caracteres]]: codificación UTF-8, constantes de cadena (comillas, continuación de línea, triple comilla), formato `%s`, secuencias de escape y cadenas crudas, similitudes y diferencias con listas (slicing, concatenación, replicación, funciones/métodos compartidos, inmutabilidad), comparación, conversión (`str`/`int`/`float`), `chr`/`ord`, `split`/`join`/`replace`, y semántica de copia de cadenas.

## Contenido principal
- Python 3 usa UTF-8 (soporta `ñ`, tildes). Comillas simples/dobles intercambiables; continuación con `\` al fin de línea; triple comilla para cadenas multilínea con formato preservado.
- Formato con `%s` (con ancho opcional), además de `%d`/`%f` ya vistos.
- Secuencias de escape (`\n`, `\t`, `\'`, `\"`, `\\`, `\a`) y cadenas crudas (`r"..."`).
- Similitudes con listas: indexado base 0, slicing, concatenación (`+`), replicación (`*`), `len()`, `in`/`not in`, `max()`/`min()`, `.index()`, `.count()`.
- Diferencia clave: inmutabilidad — sin `reverse()`, se invierte con `cadena[::-1]`.
- Comparación alfabética; conversión número↔cadena con `str()`/`int()`/`float()`.
- `chr()`/`ord()`, `.split()`, `.join()`, `.replace()`.
- Copia de cadenas: siempre copia la referencia (mismo `id()`), sin riesgo por ser inmutables.

## Contraste con el resto de la wiki
[[conceptos/cadenas-de-caracteres]] ya cubría en profundidad slicing, métodos, `split`/`join`/`replace` (vía la tabla de equivalencias con pseudocódigo), f-strings y `.format()`. Lo nuevo que aporta esta fuente: la nota sobre **UTF-8** vs. ASCII, el especificador **`%s`** (agregado también a [[conceptos/variable-programacion]]), y la **semántica de copia de cadenas** (siempre por referencia, sin riesgo por inmutabilidad) — contrastada explícitamente con el caso de las listas en [[conceptos/mutabilidad-y-referencias]].

## Referencias

- [[entidades/ricardo-thompson]]
- [[entidades/python]]
- [[conceptos/cadenas-de-caracteres]]
- [[conceptos/variable-programacion]]
- [[conceptos/mutabilidad-y-referencias]]
