---
titulo: "Arquitectura de Computadoras — Clase 5: Apunte organizado con erratas (UADE)"
tipo: fuente
creado: 2026-10-24
actualizado: 2026-10-24
tags: [arquitectura-de-computadoras, uade, erratas, flags, direccionamiento, tpo, apunte]
---

# Clase 5: Apunte organizado con erratas (UADE)

Versión reorganizada (15 páginas) de las notas de la Clase 5 de [[entidades/uade]]. El contenido de fondo (pipeline, hazards, caché, CISC vs. RISC, x86 vs. ARM) ya está en [[fuentes/arquitectura-computadoras-clase5-notas-uade]], [[fuentes/arquitectura-computadoras-clase5-uade]], [[conceptos/cisc-y-risc]] y [[conceptos/pipelining-y-superescalaridad]]. Aquí se registran solo los aportes nuevos.

## Erratas corregidas

| Tema | Apunte original | Valor correcto |
|---|---|---|
| Binario de `13725₈` / `17D5₁₆` | 11 bits (`00111110101`) | **`001011111010101`** (15 bits; mismo ejemplo que [[fuentes/arquitectura-computadoras-clase4-apunte-uade]]) |
| Ca1 de +83 (módulo de 7 bits) | fila "−46: 0101100" | `1010011 → 0101100` es el complemento (= 44), no −46; `83 + 44 = 127` |
| Bits mínimos para −8 | "4 bits" para SM, Ca1 y Ca2 | **SM y Ca1: 5 bits** (con 4 el tope es −7); **solo Ca2 alcanza con 4** |
| `1101 + 0011` (4 bits) | Z = 0 | **Z = 1** (resultado `0000`; el carry no cuenta) |
| IEEE 754 `1 10000001 101…` | 1,01 → −5 | **1,101 = 1,625 → −1 × 1,625 × 4 = −6,5** |
| Ariane 5 | "float de 16 bits", década del 80 | float de 64 bits convertido a entero de 16 con signo; **1996** |
| Pac-Man nivel 256 | mencionaba Ca2 | contador **sin signo de 8 bits** (máx. 255) |
| Cifras de instrucciones CISC/RISC | "6", "100–400", ">2000" | cifras inconsistentes; usar "mucho más / mucho menos" y verificar antes del TPO |

Sin contradicciones con las páginas existentes del wiki: [[conceptos/punto-flotante-ieee754]] y [[conceptos/flags-del-procesador]] ya traían los valores correctos.

## Aportes nuevos

- **Ejercicio de cancelación** (8 bits): `11001110 + 00110010` → resultado `00000000`, **Z=1, N=0, C=1, V=0**. En BSS: 206+50 = 256 > 255 (carry). En Ca2: (−50)+50 = 0, sin overflow, porque sumar signos distintos nunca desborda. El apunte original lo resolvía de tres formas contradictorias.
- **Direccionamiento**: con n bits hay 2ⁿ direcciones (no confundir n con 2ⁿ); para duplicarlas se suma **un** bit. Ejemplo: 512 bytes con 8 bits de dirección (256 direcciones) → palabra de 2 bytes. Capacidad = direcciones × tamaño de palabra. Ver [[conceptos/sistemas-de-numeracion]].
- **Rango vs. representabilidad**: un valor fuera de rango no es "incorrecto"; el sistema no tiene capacidad de contenerlo. Ej. +130 entra en BSS (`10000010`) pero no en los sistemas con signo de 8 bits.
- **Agrupación**: un cero a la izquierda no cambia el valor; uno a la derecha sí (23 → 023 igual, 23 → 230 distinto).
- **Parcial**: se estiman ~3 de 5 puntos sobre sistemas numéricos y de representación (incluye dos temas teóricos). El examen evalúa el significado de los bits, no solo la mecánica de convertir.
- **Práctica sugerida**: conversiones entre bases a mano, representabilidad en BSS/SM/Ca1/Ca2, rangos justificados con la regla de signos, sumas con flags en 4, 8 y 16 bits, y la relación bits ↔ direcciones.

## Logística del TPO

- TPO N°1: **debate RISC vs. CISC** (características y aplicaciones), preferentemente grupal, con cuadros comparativos. Se permite apoyarse en la IA para diagramas, no para que resuelva el trabajo.
- Mini-presentación de avance de 2 minutos por grupo: qué se avanzó, qué falta y qué dificultades hubo. No se califica.
- El apunte fecha la entrega el 13/05/2023, año que no coincide con la cursada; **confirmar la fecha real con el docente**.

## Referencias
- Archivo original: `Clase_5_Apunte.pdf` (movido a `raw/assets/Arquitectura de Computadoras/apuntes/`)
