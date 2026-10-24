---
titulo: "Arquitectura de Computadoras — Clase 6: Álgebra de Boole y ALU de 1 bit (UADE)"
tipo: fuente
creado: 2026-09-15
actualizado: 2026-09-15
tags: [arquitectura-de-computadoras, uade, algebra-de-boole, alu, sumadores]
---

# Clase 6: Álgebra de Boole y ALU de 1 bit (UADE)

Diapositivas de la Clase 6 del curso de Arquitectura de Computadoras de [[entidades/uade]] (47 páginas, PDF, con muchas láminas ilustrativas). Continúa a [[fuentes/arquitectura-computadoras-clase5-uade]] y cierra la primera parte de la materia.

## Contenido

### Repaso
- [[conceptos/flags-del-procesador|Flags]] Z/N/C/V presentados como "mensajeros del sistema" (C ↔ BSS, V ↔ Ca2; ej. kill screen del nivel 256 de Pac-Man como overflow de 8 bits).
- [[conceptos/cisc-y-risc|CISC vs RISC]] con analogías: CISC = "chef maestro" (una instrucción compleja hace todo), RISC = "línea de ensamblaje" (instrucciones simples combinadas); x86 = músculo bruto, ARM = eficiencia absoluta.

### Álgebra de Boole y compuertas (repite Clase 5, con láminas nuevas)
- Conexión álgebra proposicional ↔ álgebra de Boole ([[entidades/george-boole|Boole]] 1854, [[entidades/claude-shannon|Shannon]] 1938); equivalencias: suma lógica ↔ disyunción inclusiva, producto lógico ↔ conjunción, complemento ↔ negación.
- Compuertas OR/AND/NOT/NOR/NAND/XOR/XNOR, ejercicios byte a byte, circuitos combinacionales vs. secuenciales, integrados 7408/7400 — ver [[conceptos/compuertas-logicas]].
- Lámina "el poder de la abstracción": transistores físicos → compuertas lógicas → sumadores y multiplexores → ALU → procesador moderno.

### ALU de 1 bit (núcleo de la clase)
Ver [[conceptos/alu-de-1-bit]]:
- **Semi-sumador (half adder)**: XOR para la suma, AND para el acarreo.
- **Sumador completo (full adder de 1 bit)**: dos semi-sumadores + OR; entradas A, B, C_in; salidas S y C_out (tabla de verdad completa en la lámina).
- **Sumador de 8 bits**: encadenado ripple/parallel carry y alternativa **carry look-ahead**.
- **ALU de 1 bit**: full adder + compuertas AND (A·B), OR (A+B) y NOT (Ā) alimentando un **multiplexor** (4 entradas → 1 salida) que actúa como *selector de operación*.

## Referencias
- Archivo original: `Clase 6 - Boole - ALU de 1 bit.pdf` (movido a `raw/assets/Arquitectura de Computadoras/`)
