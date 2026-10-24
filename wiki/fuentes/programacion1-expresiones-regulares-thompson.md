---
titulo: "Programación I — Clase 6b: Expresiones Regulares"
tipo: fuente
creado: 2026-09-09
actualizado: 2026-09-09
tags: [python, expresiones-regulares, modulo-re]
---

# Programación I — Clase 6b: Expresiones Regulares

Fuente: diapositivas de la materia "Algoritmos y Estructuras de Datos I / Programación I", [[entidades/ricardo-thompson|Lic. Ricardo Thompson]].

## Resumen
Introducción a [[conceptos/expresiones-regulares|expresiones regulares]] con el módulo `re` de Python: `search()`, `findall()`, `sub()`, metacaracteres (`.`, `^`, `$`, grupos `[...]`, rangos), y cuantificadores (`?`, `*`, `+`).

## Contenido principal
- Concepto: patrón de búsqueda para encontrar coincidencias o validar formatos (emails, códigos, patentes).
- `re.search(patrón, cadena)`: primera coincidencia, objeto `re.Match` (con `.start()`/`.end()`) o `None`; `re.IGNORECASE`.
- `re.findall(patrón, cadena)`: todas las coincidencias como lista.
- Metacaracteres: `.` (cualquier carácter), `^` (ancla de inicio), `$` (ancla de fin), grupos `[abc]` y rangos `[0-9]`/`[a-d]`/`[P-Z]`, combinables con anclas.
- Cuantificadores: `?` (0 o 1), `*` (0 o más), `+` (1 o más), con ejemplos sobre una lista de números con ceros intercalados.
- `re.sub(patrón, reemplazo, cadena)`: reemplazo de todas las coincidencias.

## Contraste con el resto de la wiki
Tema completamente nuevo en la wiki — no había página sobre expresiones regulares. Se creó [[conceptos/expresiones-regulares]] como primera página del tema, enlazada desde [[conceptos/cadenas-de-caracteres]] como herramienta complementaria más potente que los métodos de cadena básicos.

## Referencias

- [[entidades/ricardo-thompson]]
- [[entidades/python]]
- [[conceptos/expresiones-regulares]]
