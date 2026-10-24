---
titulo: "Arquitectura de Computadoras — Clase 5: CISC y RISC (UADE)"
tipo: fuente
creado: 2026-09-15
actualizado: 2026-09-15
tags: [arquitectura-de-computadoras, uade, cisc, risc, pipelining, compuertas-logicas]
---

# Clase 5: CISC y RISC (UADE)

Diapositivas de la Clase 5 del curso de Arquitectura de Computadoras de [[entidades/uade]] (85 páginas, PDF). Continúa a [[fuentes/arquitectura-computadoras-clase4-uade]].

## Contenido

### Repaso (págs. 1-45)
Más de la mitad del PDF repite la Clase 4: conversiones entre bases, [[conceptos/representacion-numeros-enteros|BSS/MyS/Ca1/Ca2/exceso]], [[conceptos/flags-del-procesador|flags]], [[conceptos/punto-flotante-ieee754|IEEE 754]] y códigos ASCII/Unicode. No aporta contenido nuevo sobre esos temas.

### Ciclo de instrucción moderno
Evolución del ciclo secuencial fetch-decode-execute-write back ([[conceptos/arquitectura-von-neumann]]) — ver [[conceptos/pipelining-y-superescalaridad]]:
- **Segmentación de cauce (pipelining)**: superposición de etapas; conflictos estructurales, de dependencia de datos y de control.
- **Arquitecturas superescalares**: múltiples cauces independientes con sus propias unidades funcionales.
- **Multithread y multicore**: hilos manejados por el SO; el código debe especificar el uso de multithread.

### CISC y RISC
- **ISA** (Instruction Set Architecture): interfaz entre hardware y software; ARM y x86 como las dos ISA dominantes — ver [[conceptos/cisc-y-risc]].
- Tabla comparativa CISC vs RISC (cantidad/tamaño de instrucciones, ciclos, direccionamiento, costo).
- Historia **x86 → x64**: del Intel 8086 al Pentium; por qué "x86" quedó como sinónimo de 32 bits.
- **x86 vs ARM**: ambos usan Ca2 e IEEE 754; x86 es little endian, ARM soporta little y big endian configurable.

### Álgebra de Boole y compuertas lógicas
- De la [[conceptos/logica-proposicional|lógica proposicional]] al álgebra de Boole (Boole 1854, [[entidades/claude-shannon|Shannon]] 1938) — ver [[conceptos/compuertas-logicas]].
- Compuertas OR, AND, NOT, NOR, NAND, XOR, XNOR con tablas de verdad y ejercicios byte a byte.
- **Circuitos combinacionales vs. secuenciales** (sin/con memoria; flip-flops).
- Circuitos integrados 7408 (4 AND) y 7400 (4 NAND).
- Introducción a la suma en la ALU: semi-sumador (half adder), sumador completo (full adder), ripple carry y carry look-ahead de 8 bits — se desarrolla en la Clase 6.

## Referencias
- Archivo original: `Clase 5 - CISC y RISC.pdf` (movido a `raw/assets/Arquitectura de Computadoras/`)
