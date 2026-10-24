---
titulo: "Sumadores y ALU de 1 Bit"
tipo: concepto
creado: 2026-09-15
actualizado: 2026-10-24
tags: [alu, sumadores, circuitos-digitales, compuertas-logicas]
fuentes: [arquitectura-computadoras-clase6-uade, arquitectura-computadoras-clase6-notas-uade, arquitectura-computadoras-clase5-uade, arquitectura-computadoras-clase6-apunte-uade]
---

# Sumadores y ALU de 1 Bit

Cómo se construye la unidad aritmético-lógica desde [[conceptos/compuertas-logicas|compuertas lógicas]]. Escala de abstracción: transistores → compuertas → sumadores/multiplexores → ALU → procesador ([[conceptos/componentes-de-la-cpu]]).

## Semi-sumador (half adder)

Suma dos bits A y B, sin acarreo de entrada:
- **Suma** = A XOR B (la XOR es "crucial para sumar": 1+1 → 0)
- **Acarreo** = A AND B

## Sumador completo (full adder de 1 bit)

Agrega el **acarreo de entrada (C_in)**: se construye con **dos semi-sumadores más una compuerta OR** que combina ambos acarreos. Entradas A, B, C_in; salidas S y C_out.

| A | B | C_in | S | C_out |
|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 |

## Sumador de 8 bits

Ocho full adders encadenados: el C_out de cada etapa es el C_in de la siguiente. El primero de la cadena opera con **C_in forzado a 0** (equivale a un semi-sumador).
- **Ripple / parallel carry adder**: el acarreo se propaga en cascada (simple pero el último bit espera a todos los anteriores).
- **Carry look-ahead**: lógica adicional que anticipa los acarreos para acelerar la suma.

El acarreo que sale del último bit alimenta el flag **C** del registro de estado — ver [[conceptos/flags-del-procesador]].

## ALU de 1 bit

Combina en paralelo, sobre las mismas entradas A y B:
1. **Full adder** (suma aritmética)
2. **AND** → A·B
3. **OR** → A+B
4. **NOT** → Ā

Las cuatro salidas entran a un **multiplexor** (4 entradas → 1 salida) que funciona como **selector de operación**: la operación seleccionada (parte de la instrucción decodificada) determina cuál resultado sale de la ALU. Encadenando n de estas celdas se obtiene una ALU de n bits — la materialización física de que la ALU "solo sabe sumar y operar lógicamente" ([[conceptos/representacion-numeros-enteros]]).

### Control interno ([[fuentes/arquitectura-computadoras-clase6-notas-uade]])

- Una ALU de 8 bits recibe A y B (8 bits) más un **opcode de 4 bits** (ej. `1000` = ADD, `1100` = SUBTRACT) y emite el resultado más los [[conceptos/flags-del-procesador|flags]].
- Un **decodificador interno** interpreta el opcode y **habilita** (señal *enable*, implementada con compuertas AND) una única entrada del multiplexor; las líneas no habilitadas quedan en 0. Hay líneas adicionales `Invert A`/`Invert B` y señales de control F0/F1 enviadas por la unidad de control.
- La **multiplicación** puede resolverse por sumas sucesivas (dispositivos simples) o con unidades dedicadas (procesadores modernos).
- El ancho físico limita lo computable: en una ALU de 8 bits no existe un "noveno bit"; el acarreo excedente va al registro de estado.

Hito histórico: el **Intel 4004 (1971)** fue la primera arquitectura completa integrada en un solo chip — ver [[conceptos/historia-de-la-computacion]].

## Referencias
- [[fuentes/arquitectura-computadoras-clase6-uade]]
- [[fuentes/arquitectura-computadoras-clase5-uade]]
- [[fuentes/arquitectura-computadoras-clase6-apunte-uade]] — tabla completa del sumador completo con Cout, fórmulas y mapeo F0/F1
- [[conceptos/compuertas-logicas]]
- [[conceptos/flags-del-procesador]]
