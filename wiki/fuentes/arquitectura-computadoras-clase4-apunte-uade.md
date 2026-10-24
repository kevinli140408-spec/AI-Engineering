---
titulo: "Arquitectura de Computadoras — Clase 4: Apunte organizado con erratas (UADE)"
tipo: fuente
creado: 2026-10-24
actualizado: 2026-10-24
tags: [arquitectura-de-computadoras, uade, representacion, flags, erratas, apunte]
---

# Clase 4: Apunte organizado con erratas (UADE)

Versión reorganizada (PDF de 10 páginas) de las notas de la Clase 4 de [[entidades/uade]], que ya figuraban en [[fuentes/arquitectura-computadoras-clase4-notas-uade]] y [[fuentes/arquitectura-computadoras-clase4-uade]]. Su valor propio son los **cuadros "Atención"**, que corrigen errores del apunte original. Este resumen recoge solo lo nuevo; el resto está en [[conceptos/representacion-numeros-enteros]], [[conceptos/flags-del-procesador]] y [[conceptos/sistemas-de-numeracion]].

## Erratas corregidas

| Tema | Apunte original | Valor correcto |
|---|---|---|
| `13725₈` → hexadecimal | `1725₁₆` | **`17D5₁₆`** (15 bits `001011111010101` → grupos de 4 desde la derecha) |
| Signo y magnitud `1011100` | −52 | **−28** (módulo `011100` = 16+8+4) |
| −3 en Ca2, 4 bits | `1010 → 0101 → 0110` | **`0011 → 1100 → 1101`** |
| −5 en Ca2, 6 bits | `100000` | **`111011`** (`000101 → 111010 → 111011`) |
| Overflow de `10111001 + 10011101` (8 bits, Ca2) | "0 (según el análisis)" | **V = 1**: `(−)+(−)=(+)` |

Verificación de −3: `1101 + 0011 = (1) 0000` → el acarreo se descarta y se activa Z.

## Aportes no presentes en las otras fuentes de la clase

- **Resultado aritmético vs. resultado de procesador**: el aritmético muestra todos los bits necesarios; el de la ALU se limita al ancho del registro y el bit sobrante va al flag C. Ejemplo (4 bits): `1101 + 1100 = 11001` → el registro guarda `1001` y C = 1. En un examen hay que interpretar cuál de los dos piden.
- **Estrategia de conversión**: usar siempre la base 2 como puente (octal → binario → decimal; hex → binario → decimal) y escribir la base de cada número (`85₁₀` vs `85₈`). Para decimal → binario, primero se calcula la cantidad mínima de bits (`85` necesita 7) y luego se recorren los pesos de mayor a menor: `85₁₀ = 1010101₂`.
- **Ejemplo de Ca1**: `83₁₀ = 1010011`, su complemento es `0101100` (= 44) y `83 + 44 = 127`, el máximo de 7 bits.
- **Ejemplo de flags `0101 + 0111`** (4 bits): resultado `1100`, C = 0, Z = 0, N = 1, V = 1. En BSS es correcto (5+7 = 12); en Ca2 vale −4, así que hay overflow.
- **Regla de presentación**: si se trabaja en 8 bits, el resultado se escribe con los 8 bits aunque haya ceros a la izquierda.
- **Ejercicios propuestos**: −68₁₀ a Ca1; la secuencia −1…−8 en Ca2 con 4 bits; `11001101 + 00110101` y `11001101 + 00110110` (V, N, Z, C en MyS y en Ca2).
- **Metodología del TP**: usar la IA de forma iterativa (pedir diagramas, aclarar vocabulario, armar cuadros comparativos) y no para que resuelva el trabajo. El escrito exige profundidad técnica; el debate oral, lenguaje sencillo.

## Referencias
- Archivo original: `Clase_4_Apunte.pdf` (movido a `raw/assets/Arquitectura de Computadoras/apuntes/`)
