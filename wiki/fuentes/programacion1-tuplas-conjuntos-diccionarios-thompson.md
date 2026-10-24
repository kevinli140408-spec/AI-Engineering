---
titulo: "Programación I — Clase 7: Tuplas, Conjuntos y Diccionarios"
tipo: fuente
creado: 2026-09-09
actualizado: 2026-09-09
tags: [python, tuplas, conjuntos, diccionarios]
---

# Programación I — Clase 7: Tuplas, Conjuntos y Diccionarios

Fuente: diapositivas de la materia "Algoritmos y Estructuras de Datos I / Programación I", [[entidades/ricardo-thompson|Lic. Ricardo Thompson]].

## Resumen
Introduce las tres estructuras de datos restantes del núcleo de Python: [[conceptos/tuplas-python|tuplas]] (secuencia inmutable), [[conceptos/conjuntos-python|conjuntos]] (colección sin orden ni duplicados) y [[conceptos/diccionarios-python|diccionarios]] (clave→valor).

## Contenido principal
- Tuplas: creación (con/sin paréntesis), tupla vacía y de un elemento, inmutabilidad (sin `append`, error al asignar por índice), concatenación/replicación, anidamiento, funciones compartidas con listas (`len`/`max`/`min`/`sum`/`in`/`index`/`count`), conversión `tuple()`/`list()`, intercambio de variables `a, b = b, a`.
- Conjuntos: creación con `{}`/`set()`, eliminación automática de duplicados, restricción a elementos inmutables (*hashable*), operadores `|`/`&`/`-`/`^`, métodos `add`/`remove`/`discard`/`pop`/`clear`, ejemplo de mano de póker sin cartas repetidas.
- Diccionarios: dupla clave:valor, acceso por clave, claves inmutables/valores de cualquier tipo, formato multilínea, diccionario por comprensión, métodos `get`/`pop`/`keys`/`values`/`items`/`fromkeys`, patrón "pythonizado" de conteo con `dic.get(clave, 0) + 1`, aplicaciones típicas.

## Contraste con el resto de la wiki
No existía página de tuplas — se creó [[conceptos/tuplas-python]] desde cero. [[conceptos/conjuntos-python]] y [[conceptos/diccionarios-python]] ya existían (originadas en el libro de Marzal et al., con enfoque más conceptual/POO) pero carecían de la sintaxis y métodos concretos de esta clase — se ampliaron con operadores de conjuntos, métodos de ambos tipos, y el patrón `dict.get()` para conteo.

## Referencias

- [[entidades/ricardo-thompson]]
- [[entidades/python]]
- [[conceptos/tuplas-python]]
- [[conceptos/conjuntos-python]]
- [[conceptos/diccionarios-python]]
