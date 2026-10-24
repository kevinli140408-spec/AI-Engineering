---
titulo: "Programación I — Clase 6: Cadenas de Caracteres (Segunda Parte)"
tipo: fuente
creado: 2026-09-09
actualizado: 2026-09-09
tags: [python, cadenas, f-strings]
---

# Programación I — Clase 6: Cadenas de Caracteres (Segunda Parte)

Fuente: diapositivas de la materia "Algoritmos y Estructuras de Datos I / Programación I", [[entidades/ricardo-thompson|Lic. Ricardo Thompson]].

## Resumen
Segunda parte de [[conceptos/cadenas-de-caracteres|cadenas de caracteres]]: métodos interrogativos (`is*`), transformación de mayúsculas/minúsculas, alineación y relleno (`center`/`ljust`/`rjust`/`zfill`), recorte (`lstrip`/`rstrip`/`strip`), búsqueda (`find`/`rfind`), y f-strings en profundidad (historia, marcadores de posición, alineación, relleno, decimales).

## Contenido principal
- Métodos `is*` (interrogativos, sin parámetros, devuelven booleano): `isalpha`, `isdigit`, `isalnum`, `isupper`, `islower`.
- Ejemplo: función `limpiarpalabra()` que separa prefijo/palabra/sufijo de signos de puntuación usando `isalpha()` en un `while`.
- `upper()`, `lower()`, `capitalize()`, `title()` — con ejemplo de generación de siglas (dos estrategias: bucle vs. comprensión + `join`).
- Alineación/relleno: `center()`, `ljust()`, `rjust()`, `zfill()` — con ejemplo integral de una factura formateada.
- Recorte: `lstrip()`, `rstrip()`, `strip()`, todos con argumento opcional de caracteres a quitar.
- Búsqueda: `find()`/`rfind()` (como `index()` pero devuelven `-1` en vez de error).
- f-strings (Python 3.6+, 2016): marcadores de posición con variables, expresiones y llamadas a método; ancho, relleno con ceros, alineación (`<`/`>`/`^`), carácter de relleno personalizado, y precisión decimal (`:8.2f`) — ejemplo del triángulo de Floyd.

## Contraste con el resto de la wiki
La mayoría de los métodos `is*`/`upper`/`lower`/`capitalize`/`title`/`center`/`ljust`/`rjust`/`zfill` ya estaban en la tabla de [[conceptos/cadenas-de-caracteres]]. Se agregaron **`lstrip`/`rstrip`/`strip`** y **`find`/`rfind`**, ausentes hasta ahora. La f-string ya tenía un ejemplo mínimo; se amplió con toda la sintaxis de formato (ancho, alineación, relleno, decimales) que hasta ahora solo estaba documentada para `.format()` — ambas comparten la misma mini-sintaxis de marca de formato.

## Referencias

- [[entidades/ricardo-thompson]]
- [[entidades/python]]
- [[conceptos/cadenas-de-caracteres]]
