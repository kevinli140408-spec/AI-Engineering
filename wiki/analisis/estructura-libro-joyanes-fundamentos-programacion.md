---
titulo: "Estructura del Libro Fundamentos de Programación (Joyanes Aguilar) y su relación con el curso UADE"
tipo: analisis
creado: 2026-07-01
actualizado: 2026-07-01
tags: [algoritmia, programacion, sintesis, uade, joyanes-aguilar]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Estructura del Libro *Fundamentos de Programación* y su relación con el curso UADE

Síntesis de la ingesta completa (18 capítulos + 4 apéndices) de [[fuentes/joyanes-aguilar-fundamentos-de-programacion]], y comparación con el alcance real del curso de [[entidades/uade|UADE]] ya sintetizado en [[analisis/estructura-curso-algoritmia-uade]].

## Mapa completo del libro (6 bloques temáticos)

```
Bloque I — Fundamentos (Cap. 1-2)
├── Organización de computadoras, representación de la información, lenguajes ── [[conceptos/organizacion-de-computadoras]], [[conceptos/lenguajes-de-programacion]]
└── Metodología de la programación, POO introductoria ────────────────────────── [[conceptos/metodologia-de-la-programacion]], [[conceptos/programacion-orientada-a-objetos]]

Bloque II — Estructura de un programa y control de flujo (Cap. 3-6)
├── Tipos de datos, operadores, estructura de un algoritmo ── [[conceptos/operadores-y-expresiones]]
├── Selectiva / iterativa ──────────────────────────────────  [[conceptos/estructura-condicional]], [[conceptos/estructura-iterativa]]
└── Subprogramas: funciones y procedimientos ───────────────  [[conceptos/funciones-programacion]]

Bloque III — Estructuras de datos estáticas y archivos (Cap. 7-11)
├── Arrays, registros, cadenas ── [[conceptos/arrays-vectores-matrices]], [[conceptos/estructuras-registros]], [[conceptos/cadenas-de-caracteres]]
├── Archivos (secuencial/directo/indexado) ── [[conceptos/archivos-ficheros]]
└── Ordenación/búsqueda (interna y externa) ── [[conceptos/algoritmos-ordenamiento]], [[conceptos/algoritmos-busqueda]], [[conceptos/ordenacion-externa]]

Bloque IV — Estructuras dinámicas y recursividad (Cap. 12-14)
├── Listas enlazadas, pilas, colas ── [[conceptos/listas-enlazadas]], [[conceptos/pilas-y-colas]]
├── Árboles y grafos ──────────────── [[conceptos/arboles]], [[conceptos/grafos]]
└── Recursividad en profundidad ───── [[conceptos/recursividad]], [[conceptos/torres-de-hanoi]]

Bloque V — Orientación a objetos y UML (Cap. 15-17)
├── TAD, objetos, UML como lenguaje ──────── [[conceptos/uml]]
├── Diagrama de clases, constructores/destructores ── [[conceptos/uml-diagrama-de-clases]], [[conceptos/constructores-destructores]]
└── Relaciones entre clases, herencia, clases abstractas ── [[conceptos/relaciones-entre-clases]], [[conceptos/herencia]], [[conceptos/clases-abstractas]]

Bloque VI — Ingeniería de software y referencia (Cap. 18 + Apéndices)
├── Ciclo de vida, principios de diseño, estilo/documentación, depuración/pruebas ── [[conceptos/ciclo-de-vida-del-software]], [[conceptos/principios-diseno-software]], [[conceptos/estilo-y-documentacion]], [[conceptos/depuracion-y-pruebas]]
└── Referencia formal: pseudocódigo UPSAM, sintaxis C ── [[conceptos/lenguaje-algoritmico-upsam]], [[conceptos/guia-sintaxis-c]]
```

## Relación con el curso UADE
El curso [[analisis/estructura-curso-algoritmia-uade|Fundamentos de Informática / Algoritmia]] usa este libro como bibliografía principal, pero cubre solo una **fracción inicial** del Bloque I al III: pensamiento computacional, estructura secuencial/condicional/iterativa, funciones, cadenas, listas y ordenamiento/búsqueda — aproximadamente los capítulos 1-2, 4-6, 8 y 10 del libro, traducidos a Python. El libro va **mucho más allá** del temario del curso en tres direcciones que el curso no toca: (1) persistencia — archivos secuenciales/directos/indexados (Cap. 9, 11); (2) estructuras de datos dinámicas — listas enlazadas, pilas, colas, árboles, grafos y recursividad formal (Cap. 12-14); y (3) diseño de software a mayor escala — POO completa con UML (Cap. 15-17) e ingeniería de software (Cap. 18).

## Un contraste pedagógico notable
El curso UADE **prohíbe explícitamente** el uso de `break` y de ciclos terminados solo por bandera, exigiendo condiciones lógicas explícitas en el `mientras` (ver regla en [[analisis/estructura-curso-algoritmia-uade]]). El libro, en cambio, incluye `interrumpir`/`continuar` (equivalentes a `break`/`continue`) como parte formal del lenguaje algorítmico UPSAM (ver [[conceptos/lenguaje-algoritmico-upsam]] y [[conceptos/estructura-iterativa]]). No es una contradicción de contenido sino una **restricción pedagógica deliberada** de la cátedra sobre un lenguaje que sí los admite — vale la pena que quien cursa tenga presente que el libro describe un superconjunto de lo permitido en los ejercicios evaluados.

## Consistencia interna del libro
No se detectaron contradicciones entre capítulos: el libro mantiene terminología y convenciones de pseudocódigo consistentes de principio a fin (formalizadas recién en el Apéndice A), y los capítulos posteriores construyen explícitamente sobre los anteriores (p. ej. Cap. 14 amplía la recursividad introducida en el Cap. 6; Cap. 16-17 desarrollan la notación UML anunciada en el Cap. 15; Cap. 18 formaliza el ciclo de vida ya esbozado en el Cap. 2).

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[analisis/estructura-curso-algoritmia-uade]]
