---
titulo: "Listas en Python — Clase Práctica y Teórica"
tipo: fuente
creado: 2026-06-30
actualizado: 2026-06-30
tags: [algoritmia, listas, slicing, uade]
---

# Listas en Python — Clase Práctica y Teórica

Fuente: presentación PPTX (formato infográfico) sobre [[conceptos/listas-python|listas]] en Python, materia Fundamentos de Informática.

## Resumen
Presentación con formato visual tipo "tarjetas": introducción, acceso a elementos, slicing, modificación, uso de `random`, métodos, y ejercicios guiados por niveles.

## Contenido principal
- Listas: colección ordenada y mutable, definida con `[ ]`, admite tipos mixtos.
- Acceso por índice y recorrido (`for i in range(len(lista))` vs. `for x in lista`).
- Operador `in` para verificar existencia; `len()` para longitud.
- **Slicing**: `lista[inicio:fin:paso]` — extrae sublistas; el índice fin no se incluye.
- Modificación: `append(x)`, `insert(i, x)`, `lista[i] = valor`, `pop(i)`, `remove(x)`.
- Uso de la librería `random` para llenar listas con valores aleatorios.
- Métodos de listas: `append()`, `pop()`, `index()`, `count()`, `reverse()`, `copy()`, `clear()`, `insert()`, `remove()`.
- Ejercicios guiados (frutas) y ejercicios por niveles: fácil, intermedio, avanzado, "nivel Dios" (eliminar duplicados usando solo `pop`).
- Cierre: cuándo usar listas (colecciones ordenadas que cambian de tamaño, datos heterogéneos).

## Referencias

- [[conceptos/listas-python]]
