---
titulo: "C / C++ (lenguajes)"
tipo: entidad
creado: 2026-07-01
actualizado: 2026-07-01
tags: [c, cplusplus, lenguaje-de-programacion, herramienta]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# C / C++ (lenguajes)

**C** es un lenguaje de programación **imperativo** y de propósito general, desarrollado por Dennis Ritchie en los Bell Laboratories (1972) para reescribir el sistema operativo Unix. Estandarizado formalmente como **ANSI C** (1989), sigue siendo hoy la referencia de bajo nivel frente a la que se comparan lenguajes más modernos — ver la sintaxis específica del lenguaje en [[conceptos/guia-sintaxis-c]] y su ubicación entre los paradigmas de programación en [[conceptos/paradigmas-de-programacion]].

## Características distintivas
- **Compilado**, no interpretado: se traduce directamente a código máquina antes de ejecutarse.
- **Gestión manual de memoria** mediante **punteros explícitos** (`reservar`/`liberar` en pseudocódigo, `malloc`/`free` en C real) — sin recolección de basura automática, a diferencia de Java o Python. Ver el contraste completo en [[conceptos/listas-enlazadas]] y [[conceptos/recoleccion-de-basura]].
- Tipado estático con control fino sobre el tamaño de los datos en memoria (`char`, `short`, `int`, `long`).

## C++ como extensión orientada a objetos
**C++** (Bjarne Stroustrup, Bell Labs, 1983) extiende C agregando el paradigma **orientado a objetos** (clases, herencia, polimorfismo) sin abandonar el control de bajo nivel de su predecesor — ver [[conceptos/paradigmas-de-programacion]]. Es, junto con UML, uno de los pocos lenguajes mayores que soporta **herencia múltiple** de forma nativa (Java y C# la excluyen deliberadamente por la ambigüedad que introduce) — ver [[conceptos/herencia]].

## Por qué aparece como punto de comparación recurrente
A lo largo del wiki, C/C++ funciona como el término de comparación "de bajo nivel" frente a lenguajes gestionados como [[entidades/java]] o [[entidades/python]]: expone punteros donde estos exponen referencias gestionadas, exige gestión manual de memoria donde estos automatizan con recolección de basura, y no impone una máquina virtual intermedia.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/guia-sintaxis-c]]
- [[conceptos/paradigmas-de-programacion]]
- [[conceptos/herencia]]
- [[conceptos/listas-enlazadas]]
- [[entidades/java]]
- [[entidades/python]]
