---
titulo: "Álgebra de Boole y Compuertas Lógicas"
tipo: concepto
creado: 2026-09-15
actualizado: 2026-10-24
tags: [algebra-de-boole, compuertas-logicas, circuitos-digitales]
fuentes: [arquitectura-computadoras-clase5-uade, arquitectura-computadoras-clase6-notas-uade, arquitectura-computadoras-clase6-apunte-uade]
---

# Álgebra de Boole y Compuertas Lógicas

Base matemática y física de los circuitos digitales.

## Del álgebra proposicional al álgebra de Boole

- El álgebra proposicional estudia proposiciones con operadores lógicos y [[conceptos/tabla-de-verdad|tablas de verdad]] (conjunción, disyunción inclusiva/exclusiva) — ver [[conceptos/logica-proposicional]].
- **[[entidades/george-boole|George Boole]]** (1854): teoría lógica con **variables** (valores 0/1) en lugar de proposiciones. Operaciones: suma lógica (+, OR), producto lógico (·, AND) y complemento (NOT).
- **[[entidades/claude-shannon|Claude Shannon]]** (1938): aplicó el álgebra de Boole al análisis de circuitos electrónicos — el puente entre lógica y hardware.

## Compuertas lógicas (gates)

Redes de conmutadores con entradas y salida binarias; **bloque elemental de los circuitos digitales**.

| Compuerta | Salida = 1 cuando... |
|---|---|
| **OR** | Alguna entrada es 1 |
| **AND** | Todas las entradas son 1 |
| **NOT** | La única entrada es 0 (inversor) |
| **NOR** | OR negada: ninguna entrada es 1 |
| **NAND** | AND negada: no todas las entradas son 1 |
| **XOR** | La cantidad de entradas en 1 es **impar** (paridad) |
| **XNOR** | XOR negada: las entradas son iguales |

Ambas son suma de productos: **XOR = (¬A·B) + (A·¬B)** y **XNOR = (A·B) + (¬A·¬B)**. Ojo: el apunte original confundía las dos fórmulas ([[fuentes/arquitectura-computadoras-clase6-apunte-uade]]).

Aplicadas bit a bit sobre bytes: `00010001 AND 01011100 = 00010000`; `01010101 XOR 00000000 = 01010101`.

## Circuitos combinacionales vs. secuenciales

- **Combinacionales**: la salida depende **solo de las entradas actuales**; sin memoria, deterministas. Se expresan como funciones booleanas (entradas = variables, salida = función) en un diagrama de lógica.
- **Secuenciales**: la salida depende de las entradas **y del estado anterior**; tienen memoria mediante **realimentación (feedback)**: la salida vuelve a la entrada — base de los flip-flops, registros y máquinas de estados. Ejemplo didáctico: la luz de parada del colectivo sigue encendida tras soltar el botón, hasta que se abre la puerta ([[fuentes/arquitectura-computadoras-clase6-notas-uade]]).

## Equivalencia y simplificación

Dos circuitos con la **misma tabla de verdad son equivalentes**. El flujo de diseño es: armar el circuito funcional → simplificarlo para reducir transistores (ej. reemplazar ~20 transistores por una XNOR de 4-5; **nota**: el apunte organizado señala que la tabla de ese circuito era inconsistente y la equivalencia con XNOR no se pudo verificar — vale el método); a escala de millones de transistores, esta reducción define costo y viabilidad. Implementación física: AND = transistores en serie; OR = en paralelo; una XOR requiere ~4-8 transistores.

**Lógica ≠ aritmética**: en las operaciones lógicas bit a bit **no existe el acarreo** (`1 OR 1 = 1`, a diferencia de la suma binaria donde `1+1 = 10`).

## Implementación física

Circuitos integrados de la familia 74xx: **7408** (4 compuertas AND, 14 pines), **7400** (4 compuertas NAND, 14 pines). El conmutador físico subyacente es el transistor — ver [[conceptos/semiconductores-y-transistores]].

## Hacia la ALU

Las operaciones de la [[conceptos/componentes-de-la-cpu|ALU]] (suma/resta aritméticas; AND/OR/NOT lógicas) se construyen con compuertas: semi-sumador, sumador completo, sumadores de 8 bits y la ALU de 1 bit con multiplexor — desarrollado en [[conceptos/alu-de-1-bit]] ([[fuentes/arquitectura-computadoras-clase6-uade]]).

## Referencias
- [[fuentes/arquitectura-computadoras-clase5-uade]]
- [[conceptos/logica-proposicional]]
- [[conceptos/tabla-de-verdad]]
- [[conceptos/semiconductores-y-transistores]]
