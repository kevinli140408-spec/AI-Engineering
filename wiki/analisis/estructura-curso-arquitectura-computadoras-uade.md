---
titulo: "Estructura del Curso de Arquitectura de Computadoras (UADE)"
tipo: analisis
creado: 2026-08-19
actualizado: 2026-09-15
tags: [hardware, uade, arquitectura-von-neumann, sistemas-de-numeracion, representacion, alu]
fuentes: [arquitectura-computadoras-clase1-uade, arquitectura-computadoras-clase2-uade, arquitectura-computadoras-clase3-uade, arquitectura-computadoras-clase4-uade, arquitectura-computadoras-clase5-uade, arquitectura-computadoras-clase6-uade]
---

# Estructura del Curso de Arquitectura de Computadoras (UADE)

Síntesis de las clases 1-6 del curso **Arquitectura de Computadoras** de [[entidades/uade]] (2026), que construye el conocimiento de hardware "de abajo hacia arriba": primero la física de la electricidad, luego los componentes de silicio, luego la arquitectura lógica que los organiza, hasta llegar a la construcción de la ALU desde compuertas. Las clases 1-6 cierran la primera parte de la materia (primer parcial).

## Mapa del curso

1. **Clase 1 — Electricidad y hardware propio** ([[fuentes/arquitectura-computadoras-clase1-uade]]): magnitudes eléctricas, [[conceptos/electricidad-basica|Ley de Ohm/Potencia/Joule]], CC vs. CA, compatibilidad de cargadores, e introducción al uso de IA como herramienta de estudio.
2. **Clase 2 — De la física al procesador** ([[fuentes/arquitectura-computadoras-clase2-uade]]): [[conceptos/semiconductores-y-transistores|semiconductores y transistores]] como base física del bit, [[conceptos/ley-de-moore|Ley de Moore]], [[conceptos/historia-de-la-computacion|historia del hardware]], [[conceptos/componentes-de-la-cpu|componentes internos de la CPU]], y desarrollo profundo de la [[conceptos/arquitectura-von-neumann|arquitectura de Von Neumann]] ([[conceptos/buses-de-sistema|buses]], [[conceptos/interrupciones|interrupciones]]) en contraste con [[conceptos/arquitectura-harvard|Harvard]].
3. **Clase 3 — Sistemas de numeración** ([[fuentes/arquitectura-computadoras-clase3-uade]]): cierre del bloque de arquitectura y desarrollo de [[conceptos/sistemas-de-numeracion|bases numéricas, conversiones y aritmética binaria]].
4. **Clase 4 — Sistemas de representación** ([[fuentes/arquitectura-computadoras-clase4-uade]] + [[fuentes/arquitectura-computadoras-clase4-notas-uade|notas]]): [[conceptos/representacion-numeros-enteros|BSS, MyS, Ca1, Ca2 y exceso]], [[conceptos/flags-del-procesador|flags Z/N/C/V]], [[conceptos/punto-flotante-ieee754|IEEE 754]] y códigos ASCII/Unicode/UTF-8.
5. **Clase 5 — CISC y RISC** ([[fuentes/arquitectura-computadoras-clase5-uade]] + [[fuentes/arquitectura-computadoras-clase5-notas-uade|notas]]): [[conceptos/pipelining-y-superescalaridad|pipelining, superescalaridad, multithread/multicore]], [[conceptos/cisc-y-risc|ISA, CISC vs RISC, x86 vs ARM]] e introducción a [[conceptos/compuertas-logicas|compuertas lógicas]].
6. **Clase 6 — Álgebra de Boole y ALU de 1 bit** ([[fuentes/arquitectura-computadoras-clase6-uade]] + [[fuentes/arquitectura-computadoras-clase6-notas-uade|notas]]): compuertas, circuitos combinacionales/secuenciales y construcción de la [[conceptos/alu-de-1-bit|ALU]] (semi-sumador → full adder → sumador de 8 bits → ALU con multiplexor).

**Hilo conductor de las clases 4-6**: la ALU solo sabe sumar y operar lógicamente; los sistemas de representación (Ca2, exceso), los flags y las compuertas son las tres piezas que convierten la aritmética en lógica ejecutable por transistores.

## Relación con el curso de Fundamentos de Informática (Joyanes Aguilar)

Este curso **profundiza y no contradice** el capítulo 1 de [[fuentes/joyanes-aguilar-fundamentos-de-programacion]], que ya había introducido [[conceptos/organizacion-de-computadoras]], [[conceptos/arquitectura-von-neumann]] y [[conceptos/representacion-de-la-informacion]] de forma más resumida (nivel "programador"). Las diferencias de enfoque:

- **Punto de partida distinto**: Joyanes parte de la definición abstracta de computadora; Arquitectura de Computadoras parte de la electricidad física (voltaje, semiconductores) y sube hasta la lógica.
- **Ciclo de instrucción**: la wiki tenía 3 etapas (fetch-decode-execute); este curso agrega una cuarta (**write-back**) — ya incorporada en [[conceptos/arquitectura-von-neumann]].
- **Tema nuevo**: [[conceptos/interrupciones]] no estaba cubierto antes; ahora tiene página propia.
- **Sistemas de numeración**: [[conceptos/representacion-de-la-informacion]] cubría codificación (ASCII, complemento a dos, IEEE 754) sin desarrollar a fondo las conversiones entre bases ni la aritmética binaria manual — ahora cubierto en [[conceptos/sistemas-de-numeracion]], página hermana y complementaria.

No se detectaron contradicciones factuales entre ambos cursos.

## Para repasar antes de un parcial

- **Fórmulas físicas**: `V=I×R`, `P=V×I=I²×R`, `Q=P×t`.
- **Fórmula de memoria**: `Tamaño = Longitud de Palabra × Cantidad de Direcciones`; direcciones posibles con n bits = `2ⁿ`.
- **Ciclo de instrucción**: Fetch → Decode → Execute → Write-back.
- **Von Neumann vs. Harvard**: memoria/bus único y secuencial vs. separados y paralelos (ver tabla en [[conceptos/arquitectura-harvard]]).
- **Conversión de bases**: practicar decimal↔binario (restas sucesivas de potencias de 2) y binario↔hex (agrupando de a 4 bits) — ejemplos resueltos en [[conceptos/sistemas-de-numeracion]].
- **Rangos por sistema (8 bits)**: BSS [0,255] · MyS/Ca1 [−127,+127] · Ca2 [−128,+127]; −128 solo existe en Ca2 — tabla completa en [[conceptos/representacion-numeros-enteros]].
- **Flags**: C = fuera de rango en BSS; V = fuera de rango en Ca2 (regla de signos: `(+)+(+)=(−)` → V=1); justificar siempre con flags en el examen — ejercicios resueltos en [[conceptos/flags-del-procesador]].
- **Se estima que ~3 de 5 puntos del parcial** salen de sistemas numéricos y de representación ([[fuentes/arquitectura-computadoras-clase5-notas-uade]]).
- **Compuertas y ALU**: tablas de verdad de las 7 compuertas, semi-sumador (XOR+AND), full adder (2 half adders + OR), combinacional vs. secuencial — en [[conceptos/compuertas-logicas]] y [[conceptos/alu-de-1-bit]].

## Referencias
- [[fuentes/arquitectura-computadoras-clase1-uade]]
- [[fuentes/arquitectura-computadoras-clase2-uade]]
- [[fuentes/arquitectura-computadoras-clase3-uade]]
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[entidades/uade]]
