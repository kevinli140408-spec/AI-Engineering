---
titulo: "Arquitectura de Computadoras — Clase 6: Notas de clase (UADE)"
tipo: fuente
creado: 2026-09-15
actualizado: 2026-09-15
tags: [arquitectura-de-computadoras, uade, alu, compuertas-logicas, notas-de-clase]
---

# Clase 6: Notas de clase (UADE)

Notas HoverNotes de la grabación de la clase del **2026-09-08** del curso de Arquitectura de Computadoras de [[entidades/uade]]. Complementan las diapositivas de [[fuentes/arquitectura-computadoras-clase6-uade]]. Existían tres copias del mismo contenido (`Clase 6.md`, `Clase 6 1.md` y `clase_6_1.pdf`); se ingesta una sola.

## Aportes propios de estas notas (no presentes en las diapositivas)

### Circuitos secuenciales: la realimentación
- La memoria se logra con una conexión de **realimentación (feedback)**: la salida vuelve a la entrada y condiciona el estado futuro — base de los **flip-flops**.
- Ejemplo didáctico: la luz de parada del colectivo queda encendida tras soltar el botón hasta que se abre la puerta.
- Distinguir combinacional vs. secuencial es "tema recurrente en finales". Incorporado a [[conceptos/compuertas-logicas]].

### Equivalencia y simplificación de circuitos
- Dos circuitos con la **misma tabla de verdad son equivalentes**; el flujo de diseño es armar el circuito funcional y luego simplificarlo.
- Objetivo: reducir transistores (ej. de ~20 a 4-5 reemplazando por una XNOR equivalente) — crítico a escala de millones de transistores. Una XOR requiere ~4-8 transistores.
- **Lógica ≠ aritmética**: en operaciones lógicas bit a bit **no hay acarreo** (`1 OR 1 = 1`, no `10`).

### Estructura interna de la ALU (detalle)
Incorporado a [[conceptos/alu-de-1-bit]]:
- En la cadena de n bits, el primer sumador opera con **C_in forzado a 0** (equivale a un semi-sumador); el acarreo final va al **registro de estado**.
- Interfaz de una ALU de 8 bits: entradas A y B (8 bits) + **opcode de 4 bits** (ej. `1000` = ADD, `1100` = SUBTRACT); salidas: resultado + flags.
- Un **decodificador interno** interpreta el opcode y habilita una única entrada del multiplexor; las compuertas AND actúan como **habilitadores (enable)**; hay líneas de control `Invert A` / `Invert B` y señales F0/F1 provenientes de la unidad de control.
- La **multiplicación** puede no tener circuito propio: dispositivos simples (microondas, controles) la resuelven por sumas sucesivas; los avanzados tienen unidades dedicadas.
- Hito: **Intel 4004 (1971)**, primera arquitectura completa en un solo chip.
- El hardware limita lo computable: si la electrónica es de 8 bits, no existe "noveno bit" — el software no puede superar la restricción física.

### Contexto y cursada
- Geopolítica de semiconductores: subsidios, proteccionismo y el rol crítico de Taiwán en la cadena de suministro.
- Temas señalados para el parcial: instrucciones, [[conceptos/interrupciones|interrupciones]], sistemas de representación, [[conceptos/arquitectura-von-neumann|Von Neumann]] vs. [[conceptos/arquitectura-harvard|Harvard]].
- Pautas del TPO: carátula, índice, defensa individual, entrega por Teams.

## Contenido que repite las diapositivas
Flags Z/N/C/V, overflow (Pac-Man), CISC vs RISC, compuertas con tablas de verdad (implementación con transistores en serie = AND, paralelo = OR), semi-sumador (XOR + AND), sumador completo, ripple carry y carry look-ahead.

## Referencias
- Archivo original: `Clase 6.md` (+ duplicados `Clase 6 1.md`, `clase_6_1.pdf`), movidos a `raw/assets/Arquitectura de Computadoras/`
