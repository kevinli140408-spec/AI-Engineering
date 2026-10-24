---
titulo: "Estructura del curso Programación I (Lic. Ricardo Thompson)"
tipo: analisis
creado: 2026-09-09
actualizado: 2026-09-09
tags: [python, programacion, sintesis-de-curso]
fuentes: [programacion1-introduccion-thompson, programacion1-funciones-thompson, programacion1-listas1-thompson, programacion1-listas2-thompson, programacion1-cadenas1-thompson, programacion1-cadenas2-thompson, programacion1-expresiones-regulares-thompson, programacion1-tuplas-conjuntos-diccionarios-thompson, programacion1-excepciones-thompson, programacion1-archivos-thompson, programacion1-json-thompson, programacion1-recursividad-thompson]
---

# Estructura del curso Programación I (Lic. Ricardo Thompson)

Síntesis de las 12 clases de la materia "Algoritmos y Estructuras de Datos I / Programación I", dictada en Python 3 por el [[entidades/ricardo-thompson|Lic. Ricardo Thompson]] (institución no especificada en el material). El curso recorre una progresión clásica: fundamentos → estructuras de datos → control de errores y persistencia → recursividad.

## Mapa del curso

1. **Introducción** ([[fuentes/programacion1-introduccion-thompson]]): Python, compilación/interpretación, variables, operadores, condicional/iterativa, `match-case`.
2. **Funciones** ([[fuentes/programacion1-funciones-thompson]]): estructura, docstrings, parámetros (mutables/omisión/nombre), retorno múltiple, lambdas.
3-4. **Listas** ([[fuentes/programacion1-listas1-thompson]], [[fuentes/programacion1-listas2-thompson]]): creación, métodos, slicing avanzado, copia, `map`/`filter`, comprensión, matrices.
5-6. **Cadenas** ([[fuentes/programacion1-cadenas1-thompson]], [[fuentes/programacion1-cadenas2-thompson]]): constantes, similitudes/diferencias con listas, métodos, f-strings.
6b. **Expresiones regulares** ([[fuentes/programacion1-expresiones-regulares-thompson]]): módulo `re`, metacaracteres, cuantificadores.
7. **Tuplas, conjuntos y diccionarios** ([[fuentes/programacion1-tuplas-conjuntos-diccionarios-thompson]]): las tres estructuras restantes del núcleo del lenguaje.
8. **Excepciones** ([[fuentes/programacion1-excepciones-thompson]]): `try`/`except`/`else`/`finally`, `raise`, `assert`.
9-9b. **Archivos y JSON** ([[fuentes/programacion1-archivos-thompson]], [[fuentes/programacion1-json-thompson]]): apertura/lectura/escritura/cierre con manejo de excepciones estricto; serialización.
10. **Recursividad** ([[fuentes/programacion1-recursividad-thompson]]): factorial, Fibonacci, listas, Torres de Hanoi — cierre del curso.

## Relación con el resto de la wiki
Este curso solapa en gran medida con el contenido ya presente a partir de la cátedra de Algoritmia (UADE, prefijo `-mm`) y el libro de Marzal, Gracia y García ([[fuentes/introduccion-a-la-programacion-con-python-3]]): mismos temas de fondo (variables, control de flujo, funciones, listas, recursividad). La ingesta se resolvió **actualizando las páginas de concepto existentes** en la mayoría de los casos, en vez de duplicar contenido, agregando el detalle sintáctico específico de esta cátedra que no estaba cubierto:

- **Nuevo por completo** (sin página previa en la wiki): [[conceptos/expresiones-regulares]], [[conceptos/tuplas-python]], [[conceptos/manejo-de-excepciones]] (desglosado desde [[conceptos/depuracion-y-pruebas]]), [[conceptos/json]].
- **Ampliadas sustancialmente**: [[conceptos/funciones-programacion]] (docstrings, retorno múltiple, parámetros por omisión/nombre, lambda), [[conceptos/listas-python]] (slicing avanzado, copia, `enumerate`, `map`/`filter`, comprensión, matrices), [[conceptos/cadenas-de-caracteres]] (UTF-8, `%s`, copia, f-strings en profundidad), [[conceptos/conjuntos-python]] y [[conceptos/diccionarios-python]] (sintaxis y métodos concretos), [[conceptos/archivos-ficheros]] (patrón try/except/finally sin `with`, rutas de Windows, `seek`, encoding), [[conceptos/recursividad]] (terminología, recursión sobre listas, `RecursionError`).
- **Nueva entidad**: [[entidades/ricardo-thompson]].

## Rasgo distintivo de esta cátedra
A diferencia de las demás fuentes de la wiki, este curso **no utiliza la sentencia `with`** para archivos — enseña el patrón explícito `try`/`except`/`finally` con cierre protegido por `try/except NameError`, y prohíbe de forma estricta cualquier carga de archivo completo en memoria (ni siquiera con `readlines()`), tratándolo como un error tan grave como un ciclo infinito. También es la única fuente que cubre expresiones regulares y JSON de forma dedicada.

## Referencias
- [[entidades/ricardo-thompson]]
- [[entidades/python]]
- [[analisis/estructura-curso-algoritmia-uade]]
- [[analisis/estructura-libro-marzal-python3]]
