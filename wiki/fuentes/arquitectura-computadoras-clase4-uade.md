---
titulo: "Arquitectura de Computadoras — Clase 4: Sistemas de Representación (UADE)"
tipo: fuente
creado: 2026-09-15
actualizado: 2026-09-15
tags: [arquitectura-de-computadoras, uade, representacion, punto-flotante, flags]
---

# Clase 4: Sistemas de Representación (UADE)

Diapositivas de la Clase 4 del curso de Arquitectura de Computadoras de [[entidades/uade]] (66 páginas, PDF). Cuarta clase del curso; continúa a [[fuentes/arquitectura-computadoras-clase3-uade]].

## Contenido

### Repaso de Clase 3
- Buses de datos/direcciones/control (ver [[conceptos/buses-de-sistema]]) y ciclo de instrucción fetch-decode-execute-write back ([[conceptos/arquitectura-von-neumann]]).
- [[conceptos/interrupciones|Interrupciones]] de hardware, software e internas (excepciones/traps).
- **Ejercicios de direccionamiento de memoria** con la fórmula: `Tamaño de Memoria = 2ⁿ × Tamaño de Palabra`, donde n = bits del bus de direcciones y el rango de direcciones es `[0, 2ⁿ−1]`. Ej.: memoria de 2048 bytes con rango [0,1023] → palabra de 2 bytes; bus de direcciones de 32 bits con palabra de 1 byte → memoria máxima de 4 GB.
- Repaso de [[conceptos/sistemas-de-numeracion]]: conversiones entre bases, suma y resta binaria, fracciones.

### Sistemas de representación numéricos (núcleo de la clase)
Representación de enteros en punto fijo — ver [[conceptos/representacion-numeros-enteros]]:
- **BSS** (binario sin signo), **Módulo y Signo (MyS/BCS)**, **Complemento a 1 (Ca1)**, **Complemento a 2 (Ca2)** y **representación en exceso** (bias = 2ⁿ⁻¹).
- Comparación de rangos y ejercicios resueltos (ej.: −120 en 8 bits no es representable en BSS; en MyS es 11111000, en Ca1 10000111, en Ca2 10001000).
- Mención de **BCD** (Binary-Coded Decimal): cada dígito decimal se codifica con 4 bits; origen en las tarjetas perforadas de IBM.

### Flags del procesador
Bits de estado Z, N, C, V que la ALU actualiza tras cada operación — ver [[conceptos/flags-del-procesador]]. Punto central: **C indica fuera de rango en interpretación BSS; V en interpretación Ca2**. Varios ejercicios evalúan la misma suma binaria bajo ambas lecturas.

### Punto flotante IEEE 754
Formato float de 32 bits: signo, exponente en exceso 127, mantisa normalizada `1,M` — ver [[conceptos/punto-flotante-ieee754]]. Casos históricos de overflow: explosión del Ariane 5 (conversión float64 → int16), problema del año 2038 (Unix de 32 bits), glitch del nivel 256 de Pac-Man.

### Códigos alfanuméricos
ASCII (7 bits), EASCII (8 bits), Unicode (code points) y UTF-8 (1 a 4 bytes, compatible con ASCII) — ver [[conceptos/representacion-de-la-informacion]].

## Referencias
- Archivo original: `CLASE 4 - Sistemas de Representación.pdf` (movido a `raw/assets/Arquitectura de Computadoras/`)
