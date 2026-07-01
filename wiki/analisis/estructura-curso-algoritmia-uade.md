---
titulo: "Estructura del Curso Fundamentos de Informática / Algoritmia (UADE)"
tipo: analisis
creado: 2026-06-30
actualizado: 2026-07-01
tags: [algoritmia, uade, sintesis, curso, python]
fuentes: [pensamiento-computacional-mm, algoritmos-secuenciales-mm, control-flujo-ciclos-mm, funciones-existentes-mm, resumen-clase5-mm, cadenas-caracteres-mm, taller-listas-mm, funciones-listas-mm, listas-python-mm, orden-busqueda-mm, guia-estudio-algoritmia-mm]
---

# Estructura del Curso Fundamentos de Informática / Algoritmia (UADE)

Síntesis de las 11 fuentes ingestadas del curso de **Algoritmia / Fundamentos de Informática** (1er Cuatrimestre 2026), [[entidades/uade|UADE]], dictado por la Prof. Ing. Verónica Galati con [[entidades/python|Python]] como lenguaje de programación.

## Mapa del curso

```
Bloque I — Fundamentos (Clases 1-2)
├── Clase 1: Pensamiento Computacional ── [[conceptos/pensamiento-computacional]]
│             Lenguajes de programación ── [[conceptos/lenguajes-de-programacion]]
└── Clase 2: Algoritmos Secuenciales ──── [[conceptos/variable-programacion]]
              Estructura Secuencial ───── [[conceptos/estructura-secuencial]]

Bloque II — Estructuras de Control (Clase 2 + Control de flujo)
├── Estructura Condicional ────────────── [[conceptos/estructura-condicional]]
└── Estructura Iterativa (while/for) ──── [[conceptos/estructura-iterativa]]

Bloque III — Modularidad (Clase 4, 5)
├── Clase 4: Funciones Existentes ────── [[conceptos/funciones-programacion]]
└── Clase 5: Resumen / Casos de Prueba ── [[conceptos/algoritmo]] (verificación y depuración)

Bloque IV — Estructuras de Datos (Clase 6, 7, Taller)
├── Cadenas de Caracteres ─────────────── [[conceptos/cadenas-de-caracteres]]
├── Clase 6: Funciones y Listas ───────── [[conceptos/listas-python]]
├── Taller y Clase 7: Listas ──────────── [[conceptos/listas-python]]
└── Orden y Búsqueda ─────────────────── [[conceptos/algoritmos-busqueda]], [[conceptos/algoritmos-ordenamiento]]

Material transversal
└── Guía de Estudio (48 págs.) ────────── integra y amplía todos los bloques
```

## Progresión temática

El curso avanza de lo abstracto a lo concreto:

1. **Pensamiento computacional y algoritmos** (sin código): cómo analizar un problema antes de programarlo.
2. **Sintaxis básica de Python**: variables, tipos de datos, entrada/salida.
3. **Estructuras de control**: secuencial → condicional → iterativa, en orden de complejidad creciente.
4. **Modularización**: funciones propias y funciones de bibliotecas (`random`, `math`, `time`).
5. **Estructuras de datos**: cadenas de caracteres y listas, con sus operaciones y métodos.
6. **Algoritmos clásicos**: búsqueda (secuencial, binaria) y ordenamiento (selección, burbujeo, inserción) — la culminación práctica que combina todo lo anterior (ciclos, listas, funciones, condicionales).

## Reglas pedagógicas notables
- **Prohibición de `break` y ciclos terminados solo por bandera**: la cátedra exige resolver con condiciones lógicas explícitas en el `while`, sin atajos de ruptura de ciclo.
- **Ciclo infinito = error grave**: entregar un algoritmo con ciclo infinito implica desaprobación automática del ejercicio en examen.
- **Evaluación escrita** (primer parcial): se trabaja con lápiz y papel, pseudocódigo y diagramas de flujo (Flowgorithm) antes de traducir a código.

## Bibliografía principal
- Joyanes Aguilar, Luis. *Fundamentos de Programación*. McGraw-Hill. Ingesta completa (18 capítulos + apéndices) en [[fuentes/joyanes-aguilar-fundamentos-de-programacion]] — ver mapa completo y contraste con el alcance del curso en [[analisis/estructura-libro-joyanes-fundamentos-programacion]].
- Marzal Varó, A.; García Luengo, I.; García Sevilla, P. *Introducción práctica a la programación con Python 3*. I'Une.

## Referencias

- [[fuentes/pensamiento-computacional-mm]] | [[fuentes/algoritmos-secuenciales-mm]] | [[fuentes/control-flujo-ciclos-mm]]
- [[fuentes/funciones-existentes-mm]] | [[fuentes/resumen-clase5-mm]] | [[fuentes/cadenas-caracteres-mm]]
- [[fuentes/taller-listas-mm]] | [[fuentes/funciones-listas-mm]] | [[fuentes/listas-python-mm]]
- [[fuentes/orden-busqueda-mm]] | [[fuentes/guia-estudio-algoritmia-mm]]
