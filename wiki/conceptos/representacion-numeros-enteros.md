---
titulo: "Representación de Números Enteros (BSS, MyS, Ca1, Ca2, Exceso)"
tipo: concepto
creado: 2026-09-15
actualizado: 2026-09-15
tags: [representacion, binario, complemento-a-dos, punto-fijo]
fuentes: [arquitectura-computadoras-clase4-uade, arquitectura-computadoras-clase4-notas-uade]
---

# Representación de Números Enteros

Sistemas de **punto fijo** para representar enteros con n bits. Profundiza la sección de enteros con signo de [[conceptos/representacion-de-la-informacion]] con los rangos y mecanismos vistos en [[fuentes/arquitectura-computadoras-clase4-uade]].

## Los cinco sistemas

| Sistema | Mecanismo | Rango (n bits) | Rango (8 bits) |
|---|---|---|---|
| **BSS** (binario sin signo) | Valor binario directo | `[0, 2ⁿ−1]` | [0, 255] |
| **MyS / BCS** (módulo y signo) | MSB = signo (1 = negativo), n−1 bits de magnitud | `[−(2ⁿ⁻¹−1), +(2ⁿ⁻¹−1)]` | [−127, +127] |
| **Ca1** (complemento a 1) | Negativos: invertir todos los bits | `[−(2ⁿ⁻¹−1), +(2ⁿ⁻¹−1)]` | [−127, +127] |
| **Ca2** (complemento a 2) | Negativos: invertir bits y sumar 1 | `[−2ⁿ⁻¹, +(2ⁿ⁻¹−1)]` | [−128, +127] |
| **Exceso** (bias) | Valor guardado = valor real + 2ⁿ⁻¹ | `[−2ⁿ⁻¹, +(2ⁿ⁻¹−1)]` | [−128, +127] |

- En MyS y Ca1 el cero tiene **doble representación** (+0 y −0); Ca2 y exceso lo resuelven, y Ca2 gana un valor extra en el extremo negativo.
- Ca2 es el sistema usado por los procesadores reales: **la ALU solo sabe sumar**, y los complementos transforman la resta en suma (`10 − 5` → `10 + (−5)`), permitiendo un único datapath ([[fuentes/arquitectura-computadoras-clase4-notas-uade]]). Todos los operandos deben estar en el mismo sistema antes de operar.
- **Polisemia del binario**: la misma cadena de bits vale distinto según el sistema con que se la interprete (como "14" puede ser kilos, horas o grados); dentro de cada sistema la representación es unívoca, salvo el doble cero de MyS/Ca1.
- En los positivos, BSS, MyS, Ca1 y Ca2 coinciden bit a bit (ej.: +120 en 8 bits = `01111000` en los cuatro).

## Representación en exceso

No usa bit de signo ni complementos: se suma un **desplazamiento fijo** (bias = 2ⁿ⁻¹) antes de codificar en binario sin signo.
- Codificar: `guardado = real + bias`. Ej. (exceso 128): +5 → 133 → `10000101`; −13 → 115 → `01110011`.
- Decodificar: `real = guardado − bias`. El centro del rango (128) representa el cero real.
- Ventajas: evita operar con negativos y facilita comparaciones; es el formato del **exponente en [[conceptos/punto-flotante-ieee754|IEEE 754]]** (exceso 127 en float de 32 bits).

## Ejemplo integrador

Representar −120₁₀ en 8 bits:
- BSS: **no representable** (no admite negativos)
- MyS: `11111000` · Ca1: `10000111` · Ca2: `10001000`

Cantidad mínima de bits para −8₁₀: MyS y Ca1 necesitan n=5 (rango ±15); **Ca2 alcanza con n=4** (rango [−8,+7]) — su asimetría le da un negativo más.

## BCD

**Binary-Coded Decimal**: cada dígito decimal se codifica por separado con 4 bits (ej. 25 → `0010 0101`). Estándar creado por IBM para adaptar las tarjetas perforadas de los años 1960 a memoria binaria. No es un sistema posicional de base 2 sino un código por dígito.

## Relación con los flags

La misma cadena de bits cambia de valor según la interpretación (BSS vs. Ca2); por eso el procesador mantiene indicadores separados de fuera de rango: ver [[conceptos/flags-del-procesador]].

## Referencias
- [[fuentes/arquitectura-computadoras-clase4-uade]]
- [[conceptos/representacion-de-la-informacion]]
- [[conceptos/sistemas-de-numeracion]]
