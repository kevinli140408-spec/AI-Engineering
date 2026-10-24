---
titulo: "Flags del Procesador (Z, N, C, V)"
tipo: concepto
creado: 2026-09-15
actualizado: 2026-10-24
tags: [cpu, alu, flags, registros]
fuentes: [arquitectura-computadoras-clase4-uade, arquitectura-computadoras-clase4-notas-uade, arquitectura-computadoras-clase4-apunte-uade, arquitectura-computadoras-clase5-apunte-uade]
---

# Flags del Procesador

Bits que el procesador establece **automáticamente** según el resultado de cada operación de la ALU. Se almacenan en los **registros de estado** (registros de propósito específico — ver [[conceptos/componentes-de-la-cpu]]): la ALU opera, actualiza los flags y la UC los lee. Los procesadores actuales manejan típicamente entre 4 y 20 flags según la arquitectura.

## Los cuatro flags principales

| Flag | Nombre | Se pone en 1 cuando... |
|---|---|---|
| **Z** | Zero | El resultado tiene todos los bits en 0 |
| **N** | Negative | El bit más significativo del resultado es 1 |
| **C** | Carry | Hay acarreo desde el MSB en la suma (o *borrow* en la resta) |
| **V** | Overflow | El resultado desborda el rango en interpretación Ca2 |

## La clave: C y V son interpretaciones distintas de la misma operación

La ALU suma cadenas de bits sin saber si representan [[conceptos/representacion-numeros-enteros|BSS o Ca2]]; los flags cubren ambas lecturas:
- **C = 1** → resultado fuera de rango si los operandos se interpretan como **BSS** (sin signo).
- **V = 1** → resultado fuera de rango si se interpretan como **Ca2** (con signo).

Z y N se evalúan siempre sobre los bits de la palabra del procesador (sin contar el acarreo que la excede).

**Regla intuitiva para detectar overflow en Ca2** ([[fuentes/arquitectura-computadoras-clase4-notas-uade]]): el signo del resultado debe ser coherente con los operandos — si `(+)+(+)=(−)` o `(−)+(−)=(+)`, hay overflow (V=1). Sumar operandos de signos opuestos nunca desborda.

## Ejemplos (4 bits)

**`0101 + 0111 = 1100`** → Z=0, N=1, **C=0** (BSS: 5+7=12, cabe en [0,15]), **V=1** (Ca2: 5+7 debería ser 12 pero da −4; 12 excede [−8,7]).

**`1101 + 0011 = 1 0000`** → Z=1, N=0, **C=1** (BSS: 13+3=16 excede [0,15]), **V=0** (Ca2: −3+3=0, correcto).

En 8 bits, `10111001 + 10011101 = 1 01010110` → Z=0, N=0, C=1 (BSS: 185+157 excede 255), V=1 (Ca2: −71−99 = −170 excede [−128,127]): puede haber carry y overflow a la vez.

**`0101 + 0111 = 1100`** (4 bits): C=0, Z=0, N=1, **V=1**. En BSS es correcto (5+7=12); en Ca2 vale −4: dos positivos dieron un negativo.

**Cancelación** (8 bits): `11001110 + 00110010 = 1 00000000` → Z=1, N=0, **C=1** (206+50=256 > 255 en BSS), **V=0** (Ca2: −50+50=0; signos distintos nunca desbordan). Ver [[fuentes/arquitectura-computadoras-clase5-apunte-uade]].

**Aritmético vs. procesador**: el resultado aritmético muestra todos los bits (`1101 + 1100 = 11001`); el de la ALU se limita al ancho del registro (`1001`) y el bit sobrante queda en C=1. Ver [[fuentes/arquitectura-computadoras-clase4-apunte-uade]].

## Overflows célebres

Casos históricos citados en [[fuentes/arquitectura-computadoras-clase4-uade]]:
- **Ariane 5** (1996): la conversión de un punto flotante de 64 bits a entero con signo de 16 bits (máx. 32.767) desbordó y provocó la destrucción del cohete.
- **Problema del año 2038**: el timestamp Unix de 32 bits con signo se agota en enero de 2038.
- **Pac-Man**: el contador de nivel de 8 bits genera el "glitch del laberinto 256".

## Referencias
- [[fuentes/arquitectura-computadoras-clase4-uade]]
- [[fuentes/arquitectura-computadoras-clase4-apunte-uade]]
- [[conceptos/componentes-de-la-cpu]]
- [[conceptos/representacion-numeros-enteros]]
