---
titulo: "Python (lenguaje)"
tipo: entidad
creado: 2026-06-30
actualizado: 2026-07-01
tags: [python, lenguaje-de-programacion, herramienta]
fuentes: [guia-estudio-algoritmia-mm, pensamiento-computacional-mm, introduccion-a-la-programacion-con-python-3]
---

# Python (lenguaje)

Lenguaje de programación moderno, **interpretado** y de **alto nivel**, creado por [[entidades/guido-van-rossum]] y lanzado en 1991. Lenguaje principal usado en el curso de [[conceptos/algoritmo|Algoritmia]] (UADE) y en la asignatura "Programación I" de la UJI ([[fuentes/introduccion-a-la-programacion-con-python-3]]).

## Por qué Python (frente a otros lenguajes)
Según Marzal, Gracia y García, las ventajas didácticas de Python frente a otros lenguajes de propósito general son: es muy **expresivo** (programas más compactos que su equivalente en C), muy **legible** (sintaxis elegante), ofrece un **entorno interactivo** para experimentar y despejar dudas, su entorno de ejecución **detecta y reporta errores** de forma más rica que muchos compiladores, admite tanto el paradigma **imperativo** como el **orientado a objetos**, y posee un rico juego de estructuras de datos manipulables de forma sencilla. Frente a [[entidades/java]] (compilado a bytecode, más verboso, con mayor peso en producción empresarial), Python es interpretado y prioriza la rapidez de escritura y lectura sobre el rendimiento en crudo.

## Adopción en la industria (según el libro, 2014)
El libro cita testimonios de la época para ilustrar la adopción de Python en la industria: Google lo usa como uno de sus lenguajes principales (Guido van Rossum trabajaba allí al momento de escribir el libro); Industrial Light & Magic (efectos especiales de George Lucas) y Pixar lo usan en producción cinematográfica; BitTorrent está escrito en Python; y empresas como Intel, Hewlett-Packard, NASA y JPMorgan Chase también lo emplean.

## Características
- **Sintaxis simple y legible**, cercana al lenguaje natural (inglés).
- **Indentación obligatoria**: no usa llaves `{}`, los bloques se delimitan por sangría.
- **Multiparadigma**: imperativo, orientado a objetos, funcional.
- **Interpretado**: se ejecuta línea por línea, sin compilación previa.
- **Tipado dinámico**: no requiere declarar el tipo de las [[conceptos/variable-programacion|variables]].
- Extensa biblioteca estándar (módulos `random`, `math`, `time`, etc.).

## Entornos de programación
- **IDLE**: entorno incluido con la instalación oficial de Python (python.org).
- **Thonny**: entorno creado para principiantes; instala su propio intérprete. Usado en la cátedra.

## Instrucción print y ejecución
`print("mensaje")` muestra texto por pantalla. Los archivos fuente tienen extensión `.py`. Se ejecutan con Run → Run current script (F5).

## Referencias

- [[fuentes/guia-estudio-algoritmia-mm]]
- [[fuentes/pensamiento-computacional-mm]]
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[conceptos/lenguajes-de-programacion]]
- [[entidades/guido-van-rossum]]
- [[entidades/java]]
