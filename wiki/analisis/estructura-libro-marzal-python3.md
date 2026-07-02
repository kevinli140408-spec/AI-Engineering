---
titulo: "Estructura del Libro Introducción a la Programación con Python 3 (Marzal et al.) y su relación con el resto del wiki"
tipo: analisis
creado: 2026-07-01
actualizado: 2026-07-01
tags: [python, programacion, sintesis, uji, joyanes-aguilar, uade]
fuentes: [introduccion-a-la-programacion-con-python-3, joyanes-aguilar-fundamentos-de-programacion]
---

# Estructura del Libro *Introducción a la Programación con Python 3* (Marzal et al.) y su relación con el resto del wiki

Síntesis de la ingesta completa (8 capítulos) de [[fuentes/introduccion-a-la-programacion-con-python-3]], y comparación con [[fuentes/joyanes-aguilar-fundamentos-de-programacion]] y el curso [[analisis/estructura-curso-algoritmia-uade|Fundamentos de Informática / Algoritmia (UADE)]], ya presentes en el wiki.

## Mapa del libro (4 bloques temáticos)

```
Bloque I — Fundamentos y entorno (Cap. 1-3)
├── Computador, representación binaria, lenguajes ── [[conceptos/representacion-de-la-informacion]], [[conceptos/lenguajes-de-programacion]]
├── Sesiones interactivas, tipos básicos, operadores ── [[conceptos/operadores-y-expresiones]], [[conceptos/variable-programacion]]
└── Programas como ficheros, legibilidad, turtle ── [[conceptos/estilo-y-documentacion]], [[conceptos/graficos-de-tortuga]]

Bloque II — Control de flujo y datos secuenciales (Cap. 4-5)
├── if/while/for, excepciones ── [[conceptos/estructura-condicional]], [[conceptos/estructura-iterativa]], [[conceptos/depuracion-y-pruebas]]
└── Cadenas, listas, matrices, mutabilidad ── [[conceptos/cadenas-de-caracteres]], [[conceptos/listas-python]], [[conceptos/mutabilidad-y-referencias]]

Bloque III — Funciones y recursividad (Cap. 6)
└── Definición, ámbito, pila de llamadas, recursión ── [[conceptos/funciones-programacion]], [[conceptos/recursividad]]

Bloque IV — Objetos, colecciones con clave y persistencia (Cap. 7-8)
├── Clases en Python, diccionarios, conjuntos, colas ── [[conceptos/programacion-orientada-a-objetos]], [[conceptos/diccionarios-python]], [[conceptos/conjuntos-python]], [[conceptos/pilas-y-colas]]
└── Ficheros: protocolo abrir/leer-escribir/cerrar, pickle ── [[conceptos/archivos-ficheros]]
```

## Relación con [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
Los dos libros cubren, en gran medida, el **mismo temario de fondo** (organización de computadoras, algoritmos, control de flujo, funciones, estructuras de datos, archivos, objetos), pero con propósitos distintos:
- **Joyanes** enseña algoritmia en un **pseudocódigo multilenguaje** (UPSAM), con Python como una de varias traducciones posibles, y profundiza mucho más en estructuras de datos dinámicas avanzadas (listas enlazadas, árboles, grafos) y en UML/ingeniería de software.
- **Marzal et al.** enseñan **directamente en Python**, con mucho mayor detalle de la mecánica real del lenguaje: precedencia exacta de operadores, representación IEEE 754, el modelo de memoria con referencias y mutabilidad (`is` vs. `==`, el problema del aliasing en listas y objetos), el mecanismo de `global`, y las excepciones concretas de Python (`ZeroDivisionError`, `ValueError`, `KeyError`, `UnboundLocalError`).

La mayoría de las páginas de conceptos "clásicos" (algoritmo, lenguajes de programación, estructuras de control, funciones) ya existían por la ingesta de Joyanes y se **actualizaron** en vez de duplicarse. El aporte distintivo de Marzal et al. son 4 páginas enteramente nuevas centradas en mecánica interna y tipos de datos específicos de Python: [[conceptos/mutabilidad-y-referencias]], [[conceptos/diccionarios-python]], [[conceptos/conjuntos-python]] y [[conceptos/graficos-de-tortuga]].

## Relación con el curso UADE
El curso [[analisis/estructura-curso-algoritmia-uade|Fundamentos de Informática / Algoritmia]] (que ya usa Python como lenguaje de la cátedra) es más cercano en espíritu a este libro que a Joyanes, pero es notablemente más breve: no cubre clases/objetos, diccionarios, conjuntos, manejo de excepciones con `try`/`except`, ni ficheros — todos temas que sí forman el núcleo de los capítulos 4, 7 y 8 de Marzal et al. La cátedra UADE también **prohíbe explícitamente `break`** (ver [[analisis/estructura-curso-algoritmia-uade]]), mientras que este libro lo presenta como herramienta estándar del lenguaje sin restricción — la misma tensión pedagógica ya señalada en [[analisis/estructura-libro-joyanes-fundamentos-programacion]] respecto de Joyanes, y no una contradicción de contenido.

## Un matiz didáctico notable: reinventar estructuras ya nativas
Un rasgo distintivo de este libro es que, en el Cap. 7, hace construir desde cero clases `Conjunto` y `ColaPrioridad` como ejercicio de diseño de clases — aun cuando Python ya ofrece `set` y `heapq` con mejor rendimiento. Vale la pena tenerlo presente al usar el libro como referencia de "cómo se hace en la práctica": el objetivo es practicar POO, no recomendar reimplementar estructuras estándar en código real — se señaló explícitamente en [[conceptos/conjuntos-python]] y [[conceptos/pilas-y-colas]].

## Consistencia interna
No se detectaron contradicciones entre capítulos ni con el resto del wiki. Los capítulos posteriores construyen explícitamente sobre los anteriores (p. ej. el Cap. 5 introduce el problema de mutabilidad con listas, que el Cap. 7 retoma idéntico para objetos; el Cap. 6 introduce recursión con factorial/Fibonacci, y el propio capítulo la reutiliza para Euclides, Hanoi y fractales de Von Koch).

## Referencias
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[analisis/estructura-libro-joyanes-fundamentos-programacion]]
- [[analisis/estructura-curso-algoritmia-uade]]
- [[conceptos/mutabilidad-y-referencias]]
- [[conceptos/diccionarios-python]]
- [[conceptos/conjuntos-python]]
- [[conceptos/graficos-de-tortuga]]
