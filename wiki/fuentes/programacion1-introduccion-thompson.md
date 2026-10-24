---
titulo: "Programación I — Clase 1: Introducción"
tipo: fuente
creado: 2026-09-09
actualizado: 2026-09-09
tags: [python, programacion, introduccion, match-case]
---

# Programación I — Clase 1: Introducción

Fuente: diapositivas de la materia "Algoritmos y Estructuras de Datos I / Programación I", a cargo del [[entidades/ricardo-thompson|Lic. Ricardo Thompson]] (institución no especificada en el material).

## Resumen
Primera clase del curso: presenta [[entidades/python|Python]] 3, entornos de desarrollo, el proceso de compilación vs. interpretación, variables, operadores aritméticos, y las estructuras de control condicional (`if`/`elif`/`else`, operador ternario, `match`-`case`) e iterativa (`while`, `for`, `range()`).

## Contenido principal
- Entornos: Thonny, Python oficial, VS Code, Anaconda, Pydroid 3, y varias opciones online (online-python.com, onlinegdb.com, tutorialspoint, repl.it).
- Qué es Python: alto nivel, interpretado, multiparadigma, portable, case-sensitive ([[conceptos/lenguajes-de-programacion]]).
- Proceso de compilación (fuente → compilador → objeto → enlazador → ejecutable) vs. interpretación línea por línea.
- Estructura de programas: sin formato rígido, comentarios con `#`, `print()` con `end=`.
- Variables: reglas de nombres, tipado dinámico, valores booleanos, asignación múltiple, `input()` (siempre devuelve string) ([[conceptos/variable-programacion]]).
- Formato de salida con el operador `%` y especificadores `%d`/`%f` (ancho, decimales, relleno con ceros).
- Operadores aritméticos y orden de evaluación (potenciación → menos unario → `* / // %` → `+ -`); asignación extendida (`+=`, `-=`, etc.).
- Estructura condicional: `if`/`elif`/`else`, operadores relacionales y lógicos, condiciones encadenadas, operador condicional ternario ([[conceptos/estructura-condicional]]).
- Instrucción `match`-`case` (Python 3.10+), con `|` como *or* y guardas con `if` como *and*.
- Estructura iterativa: `while` (con `break`/`else`/`continue`), `for` con `range()` en sus tres formatos ([[conceptos/estructura-iterativa]]).
- Ejercicios propuestos: número primo, valores de 1/x, acertijo de las gallinas y conejos, error de redondeo en `for`.

## Contraste con el resto de la wiki
El contenido general (qué es Python, compilador/intérprete, variables, if/while/for) coincide en sustancia con lo ya documentado a partir de la cátedra de Algoritmia (UADE) y el libro de Marzal et al. Lo genuinamente nuevo que aporta esta fuente es el **operador `%` de formateo** (estilo antiguo, alternativo a f-strings) y la **instrucción `match`-`case`**, ninguno de los dos documentado hasta ahora en la wiki.

## Referencias

- [[entidades/ricardo-thompson]]
- [[entidades/python]]
- [[conceptos/lenguajes-de-programacion]]
- [[conceptos/variable-programacion]]
- [[conceptos/estructura-condicional]]
- [[conceptos/estructura-iterativa]]
